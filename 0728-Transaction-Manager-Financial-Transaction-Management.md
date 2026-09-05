# Transaction Manager > Financial Transaction Management - SAP TRM Knowledge Base (branch split)

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

#### Financial Transaction Management

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management | L3 | trm06 p.2 | loio `a5bbdacb983d4718b66d69311063ece5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a5bbdacb983d4718b66d69311063ece5.html?locale=en-US)

##### Apps for Processing Financial Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions | L4 | trm06 p.2 | loio `0f19c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0f19c55368511d4be10000000a174cb4.html?locale=en-US)

Here you find the apps and functions available for the handling of the different kinds of financial transaction:

The general functions Create Financial Transaction (app ID FTR_CREATE), Process Financial Transaction (app ID FTR_EDIT), Manage Financial Transactions (app ID F6157), and Collective Processing: Transaction Management (transaction FTR_00) that can be used for creating and editing every kind of financial transaction.

Change Counterparties for Financial Transactions

Display Financial Transactions with Changed Counterparty

Reference

Netting

Adjust Variable Rates/Prices

Updating Planned Records

Rate Fixing

###### Manage Financial Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Manage Financial Transactions | L5 | trm06 p.2 | loio `82017a294df345b499524973276bdbe8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/82017a294df345b499524973276bdbe8.html?locale=en-US)

App ID: F6157

You can use this app to manage all your financial transactions across all financial instrument groups in one place. From this overview, you can jump directly to the apps for creating, displaying or processing your financial transactions.

This app shows all transactions across different areas. It lets you filter easily by different attributes and save variants for a quick overview.

**Features**

The chosen Key Date influences other values, such as the nominal amount, total amount or interest rate of different instruments. The current date is set by default.

Use the tabstrip above the table to show only a particular product category.

The action toolbar shows the available processing steps for your selected product category.

You can choose Create to go directly to the Create Financial Transaction app.

**Note:**

For selected product categories, you can create a new financial transaction by copying an existing financial transaction, for example, for the following product categories:

600 FX Transaction

550 Interest Rate Instrument

Securities

010 Stock

020 Investment Fund

030 Subscription Right

- 040 Bond

- 041 Drawable Bond


160 Shareholding

620 Swap

To copy a financial transaction, proceed as follows:

- 1. Mark the financial transaction which you want to copy and choose the Copy button.
- 2. The Copy or Change Data dialog box appears.

In the fields Company Code and Business Partner the values of the copied financial transaction are displayed. For security transaction also the Security ID field is available. You can now change the values of the fields and choose Continue or you continue the copy process without changing these values.

- 3. You see the data of the new financial transaction. The data correspond with the copied transaction.
- 4. Make the required changes.
- 5. Save your entries.


**Note:**

Usually, the trader is also copied and only if the Trader field is not filled, the trader is derived. However, if you always want to derive the trader when you copy a financial transaction, you must set the indicator Der.Trader in the Define User Data app.

At the bottom of the columns with amounts (Amount in Transaction Currency, Incoming Side Nominal Amount, Nominal Amount, Opposite Amount, Outgoing Side Nominal Amount, Payment Amount and Traded Amount), you can choose Show Details for a quick overview of total volumes in different currencies.

In the table, right-click a column header and choose Group in the context menu to sort the transactions by this attribute. Right-click the header row and choose Ungroup to return to the previous view.

You can also choose Adapt Filters and in the dialog that appears choose Group View to sort attributes by product category. This lets you select the attributes that are relevant for specific instruments. You can also use predefined views. Choose Share Save as Tile to save a view on the SAP Fiori launchpad.

**Note:**

The product category 760 (OTC Option) has several different product types, but not all of these can currently be processed in

the Manage Financial Transaction app. While all available transactions for product category 760 are shown in this app, only the product types listed in the table below can be processed. Hence, the underlying information is also shown only for the currently supported product types.

Available Product Categories and Term Start and End Dates and Relevant Amounts for Different Instruments

|Product Category (Name)|Term Start|Term End|Transaction Amount|Transaction Currency|
|---|---|---|---|---|


|Product Category (Name)|Term Start|Term End|Transaction Amount|Transaction Currency|
|---|---|---|---|---|
|530-580 (Money Market)|Start Term|End Term, Give Notice Date|Nominal Amount|Nominal Currency|
|600 (Foreign Exchange)|Contract Date|Value Date|Traded Amount|Traded Currency|
|620 (Interest Rate Derivative)|Start Term|End Term|Outgoing Side - Nominal Amount|Outgoing Side - Nominal Currency|
|760 (FX option, FX as underlying)|Contract Date|Expiry Date / Exercise Date|Traded Amount|Traded Currency|
|760 (Swaption, interest rate derivative as underlying)|Contract Date|Expiry Date / Exercise Date|Nominal Amount|Traded Currency|
|760 (Securities option, securities as underlying)|Contract Date|Expiry Date / Exercise Date|Market Value Amount|Market Value Currency|
|010-042 (Securities)|Position Value Date|Position Value Date|Payment Amount|Payment Currency|
|850, 860 (Trade Finance)|Start Term|End Term|Amount|Currency|


**Situation Handling**

This app uses Situation Handling, which automatically informs users responsible about matters that require their attention. For more information, see Situation Handling.

**Procedure**

- 1. On the SAP Fiori launchpad, open the Manage Financial Transactions app.
- 2. Set the filter criteria to search for your financial transactions and choose Go to apply the filter. The Key Date is a mandatory field and is set to the current date by default.
- 3. In the list of results, you can either select a row and choose Details ( ) to go to the transaction's maintenance screen, or you can choose an action from the toolbar to directly process the transaction.



**Technical Information**

This app is available for users with the business role templates Treasury Specialist - Front Office and Treasury Specialist Back Office.

**Related Information**

Situation Template: Processing of Financial Transactions How to Create a Custom Situation Type for Processing Financial Transactions

###### Create Financial Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction | L5 | trm06 p.4 | loio `97908c53cc93ed23e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/97908c53cc93ed23e10000000a174cb4.html?locale=en-US)

Use

You can use this app to create a financial transaction. It is a central entry point for creating financial transactions of all product types.

**Prerequisites**

You have created and released business partners, assigned them roles, and determined the transaction authorizations. for more information, see also:

Business Partner

Transaction Authorization

You have set up the standing instructions .

You have defined product types in Customizing under Transaction Manager Money Market/Foreign Exchange/Securities/Listed Derivatives Transaction Management Product Types .

See also Product Types in the Transaction Manager.

You have defined product types in Customizing under Transaction Manager Money Market/Foreign

Exchange/Securities/Listed Derivatives/OTC Derivatives Transaction Management Product Types . This allows you to determine the types of transaction that can be concluded with a particular product type and control the transaction and position management process.

You have defined flow types and assigned them to a transaction type in Customizing under Transaction Manager

Money Market/Foreign Exchange/Securities/Listed Derivatives/OTC Derivatives Transaction Management Flow Types . Flow types describe the possible flows of payment flows.

You have defined condition types in Customizing under Transaction Manager Money Market/Securities/OTC Derivatives Transaction Management Condition Types . This allows you to determine which structural characteristics are displayed when you create transactions.

For more information about creating and processing financial transactions, see:

Tabs

Mirror Transaction

Object Links

**Procedure**

- 1. Open the Create Financial Transaction app on the SAP Fiori launchpad or in the area menu in the back-end system under Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Money


Market/Foreign Exchange/Derivatives/Securities/Debt Management Trading Create Financial Transaction .

- 2. Enter the required data and save your entries.


**Note:**

The Manage Financial Transaction app, also allows you to jump to the Create Financial Transaction app.

If you want to narrow down the number of input fields, you can select a group of financial instruments from the dropdown list in the Preselection for Group of Financial Instruments area.

Once you select a group of financial instruments from the list, the system limits the number of possible input values for the Product Type field or deactivates it for input completely.

Depending on your selection, the following fields might also be deactivated for input:

ID Number

Transaction Currency

Portfolio

Order/Fixing

Contract

**Related Information**

Create FX Spot/Forward Creating a Non-Deliverable Forward Creating an FX Option Create Collar FX Option Create FX Swap Creating Fixed-Term Deposit Transactions Creating Deposits at Notice Create Commercial Paper Creating an Interest Rate Instrument Create Current Acct-Style Instruments Create Facility Creating a Swaption Create OTC Option Creating a Forward Securities Transaction Creating and Editing Forward Loan Purchases Create Security Transaction Create Letter of Credit Create Bank Guarantees Creating Standby Letters of Credit

###### Tabs

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs | L6 | trm06 p.6 | loio `ab08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ab08da531198434de10000000a174cb4.html?locale=en-US)

**Use**

When you process a transaction, you can use tabs to branch between the different entry screens for the general transaction management functions.

**Structure**

Structure

Structure (Product Categories 510, 520, 530)

Basic Data - Derivatives

Administration

FX Hedge Management

Other Flows

Payment Details with Input Help for Payment Details and Repetitive Code

Cash Flows

Cash Flow

Cash Flow for the Class

Cash Flow for a Class in a Securities Account

Memos

Status

Partner Assignment

Analysis Parameters

Default Risk Limit

Using the Conditions pushbutton in the upper part of the screen, you go to the Condition Overview. For more information, see Condition Details.

Underlying (currency option)

Outgoing Flows (swap)

Incoming Flows (swap)

Interest Rate Adjustment Data (interest rate derivatives and interest rate transactions)

Price Index Adjustment (interest rate transactions)

Charges, profiles, rules (facilities)

Environment

Object Links

Extras

###### Structure (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Structure | L7 | trm06 p.7 | loio `3b07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3b07da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use the Structure tab page to enter, process, and display the structural characteristics of the individual financial transactions.

**Note:**

The structural characteristics for the transactions of the product types only differ in the system. You can use the other tab pages to enter and process information on administration, FX hedge management, additional flows, payment details, cash flows, memos, status, partner assignment, analysis parameters, and transaction default risks.

**Activities**

You can create and process the structural characteristics for the following financial transactions:

Structure (Product Categories 510, 520, 530)

Basic Data - Foreign Exchange

Basic Data - Derivatives

Basic Data - Securities

The following functions are available for activities on the Structure tab page:

Worklist

Correspondence overview of this transaction

You receive information about which correspondence was generated for a particular transaction, and the respective correspondence status.

Display business partner master data

For more information, see Business Partner.

Condition Details

You can expand and collapse the interest structure of the transaction. This changes the view in the Interest Structure area.

You can check that your entries for the transaction are complete.

You can branch to another transaction.

Save your entries.

Contract Conclusion

In this area, you can enter overall, administrative information relevant to the financial instrument:

Contract date and time

Contact person

Market identifier code (MIC)

Market identifier codes (MICs) are four-character international standard codes (ISO 10383). MICs are used to identify exchanges, trading platforms, and regulated or non-regulated markets as sources of prices and related information to facilitate automated processing (exchanges, settlement, and other automated processes).

**Note:**

You create and activate MICs in Customizing under Market Data Management Master Data Specify Market Identifier Codes .

For more information, see Market Identifier Code.

Trader

External reference

**Features**

You can enter and process financial transaction data for the following product categories:

Fixed-term deposits and deposits at notice

Commercial paper

Interest rate instruments

Cash flow transactions

Facilities

Spot exchange and forward exchange transactions

Interest rate derivatives

OTC options and listed options

Repo

Securities lending

Future

Security transaction

**Note:**

Which tab pages are visible depend on your settings in Customizing under Define Field Selection. For example, different tab pages can be displayed for Orders and Contracts. The Structure tab page is displayed by default. You find the Define Field Selection activity in Customizing for the Transaction Manager, under General Settings Transaction Management .

###### Structure (Product Categories 510, 520, 530)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Structure > Structure (Product Categories 510, 520, 530) | L8 | trm06 p.9 | loio `4e07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e07da531198434de10000000a174cb4.html?locale=en-US)

**Header data**

Company Code

Product Type

Transaction Type

Transaction

Activity

**Structure Data**

Business Partner

Investment (Purchase for Commercial Paper)

Choose the Flow Type.

Amount

This is where you enter the amount of the transaction. The Nominal Amount is used as a basis for calculating the interest.

The amount field (data element TM_XBETRAG) is an input field for amounts using abbreviated forms. You can abbreviate the amount by using default values for one thousand (default 'T'), one million (default 'M'), and now also for one billion (default 'B') when entering data. The abbreviations are converted into the corresponding amount after data release.

**Examples**

|Abbreviation|Corresponding Amount|
|---|---|
|1.25M|1,250,000.00|
|1T|1,000.00|
|1T.50|1,000.50|
|1B|1,000,000,000.00|


In the Define User Data Customizing activity, you can define your own special characters or other alphabetic values as an abbreviation for thousands, millions, or billions.

**Note:**

For selected transaction types, if you want to enter a payment amount different to the nominal amount (premium/discount) for amortization, you first need to set the indicator Permit Premium/Discount. To do this, in Customizing for the Transaction Manager, choose Money Market Transaction Management Transaction Types Define Transaction Types . Alternatively, you can specify a payment amount/nominal amount ratio in the rate field.

For the product category Commercial Paper, use the input help to select Nominal Value Without Interest Flow in the Nominal Position field.

For more information, see the relevant field help.

Term

Here you enter the Start of term and the End of term of the transaction. The system automatically shows the CPU date as a default. You can enter the + for the number of days and ++ for the number of months.

**Example:**

+ +2 means that the start of term is today + two days.

**Note:**

The deposit at notice does not have an End of Term. Instead you can enter ther Notice Period. When you execute the Give Notice function you enter the Notice Date and the repayment flow is generated.

Interest Structure

Interest Rate

The percentage rate applied to calculate the interest yield on the amount invested or the interest payment for the amount borrowed. This entry is essential, since it is used to calculate the interest.

Interest Calculation Method

In this field, you specify which interest calculation method is to be used. F1 help provides definitions of each method. (You can choose from standard interest calculation methods such as act/360, 360/360, act/365, act/366, 365/360, and so on.

**Note:**

If the start of term is earlier than the CPU date, you must backdate the contract date.

Monthly Frequency

This field indicates the interval in months between the first due date and the next due date (settlement period).

**Example:**

1. Due Date: 01.05.2004

Frequency: 06

In this case, the 2nd due date is 11/01/YY, the 3rd due date is 05/01/YY+1.

You can specifiy your conditions on Condition Details: Interest screen.

for more information, see also: Condition Details: Interest

You make the settings for work day shift of the calculation day and the due date. When you enter a working day shift, you can set in addition the Shift Due Date Back to End of Term indicator which is only relevant for the last flow at the period end.

You can set the Capitalize Interest indicator. When the indicator ist marked, each interest flow is increases the base amount of the investment and will be considered within the following interest period.

Contract Data

Close Date: Date and Time of contract close, set by system with system date.

Trader: Set by system.

Contact Person: Here you could enter the name of the contact person at the company which is the business partner of the financial transaction. If you enter a name here, you must deploy separate supplementary organizational measures to ensure that you respect the deadlines governing the storage and deletion of personal data.

For deposit at notice transactions, you enter the Notice Period in days or months. The period of notice is the period between termination agreement and when it comes into effect.

###### Basic Data - Derivatives

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Structure > Basic Data - Derivatives | L8 | trm06 p.11 | loio `fb14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fb14da531198434de10000000a174cb4.html?locale=en-US)

The basic data or structural data of derivative transactions share the properties of master data. To define and edit financial transactions, you create basic data for a transaction or change that data.

The view and the fields displayed depend on the product type that you select.

Information Specific to the Product Category

|Product Category|Structure tabe (submenu)|Indicator and Fields|Comments|
|---|---|---|---|
|OTC Option / OTC Interest Rate Instruments| Exercise Settlement|Physical Exercise Cash Settlement|When you conclude a transaction, the cash flow consists only of the premium.|
| | Exercise Exercise Type|European American| |
| |Underlying| |For currency options, you can enter a spot exchange as the|


|Product Category|Structure tabe (submenu)|Indicator and Fields|Comments|
|---|---|---|---|
| | | |underlying.|
| | |Strike Limit|Only with CAP. You use the strike limit to specify the agreed upper or lower interest limit.|
| | |Business Calendar|Only for FRA. You can specify a maximum of two calendar IDs. These IDs define the calendar forms that are used to determine the interest fixing date.|
|Repurchase Transactions (Repos)|Spot|Spot Price Units / Nominal Amounts| |
| |Forward|Forward Rate Effective Interest Rate Repo Interest Rate| |
|Listed Transactions|Position|Futures Account Units| |
| |Amounts|Rate Price| |
| | |Position Cash Flows| |
|Securities Lending| Position Flow Type|Securities Lending Securities Account Lending Securities Account Units / Nominal Amounts| |
| | Position Gen. Valuation Class| |For example, Medium-Term Investments|
| | Lending Revenues Frequency| |For example, At End of Term , Monthly Frequency|

###### Basic Data - Trade Finance

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Structure > Basic Data - Trade Finance | L8 | trm06 p.12 | loio `101702563f7a3874e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/101702563f7a3874e10000000a44147b.html?locale=en-US)

The trading area contains the key functions for entering and changing transaction data. To map transactions in the system efficiently, you first have to enter the basic data.

**Initial Data**

Company Code

When you enter the company code, you determine which division within your group is acting as the contracting party for the transaction.

Product Type

The product type indicates which specialization of the product category is involved in the current transaction.

Example of product types:

|Product Type|Product Category|Name|
|---|---|---|
|85A|850|Letter of Credit|
|86A|860|Bank Guarantee|


Depending on which product type you enter, the system calls up a different entry screen. The entry screens are described below.

Transaction Type

Transaction types define which specialization of the transaction category - issuing or receiving letters of credit or bank guarantees - is involved in the current transaction.

Example of transaction types:

|Product Type|Transaction Type|Name of Transaction Type|
|---|---|---|
|85A|100|Letter of Credit - Issue|
|85A|200|Letter of Credit - Receive|
|86A|100|Bank Guarantee - Issue|
|86A|200|Bank Guarantee - Receive|


Partner

You specify a third party as a partner in the system that issues the letters of credit or bank guarantees at your request or notifies you about a letter of credit or bank guarantee issued with you as the beneficiary.

The partner charges a certain amount of fees for a letter of credit or bank guarantee in the issuing or receiving process. An additional fee is also charged based on the total amount of the letter of credit or bank guarantee and including certain conditions, such as the payment rate.

For more information, see

Calculating Fees for Letters of Credit

Calculating Fees for Bank Guarantees

Calculating Fees for Standby Letters of Credit

Transaction

If you have specified external number assignment, you enter the key that uniquely identifies a financial transaction within a company code in the Transaction field in the External Number Assignment area.

Otherwise, the system assigns a number automatically.

**Basic Data**

General Basic Data for Trade Finance Transactions

Amount

This is where you enter the amount of the transaction. The nominal amount is used as the basis for calculating interest.

**Note:**

The amount field (data element TM_XBETRAG) is an input field for amounts using abbreviated forms. You can abbreviate the amount by using default values for one thousand (default 'T'), one million (default 'M'), and now also for one billion (default 'B') when entering data. The abbreviations are converted into the corresponding amount after data release.

**Examples**

|Abbreviation|Corresponding Amount|
|---|---|
|1.25M|1,250,000.00|
|1T|1,000.00|
|1T,50|1,000.50|
|1B|1,000,000,000.00|


In the Define User Data Customizing activity, you can define your own special characters or other alphabetic values as an abbreviation for thousands, millions, or billions.

Term

Here you enter the start and the end of the transaction term. Your system automatically shows the CPU date as the default value. You can enter ' +' for the number of days and '++' for the number of months.

**Example:**

+2 means that the start of term is today + two days.

The Inclusive drop-down field lets you choose which dates to include in the term:

Start Included: only the start date is included in the fee calculation

End Included: only the end date is included in the fee calculation

Start and End Included: both start and end date are included in the fee calculation

Start and End Excluded: both start and end date are excluded from the fee calculation

Flow Type

Specify a flow type for the transaction. The type of flow within a financial transaction specifies how the flow concerned is interpreted in terms of financial mathematics and financial accounting. A flow type can be used only in connection with a financial transaction if the flow type has been assigned to the corresponding predefined product type.

Beneficiary/Applicant

Specifies the counterparty of the transaction.

Underlying Transaction

Specifies the underlying transaction type and number of the transaction.

Basic Data for Letter of Credit Transactions

Issuing Bank/Advising Bank

Specifies the bank that issues the letter of credit or advises the beneficiary of the letter of credit.

Place of Expiry

Specifies the place where the beneficiary presents documents against the letter of credit.

Confirmation Instruction

Specifies whether the letter of credit needs to be confirmed by a confirming bank.

Time Zone

Specifies the time zone of the place where the beneficiary (seller) presents documents against the letter of credit.

Goods and Shipping

Specifies the terms and conditions related to goods and shipping.

Presentation

Specifies the terms and conditions related to presentations against the letter of credit.

Payment

Specifies the terms and conditions related to payment for the letter of credit.

Documents

Based on your business needs, you can decide whether to maintain this section. To maintain the documents for a letter of credit, you can add document types. Alternatively, you can select a document template.

For each document type, the following activities are allowed:

Specify whether it is creation-related or presentation-related

Specify the number of the originals and copies required

Upload attachments for presentations

Select a status (Waiting for Check, Rejected, or Accepted)

Basic Data for Bank Guarantee Transactions

Form of Guarantee

Specifies the form of the bank guarantee. A direct bank guarantee is issued by the applicant's bank (issuing bank) directly to the guarantee beneficiary without involving a correspondent (advising) bank. By contrast, an indirect

bank guarantee is issued by a correspondent bank (usually the guarantee beneficiary's bank) upon the counterguarantee of the guarantee applicant's bank.

Bank Guarantee Type

Specifies a bank guarantee type that you have defined. For more information, see the description in the self-service configuration app Define Bank Guarantee Types.

Basic Data for Standby Letter of Credit Transactions

Issuing Bank/Advising Bank

Specifies the bank that issues the standby letter of credit or notifies the beneficiary about the standby letter of credit

Auto Extension Period

Specifies the validity term of one automatic extension of the standby letter of credit

Extension Expiry Date

Specifies the latest term end date for the standby letter of credit

Extension Expiry Date

Specifies the latest term end date for the standby letter of credit

Nonextension Notice Days

Specifies the minimum number of calendar days before the next automatic extension for notifying the bank that the standby letter of credit is not to be extended anymore

Drawing Mode

Specifies whether multiple drawings against the standby letter of credit are allowed

###### Administration (1 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Administration | L7 | trm06 p.16 | loio `4fd8ed9d98d3121ae10000000a42189d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4fd8ed9d98d3121ae10000000a42189d.html?locale=en-US)

**Use**

On this tab, you can determine and call up administrative data for a financial transaction.

**Note:**

The various areas and fields are not visible in all financial transactions. Which ones are displayed can depend on the product type, on whether you use, for example, the integration with Public Sector Management (Fund and Grant fields), or on whether the financial transaction is relevant for clearing or for trade repository reporting.

See also:

Integration with SAP Public Sector Management (PSM)

External Accounts (Clearing Accounts)

Trade Repository Reporting (TRR)

Features

Position Assignment

In the Facility field, you assign a money market transaction to one of the facilities created in the system. If the transaction assigned has a different currency from the facility, enter the rate from the currency ratio table in the Exchange Rate field.

Here the transaction can be assigned to a particular portfolio.

You can use a finance project to issue a common key with which to group related transactions.

If a third party bears the risk related to the transaction, you enter this in the Guarantor field.

You use the general valuation class to classify transactions according to their asset type (such as short-term investments).

Hedging Classification

You must enter values to the following fields if they are used as differentiation terms for your treasury positions. Only fields that are relevant for differentiation are displayed. These fields are additional account assignments from other areas. When flows are posted to Financial Accounting, the values of the account assignments are also transferred to the jounal entry:

Cost Center

Profit Center

WBS Element

Functional Area

Up to five custom differentiation terms are available, if you defined them in the Define Custom Differentiation Terms Customizing activity:

- Custom differentiation term 1

- Custom differentiation term 2

- Custom differentiation term 3

- Custom differentiation term 4

- Custom differentiation term 5


In the Fund field, you specify unique keys for funds. You can assign budgets to funds to show their origin in detail at a later date. (Only available if you use the integration scenario with Public Sector Management.)

The Grant field contains data relating to the type and status of a grant agreement. (Only available if you use the integration scenario with Public Sector Management.)

If you use the integration with Public Sector Management and you want to distribute the nominal amount/units of a money market or security transaction to different account assignments, you can do so in the Account Assignment table on the Cash Flow tab. For more information, see also Integration with SAP Public Sector Management (PSM).

**Note:**

The differentiation must be defined in the Define and Assign Differentiations Customizing activity.

Risk Mitigation

You set this indicator for financial transactions that are used to mitigate risks.

When this indicator is set for a financial transaction, the system ignores it when calculating the rolling average position for Clearing Threshold Reporting (CTR).

You use the Hedge Request ID field for all financial transactions created based on an hedge request.

Additional Fields

You can determine the following additional fields:

You use the Assignment field to group different transactions.

You use the Reference field to create internal references.

You use the Characteristic field to mark individual transactions.

On Behalf of Company Code

Country/Region Key

Segment

Business Area

CFI Code

The Classification of Financial Instruments (CFI) code (ISO 10962) is used to define and describe financial instruments for all market participants. CFI codes are used for trade repository reporting, such as for EMIR regulations. You may receive such CFI codes when you are trading financial instruments on trading platforms.

Sec. ID (ISIN)

The International Securities Identification Number (ISIN) (ISO 6166) uniquely identifies a security. ISINs are used, for example, for trade repository reporting, such as for EMIR regulations. You may receive such ISINs when you are trading financial instruments on trading platforms.

Trade Repository

Assign the legal basis and the external trade ID of the financial transaction.

**Note:**

You can also fill the field automatically using the BAdI FTR_TR_DEFAULT_TRADE_ID (BadI: Default Value for External Trade ID in Financial Transactions). You find this BAdI in Customizing for Treasury and Risk Management under Transaction Manager General Settings Transaction Management .

See also: Update Transactions with an External Trade ID

If a financial transaction is relevant for Trade Repository Reporting (TRR), then filling this field is particularly relevant:

External Trade ID and Interim Trade ID

Forex Transactions: If you do not determine the external trade ID yourself and, instead, your counterparty communicates the external trade ID to you through the counterconfirmation (SWIFT notification MT300), the system copies the external trade ID from the incoming notification and into the financial transaction data as well as into the outgoing correspondence objects. (The prerequisite for this is that, in the Customizing activity Assign Attributes for Business Partner Groups, the Get Values from Counterconfirmation indicator is set for the business partner group in the Inbound Correspondence area.)

As soon as the external trade ID is defined in the financial transaction, it also becomes an additional matching criterion for these financial transactions. In other words, alongside the matching criteria defined in Customizing, correspondence objects that need to be matched must also share the same external trade ID.

In MT300, the external trade ID is expressed over two fields; the content of these fields forms the external trade ID when combined. These fields are 22M (namespace) and 22N (transaction ID). Further, MT300 contains the field 22L that the system uses to derive the relevant legal basis.

Authorization

You can assign the transaction to an authorization group so that only users that have an authorization for this authorization group are allowed to process the transaction. You can specify, for example, that only selected employees are allowed to process transactions related to their department. You do this by specifying the relevant authorization group when you create the transaction.

Central Clearing Data

This area appears when the financial transaction is relevant for clearing. The appearance of the area differs depending on the central clearing option that is valid for the financial transaction:

Central Clearing Optional

When the financial transaction is created, it initially has the clearing status Not Relevant for Clearing. In this area, however, the Set as Relevant for Clearing pushbutton appears. If you want the financial transaction to pass via a central counterparty, confirm the pushbutton. The financial transaction acquires the clearing status Clearing Requested (Planned). Select the clearing account.

**Note:**

If you have entered a clearing account in the Define Default Values for Clearing transaction, this account appears in this field. However, you can replace this clearing account with another clearing account.

Enter the planned clearing date.

The Set as Not Relevant for Clearing pushbutton appears. You can use this pushbutton to set the clearing status of the transaction back to Not Relevant for Clearing.

Central Clearing Mandatory

Clearing status: Clearing Requested (Planned)

Clearing account: Select the clearing account.

**Note:**

If you have entered a clearing account in the Define Default Values for Clearing transaction, this account appears in this field. However, you can replace this clearing account with another clearing account.

Planned clearing date: The current date appears by default.

When you have received confirmation that the clearing of your financial transaction has been accepted or rejected by the central counterparty, perform the Accepting/Rejecting a Clearing function.

See also: External Accounts

You either enter the Rating or the Credit Standing, this depends on the general setting for rating in Treasury and Risk Management made in the Customizing.

Rating

1. Choose the Rating Procedure.

Indicates the used rating procedure.

- 2. Choose the Rating.

Indicates the result of a rating carried out with a rating procedure.

- 3. Choose the Trend for the rating.

Indicates the trend of an existing rating so that expected changes to the business partner can be displayed.

- 4. Enter the validity for the rating using the Valid From and Valid To fields.
- 5. Save your entries.


**Note:**

You can enter the ratings of different rating procedures.

Credit Standing

- 1. Choose one of the predefined internal classificationsCredit Standing.
- 2. In the Dt.Cred.Stndg field, you can enter the date on which credit standing information on the business partner was provided.
- 3. You can enter the Status of the credit standing information.
- 4. In the Cred.Stndg Text field, you can add additional information for the credit standing.
- 5. In addition, you can enter one external provided rating information for the business partner. Choose the credit standing institute in Cred.Stndg Inst field and enter the Rating result provided by the credit standing institute.
- 6. In addition, you can set the following indicators and enter a corresponding date:

Affidavit

Bankruptcy Proceed.

Foreclosure

- 7. You can enter the status of legal proceedings and the corresponding date.
- 8. Save your entries.


In the Customizing activity Make General Settings for Rating available under Treasury and Risk Management Transaction Manager General Settings Organization Rating/Credit Standing , you decide which rating function you want to use for the rating of financial transactions, security classes, and asset pools in Treasury and Risk Management. You can decide between the following rating functions:

Rating

Credit Standing

You make the settings for Rating and Credit Standing functions in Customizing under Treasury and Risk Management Transaction Manager General Settings Organization Rating , using the following Customizing activities:

Rating

Set Rating Procedures and Ratings

You can create rating procedures and assign ratings to them.

BAdI: Calculate Rating

Credit Standing

Define Rating

Define Credit Rating Institute

Define Status of Legal Proceedings

**Note:**

The Customizing for the rating and the credit standing are the same as that available for the business partner.

SPPI Classification

This area is only available for interest-bearing financial instruments such as money market transactions.

The SPPI (solely payments of principal and interest) is relevant for IFRS 9. The field expresses whether the financial transaction passed an externally executed SPPI test or not.

- 1. Choose the Valid-From Date.
- 2. Enter the Passed or Failed value in the SPPI Criterion field.

###### FX Hedge Management

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > FX Hedge Management | L7 | trm06 p.21 | loio `8143a6c104f446289ed5000d4b881b40` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8143a6c104f446289ed5000d4b881b40.html?locale=en-US)

Assign the reference-based exposure item which should be hedged by the financial transaction.

If you create a hedging instrument for an exposure item by reference, you must enter the exposure item ID. In case, you do not know the exposure item ID, you can use the search help available for the Exposure Item ID field.

After you have assigned the exposure item, you see the following information for the exposure item:

Exposure Item Description

Assigned Amount

Risk Currency

Due Date of the Exposure Item

**Related Information**

Elementary Search Help for Exposure Item ID by String

###### Other Flows (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Other Flows | L7 | trm06 p.21 | loio `3507da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3507da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The concept of flow types allows you to define other flows - such as charges or commissions (absolute or proportional) - for the individual product types. These other flows are created with each transaction.

The flow types that are assigned are displayed in the other flows area as a default. You also still enter the payment amount, currency with the direction and the payment date.

**Procedure**

- 1. Use the input help for the Flow Type field to choose the flow type that you require (such as commission or charges).
- 2. Enter the direction of the payments by indicating whether it is an incoming payment (+) or an outgoing payment (-).
- 3. Enter the payment amount, the payment date and the currency in which the flow is to be paid.
- 4. You can change the entries for the other flows provided that the flows have not yet reached the Flagged for Posting status.
- 5. To delete one of the other flows, select the flow you want to delete and choose “Delete”.
- 6. You can display the details for a flow and change the entries if required.

###### Payment Details (2 of 4)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Payment Details | L7 | trm06 p.22 | loio `2707da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2707da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You enter the data that is required for making transactions with your business partner in the payment details of a financial transaction.

**Note:**

The system provides these payment details by default when you create a transaction based on the product type, transaction type, and currency. Alternatively, you can also determine the payment details for the individual transactions. You enter the details in the system when you save the transaction.

For more information, see Input Help: Payment Details.

**Prerequisites**

You have created the payment details in the Standing Instructions. On the SAP Easy Access screen, choose Maintain Business Partner (BP) or Payment Details (TBI1).

**Features**

In addition to the Payer/Payee (business partner) field, you can also see the Alternative Payer/Payee field if you defined this in the system.

Payer/Payee and Alternative Payer/Payee

- 1. If the business partner is a house bank that supports clearing between the sender and receiver accounts, then payment using the payment programs and an entry in the Payer/Payee field are not required.
- 2. If the business partner is not a house bank, you must specify a payer/payee in the payment details for the transaction.


The business partner makes and receives payments:

The business partner is proposed by the system as the payer/payee provided that the bank details are recorded in the master data and no alternative payer/payee has been entered.

A third party makes and receives payments rather than the business partner:

If payment is not made by the business partner, a third party must be entered as an alternative payer/payee. These bank details must be entered in the system.


Payments:

If there is no alternative payer entered in the master record of the payer/payee, payment is made to the payee account for this payee.

If there is an alternative payer entered in the master record of the payer/payee, payment is made to the account of this alternative payee for the actual payee.

Regardless of whether or not the business partner makes/receives payment, the following applies:

The Payer/Payee field specifies for whom the payment is being made. The account to which payment is made depends on the master record of the business partner entered as the payer/payee in the payment details of the transaction.

Special Functions

You can define data for the state central bank indicator and the country/region of origin using the detailed screen of the Payment Details tab. This function is available only if it is released using the field modification.

For more information, see Repetitive Code.

###### Cash Flow (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Cash Flow | L7 | trm06 p.23 | loio `3807da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3807da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The cash flow contains all flows of a financial transaction, classified by flow types, in chronological order. Typical flow types include nominal amount increases, fixed or variable interest, and repayments. The investment amount, the interest payment, and repayment amount are concentrated on one or several flow records through this.

**Integration**

As the cash flow of financial transactions forms the basis for all trading, management and evaluation activities within Treasury, the flows have particular significance. They're generated by financial mathematics from the general data on the transaction, the structural characteristics, and the conditions assigned to the transactions. The flows contain both the payment data and their calculation bases, as well as all data required for posting.

The single flow records, from which the cash flow is made up, can be generated in various ways:

By Manual Entry, such as investment amounts, charges, or special repayments.

By Automatic Generation, that is generated from the conditions. These include, for example, interest or regular repayments.

By Derivation, whereby the flows appear here automatically.

By Accrual/Deferral Flows that arise from the periodical assignment of expenses and revenues from the transaction.

As a result of transaction valuations (Valuation Flows), for example, with regard to price gains and losses.

The cash flow forms the basis for the following:

The effective interest rate calculation

The accrual/deferral of expenses and revenues

Triggering payments

Updating the flows in Cash Management

Updating Financial Accounting by using flexible account determination

Updating positions

Interest accruals/deferrals

Foreign currency valuations

Yield calculations

**Features**

Cash Flow Area

You use the SAP List Viewer to display the cash flow. You can use the following functions:

You use the Details function to display the details of a flow.

The Set Filter function enables you to display just the lines in a column or several columns that fulfill certain criteria. With the standard settings, you only see the structural characteristics. You've the option of displaying accrual/deferral flows, valuation, and transfer flows.

By double-clicking a flow, you can display the flow details.

By choosing Select Layout, you can select one of the following predefined display variants:

Basic View

This is set up as a standard view and contains information on payment dates, payment amounts, currencies, flow types with names, posting keys, and activities.

Due Date View:

This view displays information on the due dates.

Posting Information:

Entries for the payment date, payment amount, currency, flow type, posting status, posting date, document number, year, and assignment.

Calculation Bases:

This view displays information about the interest rates, the calculation methods and the relevant calculation periods that were used to calculate the flow amount.

Local Currency View:

For transactions in a foreign currency, you see an entry for the amounts in the local currency as well as the payment amount in the transaction currency. view displays the foreign and local currency amount and the exchange rate for flows that haven't yet been posted. The exchange rate is taken from the current rate table and has Current Rate status.

You can edit the flows. You can set either the exchange rate or the local currency amount here, for example, to avoid rounding off an amount when the exchange rate is fixed. When you double-click a line in the cash flow, an entry screen appears on which you can change the corresponding condition.

If you want to set the exchange rate, enter the rate and select Rate Set. You set the local currency amount in a similar way.

In the local currency view of the cash flow, you can see any changes that have been made and you can see whether the translation was carried out based on current rates or manual rates that were set.

Payment View:

This view displays data relevant to payments for the house bank and house bank account, payer/payee, partner bank details and different payment methods.

Posting View:

This view shows you the data, such as posting date, flow type, payment amount, payment currency, posting status (name), document number, and year (year for the document).

You can change these predefined views or define your own display variants.

Account Assignment Table

This table is only available if you use the integration with Public Sector Management. If this is the case, you can distribute the total nominal amount of money market or securities transactions to different account assignments in this table.

Specify the different partial amounts either by entering the amounts directly or by entering the percentages and assigning the corresponding account assignments to them.

###### Memos (1 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Memos | L7 | trm06 p.25 | loio `5a07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5a07da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The Memos tab page provides additional information about a transaction that has been created.

**Use**

You can create a memo both during and after the creation of a transaction. You define memo types in Customizing to enter the memos structurally in the system. In Customizing for Transaction Manager, choose General Settings Transaction Management Define Memo Book .

Operating Notes:

Use S to select the memo type(s).

If the indicator M is set, you cannot see all the text defined in the entry field.

The S indicator shows that memos of this type are available in other languages.

Use the Editor to enter the memo.

###### Status (1 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Status | L7 | trm06 p.25 | loio `5d07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5d07da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

This tab page shows you the current status of a financial transaction, which results from the Customizing settings for Correspondence, the product-specific Activity category and the processing category assigned to the Transaction type.

Correspondence

You can make external correspondences for a transaction for which you created business partners in the Standing Instructions . In these standing instructions, you specify for each product and transaction type whether a confirmation and a counterconfirmation are required for the particular transaction. You can choose from the following correspondence statuses: 0 (not required), 1 (required), 2 (confirmation executed). If the transaction has been carried out, the name of the user and the date are displayed.

Activity Alongside the current activity category (such as order or contract), the current status of the transaction (such as active or closed), the person who entered the transaction and the name of the last person to change it are displayed.

Example:

In the case of a retrospective rise in the interest rate, a new field appears with information about the last person to change the transaction, the date, time and the comment Activity change.

Transaction This area provides information about the entire transaction process (such as whether a settlement transaction is included).

The statuses predefined by the system are shown as the System Status in status management. You can also add to the transaction status by user-defined statuses ( user status).

**Structure**

A status can be set or deleted automatically as the result of a business activity. You use a status profile to do this. In Customizing for the Transaction Manager , choose General Settings Transaction Management Status Management

Define Status Profiles.


You can also enter the user status manually. To do this, choose Status Management and then the Business Activities tab page. This provides you with an overview of the activities that are permitted, or not permitted.



For more information about the user status, choose User Status .

**Use**

The transactions available in the transaction management functions (for example, settlement) are defined in the general status management as business activities. An activity can set or delete one or several statuses. The impact of business activities on the system status is predefined, but you can set up the user status management. You can therefore add extra statuses to a transaction type. These are managed centrally and displayed for the relevant financial transactions.


In Status Management you can specify that a transaction cannot be settled until it has been confirmed.

You can also trigger an event and workflows for the business object Financial Transaction by setting and deleting statuses. In Customizing for the Transaction Manager , choose General Settings Transaction Management Status Management

Define Event Creation.


Transferring a transaction from the trading area to the back office.

###### Partner Assignment (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Partner Assignment | L7 | trm06 p.27 | loio `c307da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c307da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The tab page Partner assignment provides an overview of all of the relevant data for the partners assigned to the transaction. You can branch directly to the SAP business partner and change the data if necessary. You can also assign or create additional partners for the transaction.

**Prerequisites**

To make the necessary settings for the SAP business partner in Customizing, choose Basic Functions SAP Business Partner for Financial Services SAP Business Partner.

**Procedure**

Partner List

In addition to the partner's name and standard address, the partner list displays the address type relevant for correspondence, such as Business address . You define the default value for the address type in Customizing. The correspondence is sent to the address that has been assigned to this address type. You can select a different address type using the address type button, which displays all of the address types that have been assigned to the partner. You assign the partner's addresses to address types using the Address Overview function in SAP business partner maintenance (section Address Usage ).

**Note:**

You assign a grouping and an address type for each role in the Customizing activity Assign Grouping and Address Type per Assignment Cat., Application Cat. and Role (SAP Business Partner Settings for Partner-Object Relationships) . This appears as the default address type in the partner list, provided you have also assigned an address to this address type in the Address Usage section of the Address Overview for the business partner. If no address has been assigned to this address type for the partner, the partner list defaults to the standard address type XXDEFAULT.

If you choose History , the partner list displays all the partners that have been assigned to the transaction so far , including those valid in the past and in the future. If you choose Date , the display reverts to the partners that are valid for the date you enter.

The partner list also contains the business partner key and the role category (field ObjectPart ). These appear as information fields that cannot be changed.

- 1. Select a partner from the Partner list . To display the data for the SAP business partner, choose Display .
- 2. To assign an existing partner to the transaction, choose Add Partner. The Object Part screen displays the roles delivered by SAP (such as counterparty). To display additional roles in this screen, you first need to define them. You can do this from the application menu by choosing Basic Functions Tools SAP Business Partner SAP Business Partner: Application Development BP Control BP Roles. You then have to assign these roles in the Customizing activity Assign Additional Roles per Assignment Category and Application Category (SAP Business Partner Settings for Partner-Object Relationships).


After selecting the role, enter the relevant data in the Business Partner Search screen. The partners you assign in this way are added to partner list .

To delete partner assignments from the partner list, choose Delete Assignment .

**Note:**

In the IMG activity Assign Additional Roles per Assignment Category and Application Category, you determine whether or not the additional roles that you have defined can be deleted. If you want to prevent a partner in a certain role from being deleted, flag the role as a required entry field. This also means that you cannot save the transaction unless a partner has been assigned in this role.

###### Analysis Parameter (RM) (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Analysis Parameter (RM) | L7 | trm06 p.28 | loio `740fda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/740fda531198434de10000000a174cb4.html?locale=en-US)

- 1. Choose Analysis Parameters (RM) to add to the contract data the information necessary for transaction valuation.

- a. Set the Analysis Active indicator.

All financial objects to be taken into account when evaluations are run in Risk Analysis have to be flagged in this way.

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

- b. Enter a summarization rule for transactions that you want to summarize.

The system uses the summarization rule to aggregate the balances of accounts, fully disbursed loans, and variable transactions in the database. The Summarization Rule field does not appear on the screen for any of the other transactions.

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

- c. Set the balance sheet indicator for the transaction on which the financial object is based.

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

- d. Enter the valuation rule.


The valuation rule controls how the transaction is treated in the individual risk evaluations.

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

- 2. You can define precisely the validity of the financial object by entering the validity period.

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

- 3. In the data group Analysis Characteristics, define the characteristic values for the financial object.


Generated Analysis Structure

**Recommendation:**

You can define the sequence of the RM analysis characteristics and how they appear on the screen by choosing Financial Supply Chain Management Treasury and Risk Management Basic Analyzer Settings


Reporting Characteristics Define Generated Analysis Structure . You can enter values for hidden characteristics only by using derivation strategies. If a characteristic is hidden by linking, then the other characteristics in the linking will also be hidden.

**Note:**

If you want to know how characteristics are derived when you save and run checks on a financial object, choose

Extras Characteristic Derivation Log . A list then shows you the source fields along with the corresponding target fields.


Static Analysis Structure

Business Partner

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

Trader

Automatically derived by the system from the corresponding field in the financial transaction data.

Contract Type

Automatically derived by the system from the corresponding field in the financial transaction data.

Product Category

Automatically derived by the system from the corresponding field in the financial transaction data.

Product Type

Automatically derived by the system from the corresponding field in the financial transaction data.

Security ID

Automatically derived by the system from the corresponding field in the financial transaction data.

Securities Acct

Automatically derived by the system from the corresponding field in the financial transaction data.

Futures Account

Automatically derived by the system from the corresponding field in the financial transaction data.

Currency

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

Portfolio

Automatically derived by the system from the corresponding field in the financial transaction data.

Country/Region

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

Transaction

Automatically derived by the system from the corresponding field in the financial transaction data.

Contract Number

Automatically derived by the system from the corresponding field in the financial transaction data.

Position ID

Automatically derived by the system from the corresponding field in the financial transaction data.

Characteristics

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

If you decided to use the generated and the static analysis structure, you can toggle between the analysis parameters for the different analysis structures.

**Related Information**

Analysis Structure

###### Creating Data for Default Risk Limits (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Creating Data for Default Risk Limits | L7 | trm06 p.30 | loio `770fda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/770fda531198434de10000000a174cb4.html?locale=en-US)

- 1. Go to the Default Risk Limit tab within the financial transaction data.
- 2. Set the Counterparty/Issuer Risk Active (CP Risk Active) indicator so that an attributable amount is calculated for the transaction.
- 3. Enter the following limit characteristics:

Limit Product Group (the limit product group you enter here overwrites the default limit product group.)

Monitoring Unit (freely definable reporting characteristic)

Rating (the rating you enter here overwrites the rating for the business partner, but this is not the case for the integrated external business partner).

- 4. Enter the following evaluation parameters:

Default Risk Rule (the default risk rule you enter here will override the one set in Customizing).

Recovery Rate

- 5. Enter the following netting information:

Netting ID

Collateral ID

- 6. Enter the validity.


Transaction Start CPR: Start of validity of transaction for counterparty/issuer risk

Transaction End CPR: End of validity of transaction for counterparty/issuer risk

**Note:**

If you are using generated characteristics, you must maintain them in the analysis (RM) part of the financial object. To do this, return to the Process Financial Object: General Part screen and choose Analysis (RM).

Result

In the next end-of-day processing run, the system calculates an attributable amount for the transaction to which you assigned this financial object.

**Note:**

External transactions do not have to be assigned a financial object in order for them to be taken into account when the attributable amount is calculated.

###### Conditions Overview

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Conditions Overview | L7 | trm06 p.30 | loio `e2ca6a06238f42c7811d29a54b877860` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e2ca6a06238f42c7811d29a54b877860.html?locale=en-US)

Using the Conditions pushbutton in the upper part of the screen, you can navigate to the Overview of Conditions.

A condition is a contractually agreed element of a financial instrument. It describes the structure of the transaction in terms of the period and amount (interest, repayment, and so on).

You enter conditions using predefined condition types. Predefined flow types are assigned to condition types. These flow types display changes to the payment flows and are part of the cash flow.

**Use**

Conditions include all the data that is relevant for generating condition-based flows in the cash flow. The different entries for the individual condition types determine exactly how the flows are calculated.

**Structure**

Condition Items

You can choose from several condition types for each product type.

A condition item comprises entries (dates and amounts) for the condition type, such as the entries in the following fields: Effective-From Date, Calculation Date, Due Date, and Percentage Rate.

Condition Details

By double-clicking a condition item or by selecting the condition item and choosing Detail, you can display the detail screens for the conditions.

Here, you find the effective-from date again for the condition item, the Condition Form field (Active), and the Amounts, Dates, and Payment Data / Other tabs, depending on the condition type.

The Amounts, Dates, and Payment Data / Other tabs show you exactly how the conditions are structured. The screen contains more fields than the initial Conditions screen, depending on which fields you select for the condition.

Amounts

This tab includes entries for the amounts and/or the amount of a condition type.

Dates

- 1. Calendar

If you always want to shift the due date to a working day, enter up to five calendars you want to use to calculate the working day.

- 2. Calculation Date/Due Date

The calculation date is the last day of the current interest period. The due date is the day on which the interest payment is due.

This area includes the fields for determining the exact calculation dates and due dates of the condition item.

- 3. Calculation Modes


Here, you define the method used to determine the next calculation date or due date.

Choose Date Preview to display a list of the dates of the flows of the relevant condition type. The list includes the due date, the payment date, the calculation period, and the resulting number of days (interest days), as well as the interest calculation method.

Using the Create Parallel Condition Gr. button, you can enter parallel condition items.

**Note:**

For product types with 610 Cap/Floor product category the parallel conditions aren’t available, they have only one condition.

To delete a condition item, select it and choose (Delete Line).


The entry options in the condition details differ depending on the condition type.

**Related Information**

Condition Details: Interest (New FIMA) Interest Rate Adjustment Scaled Conditions

###### Condition Details

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Condition Details | L7 | trm06 p.32 | loio `d507da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d507da531198434de10000000a174cb4.html?locale=en-US)

**Use**

To see the conditions details of a financial transaction, you can either use a pushbutton on the Structure tab or in the upper applications toolbar.

Condition Details: Interest (New FiMa)

These condition details are available for product categories 550, 580, and 620, if you have activated the new FiMa by choosing Parallel Conditions in the Cash Flow Calculation field for these product types in the Customizing settings for the product types. This setting enables the use of enhanced financial mathematics functions (new FiMa), such as parallel conditions and additional interest calculation types such as the Average Compound Interest Calculation. It influences how conditions are managed and therefore how cash flow is calculated.

Condition Details: Interest

For other financial transactions with interest conditions like Fixed Term Deposits and Deposit at Notice.

If you haven't activated the new FiMa as explained above.

Interest Payment

See also: Interest Rate Adjustment Data tab

###### Condition Details: Interest (New FIMA) (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Condition Details > Condition Details: Interest (New FIMA) | L8 | trm06 p.32 | loio `9f07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9f07da531198434de10000000a174cb4.html?locale=en-US)

**Use**

On the Condition Details: Interest screen, you can make more detailed entries for the interest calculation to supplement those entries you have already entered on the Structure tab in the Interest Structure area.

**Note:**

Two types of condition item are required to represent the variable interest rate condition.

- 1. Define the underlying reference interest rate and the calculation method for the variable interest rate in the condition item Nominal Interest.
- 2. Define the frequency with which you want the variable interest to be adjusted, and the corresponding interest rate fixing date in the condition item Interest Adjustment. For more information, see also Interest Rate Adjustment.


Prerequisites

These condition details are available for product categories 550, 580, and 620, if you have activated the new FIMA by choosing Parallel Conditions in the Cash Flow Calculation field for these product types in the Customizing settings for the product types. This setting enables the use of enhanced financial mathematics functions (new FIMA), such as parallel conditions and additional interest calculation types such as the Average Compound Interest Calculation. It influences how conditions are managed and therefore how cash flow is calculated.

**Procedure**

- 1. By choosing the Conditions pushbutton or by choosing Goto Conditions , the Conditions Overview appears. Each condition has a line in the overview, such as one line for the interest condition and one line for the repayment condition.
- 2. You reach the Conditions Detail: Interest screen when you double-click the interest item on the Conditions Overview screen or when you choose the Detail View: Interest Condition pushbutton.
- 3. The details screen comprises the following areas:


Header data of the condition at the top of the screen.

Amount tab

Data for Percentage Calculation

Interest calculation method and the type of interest calculation

The interest calculation method is a procedure for counting the days for the interest calculation. Therefore, it is also often called the days count method. This is defined by a quotient of days method and a base days method.

The following types of interest calculation are available:

Linear Interest Calculation

Exponential Interest Calculation

Exponential Interest Calculation with Factors

Percentage Interest Calculation

Percentage Interest Calculation per Day

Compound Interest Calculation

Average Compound Interest Calculation

For more information, see also Interest Calculation Types.

Scaled Calculation

By setting the Scaled Calc. indicator, you can enter scaled conditions. See also: Scaled Conditions

Formula

You can enter a formula for the interest rate calculation. Choose a formula and enter the values for the variable.

Ref. Int. Rate

For variable interest conditions, you can enter a sign (+ or -) and a reference interest rate.

Percentage Rate

Enter the percentage rate for the interest condition.

**Note:**

For variable interest conditions, you can also add here a percentage that is a spread on top of the variable interest rate.

Payment Rate

The payment rate indicates a percentage rate that is applied to the condition amount calculated previously. The cash flow therefore does not display the condition amount calculated, but the condition amount multiplied by the payment rate in percentage. For more information, see the field help.

The Average Interest Rate area contains specific settings for the average interest rate calculation of the Average Compound Interest Calculation. You see this area only if you have chosen this interest calculation type.

Weighting category

To determine the average interest rate, the reference interest rates of a period are weighted.

You can choose from two weighting categories:

S Based on Interest Rate Fixing Date

The weighting corresponds to the number of calendar days from the interest fixing date to the next working day.

L Based on Interest Rate Adjustment Date

The weighting corresponds to the number of calendar days from the interest rate adjustment date to the next working day.

You can define the rounding decimal places for the average interest rate.

The average interest rate can contain a spread (S). This is added after the rounding of the average interest rate.

The rounded average interest rate including the spread can be limited by an upper limit and a lower limit.

Rounding Factors

In this area, you define the rounding rules (rounding category and the number of decimal places) for the calculated factors. Which factors are available here depends on the interest calculation type chosen:

Base Factor

Interest Factor

Flow Factor

Example:

For the Average Compound Interest Calculation, you can enter a rounding category and the number of rounding decimal places for the interest factor.

Round Amounts

In this area, you can define rounding rules for the calculated amount using the following fields:

Rounding Cat.

Rounding Unit

Base Unit

For the Exponential Interest Calculation with Factors, you can enter a rounding category in the Factor RC field for the factor and the number of rounding decimal places for a factor in the Dec. Fac. Round field. The number of rounding decimal places is used with the rounding category for the factor to be rounded or truncated.

For more information, see the field help.

Calculation Base

Amount

Reference

For the Exponential Interest Calculation with Factors, you can enter a rounding category for the base factor in the Base Factor RC field and the the number of rounding decimal places for a base factor in the Dec. BF Round. field. The number of rounding decimal places is used with the rounding category for the base factor to be rounded or truncated.

Currency-Related Data

Condition Amnt

Currency

Lower Limit

Upper Limit

You can find a more detailed description of the methods in the field help for this field.

Date tab

Calendar

You can enter up to five calendars as relevant for the working day check for the interest flows generated from the conditions.

The system proposes the calendar of the country/region in whose currency the transaction was created.

Calculation Date

First you choose the rule for date updates. The default value is Regular, which means that the frequency of the calculation date is also relevant for the due date.

Enter the frequency by entering the unit for the frequency (Months or Calendar Days) and the cycle.

Enter the first date.

Set the Month End indicator if needed.

Set the Inclusive indicator if needed.

Enter the settings for the working day shift if needed.

Due Date

First you choose the rule for date updates. The default value is Regular, which means that the frequency of the calculation date is also relevant for the due date.

Enter the frequency by entering the unit for the frequency (Months or Calendar Days) and the cycle.

Enter the first date.

Specify how to handle the due date if it falls on a day that is not a working day according to the settings in the Customizing activity Maintain Calendar.

Select the rule and, if required, enter the number of days by which the due date is to be shifted.

Set the Month End indicator if needed.

Other calculation data

Shift due date

First period

Last period

For more information, see the field help.

- 4. You can use the Date Preview button to see whether the settings made lead to the desired dates.
- 5. To check your entries, you can also look at their impact on the cash flow. To do this, you have to exit the details screen and go to the Cash Flow tab of the financial transaction data.

###### Interest Calculation Types (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Condition Details > Condition Details: Interest (New FIMA) > Interest Calculation Types | L9 | trm06 p.36 | loio `682d3fcfc9ad4b4289bdba925f156bd0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/682d3fcfc9ad4b4289bdba925f156bd0.html?locale=en-US)

Specifies the type of interest calculation within the calculation period.

The following options are available for interest calculation:

**Linear Interest Calculation**

Interest amount = capital * percentage rate / 100 * days / base days

**Exponential Interest Calculation**

In the case of interest rate adjustments, an interest period is divided into calculation periods.

Interest amount = Base amount * ( q ** (days / base days) - 1 )

where

q = 1 + percentage rate / 100 (compounding factor)

** = power operator

[figure TRM06-F017]

**Exponential Interest Calculation with Factors**

The system calculates the interest factor according to the formula for the exponential interest calculation. However, basic factors have been introduced to calculate the calculation base amount, which is used to capitalize the capital amount within a calculation period.

In the case of interest adjustments within an interest period, the interest calculation type Exponential Interest Calculation with Factors delivers more precise values because the determination of the calculation base amount has been changed from a summation of amounts to multiplying the capital with the base factors.

[figure TRM06-F018]

**Percentage Interest Calculation**

Interest amount = Base amount x percentage rate / 100

**Percentage Interest Calculation per Day**

Interest amount = Base amount x percentage rate per day / 100 x days

**Compound Interest Calculation**

In the case of interest rate adjustments, an interest period is divided into calculation periods. The compound interest calculation uses the formula for linear interest calculation to calculate the interest amount of a calculation period:

[figure TRM06-F019 - In the case of interest rate adjustments, an interest period is divided into calculation periods. The compound interest calculation uses the formula for linear interest calculation to calculate the interest amount of a calculation period:]

Explanations

|Z|Interest amount|
|---|---|
|K|Capital at the start of the interest period|
|R|Interest rate of the calculation period|
|D|Number of days of the calculation period|
|BD|Base days|


The base amount of the calculation period is the sum of the capital amount at the start of the interest period and the interest of the previous calculation periods within the interest period:

Calculation of the Base Amount

[figure TRM06-F020 - Calculation of the Base Amount]

Explanations

|i, n|Index of a interest flow|
|---|---|
|Bn|Base amount of the calculation period n|
|Zi|Interest amount of the calculation period i|
|K|Capital at the start of the interest period|


This results in the following formula for the calculation of the interest amount (for the respective calculation period within the interest period):

Interest Amount of Calculation Period

[figure TRM06-F021 - Interest Amount of Calculation Period]

Explanations

|i, n|Index of a interest flow|
|---|---|


|Zi|Interest amount of the calculation period i|
|---|---|
|K0|Capital at the start of the interest period|
|Rn|Interest rate of the calculation period n|
|Dn|Number of days of the calculation period n|
|BD|Base days|


**Note:**

Only supported for interest calculation methods using days method act, such as act/360 and act/365.

**Average Compound Interest Calculation**

The system calculates the interest amount using an average interest rate. This is determined per calculation period from the average product of the previous interest factors of the interest period.

The Average Interest Rate area contains specific settings for the average interest rate calculation:

Weighting category

To determine the average interest rate, the reference interest rates of a period are weighted.

You can choose from two weighting categories:

S Based on Interest Rate Fixing Date

The weighting corresponds to the number of calendar days from the interest fixing date to the next working day.

L Based on Interest Rate Adjustment Date

The weighting corresponds to the number of calendar days from the interest rate adjustment date to the next working day.

You can define the rounding category and the number of decimal places for rounding the average interest rate.

The average interest rate can contain a spread (S). This is added after the rounding of the average interest rate.

The rounded average interest rate including the spread can be restricted by an upper limit and a lower limit.

[figure TRM06-F022 - Example of Specific Settings for Interest with ACIC]

Example of Specific Settings for Interest with ACIC

Calculation of Average Interest Rate

[figure TRM06-F023 - Calculation of Average Interest Rate]

Explanations

|i, n|Index of a interest flow|
|---|---|
|r|Average interest rate|
|R|Interest rate of the calculation period i|
|w|Weighting of the calculation period i|
|BD|Base days|
|RD|Rounding decimals|


Calculation of the average interest rate with spread

In the condition details, you can enter a spread (S) in the area of the average interest rate. This is added after rounding the average interest rate.

[figure TRM06-F024]

Explanations

|i, n|Index of a interest flow|
|---|---|
|r|Average interest rate|
|R|Interest rate of the calculation period i|
|w|Weighting of the calculation period i|
|BD|Base days|
|RD|Rounding decimals|
|S|Spread|


**Note:**

The rounded average interest rate including the spread can be restricted by an upper limit and a lower limit.

Calculation of the interest amount with average compound interest calculation type:

[figure TRM06-F025 - Calculation of the interest amount with average compound interest calculation type:]

Explanations

|i, n|Index of a interest flow|
|---|---|
|Z|Interest amount of a calculation period n|
|B|Base amount|
|r|Average interest rate|
|BD|Base days|
|D|Number of days of a calculation period|


**Note:**

Only supported for interest calculation methods using days method act, such as act/360 and act/365.

###### Condition Details: Interest

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Condition Details > Condition Details: Interest | L8 | trm06 p.42 | loio `20b3caf16a5649d1816af67b630303f8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/20b3caf16a5649d1816af67b630303f8.html?locale=en-US)

Use

On the details screen, you can make more detailed entries for the interest calculation that you already entered on the Structure tab.

**Procedure**

- 1. By choosing the conditions pushbutton or by choosing Goto Conditions the conditions overview appears.
- 2. The Conditions Detail: Interest screen appears when you double-click the interest item on the conditions overview screen or when you choose the Detail View: Interest Condition pushbutton.
- 3. The details screen comprises the following areas:


Structure

The reference interest rate, the interest rate or interest amount, and the interest calculation methods are all specified here. The system provides many methods for you to choose from. You can find a more detailed description of the methods in the F1-Help for this field.

In the case of fixed-term deposits and deposits at notice, you can choose to have the interest calculated exponentially.

Update

Here, you select the method according to which you want the interest period and the due date to be updated.

The update rules that are provided by the F4 help for selection depend on whether you selected the standard or the special rule for updating the interest.

In the Money Market area, the system defaults to the Regular method (at end of term). This means that the first interest period ends at the end of the term. With Derivatives, the system usually defaults to the Unadjusted rule.

Standard

Regular update:

Both the interest period end and the due date are updated regularly. The update takes place according to the frequency entered. Both of these dates are independent of each other, since each of them is determined separately, and one date is not affected by a shift in the other date.

If one or both dates shift(s) to a working day according to the calendar entered, the dates before the shift provide the basis for calculating the following dates. In other words, the following interest period is shortened accordingly.

**Example:**

Term of an interest rate swap: 11/22/2000 to 12/22/2001

Frequency of the interest payment: Monthly

The interest period end is calculated initially as Friday 12/22/2000 on the basis of the frequency. This date can be shifted to a working day, provided that a working day check has been set up for the end of the interest period. In this example, the calendar specified does not require a shift.

When you use this update method, it does not matter what is in the "Due date +/-" field.

The end of the interest period of the second interest period is one month after the end of the interest period of the first period before this was shifted. As a result, it first falls on the 01/22/2001, is then checked by the working day check, and shifted to the next working day, if required.

Adjusted and unadjusted update methods

The due date is updated regularly.

The end of the interest period is calculated in relation to the due date, either

before(unadjusted) or

after(adjusted)

the due date is shifted by the working day check.

The interest period end is based on the due date and the number of days entered in the "Days +/-" field. If the dates are shifted to a working day, the dates before the shift provide the basis for calculating the following dates. In other words, the interest period that follows is shortened accordingly.

**Example:**

Term of an interest rate swap: 11/24/2000 - 12/24/2001

Frequency of the interest payment: Monthly

On the basis of the frequency, the due date is initially calculated as Sunday 12/24/2000. As a result of the working day check, this date is then shifted to the next working day, which is Wednesday 12/27/2000.

In the next step the interest period end is determined:

Using the "unadjusted" update method, the interest period end (according to the number of shift days entered in the "Days +/-" field) is one day before the due datebeforebeing shifted, in other words, one day before 12/24/2000. Therefore the end of the interest period is 12/23/2000.

Using the "adjusted" update method, the interest period end (according to the number of shift days entered in the "Days +/-" field) is one day before the due dateafterthe due date has been shifted, in other words, one day before 12/27/2000. Therefore the end of the interest period is 12/26/2000.

Special

Adjusted (interest rate period) and unadjusted (interest rate period) update:

The interest period end is updated regularly.

The due date is calculated in relation to the end of the interest period, either

- before(unadjusted) or

- after(adjusted)


the interest period end is shifted by the working day check.

The due date is based on the interest period end and the number of days entered in the "Days +-" field. If the dates are shifted to a working day, the datesbeforethe shift provide the basis for calculating the following dates. In other words, theinterest period that follows is shortened accordingly.

**Example:**

Term of an interest rate swap: 11/22/2000 - 12/22/2001

Frequency of the interest payment: Monthly

The interest period end is calculated initially as Friday 12/22/2000 on the basis of the frequency. This date can be shifted to a working day, provided that a working day check has been set up for the end of the interest period. In this example, the calendar specified does not require a shift.

In the next step the due date is specified: This is calculated initially as Saturday, 12/23/2000 using the interest period end, 12/22/2000, and the shift of one day that is set up. The working day check that follows shifts this date to the next possible working day, which is Wednesday 12/27/2000.

With the "unadjusted" (interest period) update method, the dates that are calculated remain as they are. This means that interest is only calculated up to 12/22/2000 for the nominal amounts upon which the interest rate swap is based. However, the interest is only paid on 12/27/2000.

With the "adjusted" (interest period) update method, the interest period end is adjusted again if the due date shifts. If, for example, a shift of one day is entered in the "Days +/-" field, the interest period end is finally shifted to 12/26/2000.

With both update methods the interest period that follows is shortened accordingly. In other words, the interest period end of the following period is initially still the 22 of the month.

nd

Regular update methods with variable dates / adjusted and regular update methods with variable dates / unadjusted

The interest period end and the due date of the first period are calculated in the same way as the "unadjusted" update method. The interest period is updated regularly according to the time frame entered as the frequency.

The due date is based on the interest period end and the shift entered in the "Due date +/-" field.

In the case of the "Regular with variable dates / unadjusted" update method, these dates stay as they are. In the case of the "Regular with variable dates / adjusted" update method, the interest period end can be changed again: If the due date has to be shifted to a working day according to the calendar entered, the interest period end is adjusted in line with the due date to ensure that the interval between these two dates is the same as the number of days entered in the "Days +/-" field.

The difference between the "adjusted (interest rate period)" and the "unadjusted (interest rate period)" update methods is only apparent when the following dates or the length of the following periods are calculated. If one or both of these dates shift(s) to a working day according to the calendar entered, the dates that are found (after the shift) form the basis for calculating the next interest period. In other words, the dates of the following interest period are also shifted and the followinginterest period is not shortened.

**Example:**

Term of an interest rate swap: 11/22/2000 - 12/22/2001

Frequency of the interest payment: Monthly

The dates for the end of the interest period and for the due date are calculated as follows:

For the "Regular with variable dates / unadjusted" update method, they are calculated in the same way as the "Unadjusted (interest period end)" update method, that is, the interest period end falls on the 12/22/2000 and the due date is the 12/27/2000.

For the "Regular with variable dates / adjusted" update method, they are calculated in the same way as the "Adjusted (interest period end)" update method, that is, the interest period end falls on the 12/26/2000 and the due date is the 12/27/2000.

The interest period end of the second interest period is one month after the interest period end of the first interest periodafterbeing shifted. Since the interest period end of the first period is shifted to 12/26/2000 according to the "Regular with variable dates / adjusted" update method, the interest period end of the following period falls on the 01/26/2001. After undergoing a working day check, this date may then be shifted to the next working day. Since there was no shift in the case of the "Regular with variable dates / unadjusted" update method, the interest period end of the following period continues to be the 22 of the month.

nd

Single dates / adjusted and single dates / unadjusted update methods:

You enter the dates for the interest period end and the due dates individually by choosing Edit => Single dates from the menu. In the case of a term greater than one year, it is sufficient to enter the dates for the first year. These are then used automatically as a basis for the following years.

In the case of the "Single dates" method, the dates for the end of the interest periods and for the due dates are determined independently of each other. With the other two update methods, the due date is calculated from the interest period end and the "Days +/-" field.

For the "Single dates unadjusted" method, these two dates no longer change after this.

According to the "Single dates adjusted" method, on the other hand, the interest period end can be changed again, provided that the due date is shifted to a working day: The interest period end is then adjusted in line with the due date to ensure that the interval between the two dates is the same as the number of days entered in the "Due date

+/-" field.

The table below demonstrates the above-mentioned relationships more clearly:

|Calculation date|Due date|Update methods|
|---|---|---|
|Relative to due date before shift|Regular|Unadjusted|
|Relative to due date after shift|Regular|Adjusted|
|Regular|Relative to calculation date before shift|Unadjusted (interest period)|
|Regular|Relative to calculation date after shift|Adjusted (interest period)|


End of interest period

This date is the first interest period end. All subsequent interest period ends are then calculated according to the update rule selected.

If you select the Month-end field, the interest period ends on the last day of the month.

If you select the Inclusive field, the interest period end is included in the interest calculation.

In the Working day field, you specify the rule to be used for shifting the interest period end if it does not fall on a working day. 5 methods are available and are described in the F1 Help for this field.

Due date

This date is the first due date. All subsequent due dates are calculated according to the update rule selected.

If you select the Month-end field, the due date is the last day of the month.

In the Working day field, you specify the rule to be used for shifting the interest period end if it does not fall on a working day. 5 methods are available and are described in the F1 Help for this field.

Rounding

Rounding Cat.

Rounding unit

Base Unit

###### Interest Rate Adjustment (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Condition Details > Interest Rate Adjustment | L8 | trm06 p.46 | loio `3c09b166f4b847c09db5f96390641244` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3c09b166f4b847c09db5f96390641244.html?locale=en-US)

Define the frequency with which you want the variable interest to be adjusted and the corresponding interest rate fixing date.

**Definition**

You need two types of condition item to represent the variable interest rate condition.

- 1. Firstly, you need the condition item Nominal Interest in which you enter details for the variable interest condition, such as the reference interest rate, the interest calculation method, and the interest calculation type. In addition, you enter the details for the interest period here.

For more information, see also Condition Details: Interest (New FIMA)

- 2. Secondly, you need the condition item Int. Rate Adjustment in which you define the frequency with which you want the variable interest to be adjusted and the corresponding interest rate fixing date.


**Prerequisites**

The relevant reference interest rate needs to have been defined, and you must ensure that current data is available for interest rate fixing.

**Create Condition Item for Interest Rate Adjustment**

- 1. Enter the Effective from date.
- 2. Branch to the Condition Detail Screen
- 3. The screen is divided into the Amounts and Dates tabs.


On the Amounts tab, you enter the interest calculation method.

The Dates tab is divided into two areas: Interest Rate Adjustment and Interest Rate Fixing Date:

In the Interest Rate Adjustment area, you enter the frequency with which you want the variable interest to be recalculated or become effective. The following alternatives are available:

At start of period

Regular

You define the frequency using the available fields.

Single Dates

The Single Dates function displays the interest rate adjustments that recur annually and that you can’t display via At Start of Period and Regular.

Example:

Interest rate adjustment takes place annually in 03/15 and 10/15.

You can show only this irregular sequence of interest rate adjustment dates using Single Dates.

For reference interest rate entry

Enter the calendar rule, which specifies how to handle the date if it falls on a day that isn’t a working day.

Also define which calendars are relevant for determining the date as a working day.

In the Interest Rate Fixing Date area, you define when you want to determine the interest rate value from the market data table. You can choose from the following:

Relative to interest rate adjustment date

Relative to start of period

Relative to period end

Relative to due date

In the following two fields, you enter the lookback period, which specifies how many working days before or after the selected reference date the interest fixing date is.

Lockout Period in working days: Period at the end of the interest period where the reference rate isn’t adjusted anymore. For these last days of the interest period, the last reference rate adjusted one day before the lockout period is used.

Also define which calendars are relevant for determining the date as a working day.

Example Settings for Daily Interest Rate Adjustment, with Lookback Days and Lockout Period

[figure TRM06-F026 - Example Settings for Daily Interest Rate Adjustment, with Lookback Days and Lockout Period]

- 4. Using the Date preview button, you can display the interest rate adjustment dates. The system displays the following dates per interest rate adjustment:


Effective From date of the new interest rate (interest rate adjustment date)

Interest Fixing Date

Percentage Fixing Date

This can differ from the interest fixing date if no entry has been made in the reference interest rate table. The system therefore chooses the previous entry.

Percentage: In this field, you can see the interest rate that is read from market data table.

- Example 1: Date Preview for Daily Interest Rate Adjustments with 2 Lookback Days


[figure TRM06-F027]

- Example 2:


The interest rate is adjusted at the start of a period on February 1, 2016 (Monday). The interest rate has to be fixed two working days before the interest rate is adjusted, which means that the interest rate fixing date is January 28, 2016 (Thursday). If a reference interest rate hasn’t been entered for this date, the system uses the reference interest rate fixed for the last time on January 27, 2016. The date on which the reference interest rate is fixed for the last time is documented as the percentage fixing date.

**Overview of Interest Rate Adjustments**

On the Int. Rate Adj. tab in the financial transaction data, you obtain an overview of all data relevant for interest rate adjustments for the variable interest conditions. The data is grouped according to due date, adjustment date, reference interest rate, interest rate, and the date of the rate fixing.

**Execute Interest Rate Adjustments**

At the interest rate adjustment dates, you must fix the interest rates for the interest flows. For more information, see also Adjust Variable Rates/Prices.

###### Interest Payment

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Condition Details > Interest Payment | L8 | trm06 p.49 | loio `8115da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8115da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this pushbutton to enter a time sequence for paying capitalized interest. You should ensure, however, that the payment dates always coincide with the interest capitalization dates. Otherwise, this will affect the nominal capital, as accrued interest will be paid that has not been capitalized. When you save your entries, the data is checked by the system. A warning message appears if inconsistencies are found.

**Example**

Start date: 01.01.2001 01.01.2001

End date: 01.01.2003 01.01.2003

Nominal amount: EUR 100 million

Variable Interest Calculation: Every 6 months using 6-M-EURIBOR+ 0.5%. The spread must be capitalized too.

Fixed interest calculation: 4% (payable annually)

The interest calculation on the variable side of a swap takes place every 6 months, whereas interest is only calculated for the fixed side once per year. If the actual payment of interest is orientated on the calculation periods, this would result in greater fulfillment risk for the payer of the variable interest rates. For this reason, the variable interest is also paid annually, and the accrued interest is capitalized.

Interest fixing 6-M-Euribor:

- 01.01.2001: 4,5%

01.07.2001: 5%

- 01.01.2002: 3,5%


01.07. 2002: 4,5%

Cash flow for the variable side (interest calculation method = 360/360. Assumption: 6 months = 180 days)

- 01.07.2001: Interest capitalization: EUR 2,500,000 (= 100m * 0.05 * 180/360)

- 01.01.2002: Interest capitalization: EUR 2,818,750 (= 102,500,000 * 0.055 * 180/360)

- 01.01.2002: Capitalized interest payment: EUR 5,318,750

01.07.2002: Interest capitalization: EUR 2,000,000 (= 100m * 0.04 * 180/360)

- 01.01.2003: Interest capitalization: EUR 2,550,000 (= 102m * 0.05 * 180/360)


- 01.01.2003: Capitalized interest payment: EUR 4,550,000

**Price Index Adjustment Condition**

Prerequisites

You activate Parallel (Interest) Conditions to use Price Index Adjustment Condition.

Interpolation takes place when the key date, for example due date of a flow, falls within the calculation period. There are following options:

linear

exponential

without interpolation

Calculation date field represents end of first price index calculation period. For the date within the calculation period, the price index factor is determined using the price index values on the low and high fixing dates. For the next calculation period, the fixing dates are determined accordingly. For example, for the next monthly period the fixing dates are shifted by one month.

**Tip:**

Usually, price index calculation date corresponds to the end of interest period and has monthly frequency.

You define how system reads price index values for fixing date high and fixing date low in order to enter shift from previous months against the calculation date. Maintain price index values in the Enter Price Index Values app.

**Example:**

[figure TRM06-F028 - Valid From: November 15th]

Valid From: November 15th

Calculation Date: December 12th

Fixing Date Low: October 1st

Fixing Date High: November 1st

Inflation in October is used for calculation period till December 15.

In case the index key date falls between two index calculation dates, the system calculates the price index factor based on the value of interpolation.

Rounding

You can define rounding during price index factor calculation. The following formulas show how the rounding is applied:

Off/Linear

[figure TRM06-F029 - Off/Linear]

Exponential

[figure TRM06-F030 - Ik – price index for key date (after linear interpolation)]

Ik – price index for key date (after linear interpolation)

In – price index (end of period)

In-1 – price index (beginning of period)

Ib – base price index (calculated from base date or if this is not provided then base value is used)

Dk – days to key date

Dp – all days in periods

- Ra – round number of places (Index // Interest Factor field)
- Rb – round number of places (Day Fraction // Day Fraction Round field)
- Rc – round number of places (Factor // Base Factor field)
- Rd – round number of places (Accumulated Factor // Flow Factor field)


F – price index factor

###### Incoming and Outgoing Flows (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Incoming and Outgoing Flows | L7 | trm06 p.52 | loio `9315da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9315da531198434de10000000a174cb4.html?locale=en-US)

Use

You can display the cash flow for a swap either separately for incoming and outgoing interest payments or for both directions together. To do this, choose the Incoming or Outgoing tab pages.

###### Interest Rate Adjustment Data (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Interest Rate Adjustment Data | L7 | trm06 p.52 | loio `9015da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9015da531198434de10000000a174cb4.html?locale=en-US)

**Use**

For financial transactions with variable interest rate conditions, the Interest Rate Adjustments tab is available.

On this tab, you find all data that is relevant for interest rate adjustments and that is used to fill the cash flow. The data is grouped according to due date, adjustment date, reference interest rate, interest rate, and the date of the rate fixing.

**Features**

You can enter interest rate adjustments manually or have them made automatically. For more information, see Interest Rate Adjustments in Back-Office Processing.

For swaps with variable interest calculation, interest rate adjustments are made periodically throughout the term. This tab shows you the current values.

If a cap is in the money, this amount is displayed here as a single amount or together with the previous payment flows. If you have opted for automatic interest rate adjustment, the system proceeds with this method for each interest rate adjustment until the transaction expires. If a cap is out of the money, no payments are made on either side.

**Activities**

- 1. The tab contains the list Interest Rate Adjustments: Overview, which is divided up according to the interest fixing date, weekday, reference interest rate, status, interest rate, and the expiration date. Interest rate adjustments can have the following statuses

Fixed

Not Fixed

In Processing

- 2. By double-clicking Create in the line that you require, you can edit the corresponding Interest Rate Adjustment: Detail View in the lower area of the screen.
- 3. You can display, change, and cancel interest rate adjustments.


Change = Change the rate of interest

Display

Cancel = Cancel the Fixed status. Cancellation is performed chronologically from the present into the past (step-by-step).

###### Price Index Adjustment

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Price Index Adjustment | L7 | trm06 p.53 | loio `dbbb7fbf315f494a8d02de86a84bf392` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dbbb7fbf315f494a8d02de86a84bf392.html?locale=en-US)

When you create financial transactions for product types related to price indexes, the Price Index Adj. tab is available.

Here you obtain an overview of all the data relevant for price index adjustments.

**Note:**

You use the Run Automatic Adjustments - Rates/Prices app to execute the price index adjustments at the fixing dates.

For interest rate transactions of product types related to price indexes, price index adjustments are made periodically throughout the term. This tab shows you the current values.

Price Index Adjustment: Overview

This tab contains the Price Index Adjustments: Overview table, which is divided according to the fixing date, weekday, fixing reference ID, status, and index value.

The following statuses for an index adjustment are possible:

Fixed

Not Fixed

In Processing

By double-clicking the line that you require, you can edit the corresponding Price Index Adjustment: Detail View in the lower area of the screen.

**Related Information**

Process Automatic Adjustments - Rates/Prices Price Index Adjustment Condition

###### Environment

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Environment | L7 | trm06 p.55 | loio `7707da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7707da531198434de10000000a174cb4.html?locale=en-US)

**Use**

In the upper application toolbar, under Environment, you will find the following functions:

**Structure**

Worklist

Object Links (links to the respective transaction)

Change Documents for the Transaction

Regulatory Reporting (in money market trading)

Position indicator (for options market transactions). This takes you to the Futures Account Generic Position.

###### Object Links

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Environment > Object Links | L8 | trm06 p.55 | loio `3f14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3f14da531198434de10000000a174cb4.html?locale=en-US)

**Use**

To document the fact that certain transactions or objects belong together, you can define links in the administrative data of a transaction. To do this, you use fields in which you assign your own reference terms or numbers, which you can use for later evaluations. Relationships between transactions, which result from processing activities such as rollovers or netting transactions, or parts of a transaction such as the spot and forward transaction of a currency swap, are automatically linked by the system.

In the transaction data screen, you can display the links for this transaction by choosing Environment Object Links . An overview appears with a reference number, reference name, reference status, and business partner.

**Key Features**

**Example:**

Examples of reference/object links:

Spot/Forward Transaction: Rollover/Premature Settlement

When you use the rollover or premature settlement functions, the system generates two single transactions that are linked by a reference/swap unit. One transaction offsets the forward exchange transaction originally entered (possibly with identical, opposite conditions to avoid rate gains/losses). The other transaction, a new one, allows the term to be adjusted using the amount data as default values. The two new transactions are linked to the original transaction.

The relationship of a swap to the original forward transaction is automatically documented by the assignment of the individual transactions to a common finance project with an identical project number. This project number is in the administrative data. This enables you to display this referencing between related transactions in the transaction data. The moment you want to change part of a swap the system displays a warning message to show that there is a second swap component.

With the outlined change in the transaction data, you can break down a forward exchange transaction into subsequent transactions using premature settlement or rollover. As a result, you can prematurely settle one part of the transaction and roll over the other part of the amount using two subsequent transactions with different value dates. Using the liquidity

effect, you can generate revenues and expenses for rollovers on the basis of the old rate and include them as a markup in the rollover transaction. The swap components are also grouped into pairs here by means of a reference.

Spot/Forward Transaction: Forex Swap

For more information, see FX Swap.

Standard Options: Option Spread

The option spread allows you to enter two currency options (including currency barrier options) at the same time. You can then copy the structure characteristics of the first option to the second option as a default value. This second option can have a different product and transaction type from the first option.

With the option spread, these two options are linked by a reference (unit) of the category OPT (reference option for derivatives).

You can also use the option spread function to create combinations of puts and calls (straddle or strangle; option spread) with identical or differing strikes in parallel.

If you conclude transactions in the local currency, you only need to enter data on the Underlying tab page since, in this case, the Currency Pair field is filled automatically with the local currency.

Back Office: Netting

For more information, see Netting.

Mirror Transactions

This function is available in the Money Market and Foreign Exchange areas for fixed-term deposits, deposits at notice and for spot exchange transactions and forward exchange transactions. The transactions that are mirrored are linked to each other and also reference each other (reference MIR).

For more information, see Mirror Transactions.

**Procedure**

Spot/Forward Transaction: Rollover/Premature Settlement

- 1. Choose Rollover or Premature Settlement.
- 2. The same screen that you use for the fast entry of swaps appears, but you can only enter data on the left-hand side of the screen (first transaction).
- 3. The following fields in this area automatically contain values: Currency ID, amounts, and forward rate of the transaction to be rolled over (prematurely settled). This forward rate is the spot basis for the rollover (premature settlement) and for the value date to be changed.
- 4. The second side (second transaction) shows you the details of the forward transaction to be rolled over, but with offsetting payment flows in the opposite direction.
- 5. To make the new entry, you only need to enter the swap rate and the changed value date.
- 6. You can enter the liquidity costs of a rollover for the changed spot rate separately in the Liquidity field and use them for your own evaluation reports at transaction level.

Standard Options: Option Spread

- 7. Choose Option Spread.


- 8. Enter the data for the first transaction in the Option 1 area.
- 9. Choose the Option Spread pushbutton at the top of the screen. The data is copied to Option 2.
- 10. The transaction type and the strike have to be adjusted.
- 11. You can use the Copy function for similar options.

###### Extras

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Financial Transaction > Tabs > Extras | L7 | trm06 p.57 | loio `7407da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7407da531198434de10000000a174cb4.html?locale=en-US)

**Use**

In the upper application toolbar, under Extras, you will find the following functions:

**Structure**

Effective Interest: You can use this function when processing transactions in the Money Market area to calculate the effective interest rate and update the database.

Amount Overview: with entries for the total capital amount in position currency and the interest amount.

Calendar

Option Price Calculator

Cross Rates: In the Foreign Exchange area, you can use the Cross Rate Calculator additional function to translate currencies.

Net Present Value Calculation

User Data

User Info

User Status

###### Process Financial Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Process Financial Transaction | L5 | trm06 p.57 | loio `1519c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1519c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to process a financial transaction. It is a central entry point for processing your financial transactions. However, you can call each processing function for a financial transaction from the initial screen.

**Features**

- 1. Open the Process Financial Transactions app on SAP Fiori launchpad, or choose in the area menu in the back-end system Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Trading


/ Back Office Process Financial Transaction .

- 2. Enter the company code.
- 3. Select the transaction. You can make this selection using the search help. On the different tabs in the search help, you can use a broad range of criteria to search for your financial transactions.


The following trading and back office functions are available for your financial transactions:

**Note:**

You can use the dropdown list in the Preselection for Group of Financial Instruments box to preselect the relevant activities available for further processing of a financial transaction.

|Function|Entries|Comment|
|---|---|---|
|Change|Choose Change. Make your changes and save your entries.|You can change the data on the tabs. |
|Display|Choose Display.|You can also display the master data for the business partner.|
|Settle|Choose Settle. The Contract Settlement screen appears. Choose the area for which you want to enter or change settlement data. Save your entries.|Use the Settle Financial Transactions function to indicate a transaction that was processed in the back-office area. When you save your entries, the system changes the activity category of the transaction. Use the Settlement Check function to check and, if required, add data for the financial transaction. When you save a transaction, you fix it and mark the transaction flows for posting. You can clear the account after settlement. See also: Settlement |
|Reverse|See also Reversal. | |
|Give Notice|Choose Give Notice. Make your changes and save your entries.|When you give notice on a financial transaction, the transaction remains active and changes to the Termination activity category. When you value this transaction again, any unrealized gains and losses that have already been posted are disregarded. By giving notice, you are settling the OTC option. Outstanding (fixed or variable) interest payments of swaps and cap/floors are carried out up to the notice date. Interest rate adjustment dates that fall before the notice date but after the contract conclusion date do not change. The final payment due upon maturity is not made. You have to return the nominal amounts manually. You can only give notice on FRAs before the interest rate adjustment date. In this case, giving notice terminates the contract within the lead period (unscheduled termination), and results in a settlement payment. |


|Function|Entries|Comment|
|---|---|---|
| | |You can enter a settlement payment on the Other Flows tab when you give notice.|
|Roll Over|Choose Roll Over. If the rollover is linked to a change in the amount invested or borrowed, enter the amount and the flow type. This indicates whether an increased or decreased amount is involved. You use the For Rollover field to specify the type of interest flows that are due on the rollover date. The interest can be paid, capitalized, or deferred on the rollover date.|You can also roll over a financial transaction with changed conditions and use the same transaction number. You can display the current business transaction along with its history and detailed information. With the memo book function, you can enter additional information for each activity. By choosing Extras Amount Overview  , you view a list of all transaction-related capital and interest flows sorted according to amounts that are due prior to/on the respective key date. When you roll over the transaction, you add a new activity to the transaction. The activity is processed in accordance with the determined transaction and position management process. You can change the end of term in the fastprocessing function. You can change the end of term of a financial transaction until repayment. You have to make sure, however, that interest flows that have already been released, posted, or manually changed are not affected by shortening the term. You can make no further changes to the lent number of units or the nominal amount.|
|History|Choose History. The system lists the activities that are active, reversed, or have been replaced by a follow-up activity. Information on the transaction status and processor is also displayed.|The history function lists all previous activities for the selected transaction.|
|Expiration|Choose Expiration.|A security option is deleted if it has no value. You use this function to settle the expiration at a later stage in the back-office area.|
|Exercise|Choose Exercise. When you save the option, it is stored under the relevant activity category.|You can only exercise an OTC option when it has reached the Knock-In or Knock-Out activity category. In the case of a knock-in option, the transaction must first run through the knock-in process. In the case of cash settlement, the system uses the clearing amount when the option|


|Function|Entries|Comment|
|---|---|---|
| | |is exercised. This is based on the difference between the strike and market price. When the option is exercised physically, the system generates the spot transaction from the underlying transaction (option). To transfer unrealized gains and losses that have already been posted, you have to restart the Determine Realized Gains/Losses program.|
|Choose Execute.|Choose Execute. Choose Save.|The function for executing a financial transaction changes a security transaction from the Order activity category into the Contract activity category. You can add to and change the order data to reflect the actual transaction data. If you have assigned processing category 00001 to the transaction type, you can no longer change the data once you have saved the transaction. The transaction is assigned the status Flagged for Posting.|
|Knock-In|Choose Knock-In. Enter the company code and the barrier transaction number. Save your entries. The transaction has the Knock-In activity category.|If a barrier option has reached the agreed limit, you have to set the Knocked-In status (see Barrier Option). Using the knock-in activity, you can activate the option for Exercise or Expiration. Depending on the processing category, settlement can be a prerequisite for knockin. You can check the instrikes and outstrikes of currency barrier options using the Expiration/Barrier Check function (see Collective Processing: Financial Transaction). After comparing the transaction data with the relevant prices, the system proposes a transaction (knockin, knock-out, or expiration) for further processing.|
|Knock-Out|Choose Knock-Out. Enter the company code and the barrier transaction number. Save your entries. The transaction has the Knock-Out activity category.|If a barrier option has reached the agreed limit, you have to set the Knocked-Out status. After the knock-out activity has been performed, the option is activated for Expiration.|
|Premature Settlement| |When you use the Premature Settlement function, the system generates two single transactions that are linked by a reference (swap unit): One transaction offsets the forward exchange transaction initially entered (possibly with identical, opposite|


|Function|Entries|Comment|
|---|---|---|
| | |conditions to avoid rate gains/losses). You can adjust the term with the other transaction, using existing amount data as default values. The new transactions are linked to the original transaction. You can break down a forward exchange transaction into subsequent transactions using premature settlement and/or rollover. As a result, you can prematurely settle one part of the transaction and roll over the other part of the amount using two subsequent transactions with different value dates. Using the liquidity effect, you can generate revenues and expenses for rollovers on the basis of the old rate and include them as a markup in the rollover transaction. The swap components are also grouped into pairs here by means of a reference.|


**Related Information**

Processing Spot/Forward Transactions Processing a Non-Deliverable Forward Processing an FX Option Processing Fixed-Term Deposits Processing Deposits at Notice Create Commercial Paper Processing Interest Rate Instruments Processing Current Account-Style Instruments Processing Facilities Creating and Editing Forward Loan Purchases Processing Listed Options and Futures Editing a Security Transaction Processing Letters of Credit as an Exporter Processing Letters of Credit as an Importer Processing Bank Guarantees as an Exporter Processing Bank Guarantees as an Importer Processing Standby Letters of Credit as an Exporter Processing Standby Letters of Credit as an Importer

###### Settlement

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Process Financial Transaction > Settlement | L6 | trm06 p.61 | loio `3ddbd7531a4d414de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3ddbd7531a4d414de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to settle financial transactions in the “Contract” activity. The flows for the purchase/sale of transactions with status Planned acquire the status Actual.

You can call up information about transactions entered, make subsequent changes to them, or add missing information, such as payment instructions or posting details.

**Prerequisites**

In Customizing, you can use the processing category to control whether the financial transaction is settled or checked. If, in the Customizing activity "Define Transaction Types”, you have defined a processing category that contains settlement activities, a transaction must be created by a trader in the front end and settled/checked by another processing officer in the back office.


Example: Use processing category 00002 for the product category “Fixed-Term Deposit”.

###### Reversal

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Process Financial Transaction > Reversal | L6 | trm06 p.62 | loio `e907da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e907da531198434de10000000a174cb4.html?locale=en-US)

**Use**

When you reverse a transaction, you reset the most recent change made to the transaction, which is identified by the system as an activity.

If postings are linked to the reversed activity, these are flagged for reversal.

The reversal function reverses the last active activity and reactivates the previous activity.

When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and which you must settle again (in the back office).

Documents, which cannot be reversed automatically (for example, if they have been cleared in FI), must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to release the flows before you post or reverse them.

**Activities**

- 1. Choose Reverse.
- 2. The Reverse Financial Transaction: Management screen appears.
- 3. To reverse a transaction you have to enter a reversal reason in the corresponding field. Enter the key for the reversal in the Reversal Reason field. This key represents the reason for the reverse posting. You define the permitted reversal reasons in Customizing. For more information, see the Implementation Guide (IMG) under Define Reversal Reasons.


**Integration**

The graphics below provide an overview of the Reversal function, using Reverse Contract: Fixed-Term Deposit as an example.

[figure TRM06-F034]

[figure TRM06-F035 - If it is just a question of incorrect condition data, or other data, you can change this directly without having to reverse the activity.]

If it is just a question of incorrect condition data, or other data, you can change this directly without having to reverse the activity.

###### Collective Processing: Transaction Management

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Collective Processing: Transaction Management | L5 | trm06 p.63 | loio `2419c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2419c55368511d4be10000000a174cb4.html?locale=en-US)

Transaction Code: FTR_00

**Use**

Collective processing enables you to manage your own financial transactions in the Transaction Manager. Besides functions that allow you to select and display transactions, you can also go to the individual screens for processing the transactions.

**Feature Comparison Documentation**

For a comparison of the features offered by this app and other apps in the area of treasury and risk management, see also Feature Comparison for Collective Processing Apps for Financial Transactions.

**Features**

Transaction management includes entering and processing financial transactions for the following product categories:

Fixed-term deposits and deposits at notice

Commercial Paper

Cash flow transactions

Interest rate instruments

Facilities

Spot exchange and forward exchange transactions

Interest rate derivatives

OTC options and listed options

Futures

Security transactions

Letters of Credit

**Activities**

Start of collective processing

Choose Trading Collective Processing Transaction Management or Back Office Collective Processing

Transaction Management . The screen for collective processing appears, which is divided into two areas. The area to the left of the screen shows the selection variants in a tree view, which you can configure yourself, whereas the area to the right of the screen displays the last selection of transactions the user made.

Selecting transactions

Collective processing enables you to generate a list of transactions according to selection criteria that you define. To enter selection criteria on an entry screen:

- 1. Choose Worklist New .


- 2. The initial screen for collective processing appears. Here, you enter the selection criteria according to which you want to create the list of business transactions (for example, general selections, position assignment, additional fields, entered on/last changed).
- 3. Choose Execute (the execute button is in the lower part of the entry screen).
- 4. The system displays a list of the selected transactions.


You can also store any number of selections as variants and manage them in collective processing in a tree view for specific users or for all users. You can access all the management functions for variants via a context menu in the tree view.

To add a variant that has already been defined to the tree view:

- 1. To open the context menu, right-click with the mouse on the node in the tree, below which you want the variant to appear.
- 2. Then choose Insert Variant .
- 3. Enter the name of the variant you want to add and confirm your entry with ENTER.
- 4. The variant now appears as a separate node below the tree node you selected. By double-clicking this node, you can execute the assigned selection for the variant.


Visualizing transactions

The list of transactions provides extensive options for structuring the list rows and columns, and for sorting and displaying totals.

Processing transactions

You also have the option of processing the transactions from the collective processing list.

- 1. Position your cursor on the transaction you want to process.
- 2. Open the context menu using the right mouse button. You can select one of the functions from the menu with which you can process the selected transaction. Alternatively, you can go these functions using the buttons above the list display.
- 3. When you select a function, the corresponding processing mode appears, from which you can carry out the necessary steps.

###### Create FX Spot/Forward

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create FX Spot/Forward | L5 | trm06 p.65 | loio `0614da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0614da531198434de10000000a174cb4.html?locale=en-US)

**Use**

With spot transactions, traded currencies are bought and sold for other currencies at the spot rate. Forward transactions are traded on a certain date in the future with the relevant premiums and discounts for calculating the forward rate being specified.

**Procedure**

- 1. Call the function Create Financial Transaction (transaction FTR_CREATE).
- 2. Enter the Company Code, Product Type, Transaction Type, and the Business Partner.
- 3. If you want to assign the transaction to a portfolio, enter a portfolio in the Limits area. Alternatively, you can enter a portfolio on the Administration tab in the Position Assignment area.
- 4. For the activity, choose whether you want to create the transaction as a Contract or as an Order/Fixing (depending on the processing category).
- 5. If you work with external number assignment, you have to enter a key for the transaction in the corresponding field, which enables it to be uniquely identified within a company code. Otherwise, the system assigns a number automatically and displays this number when you save the transaction.
- 6. Choose Enter to branch to the basic data screen for the transaction. On the Structure tab, enter the actual transaction data for the swap, forward, or fixing transaction.

- 7. Enter the required structure data:


Currency pair/Exchange rate

Buy/Sell indicator

Traded currency

Traded amount

**Note:**

The amount field (data element TM_XBETRAG) is an input field for amounts using abbreviated forms. You can abbreviate the amount by using default values for one thousand (default 'T'), one million (default 'M'), and now also for one billion (default 'B') when entering data. The abbreviations are converted into the corresponding amount after data release.

**Examples**

|Abbreviation|Corresponding Amount|
|---|---|
|1.25M|1,250,000.00|
|1T|1,000.00|
|1T,50|1,000.50|
|1B|1,000,000,000.00|


In the Define User Data Customizing activity, you can define your own special characters or other alphabetic values as an abbreviation for thousands, millions, or billions.

Value date

The offsetting amount is calculated by the system You can change the amount calculated (within certain limits).

- 8. Contract Conclusion

In this area, you can enter overall, administrative information relevant to the financial instrument:

Contract date and time

Contact person

Market identifier code (MIC)

Market identifier codes (MICs) are four-character international standard codes (ISO 10383). MICs are used to identify exchanges, trading platforms, and regulated or non-regulated markets as sources of prices and related information to facilitate automated processing (exchanges, settlement, and other automated processes).

For more information, see Market Identifier Code.

Trader

External reference

- 9. In the case of forward transactions, you enter the forward rate in the Rate field adjacent to the relevant currency pair. The system calculates the offsetting amount from the rate and the traded amount. You can change the amount calculated (within certain limits).
- 10. When creating a foreign exchange fixing transaction, the transaction data for the contract conclusion is defined on the entry as described above, however, you do not enter an exchange rate. You can enter the fixing date manually or have the


**Note:**

You create and activate MICs in Customizing under Market Data Management Master Data Specify Market Identifier Codes .

system fill it automatically with the "Value date minus 2 bank working days". The rate fixing then takes place later in the back office. This can be done manually or automatically. For more information, see also Rate Fixing.

- 11. You can also branch to the entry screens for the general transaction management functions. You can use the tab pages to navigate between the different screens.

For more information, see Tabs.

In the upper menu bar, you can access other functions by choosing Extras and Environment.

For information about creating a mirror transaction, see Intercompany Trading Process.

- 12. Save the FX transaction you have created.


**Note:**

If you use the financial transaction as hedging instrument within the Hedge Management and Accounting of Exposure Items process, you must enter the hedging classification and hedge request on Administration tab and if the hedged exposure item is reference based, you must assign the exposure item ID on FX Hedge Management tab. See also: Create Hedging Instruments

See also:

Spot / Forward Transactions

Processing Spot / Forward Transactions.

###### Create FX Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create FX Swap | L5 | trm06 p.67 | loio `de14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/de14da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

When you create a foreign exchange swap, the system creates a spot transaction and a forward transaction at the same time. The foreign currency bought at the spot rate is sold again at the forward rate. The foreign currency sold at the spot rate is bought back again at the forward rate.

You enter a forex swap via the combined entry of a spot exchange transaction and a forward exchange transaction (transaction TX10).

**Use**

Rate and Swap Proposal

The forward rate is automatically determined by an incoming premium or discount. The conditions for the authorized business partner, like the payment details, correspond to those for spot and forward transactions. If you have a realtime datafeed link, you can also use the rate and swap proposals to simulate transactions, and compare them to the rates agreed. You can use copy functions to speed up entry. These functions allow you to copy identical data from the first transaction (spot/forward) into the corresponding field of the second transaction (forward/spot).

Premature Settlement and Rollover

When you roll over a forex swap, this prolongs the forward transaction - the initial transaction is cleared and a forward transaction is created with a changed due date. The relevant data is transferred as a default value to the forward transaction to be generated. In the case of premature settlement, clearing the old transaction is linked to the creation of a new transaction with an earlier value date than the original end of term. The Liquidity Effect field can be used to clear any rate differences between the original transaction and the netting transaction.

Foreign currency valuation

You perform foreign currency valuations on the basis of single transactions that have been generated. With a forward exchange transaction, you can also have a split valuation with spot and swap transactions provided that you have made the required settings.

For more information, see Object Links.

**Procedure**

- 1. Choose Create Forex Swap (transaction TX10).
- 2. You make the same entries here as you do for single spot or forward transactions: Company Code, Product Type, Transaction Type, and Partner.
- 3. The screen for entering a forex swap appears. The swap entry screen saves you time by enabling you to enter two forex transactions next to each other.
- 4. Enter the following data for the first transaction:

Currencies of the currency pair

Rate

Buy/Sell indicator

Traded currency

Traded amount

Value Date

Spot Rate

- 5. Choose Enter.


**Note:**

The amount field (data element TM_XBETRAG) is an input field for amounts using abbreviated forms. You can abbreviate the amount by using default values for one thousand (default 'T'), one million (default 'M'), and now also for one billion (default 'B') when entering data. The abbreviations are converted into the corresponding amount after data release.

**Examples**

|Abbreviation|Corresponding Amount|
|---|---|
|1.25M|1,250,000.00|
|1T|1,000.00|
|1T,50|1,000.50|
|1B|1,000,000,000.00|


In the Define User Data Customizing activity, you can define your own special characters or other alphabetic values as an abbreviation for thousands, millions, or billions.

The following data for the second transaction are filled automatically:

Traded currency

Traded amount

Buy/Sell indicator

Spot Rate

Enter the remaining data for the forward transaction as the Rate and the Value Date.

**Note:**

Since the screen for entering a currency swap is a form of input help, you are not allowed to enter payment details here. You enter these in the individual transactions.

- 6. Enter data to all other fields relevant for the financial transaction. The following fields are available:

External Ref.

Finance Project

Assignment

Internal Ref.

Characteristics

Gen. Valn Class

Hdg Class.

HReq.ID

Profit Center

Cost Center

WBS Element

Business Area

Country/Region

Segment

OnBehalfCC

- 7. Enter the following data that is relevant for both financial transactions:

Parent CFI Code

The Classification of Financial Instruments (CFI) code is used for trade repository reporting, such as for EMIR regulations. The parent CFI code is used to define structured or composite financial instruments, such as FX swaps.

Parent ISIN

The International Securities Identification Number (ISIN) is used, for example, for trade repository reporting, such as for EMIR regulations. The parent ISIN is used to uniquely define structured or composite financial instruments, such as FX swaps.

- 8. Contract Conclusion


In this area, you can enter overall, administrative information relevant to the financial instrument:

Contract date and time

Contact person

Market identifier code (MIC)

Market identifier codes (MICs) are four-character international standard codes (ISO 10383). MICs are used to identify exchanges, trading platforms, and regulated or non-regulated markets as sources of prices and related information to facilitate automated processing (exchanges, settlement, and other automated processes).

**Note:**

You create and activate MICs in Customizing under Market Data Management Master Data Specify Market Identifier Codes .

For more information, see Market Identifier Code.

Trader

External reference

- 9. Save your entries.


**More Information**

You can also map a forex swap as a mirror transaction.

Four transactions are created when a forex swap is mirrored. A spot transaction and a forward transaction are created in each of the two company codes involved. The reference category SWP (forex swap) also appears in this context. The spot transaction and forward transaction in one company code are linked by the SWP reference.

You do not need to make any special Customizing settings to mirror forex swaps. You need to change Customizing settings for other transactions in foreign exchange trading.

For more information on creating mirror transactions, see Intercompany Trading Process.

###### Create OTC Option

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create OTC Option | L5 | trm06 p.70 | loio `0314da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0314da531198434de10000000a174cb4.html?locale=en-US)

App ID: TI71

With this app, you can create OTC currency options and swaptions. The following product types are predefined:

The FX option is an option on a spot exchange transaction and is used as protection from currency fluctuations. The purchaser of a standard FX option, also known as an OTC (over the counter) option, has the right to buy a fixed amount of currency on the exercise date at a previously agreed rate. The option purchaser pays a premium for this right. The amount of the premium paid varies depending on supply and demand in the foreign exchange market. FX options are asymmetrical hedging instruments - this means that rights and obligations are unevenly distributed between the buyers and sellers. Unlike listed instruments, these options are traded directly between business partners with user-defined structure characteristics. The main difference with forward exchange transactions is that the buyer of an option has the right but not the obligation to buy or sell a certain currency amount.

76A - OTC Currency Option

A swaption is an option on a interest rate swap, which you can exercise on a certain date or within a certain period (product category 760 OTC Options using product category 620 Swap as underlying). As the buyer, you can choose whether to pay fixed interest rates or whether to receive fixed interest rates after the option has been exercised. You pay a premium to the seller for this right upon conclusion of the transaction.

**Note:**

For the creation of financial transactions you can also use the Manage Financial Transactions app or the Create Financial Transaction app.

**Procedure**

- 1. Open the Create OTC Option app on SAP Fiori launchpad.
- 2. Enter the company code, product type, transaction type (100 (Buy) or 200 (Sell), and the business partner. When you create a currency option, you are documenting the intention to buy or sell a currency option.
- 3. If you want to assign the transaction to a portfolio, enter a portfolio in the Limits area. Alternatively, you can enter a portfolio on the Administration tab in the Position Assignment area.
- 4. In the Activity area, choose whether you want to create the transaction as a contract or as an order.
- 5. Choose Enter to go to the basic data screen for the option.
- 6. On the Structure tab, you enter the actual transaction data.

- a. Enter the general data of the option in the Option section, such as Expiry Date, Expiry Time, Exercise Type and Settlement.
- b. In the following, you enter the data for the underlying transaction of the option. For more information, see also:


Creating a Swaption

Creating an FX Option

- 7. In the Premium area, choose the flow type of the premium. Then enter the payment date, the curency and the amount of the premium.
- 8. You can change additional data on the different tabs.

For more information, see Tabs.

- 9. To store the transaction, choose Save.


**Note:**

The Expiry Time field is available for input only if you have assigned predefined location codes to specific times using the Define Values for Expiry Time app.

Comments

When you conclude a transaction, the cash flow consists only of the premium. You can create both European and American types of option in the system (settlement).

**Supported Device Types**

Desktop

Tablet

**Related Information**

**Process OTC Options - Collective Processing**

###### Create Collar FX Option (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Collar FX Option | L5 | trm06 p.72 | loio `496eb6ad79224d93ba11c113b1055b20` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/496eb6ad79224d93ba11c113b1055b20.html?locale=en-US)

With this app, you can create collar FX options by creating two FX options and linking them to each other. A collar FX option involves the purchase of a call option and the sale of a put option, or vice versa.

**Key Features**

This app provides the following key features:

Creation of collar FX options

Possibility to edit the two FX options forming the FX collar by choosing More OTC Option and selecting one of the following activities:

Change

Display

Exercise

Expiration

Terminate

Settle

Reverse

Displaying business partner details by choosing Display Partner

**Procedure**

- 1. Launch the Create Collar FX Option app from your SAP Fiori Launchpad.
- 2. Enter the company code, business partner, product type (76A), and the transaction type (100 Buy or 200 Sell) for both FX transactions.
- 3. If you want to, you can assign the transactions to a portfolio on the initial screen of the app.
- 4. In the Activity area, choose whether you want to create the transaction as a contract or as an order.
- 5. Choose Enter to jump to the next screen.
- 6. On the next screen, you enter the actual transaction data for the call and the put option that make up the collar FX option.
- 7. Select the Exercise Type (European or American) and the settlement (1 Physical Exercise, 2 Cash Settlement, or * Not Yet Specified) for the first transaction.
- 8. Enter the Expiry Date and Expiry Time for the first transaction.


**Note:**

The system automatically takes over the entries made for the first transaction to the second transaction.

**Note:**

The Expiry Time field is only available for input if you have maintained location codes in Customizing under Treasury and Risk Management Transaction Manager Correspondence General Settings Define Location Codes and have assigned them to specific times using the Define Values for Expiry Time function.

- 9. Enter the currency pair and the strike for the first and the second transaction.
- 10. Specify whether the first transaction is a put or a call.
- 11. Enter the traded currency and the traded amount.
- 12. Enter the value date.

This is the payment date when the transaction is exercised (generally, two working days after the exercise date).

- 13. You can define the current spot rate as a spot reference in the Option area.
- 14. Specify the following for the option premium:

Select the premium notation (Points or Percentage).

Enter the percentage or points.

Select the desired flow type for both transactions.

Enter the premium amount for both transactions.

Select the payment date for the premium.

Choose the currency in which the premium is to be paid. If this currency is one of the currencies in the currency pair for the transaction, the system calculates the amount automatically when you enter the percentage or points.

- 15. Enter the following data that is relevant for both financial transactions:

Parent CFI Code

The Classification of Financial Instruments (CFI) code is used for trade repository reporting, such as for EMIR regulations. The parent CFI code is used to define structured or composite financial instruments, such as FX swaps.

Parent ISIN

The International Securities Identification Number (ISIN) is used, for example, for trade repository reporting, such as for EMIR regulations. The parent ISIN is used to uniquely define structured or composite financial instruments, such as FX swaps.

- 16. Contract Conclusion


**Note:**

The system automatically sets the opposite value for the second (offsetting) transaction.

**Note:**

The offsetting amount is calculated by the system.

In this area, you can enter overall, administrative information relevant to the financial instrument:

Contract date and time

Contact person

Market identifier code (MIC)

Market identifier codes (MICs) are four-character international standard codes (ISO 10383). MICs are used to identify exchanges, trading platforms, and regulated or non-regulated markets as sources of prices and related information to facilitate automated processing (exchanges, settlement, and other automated processes).

**Note:**

You create and activate MICs in Customizing under Market Data Management Master Data Specify Market Identifier Codes .

For more information, see Market Identifier Code.

Trader

External reference

- 17. Save your entries.


**Supported Device Types**

Desktop

Tablet

**Related Information**

Creating an FX Option

###### Create IR Instrument

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Instrument | L5 | trm06 p.74 | loio `5407da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5407da531198434de10000000a174cb4.html?locale=en-US)

App ID: TM_51

With this app, you can create interest rate instruments.

**Prerequisites**

For variable interest conditions, you need to have defined the relevant reference interest rates in the Define Reference Interest Rates configuration activity in your configuration environment. Further, the current values of the reference interest rates must be entered regularly in the market data table.

For financial transactions of price-index-related product types, you need to have defined the relevant price indexes in the Define Price Index configuration activity in your configuration environment. Furthermore, the current values of the price indexes need to be entered into the market data table on a regular basis.

For more information, see also:

Editing Reference Interest Rates Manually

Enter Price Index Values

**Procedure**

- 1. Open the Create IR Instrument app on SAP Fiori launchpad.
- 2. Enter the company code, product type, transaction type, and the business partner.


**Note:**

For the creation of financial transactions you can also use the Manage Financial Transactions app or the Create Financial Transaction app.

- 3. Optionally, you can make entries in the Limits area:

Currency: If you do not specify a currency when you create a financial transaction, the company code currency is applied automatically.

Portfolio: If you want to assign the transaction to a portfolio, enter a portfolio in the corresponding field.

Alternatively, you can enter the portfolio and the master agreement on the Administration tab in the Position Assignment area.

- 4. Choose Create to branch to the basic data screen for the interest rate instruments.
- 5. Enter the required data for creating the interest rate instrument on the Structure tab.


- a. In the Invest area, enter the flow type (automatically derived from the transaction type, such as 1100 Principal Increase for transaction type 100 Investment) and the (payment) amount in a specific currency.

If the nominal amount and the payment amount are not the same, you can enter either the nominal amount or the payment rate (%) and then the system calculates the nominal amount.

In the Rounding field, specify how amounts are rounded during cash flow calculation. You can choose between rounding up, rounding down, or arithmetic rounding.

- b. In the Term area, you enter the start date for the interest rate instrument.


**Note:**

The amount field (data element TM_XBETRAG) is an input field for amounts using abbreviated forms. You can abbreviate the amount by using default values for one thousand (default 'T'), one million (default 'M'), and now also for one billion (default 'B') when entering data. The abbreviations are converted into the corresponding amount after data release.

**Examples**

|Abbreviation|Corresponding Amount|
|---|---|
|1.25M|1,250,000.00|
|1T|1,000.00|
|1T,50|1,000.50|
|1B|1,000,000,000.00|


In the Define User Data Customizing activity, you can define your own special characters or other alphabetic values as an abbreviation for thousands, millions, or billions.

**Note:**

For price-index-related product types, the initial investment has a payment amount equal to the index-clean amount. This corresponds to a price index factor of 1. Further nominal changes can be recorded with both the payment amount and the index-clean amount.

The Term Category field is predefined for the different product types. For example, product types 51A, 55A, and 55I have the term category Fixed-Term. For these interest rate instruments, you can enter the end date of the financial transaction.

For product type 52B Deposit at Notice (Variable), the term category is set to At Notice and you cannot enter an end date for the financial transaction. Therefore, the Repayment area is not available on the Structure tab either.

Set the Inclusive indicator to define whether the entered start and end date are included in the term of the financial transaction.

- c. For the price-index-related product types 55P and 55Q, the Index Adjustment area is available. Here you choose the relevant price index, define the dates for the price index adjustment, and also determinehow the price index factor is calculated and applied to the flows.


Choose the price index in the Index Name field.

Base Date

The financial transaction must be updated regularly with the price index starting from the base date. Prorata calculation is performed if the issue date or payment date differ from the base date. The value of the price index on this date is taken as the basis for calculating the proportion.

Recommendation:

**Tip:**

Enter the term start date as the base date.

Index Interpolation (IdxInterpolate)

The index interpolation method defines how interpolation is executed. Interpolation is used in cases when the index key date falls between two index fixing dates. Possible values:

(space) Without Interpolation

The last price index value corresponding to the price index fixing low date is used.

LIN Linear Interpolation

EXP Exponential Interpolation

Price Index Application (PriceIdxApply)

The price index application method determines at which stage of (interest or repayment) amount calculation the price index factor is applied. With the standard interest formula "base amount * percentage rate * day fraction", the price index factor multiplies either the base amount (Price Index Applied on Base Amount) or the final index-clean amount, result of the formula above (Price Index Applied on Index-Clean Amount). The application method is relevant due to the various rounding stages within the amount calculation.

Reference Date for Index Adjustment (IdxRelDate)

The reference date for the index adjustment is the date that is used as the basis for determining the index adjustment date. You can choose between the following dates:

Calculation date

Due date

Period end

Calculation Date

End of the first price index period, usually equal to the Interest Calculation Date.

Select the Inclusive indicator, if needed. In the case of interpolation, the inclusive indicator is important for the calculation of days for interpolation. However, even if the price index value is not interpolated, the indicator is important. In this case, the indicator has the following effects:

If the indicator is selected, the calculation date receives the low price index value from the current period.

If the indicator is not selected, the calculation date receives the low price index value from the next period.

You can enter a workday shift rule.

Every

Enter the frequency for the price index adjustment by entering a number and choosing the frequency unit.

Example: 1 Months

IdxFixDateLow and IdxFixDateHigh

The index fixing date is the date of the index value used. The low index fixing date is the lower date used in the interpolation of the index factor between the two fixing dates.

Dates for reading the values of the price index in the market data table for interpolation. Basically, it is the day when the price index value is published.

Example:

For the price index IGPM and IPCA, the IdxFixDateLow is the first day of the month.

**Tip:**

If the price index value is not interpolated, it is sufficient to enter the low index fixing date. Make sure that the low index fixing date is before the calculation date.

Example: Determination of the price index value at calculation date of the flow

Assume the price index values are always entered on the first day of a month.

The interest period is the same as the price index calculation period.

Term start is 05/01/2021.

Term end is 07/01/2021.

Interest and the price index have a monthly frequency with the calculation date 06/01/2021.

Exponential interpolation is set for the price index adjustment condition.

Price index fixing date low is 04/01/2021.

Price fixing date high is 05/01/2021.

Price index base date is 05/01/2021.

The price index factor will be interpolated as follows:

For the flows within the first period between 05/01/2021 and 06/01/2021, using the price index values on

- 04/01/2021 and 05/01/2021

- For the flow with the calculation date 05/01/2021, using the value on 04/01/2021

- For the flow with the calculation date 06/01/2021, using the value on 05/01/2021


For the flows in between, using exponential interpolation. For example, for a flow with the calculation date

- 05/10/2021 with 10 days between 05/01/2021 and 05/10/2021, and 31 days for the whole interpolation


- period between 05/01/2021 and 06/01/2021.


For the flows within the next period between 06/01/2021 and 07/01/2021, using the price index values on

- 05/01/2021 and 06/01/2021.

- For the flow with the calculation date 06/01/2021, using the value on 05/01/2021.

- For the flow with the calculation date 07/01/2021, using the value on 06/01/2021.


For the flows in between, using exponential interpolation. For example, for a flow with the calculation date

- 06/20/2021 with t20 days between 06/01/2021 and 06/20/2021, and 30 days for the whole interpolation


- period between 06/01/2021 and 07/01/2021.


In this example, there are price index adjustments with the three price index fixing dates 04/01/2021, 05/01/2021, and 06/01/2021. Fixing dates are also determined for the base date of the price index.

**Note:**

After you have determined the variable interest value and the price index value for an interest flow or repayment flow, you see both the index-clean amount of the condition flow and the payment amount of the flow, which also includes the price index adjustment.

- d. In the Interest Structure area, you enter the settings for interest. Interest rate instruments allow fixed and variable forms of interest calculation to be entered and performed. Besides the option of entering the amount of interest, there is the option of entering the interest conditions Scaled (Interval) and Scaled (Incremental). See also: Scaled Conditions

Enter values in the following fields: Interest Cat., Int.Calc.Method, Percentage Rate, and Frequency.

Using the Condition button, you see the Condition Overview. Mark a condition item and choose Condition Details.

See also Condition Details: Interest (New FIMA)

- e. In the Repayment Structure area, you can choose between installment repayment and full repayment upon maturity (final repayment).


**Note:**

During the creation of the financial transaction, this area is not available for product type 52B Deposit at Notice(variable). This area is visible only when the Give Notice function is executed for the financial transactions of this product type.

In the case of final repayments, no further entries are necessary. The system automatically sets the interest period update to Final Repayment.

If you have opted for installment repayment, the structure of the screen is changed. Enter the repayment amount and the frequency. By default, the currency in the Currency field is the same as that for the interest rate instrument. In this area, you can also use the pushbutton to expand or close the repayment structure.

- 6. In the Contract Conclusion area, you enter the following data:


Close Date:

Date and time of contract close, set by the system with the system date.

Trader: Set by the system.

Contact Person:

Here you can enter the name of the contact person at the company that is the business partner of the financial transaction. If you enter a name here, you must deploy separate supplementary organizational measures to ensure that you respect the deadlines governing the storage and deletion of personal data.

External Ref.:

You can enter an external reference for the financial transaction.

Notice Period

Enter the period of notice in days or months. The period of notice is the period between the termination agreement and when it comes into effect.

- 7. To store the transaction, choose Save. Flows are generated automatically when you create a financial transaction.


More Functions

You can also branch to the entry screens for the general transaction management functions. You can use the tabs to navigate between the different screens.

For more information, see Tabs.

In the upper menu bar, you can access other functions by choosing Extras and Environment.

Effective Interest Rate

You use this function when you process transactions in the Money Market area to calculate the internal interest flows and update these to the database. You can use the effective interest for evaluations as part of reporting.

- 1. You can generate a list of financial transactions with an unknown effective interest or using specific transaction numbers.
- 2. You can also choose whether to carry out a test run or an update run.
- 3. Choose Execute.
- 4. The system generates a calculation log.


Position Indicator

Choose Environment Position Indicator to go to the class position.

Also in the upper menu bar, you can access the interest rate adjustment function by choosing Conditions. For more information, see also Condition Details: Interest (New FIMA).

**Supported Device Types**

Desktop

Tablet

###### Create Current Acct-Style Instruments

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Current Acct-Style Instruments | L5 | trm06 p.79 | loio `fad64b56d682f81ae10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fad64b56d682f81ae10000000a441470.html?locale=en-US)

App ID: FTRCAI01

**Use**

With this app, you can create a current account-style instrument.

**Prerequisites**

See Current Account-Style Instruments and Processing Current Account-Style Instruments.

**Procedure**

- 1. Open the Create CA Style Instrument app on SAP Fiori Launchpad.
- 2. Enter the Company Code, Product Type, Transaction Type, and the Partner.
- 3. You can make the following entries in the Specifications area:

Transaction Currency: If you don’t specify a currency when you create a financial transaction, the system automatically uses the currency of the company code.

Portfolio: If you want to assign the transaction to a portfolio, enter this portfolio in the corresponding field.

Alternatively, you can enter the portfolio on the Administration tab in the Position Assignment section.

- 4. If you work with External Number Assignment, you have to enter a key for the transaction in the corresponding field, which enables it to be uniquely identified within a company code. Otherwise, the system assigns a number automatically and displays this number when you save the transaction.
- 5. Choose Enter to branch to the Structure tab. Where you enter the basic data for the current acct style instrument transaction.
- 6. In the Borrowing area, enter the flow type and the amount.

In the field,Rounding Cat. you specify how amounts should be rounded for the cash flow calculation. You choose to round down, round up or round to the nearest whole number.

- 7. In the Term area, define the term of the transaction.


**Note:**

For the creation of financial transactions you can also use the Manage Financial Transactions app or the Create Financial Transaction app.

**Note:**

The amount field (data element TM_XBETRAG) is an input field for amounts using abbreviated forms. You can abbreviate the amount by using default values for one thousand (default 'T'), one million (default 'M'), and now also for one billion (default 'B') when entering data. The abbreviations are converted into the corresponding amount after data release.

**Examples**

|Abbreviation|Corresponding Amount|
|---|---|
|1.25M|1,250,000.00|
|1T|1,000.00|
|1T,50|1,000.50|
|1B|1,000,000,000.00|


In the Define User Data Customizing activity, you can define your own special characters or other alphabetic values as an abbreviation for thousands, millions, or billions.

- 8. In the Interest Structure area, you can expand the interest structure and compress the structure. This changes the structure of the screen.
- 9. For the Interest Cat. field, you can select among Fixed, Variable, Amount, Scaled (Interval) and Scale (Incremental) from the dropdown list, and perform the relevant calculations.

Choose the Detail View Int. Condition button to reach the detailed entry screen for the interest conditions. For more information, see also Condition Details: Interest (New FIMA)

- 10. In the condition overview, you can enter additional condition items according to the available condition types for the current account style instruments, such as an interest adjustment condition for variable interest conditions. If you want to reach the Condition Overview screen, choose the Condition button on top of the screen.
- 11. In the Repayment Structure area, only final repayment is available.
- 12. To save the transaction, choose Save. Flows are generated automatically when you create financial transactions.
- 13. You can also navigate to the tabs of the general transaction management. For more information, see also Tabs

###### Create Cash Flow Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Cash Flow Transactions | L5 | trm06 p.81 | loio `d207da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d207da531198434de10000000a174cb4.html?locale=en-US)

With cash flow-based transactions you can manage transactions whose structural characteristics cannot be mapped by the standard product categories. You can enter and process transactions by entering their cash flow. A cash flow is a chronological sequence of flows: you enter the term alongside the cash flow that results from the transaction structure. This enables you to map your financial transactions flexibly.

**Procedure**

- 1. Launch the app Create Cash Flow Transactions from your SAP Fiori Launchpad.
- 2. Enter the company code, product type, transaction type, and the business partner.
- 3. Optionally, you can make entries in the Limits area:

Currency: If you do not specify a currency when you create a financial transaction, the company code currency is applied automatically.

Master Agreement: If the general conditions that you have already agreed upon are connected to the transaction, enter the master agreement in the corresponding field.

Portfolio: If you want to assign the transaction to a portfolio, enter a portfolio in the corresponding field.

Alternatively, you can enter the portfolio and the master agreement on the Administration tab in the Position Assignment area.

- 4. Choose Enter to branch to the basic data screen for the transaction. On the Structure tab, you enter the actual transaction data for the purchase or sale.
- 5. Enter the following data:


In the Term area, you enter the start and end dates of the term as well as the period (including start or including end).

As with the cash flow structure, you enter the following values in the Flows area:

Flow type

Flow description

Direction of the flow You denote incoming cash flows with "+" and outgoing cash flows with "-".

Payment amount

**Note:**

The amount field (data element TM_XBETRAG) is an input field for amounts using abbreviated forms. You can abbreviate the amount by using default values for one thousand (default 'T'), one million (default 'M'), and now also for one billion (default 'B') when entering data. The abbreviations are converted into the corresponding amount after data release.

**Examples**

|Abbreviation|Corresponding Amount|
|---|---|
|1.25M|1,250,000.00|
|1T|1,000.00|
|1T,50|1,000.50|
|1B|1,000,000,000.00|


In the Define User Data Customizing activity, you can define your own special characters or other alphabetic values as an abbreviation for thousands, millions, or billions.

Payment currency

Payment date

Posting status of the flow

An explanatory text (optional)

A financial transaction is based on the chronological sequence of these flows. They describe position changes, revenues and expenses (such as interest and fees), and payments relating to the transaction.

- 6. To store the transaction, choose Save.
- 7. You can also branch to the entry screens for the general transaction management functions. You can use the tab pages to navigate between the different screens.


For more information, see Tabs.

You find the following functions in the menu under More Extras or More Environment :

Effective Interest Rate

You use this function when you process transactions in the Money Market area to calculate the internal interest flows and update these to the database. You can use the effective interest for evaluations as part of reporting.

- a. You can generate a list of financial transactions with an unknown effective interest or using specific transaction numbers.
- b. You can also choose whether to carry out a test run or an update run.
- c. Choose Execute.
- d. The system generates a calculation log.


Position Indicator

Choose Environment Position Indicator to go to the class position.

**Additional Functions**

Call up the relevant correspondence by choosing Correspondence.

Check the correctness of your entries by choosing Check.

Navigate to another cash flow transaction by choosing the Other Cash Flow Transaction pushbutton in the menu bar.

**Supported Device Types**

Desktop

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**Related Information**

Cash Flow

###### Create Commercial Paper

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Commercial Paper | L5 | trm06 p.83 | loio `9a08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9a08da531198434de10000000a174cb4.html?locale=en-US)

App ID: TM31

With this app, you can create a commercial paper.

Commercial Paper transactions are transactions on which no interest payments are made during the term of the transaction. Instead, two business partners agree on a repayment amount to be repaid to the investor by the borrower at the end of the life of the contract.

A company requires 1 million for three months. The amount is discounted using a pre-defined yield. The company receives the discounted amount, 980,000 from an investor. At the end of the term, the company repays the full amount of 1 million.

**Note:**

For the creation of financial transactions you can also use the Manage Financial Transactions app or the Create Financial Transaction app.

**Features**

For product type 53A Commercial Paper the following transaction types are available:

|Transaction Type Number|Transaction Type Name|
|---|---|
|100|Purchase (NPV with interest)|
|101|Purchase (Nominal with interest)|
|102|Purchase (Nominal without Interest)|


|Transaction Type Number|Transaction Type Name|
|---|---|
|200|Sale (NPV with interest)|
|201|Sale (Nominal with interest)|
|202|Sale (Nominal without Interest)|


The following example for purchasing commercial papers shows how the system maps payment flows:

[figure TRM06-F037 - The following example for purchasing commercial papers shows how the system maps payment flows:]

[figure TRM06-F038]

[figure TRM06-F039 - Creating a Commercial Paper]

Creating a Commercial Paper

You create a money market transaction directly as an order. The transaction is settled automatically after counterconfirmation. A transaction becomes legally binding with the activity category Contract.

An activity can be changed as long as it is not relevant for posting. The last activity in the activity chain is relevant for posting. When you save this activity, the transaction is given fixed status.

You can branch from each application for the creation of financial transactions to the business partner to create or change business partner data.

**Generic Features**

Save a specific variant and/or layout according to your preferred settings

**Supported Device Types**

Desktop

Tablet

**Related Information**

Creating a Commercial Paper Commercial Paper: NPV Calculator

###### Commercial Paper: NPV Calculator

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Commercial Paper > Commercial Paper: NPV Calculator | L6 | trm06 p.85 | loio `6607da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6607da531198434de10000000a174cb4.html?locale=en-US)

**Features**

You use the net present value calculator to calculate the payment amount, that is, the discounted amount and the interest amount. You can also display the price as a percentage and the term (number of days).

**Activities**

1. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Money Market Trading Commercial Paper: NPV Calculator .


The selection of the procedures Yield and Discount for net present value calculation is available in the following transactions in the Commercial Paper area:

NPV Calculator

Fast data entry

Entering and processing transactions

If you do not set the indicator Exponential discounting for term over one year , the system uses linear discounting. You can use the F1 help to see what discounting method formulas are available for calculating the net present value.

- 1. To display the results of the net present value calculation, choose per Interest Rate or per Price .
- 2. To display more detailed information about the start and end of term, such as the day of the week, the calendar week, and the total number of days, choose Term Information.

###### Create IR Derivatives

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives | L5 | trm06 p.85 | loio `b316da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b316da531198434de10000000a174cb4.html?locale=en-US)

Create Swaps, Caps and Floors, and Forward Rate Agreements.

**Use**

You can create interest rate derivatives for product types based on the following product categories:

610 Cap and Floor

For more information, see also Caps/Floors

620 Swap

Examples for interest rate derivatives based on product category 620 Swap:

Interest Rate Swaps

Cross-Currency Interest Rate Swaps

Discount Swap

Compound Swap

Overnight Index Swap (Obsolete)

**Note:**

You can also create a new IR swap by copying an existing IR swap.

To copy an IR swap, open the Manage Financial Transactions app or the Process IR Derivatives - Collective Processing app and filter the relevant IR swap.

- 1. Mark the IR swap which you want to copy.
- 2. Choose the Copy button.
- 3. The Copy or Change Data dialog box appears.

In the fields Company Code and Business Partner the values of the copied financial transaction are displayed. You can now change the company code or the business partner and choose Continue or you continue the copy process without changing these values.

- 4. You see the data of the new IR swap. The data correspond with the copied transaction.
- 5. Make the required changes.
- 6. Save your entries.


**Note:**

Usually, the trader is also copied and only if the Trader field is not filled, the trader is derived. However, if you always want to derive the trader when you copy a financial transaction, you must set the indicator Der.Trader in the Define User Data app.

630 Forward Rate Agreement

For more information, see also Forward Rate Agreements (FRAs)

**Prerequisites**

Customizing

Define the product types. (If you do not want to use one of the standard product types delivered with the system, you can define your own product types). You create financial transactions and manage positions on the basis of

product types.

You can choose Parallel Conditions in the Cash Flow Generation field for product types for product category 620 Swap.

However, regardless of this setting, all new swap transactions are created with parallel conditions (new FiMA). This means, you have the the same Condition Details: Interest (New FiMa) screen as interest rate instruments and securities. This includes interest calculation types, such as Exponential Interest Calculation with Factors, Compound Interest Calculation, and Average Compound Interest Calculation. So, you can enter variable interest conditions with risk-free reference rates. For more information, see also Interest Calculation Types.

In addition, parallel interest conditions are possible.

Define the transaction type. The transaction type determines the types of transactions that can be concluded with a particular product type. It also controls the transaction and position management process. Example: Purchase

Define the flow type. Flow types describe the various changes to the cash flows. Example: Cash Settlement

You must assign the flow type to the transaction type.

Define the condition types and assign them to your product types using the Customizing activities available in the Customizing of the Treasury and Risk Management under Transaction Manager OTC Derivatives Transaction Management Condition Types . You decide in the Field Selection for each condition type, which fields should be hidden, optional, required or only displayed for a condition of the condition type.

[figure TRM06-F041 - Examples for Field Selection of Interest Rate and Interest Rate Adjustment Condition Types]

Examples for Field Selection of Interest Rate and Interest Rate Adjustment Condition Types

**Tip:**

Flow types and update types for business transactions of nominal changes, for the interest flows and the net payments must be defined. Only the update types then decide whether the flows are relevant for posting. For net payments, the update types for the original flows are not relevant for posting.

|Flow Type|Direction|Update Type|
|---|---|---|
|1105 Nom.Amt Incr.(Not Rel.f.Postg)|Inflow|DE1105+ Increase in Nominal Amount (Not Rel. for Posting)|
|1105 Nom.Amt Incr.(Not Rel.f.Postg)|Outflow|DE1105- Reduction in Nominal Amount (Not Rel. for Posting)|
|1115 Nom.Amt Decr.(Not Rel.f.Postg)|Inflow|DE1115+ Increase in Nominal Amount (Not Rel. for Posting)|
|1115 Nom.Amt Decr.(Not Rel.f.Postg)|Outflow|DE1115- Reduction in Nominal Amount (Not Rel. for Posting)|


|Flow Type|Direction|Update Type|
|---|---|---|
|1125 Contract (Not Rel.for Posting)|Inflow|DE1125+ Contract (Not Relevant for Posting)|
|1125 Contract (Not Rel.for Posting)|Outflow|DE1125- Contract (Not Relevant for Posting)|
|1135 Install. rep.(Not Rel.f.Postg)|Inflow|DE1135+ Instalment Repayment (Not Rel. for Posting)|
|1135 Install. rep.(Not Rel.f.Postg)|Outflow|DE1135- Instalment Repayment (Not Rel. for Posting)|
|1145 Annuity Rep. (Not Rel.f.Postg)|Inflow|DE1145+ Annuity Repayment (Not Rel. for Posting)|
|1145 Annuity Rep. (Not Rel.f.Postg)|Outflow|DE1145- Annuity Repayment (Not Rel. for Posting)|
|1205 Interest (to be netted)|Inflow|DE1205+ Interest (to be netted) Not relevant for posting|
|1205 Interest (to be netted)|Outflow|DE1205- Interest (to be netted) Not relevant for posting|
|1250 Interest (net)|Inflow|DE1250+ Interest (net)|
|1250 Interest (net)|Outflow|DE1250- Interest (net)|
|1107 Cross Curr. Swap Payment (net)|Inflow|DE11107+ Cross Curr. Swap Payment (net)|
|1107 Cross Curr. Swap Payment (net)|Outflow|DE11107- Cross Curr. Swap Payment (net)|


Important Information: When you create, for example, a cross-currency interest rate swap with net payment, the posting-relevant flow types must be exchanged with flow types that aren’t relevant for posting (all the flow types ending with 5) in the conditions of the financial transaction.

For more information, see the relevant section in the Implementation Guide.

Before you can create an interest rate derivative, you have to enter master data.

Maintain your business partner. For more information, see also Business Partner.

Set up the standing instructions for payment details and derived flows in the master data of your counterparty and release the business partner. To process financial transactions, you need to have defined the banks that are authorized as business partners in the system with the corresponding payment details.

Creating Standing Instructions for Payment Details

Derived Flows

Used, for example, to enable net payments for interest rate swaps with this business partner.

Define derivation procedures in the Define Derivation Procedures and Rules Customizing activity and you must assign the derivation procedure in the standing instructions to your business partner, if you agreed on net payments.

Examples:

NTINT Swap: Net Interests

Netting of interest flows only

NTALL Swap: Net Int. and Nom.

Separate netting of interests and nominal changes

NTTOT Swap: Net All Flows

One net payment/posting of all flows together.

For the FX rate adjustments for net payments of the cross-currency interest rate swaps, define fixing references using the Define Fixing References app. These settings are needed to identify the leading and the following currency for the needed FX rates.

**Activities**

- 1. On the initial screen, enter the following basic data to create the transaction:

Company code

Product type

Transaction type

Business partner

Current activity of transaction (such as order or contract)

- 2. Choose Enter to go to the basic data screen for the transaction. On the Structure tab, enter the actual transaction data for the swap.


**Note:**

Navigate to the business partner by choosing the Display Partner button on the Structure tab

The fields are either required entry or optional fields:

Term

Business calendar

Outgoing Interest / Incoming Interest

In these areas, you define the interest conditions of the swaps:

Nominal Amount and Currency

Effective From

**Note:**

You can create an interest rate condition with a start date before the Start date of the financial transaction.

1st Due Date

Freq.Month

Enter a fixed rate or Variable Reference Interest Rate.

Int. Calc.Method

Using the Details button, you can switch to the Condition Details: Interest (New FIMA) screen. For the variable interest conditions, also the Interest Adjustment button is available to jump to the related interest rate adjustment (Interest Rate Adjustment) condition. In the Detail View: Interest Rate Adjustment, you can specify how frequently the variable interest rate is recalculated and on which day the underlying reference interest rate is set. An interest rate adjustment can be carried out at the start of the period, regularly or on specific dates, for example.

Using the Conditions - Outgoing Side / Conditions - Incoming Side button, you can jump to the condition overview for either the outgoing or the incoming conditions. There you can drilldown to the condition details of the available condition items and you can create additional condition items.

**Note:**

For interest rate swaps with a business partner with whom you have agreed on net payments, you must ensure that the original flows aren’t posted. To do this, go to Conditions - Outgoing Side and Conditions - Incoming Side, from where you can navigate to the condition details for all conditions. In the condition details, for example, for interest and closing, you select the condition types that are not relevant for posting.

In addition, you can change the flow types for the posting relevant nominal flows. Click the Create Nominal Changes icon next to the Nominal Amount fields and change the flow type for nominal flow to 1105.

Check the results of your entries on the cashflow tabs (Cash Flow and Incoming and Outgoing Flows).

- 3. For cross-currency interest rate swaps with net payments, you use the Settlement area to enter the settlement currency. After you select the settlement currency, a table appears in which you enter the exchange rate adjustment settings required to determine the fixing date. The fixing date is the date of the FX rate used for the currency translation.

- a. The Crcy and the Fixing Reference ID columns are filled automatically by the system, you can change the proposed values..
- b. The determination of the fixing date starts with a date of the related business transaction, which requires the currency translation. In the column Fixing Rel.to, you can choose between the Due Date and the Period End.
- c. Enter the direction (- or +) for the determination of the fixing date.
- d. Enter the number of working days before (or after) the chosen reference date the fixing date lies.
- e. You can set the Modified indicator. This indicator ensures that the reference date and the corresponding fixing date are in the same month.


- 4. To save the basic data, choose Save.
- 5. You can also branch the other tabs available to complete your data entries for the financial transaction:


**Note:**

Go to tab Cash Flow and then to tab FX Rate Adjustment Data, where you can see the fixing dates determined by your settings.

Administration

Other Flows

Payment Details

Cash Flow

Interest Rate Adjustment Data and FX Rate Adjustment Data

Incoming and Outgoing Flows

You can also use these tabs to display the cash flows of an interest rate derivative. You can display incoming and outgoing interest rate payments either separately or together. To do so, choose the Outgoing or Incoming tabs.

Memos

Status

Analysis Parameter (RM)

Creating Data for Default Risk Limits

More Features

An important additional function is the NPV Calculator, which enables you to calculate the value of the swap on the basis of the zero coupon curve. Choose More Extras NPV Calculation. The NPV calculator calculates both of the following:

The price you would have to pay to clear the swap

The price you would have to pay to buy the instrument

The difference between the displayed NPVs reflects the corresponding bid/ask spreads.

To use more functions, choose Extras and Environment from the menu under More:

Position indicator

Choose Environment Position Indicator to go to the class position.

**Further Processing**

Use the Process IR Derivatives - Collective Processing app, for further processing of the swap.

Use the apps to adjust variable interest rates and FX rates regularly during the term of the swap. For more information, see also Adjust Variable Rates/Prices.

**More Information**

For more information, see Swaps

###### Administration (2 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Administration | L6 | trm06 p.91 | loio `5f4d20ba2ec34fdfb534456e5327bcaa` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5f4d20ba2ec34fdfb534456e5327bcaa.html?locale=en-US)

**Use**

On this tab, you can determine and call up administrative data for a financial transaction.

**Note:**

The various areas and fields are not visible in all financial transactions. Which ones are displayed can depend on the product type, on whether you use, for example, the integration with Public Sector Management (Fund and Grant fields), or on whether the financial transaction is relevant for clearing or for trade repository reporting.

See also:

Integration with SAP Public Sector Management (PSM)

External Accounts (Clearing Accounts)

Trade Repository Reporting (TRR)

**Features**

Position Assignment

In the Facility field, you assign a money market transaction to one of the facilities created in the system. If the transaction assigned has a different currency from the facility, enter the rate from the currency ratio table in the Exchange Rate field.

Here the transaction can be assigned to a particular portfolio.

You can use a finance project to issue a common key with which to group related transactions.

If a third party bears the risk related to the transaction, you enter this in the Guarantor field.

You use the general valuation class to classify transactions according to their asset type (such as short-term investments).

Hedging Classification

You must enter values to the following fields if they are used as differentiation terms for your treasury positions. Only fields that are relevant for differentiation are displayed. These fields are additional account assignments from other areas. When flows are posted to Financial Accounting, the values of the account assignments are also transferred to the jounal entry:

Cost Center

Profit Center

WBS Element

Functional Area

Up to five custom differentiation terms are available, if you defined them in the Define Custom Differentiation Terms Customizing activity:

- Custom differentiation term 1

- Custom differentiation term 2

- Custom differentiation term 3

- Custom differentiation term 4

- Custom differentiation term 5


In the Fund field, you specify unique keys for funds. You can assign budgets to funds to show their origin in detail at a later date. (Only available if you use the integration scenario with Public Sector Management.)

The Grant field contains data relating to the type and status of a grant agreement. (Only available if you use the integration scenario with Public Sector Management.)

If you use the integration with Public Sector Management and you want to distribute the nominal amount/units of a money market or security transaction to different account assignments, you can do so in the Account Assignment table on the Cash Flow tab. For more information, see also Integration with SAP Public Sector Management (PSM).

**Note:**

The differentiation must be defined in the Define and Assign Differentiations Customizing activity.

Risk Mitigation

You set this indicator for financial transactions that are used to mitigate risks.

When this indicator is set for a financial transaction, the system ignores it when calculating the rolling average position for Clearing Threshold Reporting (CTR).

You use the Hedge Request ID field for all financial transactions created based on an hedge request.

Additional Fields

You can determine the following additional fields:

You use the Assignment field to group different transactions.

You use the Reference field to create internal references.

You use the Characteristic field to mark individual transactions.

On Behalf of Company Code

Country/Region Key

Segment

Business Area

CFI Code

The Classification of Financial Instruments (CFI) code (ISO 10962) is used to define and describe financial instruments for all market participants. CFI codes are used for trade repository reporting, such as for EMIR regulations. You may receive such CFI codes when you are trading financial instruments on trading platforms.

Sec. ID (ISIN)

The International Securities Identification Number (ISIN) (ISO 6166) uniquely identifies a security. ISINs are used, for example, for trade repository reporting, such as for EMIR regulations. You may receive such ISINs when you are trading financial instruments on trading platforms.

Trade Repository

Assign the legal basis and the external trade ID of the financial transaction.

**Note:**

You can also fill the field automatically using the BAdI FTR_TR_DEFAULT_TRADE_ID (BadI: Default Value for External Trade ID in Financial Transactions). You find this BAdI in Customizing for Treasury and Risk Management under Transaction Manager General Settings Transaction Management .

See also: Update Transactions with an External Trade ID

If a financial transaction is relevant for Trade Repository Reporting (TRR), then filling this field is particularly relevant:

External Trade ID and Interim Trade ID

Forex Transactions: If you do not determine the external trade ID yourself and, instead, your counterparty communicates the external trade ID to you through the counterconfirmation (SWIFT notification MT300), the system copies the external trade ID from the incoming notification and into the financial transaction data as well as into the outgoing correspondence objects. (The prerequisite for this is that, in the Customizing activity Assign Attributes for Business Partner Groups, the Get Values from Counterconfirmation indicator is set for the business partner group in the Inbound Correspondence area.)

As soon as the external trade ID is defined in the financial transaction, it also becomes an additional matching criterion for these financial transactions. In other words, alongside the matching criteria defined in Customizing,

correspondence objects that need to be matched must also share the same external trade ID.

In MT300, the external trade ID is expressed over two fields; the content of these fields forms the external trade ID when combined. These fields are 22M (namespace) and 22N (transaction ID). Further, MT300 contains the field 22L that the system uses to derive the relevant legal basis.

Authorization

You can assign the transaction to an authorization group so that only users that have an authorization for this authorization group are allowed to process the transaction. You can specify, for example, that only selected employees are allowed to process transactions related to their department. You do this by specifying the relevant authorization group when you create the transaction.

Central Clearing Data

This area appears when the financial transaction is relevant for clearing. The appearance of the area differs depending on the central clearing option that is valid for the financial transaction:

Central Clearing Optional

When the financial transaction is created, it initially has the clearing status Not Relevant for Clearing. In this area, however, the Set as Relevant for Clearing pushbutton appears. If you want the financial transaction to pass via a central counterparty, confirm the pushbutton. The financial transaction acquires the clearing status Clearing Requested (Planned). Select the clearing account.

**Note:**

If you have entered a clearing account in the Define Default Values for Clearing transaction, this account appears in this field. However, you can replace this clearing account with another clearing account.

Enter the planned clearing date.

The Set as Not Relevant for Clearing pushbutton appears. You can use this pushbutton to set the clearing status of the transaction back to Not Relevant for Clearing.

Central Clearing Mandatory

Clearing status: Clearing Requested (Planned)

Clearing account: Select the clearing account.

**Note:**

If you have entered a clearing account in the Define Default Values for Clearing transaction, this account appears in this field. However, you can replace this clearing account with another clearing account.

Planned clearing date: The current date appears by default.

When you have received confirmation that the clearing of your financial transaction has been accepted or rejected by the central counterparty, perform the Accepting/Rejecting a Clearing function.

See also: External Accounts

You either enter the Rating or the Credit Standing, this depends on the general setting for rating in Treasury and Risk Management made in the Customizing.

Rating

- 1. Choose the Rating Procedure.

Indicates the used rating procedure.

- 2. Choose the Rating.

Indicates the result of a rating carried out with a rating procedure.

- 3. Choose the Trend for the rating.

Indicates the trend of an existing rating so that expected changes to the business partner can be displayed.

- 4. Enter the validity for the rating using the Valid From and Valid To fields.
- 5. Save your entries.


**Note:**

You can enter the ratings of different rating procedures.

Credit Standing

- 1. Choose one of the predefined internal classificationsCredit Standing.
- 2. In the Dt.Cred.Stndg field, you can enter the date on which credit standing information on the business partner was provided.
- 3. You can enter the Status of the credit standing information.
- 4. In the Cred.Stndg Text field, you can add additional information for the credit standing.
- 5. In addition, you can enter one external provided rating information for the business partner. Choose the credit standing institute in Cred.Stndg Inst field and enter the Rating result provided by the credit standing institute.
- 6. In addition, you can set the following indicators and enter a corresponding date:

Affidavit

Bankruptcy Proceed.

Foreclosure

- 7. You can enter the status of legal proceedings and the corresponding date.
- 8. Save your entries.


In the Customizing activity Make General Settings for Rating available under Treasury and Risk Management Transaction Manager General Settings Organization Rating/Credit Standing , you decide which rating function you want to use for the rating of financial transactions, security classes, and asset pools in Treasury and Risk Management. You can decide between the following rating functions:

Rating

Credit Standing

You make the settings for Rating and Credit Standing functions in Customizing under Treasury and Risk Management Transaction Manager General Settings Organization Rating , using the following Customizing activities:

Rating

Set Rating Procedures and Ratings

You can create rating procedures and assign ratings to them.

BAdI: Calculate Rating

Credit Standing

Define Rating

Define Credit Rating Institute

Define Status of Legal Proceedings

**Note:**

The Customizing for the rating and the credit standing are the same as that available for the business partner.

SPPI Classification

This area is only available for interest-bearing financial instruments such as money market transactions.

The SPPI (solely payments of principal and interest) is relevant for IFRS 9. The field expresses whether the financial transaction passed an externally executed SPPI test or not.

- 1. Choose the Valid-From Date.
- 2. Enter the Passed or Failed value in the SPPI Criterion field.

###### Payment Details (3 of 4)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Payment Details | L6 | trm06 p.96 | loio `37cdacba5ad0487d8cf9076ca944a5a9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/37cdacba5ad0487d8cf9076ca944a5a9.html?locale=en-US)

Use

You enter the data that is required for making transactions with your business partner in the payment details of a financial transaction.

**Note:**

The system provides these payment details by default when you create a transaction based on the product type, transaction type, and currency. Alternatively, you can also determine the payment details for the individual transactions. You enter the details in the system when you save the transaction.

For more information, see Input Help: Payment Details.

**Prerequisites**

You have created the payment details in the Standing Instructions. On the SAP Easy Access screen, choose Maintain Business Partner (BP) or Payment Details (TBI1).

**Features**

In addition to the Payer/Payee (business partner) field, you can also see the Alternative Payer/Payee field if you defined this in the system.

Payer/Payee and Alternative Payer/Payee

- 1. If the business partner is a house bank that supports clearing between the sender and receiver accounts, then payment using the payment programs and an entry in the Payer/Payee field are not required.
- 2. If the business partner is not a house bank, you must specify a payer/payee in the payment details for the transaction.


The business partner makes and receives payments:

The business partner is proposed by the system as the payer/payee provided that the bank details are recorded in the master data and no alternative payer/payee has been entered.

A third party makes and receives payments rather than the business partner:

If payment is not made by the business partner, a third party must be entered as an alternative payer/payee. These bank details must be entered in the system.


Payments:

If there is no alternative payer entered in the master record of the payer/payee, payment is made to the payee account for this payee.

If there is an alternative payer entered in the master record of the payer/payee, payment is made to the account of this alternative payee for the actual payee.

Regardless of whether or not the business partner makes/receives payment, the following applies:

The Payer/Payee field specifies for whom the payment is being made. The account to which payment is made depends on the master record of the business partner entered as the payer/payee in the payment details of the transaction.

Special Functions

You can define data for the state central bank indicator and the country/region of origin using the detailed screen of the Payment Details tab. This function is available only if it is released using the field modification.

For more information, see Repetitive Code.

###### Input Help for Payment Details

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Payment Details > Input Help for Payment Details | L7 | trm06 p.98 | loio `f705aede5690473381dfe759aaeed46b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f705aede5690473381dfe759aaeed46b.html?locale=en-US)

Use

By selecting/not selecting the Payment activity and Payment request fields in the payment details for a financial transaction, you are deciding whether you want the payment program to be used for payment and if so, which payment program to use. The posting logic differs according to the selections you make.

|Numbers for posting logic|Payment activity|Payment request|
|---|---|---|
|1|No|No|
|2|No|Yes|
|3|Yes|No|
|4|Yes|Yes|


Depending on the selections you made (table 1), you proceed as follows when you enter the payment details. The following table shows you which entries are required or optional and which entries are ignored:

| |Possible entries| | | |
|---|---|---|---|---|
|Entry fields|1|2|3|4|
| | | | | |
|Direction|x|x|x|x|
| | | | | |
|Currency|x|x|x|x|
| | | | | |
|Validity|o|o|o|o|
| | | | | |
|Flow type|o|o|o|o|
| | | | | |
|Description| | | | |
| | | | | |
|House bank|o|o|o|o|
| | | | | |
|Account ID|o|o|o|o|
| | | | | |
|Payment activity| | |x|x|
| | | | | |
|Payer/payee| |o|o|o|


| | | | | |
|---|---|---|---|---|
|Partner bank| |x|o|x|
| | | | | |
|Payment method| | |o| |
| | | | | |
|Payment method supplement| |o|o|o|
| | | | | |
|Payment request| |xc| |xc|
| | | | | |
|Individual payment| |oc| |oc|
| | | | | |
|Same direction| |o| |o|
| | | | | |
|Determine grouping definition| |o| |o|
| | | | | |
|Payment methods| |x| |x|


x: Required entry

o: Optional entry

c: Entry is only included if it does not contradict the Customizing settings for flow types.

/: Entry not included


For more information, see Repetitive Codes , if you have implemented this function.

###### Cash Flow (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Cash Flow | L6 | trm06 p.99 | loio `a0ddd1e69d9b48a5808d680a3b6b5f12` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a0ddd1e69d9b48a5808d680a3b6b5f12.html?locale=en-US)

**Definition**

The cash flow contains all flows of a financial transaction, classified by flow types, in chronological order. Typical flow types include nominal amount increases, fixed or variable interest, and repayments. The investment amount, the interest payment, and repayment amount are concentrated on one or several flow records through this.

**Integration**

- As the cash flow of financial transactions forms the basis for all trading, management and evaluation activities within Treasury, the flows have particular significance. They're generated by financial mathematics from the general data on the transaction, the


structural characteristics, and the conditions assigned to the transactions. The flows contain both the payment data and their calculation bases, as well as all data required for posting.

The single flow records, from which the cash flow is made up, can be generated in various ways:

By Manual Entry, such as investment amounts, charges, or special repayments.

By Automatic Generation, that is generated from the conditions. These include, for example, interest or regular repayments.

By Derivation, whereby the flows appear here automatically.

By Accrual/Deferral Flows that arise from the periodical assignment of expenses and revenues from the transaction.

As a result of transaction valuations (Valuation Flows), for example, with regard to price gains and losses.

The cash flow forms the basis for the following:

The effective interest rate calculation

The accrual/deferral of expenses and revenues

Triggering payments

Updating the flows in Cash Management

Updating Financial Accounting by using flexible account determination

Updating positions

Interest accruals/deferrals

Foreign currency valuations

Yield calculations

**Features**

Cash Flow Area

You use the SAP List Viewer to display the cash flow. You can use the following functions:

You use the Details function to display the details of a flow.

The Set Filter function enables you to display just the lines in a column or several columns that fulfill certain criteria. With the standard settings, you only see the structural characteristics. You've the option of displaying accrual/deferral flows, valuation, and transfer flows.

By double-clicking a flow, you can display the flow details.

By choosing Select Layout, you can select one of the following predefined display variants:

Basic View

This is set up as a standard view and contains information on payment dates, payment amounts, currencies, flow types with names, posting keys, and activities.

Due Date View:

This view displays information on the due dates.

Posting Information:

Entries for the payment date, payment amount, currency, flow type, posting status, posting date, document number, year, and assignment.

Calculation Bases:

This view displays information about the interest rates, the calculation methods and the relevant calculation periods that were used to calculate the flow amount.

Local Currency View:

For transactions in a foreign currency, you see an entry for the amounts in the local currency as well as the payment amount in the transaction currency. view displays the foreign and local currency amount and the exchange rate for flows that haven't yet been posted. The exchange rate is taken from the current rate table and has Current Rate status.

You can edit the flows. You can set either the exchange rate or the local currency amount here, for example, to avoid rounding off an amount when the exchange rate is fixed. When you double-click a line in the cash flow, an entry screen appears on which you can change the corresponding condition.

If you want to set the exchange rate, enter the rate and select Rate Set. You set the local currency amount in a similar way.

In the local currency view of the cash flow, you can see any changes that have been made and you can see whether the translation was carried out based on current rates or manual rates that were set.

Payment View:

This view displays data relevant to payments for the house bank and house bank account, payer/payee, partner bank details and different payment methods.

Posting View:

This view shows you the data, such as posting date, flow type, payment amount, payment currency, posting status (name), document number, and year (year for the document).

You can change these predefined views or define your own display variants.

Account Assignment Table

This table is only available if you use the integration with Public Sector Management. If this is the case, you can distribute the total nominal amount of money market or securities transactions to different account assignments in this table.

Specify the different partial amounts either by entering the amounts directly or by entering the percentages and assigning the corresponding account assignments to them.

###### Conditions - Outgoing Side / Conditions - Incoming Side

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Conditions - Outgoing Side / Conditions - Incoming Side | L6 | trm06 p.101 | loio `a39e19db7f124478879ed35491bdd410` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a39e19db7f124478879ed35491bdd410.html?locale=en-US)

Using the Conditions - Outgoing Side / Conditions - Incoming Side pushbutton in the upper part of the screen, you can navigate to the Overview of Conditions either the outgoing or the incoming conditions.

A condition is a contractually agreed element of a financial instrument. It describes the structure of the transaction in terms of the period and amount (interest, repayment, and so on). You enter conditions using condition types. Flow types are assigned to condition types. These flow types display changes to the payment flows and are part of the cash flow.

**Note:**

In the Customizing, you define the condition types and assign them to your product types using the Customizing activities available in the Customizing of the Treasury and Risk Management under Transaction Manager OTC Derivatives

Transaction Management Condition Types . You decide in the Field Selection for each condition type, which fields should be hidden, optional, required or only displayed for a condition of the condition type.

[figure TRM06-F044 - Examples for Field Selection of Interest Rate and Interest Rate Adjustment Condition Types]

Examples for Field Selection of Interest Rate and Interest Rate Adjustment Condition Types

Examples for condition types.

1120 Closing (Rel. to Posting)

You don’t have to enter the closing condition yourself. The system calculates it automatically using the due date of the swap. The system, however, assumes it to be a 100% repayment.

1125 Closing (not rel. to posting)

You don’t have to enter the closing condition yourself. The system calculates it automatically using the due date of the swap. The system, however, assumes it to be a 100% repayment.

The flows of this condition aren’t posting relevant.

1130 Install. repay.(Rel.f.Posting)

1135 Install. rep.(Not Rel.f.Postg)

The flows of this condition aren’t posting relevant.

1140 Annuity Repay. (Rel.f.Posting)

1145 Annuity Rep. (Not Rel.f.Postg)

The flows of this condition aren’t posting relevant.

1150 Interest Capitalization

Interest flows are capitalized and are part of the base amount in the following interest period.

1160 Capitalized Interest Payment

Belongs to the condition type 1150 Interest Capitalization and generates the repayment flow for the capitalized interest.

1200 Interest

Interest conditions are either fixed interest conditions or variable interest conditions. For variable interest conditions, you must also enter the interest rate adjustment condition.

1205 Interest (to be netted)

Use this condition type if interest flows must be netted for payment.

The flows of this condition aren’t posting relevant.

- 1210 Interest rate adjustment

Needed for variable interest conditions.

- 1211 Split Event


You can use the split event to split the interest flow of, for example, a monthly paid fixed interest flow into daily interest flows.

1777 FX Fixing

The settings for the FX rate adjustments are entered in the Settlement area on Structure tab.

**Use**

Conditions include all the data that is relevant for generating condition-based flows in the cash flow. The different entries for the individual condition types determine exactly how the flows are calculated. On the condition overview screen, you can see the condition items of the financial transaction in a table either the outgoing conditions or the incoming conditions. In the table, you see the following data for a condition item:

Logical Condition Group

Condition Type and Name

Effective-From Date

Amount-Based Structure

Date Structure

**Features**

Using the   Create Parallel Condition Gr.button, you can enter parallel condition items.

- 1. Choose the condition type from the list of possible condition types.
- 2. Enter the Effective from date for the new condition item and choose copy.
- 3. You’re now in the condition details screen for the selected condition type. Enter the required data on Amounts and Dates tab pages.


1200 Interest / 1205 Interest (to be netted) / 1150 Interest Capitalization

Interest conditions are either fixed interest conditions or variable interest conditions. For variable interest conditions, you must also enter the interest rate adjustment condition.

Condition Details: Interest (New FIMA)

1210 Interest rate adjustment

Needed for variable interest conditions.

Interest Rate Adjustment

4. Save your entries.

Display or change condition details by double-clicking a condition item or by selecting the condition item and choosing Detail. The details screen comprises the following areas:

Header data of the condition at the top of the screen.

Here, you find the effective-from date again for the condition item, the Condition Form field (Active), and the Amounts, Dates, and Payment Data / Other tabs, and the Condition Type.

**Note:**

You can change the condition type, for example, if you create a cross-currency interest rate swap with net payment, you must change the condition type for interest and closing conditions to a not posting relevant condition type.

The Amounts, Dates, and Payment Data / Other tabs show you exactly how the conditions are structured. The screen contains more fields than the initial Conditions screen, depending on which fields you select for the condition. The entry options in the condition details differ depending on the condition type.

Amounts

This tab includes entries for the amounts and/or the amount of a condition type.

Dates

- 1. Calendar

If you always want to shift the due date to a working day, enter up to five calendars you want to use to calculate the working day.

- 2. Calculation Date/Due Date

The calculation date is the last day of the current interest period. The due date is the day on which the interest payment is due.

This area includes the fields for determining the exact calculation dates and due dates of the condition item.

- 3. Calculation Modes


Here, you define the method used to determine the next calculation date or due date.

Choose Date Preview to display a list of the dates of the flows of the relevant condition type. The list includes the due date, the payment date, the calculation period, and the resulting number of days (interest days), as well as the interest calculation method.

To delete a condition item, select it and choose (Delete Line).

Related Information

Condition Details: Interest (New FIMA) Interest Rate Adjustment

###### Condition Details: Interest (New FIMA) (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Conditions - Outgoing Side / Conditions - Incoming Side > Condition Details: Interest (New FIMA) | L7 | trm06 p.105 | loio `e11602151b654dbb87dfd45970962b6d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e11602151b654dbb87dfd45970962b6d.html?locale=en-US)

**Use**

On the Condition Details: Interest screen, you can make more detailed entries for the interest calculation to supplement those entries you have already entered on the Structure tab in the Interest Structure area.

**Note:**

Two types of condition item are required to represent the variable interest rate condition.

- 1. Define the underlying reference interest rate and the calculation method for the variable interest rate in the condition item Nominal Interest.
- 2. Define the frequency with which you want the variable interest to be adjusted, and the corresponding interest rate fixing date in the condition item Interest Adjustment. For more information, see also Interest Rate Adjustment.


**Prerequisites**

These condition details are available for product categories 550, 580, and 620, if you have activated the new FIMA by choosing

Parallel Conditions in the Cash Flow Calculation field for these product types in the Customizing settings for the product types. This setting enables the use of enhanced financial mathematics functions (new FIMA), such as parallel conditions and additional interest calculation types such as the Average Compound Interest Calculation. It influences how conditions are managed and

therefore how cash flow is calculated.

**Procedure**

- 1. By choosing the Conditions pushbutton or by choosing Goto Conditions , the Conditions Overview appears. Each condition has a line in the overview, such as one line for the interest condition and one line for the repayment condition.
- 2. You reach the Conditions Detail: Interest screen when you double-click the interest item on the Conditions Overview screen or when you choose the Detail View: Interest Condition pushbutton.
- 3. The details screen comprises the following areas:


Header data of the condition at the top of the screen.

Amount tab

Data for Percentage Calculation

Interest calculation method and the type of interest calculation

The interest calculation method is a procedure for counting the days for the interest calculation. Therefore, it is also often called the days count method. This is defined by a quotient of days method and a base days method.

The following types of interest calculation are available:

Linear Interest Calculation

Exponential Interest Calculation

Exponential Interest Calculation with Factors

Percentage Interest Calculation

Percentage Interest Calculation per Day

Compound Interest Calculation

Average Compound Interest Calculation

For more information, see also Interest Calculation Types.

Scaled Calculation

By setting the Scaled Calc. indicator, you can enter scaled conditions. See also: Scaled Conditions

Formula

You can enter a formula for the interest rate calculation. Choose a formula and enter the values for the variable.

Ref. Int. Rate

For variable interest conditions, you can enter a sign (+ or -) and a reference interest rate.

Percentage Rate

Enter the percentage rate for the interest condition.

**Note:**

For variable interest conditions, you can also add here a percentage that is a spread on top of the variable interest rate.

Payment Rate

The payment rate indicates a percentage rate that is applied to the condition amount calculated previously. The cash flow therefore does not display the condition amount calculated, but the condition amount multiplied by the payment rate in percentage. For more information, see the field help.

The Average Interest Rate area contains specific settings for the average interest rate calculation of the Average Compound Interest Calculation. You see this area only if you have chosen this interest calculation type.

Weighting category

To determine the average interest rate, the reference interest rates of a period are weighted.

You can choose from two weighting categories:

S Based on Interest Rate Fixing Date

The weighting corresponds to the number of calendar days from the interest fixing date to the next working day.

L Based on Interest Rate Adjustment Date

The weighting corresponds to the number of calendar days from the interest rate adjustment date to the next working day.

You can define the rounding decimal places for the average interest rate.

The average interest rate can contain a spread (S). This is added after the rounding of the average interest rate.

The rounded average interest rate including the spread can be limited by an upper limit and a lower limit.

Rounding Factors

In this area, you define the rounding rules (rounding category and the number of decimal places) for the calculated factors. Which factors are available here depends on the interest calculation type chosen:

Base Factor

Interest Factor

Flow Factor

Example:

For the Average Compound Interest Calculation, you can enter a rounding category and the number of rounding decimal places for the interest factor.

Round Amounts

In this area, you can define rounding rules for the calculated amount using the following fields:

Rounding Cat.

Rounding Unit

Base Unit

For the Exponential Interest Calculation with Factors, you can enter a rounding category in the Factor RC field for the factor and the number of rounding decimal places for a factor in the Dec. Fac. Round field. The number of rounding decimal places is used with the rounding category for the factor to be rounded or truncated.

For more information, see the field help.

Calculation Base

Amount

Reference

For the Exponential Interest Calculation with Factors, you can enter a rounding category for the base factor in the Base Factor RC field and the the number of rounding decimal places for a base factor in the Dec. BF Round. field. The number of rounding decimal places is used with the rounding category for the base factor to be rounded or truncated.

Currency-Related Data

Condition Amnt

Currency

Lower Limit

Upper Limit

You can find a more detailed description of the methods in the field help for this field.

Date tab

Calendar

You can enter up to five calendars as relevant for the working day check for the interest flows generated from the conditions.

The system proposes the calendar of the country/region in whose currency the transaction was created.

Calculation Date

First you choose the rule for date updates. The default value is Regular, which means that the frequency of the calculation date is also relevant for the due date.

Enter the frequency by entering the unit for the frequency (Months or Calendar Days) and the cycle.

Enter the first date.

Set the Month End indicator if needed.

Set the Inclusive indicator if needed.

Enter the settings for the working day shift if needed.

Due Date

First you choose the rule for date updates. The default value is Regular, which means that the frequency of the calculation date is also relevant for the due date.

Enter the frequency by entering the unit for the frequency (Months or Calendar Days) and the cycle.

Enter the first date.

Specify how to handle the due date if it falls on a day that is not a working day according to the settings in the Customizing activity Maintain Calendar.

Select the rule and, if required, enter the number of days by which the due date is to be shifted.

Set the Month End indicator if needed.

Other calculation data

Shift due date

First period

Last period

For more information, see the field help.

- 4. You can use the Date Preview button to see whether the settings made lead to the desired dates.
- 5. To check your entries, you can also look at their impact on the cash flow. To do this, you have to exit the details screen and go to the Cash Flow tab of the financial transaction data.

###### Interest Calculation Types (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Conditions - Outgoing Side / Conditions - Incoming Side > Condition Details: Interest (New FIMA) > Interest Calculation Types | L8 | trm06 p.108 | loio `716d928dbfc848448dd4607c83a1ec68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/716d928dbfc848448dd4607c83a1ec68.html?locale=en-US)

Specifies the type of interest calculation within the calculation period.

The following options are available for interest calculation:

**Linear Interest Calculation**

Interest amount = capital * percentage rate / 100 * days / base days

**Exponential Interest Calculation**

In the case of interest rate adjustments, an interest period is divided into calculation periods.

Interest amount = Base amount * ( q ** (days / base days) - 1 )

where

q = 1 + percentage rate / 100 (compounding factor)

** = power operator

[figure TRM06-F045 - ** = power operator]

**Exponential Interest Calculation with Factors**

The system calculates the interest factor according to the formula for the exponential interest calculation. However, basic factors have been introduced to calculate the calculation base amount, which is used to capitalize the capital amount within a calculation period.

In the case of interest adjustments within an interest period, the interest calculation type Exponential Interest Calculation with Factors delivers more precise values because the determination of the calculation base amount has been changed from a summation of amounts to multiplying the capital with the base factors.

[figure TRM06-F046]

**Percentage Interest Calculation**

Interest amount = Base amount x percentage rate / 100

**Percentage Interest Calculation per Day**

Interest amount = Base amount x percentage rate per day / 100 x days

**Compound Interest Calculation**

In the case of interest rate adjustments, an interest period is divided into calculation periods. The compound interest calculation uses the formula for linear interest calculation to calculate the interest amount of a calculation period:

[figure TRM06-F047 - In the case of interest rate adjustments, an interest period is divided into calculation periods. The compound interest calculation uses the formula for linear interest calculation to calculate the interest amount of a calculation period:]

Explanations

|Z|Interest amount|
|---|---|
|K|Capital at the start of the interest period|
|R|Interest rate of the calculation period|
|D|Number of days of the calculation period|
|BD|Base days|


The base amount of the calculation period is the sum of the capital amount at the start of the interest period and the interest of the previous calculation periods within the interest period:

Calculation of the Base Amount

[figure TRM06-F048 - Calculation of the Base Amount]

Explanations

|i, n|Index of a interest flow|
|---|---|
|Bn|Base amount of the calculation period n|
|Zi|Interest amount of the calculation period i|
|K|Capital at the start of the interest period|


This results in the following formula for the calculation of the interest amount (for the respective calculation period within the interest period):

Interest Amount of Calculation Period

[figure TRM06-F049 - Interest Amount of Calculation Period]

Explanations

|i, n|Index of a interest flow|
|---|---|


|Zi|Interest amount of the calculation period i|
|---|---|
|K0|Capital at the start of the interest period|
|Rn|Interest rate of the calculation period n|
|Dn|Number of days of the calculation period n|
|BD|Base days|


**Note:**

Only supported for interest calculation methods using days method act, such as act/360 and act/365.

**Average Compound Interest Calculation**

The system calculates the interest amount using an average interest rate. This is determined per calculation period from the average product of the previous interest factors of the interest period.

The Average Interest Rate area contains specific settings for the average interest rate calculation:

Weighting category

To determine the average interest rate, the reference interest rates of a period are weighted.

You can choose from two weighting categories:

S Based on Interest Rate Fixing Date

The weighting corresponds to the number of calendar days from the interest fixing date to the next working day.

L Based on Interest Rate Adjustment Date

The weighting corresponds to the number of calendar days from the interest rate adjustment date to the next working day.

You can define the rounding category and the number of decimal places for rounding the average interest rate.

The average interest rate can contain a spread (S). This is added after the rounding of the average interest rate.

The rounded average interest rate including the spread can be restricted by an upper limit and a lower limit.

[figure TRM06-F050 - Example of Specific Settings for Interest with ACIC]

Example of Specific Settings for Interest with ACIC

Calculation of Average Interest Rate

[figure TRM06-F051 - Calculation of Average Interest Rate]

Explanations

|i, n|Index of a interest flow|
|---|---|
|r|Average interest rate|
|R|Interest rate of the calculation period i|
|w|Weighting of the calculation period i|
|BD|Base days|
|RD|Rounding decimals|


Calculation of the average interest rate with spread

In the condition details, you can enter a spread (S) in the area of the average interest rate. This is added after rounding the average interest rate.

[figure TRM06-F052]

Explanations

|i, n|Index of a interest flow|
|---|---|
|r|Average interest rate|
|R|Interest rate of the calculation period i|
|w|Weighting of the calculation period i|
|BD|Base days|
|RD|Rounding decimals|
|S|Spread|


**Note:**

The rounded average interest rate including the spread can be restricted by an upper limit and a lower limit.

Calculation of the interest amount with average compound interest calculation type:

[figure TRM06-F053 - Calculation of the interest amount with average compound interest calculation type:]

Explanations

|i, n|Index of a interest flow|
|---|---|
|Z|Interest amount of a calculation period n|
|B|Base amount|
|r|Average interest rate|
|BD|Base days|
|D|Number of days of a calculation period|


**Note:**

Only supported for interest calculation methods using days method act, such as act/360 and act/365.

###### Interest Rate Adjustment (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Conditions - Outgoing Side / Conditions - Incoming Side > Interest Rate Adjustment | L7 | trm06 p.114 | loio `098b57001c904c2889a68ae385966f26` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/098b57001c904c2889a68ae385966f26.html?locale=en-US)

Define the frequency with which you want the variable interest to be adjusted and the corresponding interest rate fixing date.

Definition

You need two types of condition item to represent the variable interest rate condition.

1. Firstly, you need the condition item Nominal Interest in which you enter details for the variable interest condition, such as the reference interest rate, the interest calculation method, and the interest calculation type. In addition, you enter the details for the interest period here.

For more information, see also Condition Details: Interest (New FIMA)

2. Secondly, you need the condition item Int. Rate Adjustment in which you define the frequency with which you want the variable interest to be adjusted and the corresponding interest rate fixing date.

**Prerequisites**

The relevant reference interest rate needs to have been defined, and you must ensure that current data is available for interest rate fixing.

**Create Condition Item for Interest Rate Adjustment**

- 1. Enter the Effective from date.
- 2. Branch to the Condition Detail Screen
- 3. The screen is divided into the Amounts and Dates tabs.


On the Amounts tab, you enter the interest calculation method.

The Dates tab is divided into two areas: Interest Rate Adjustment and Interest Rate Fixing Date:

In the Interest Rate Adjustment area, you enter the frequency with which you want the variable interest to be recalculated or become effective. The following alternatives are available:

At start of period

Regular

You define the frequency using the available fields.

Single Dates

The Single Dates function displays the interest rate adjustments that recur annually and that you can’t display via At Start of Period and Regular.

Example:

Interest rate adjustment takes place annually in 03/15 and 10/15.

You can show only this irregular sequence of interest rate adjustment dates using Single Dates.

For reference interest rate entry

Enter the calendar rule, which specifies how to handle the date if it falls on a day that isn’t a working day.

Also define which calendars are relevant for determining the date as a working day.

In the Interest Rate Fixing Date area, you define when you want to determine the interest rate value from the market data table. You can choose from the following:

Relative to interest rate adjustment date

Relative to start of period

Relative to period end

Relative to due date

In the following two fields, you enter the lookback period, which specifies how many working days before or after the selected reference date the interest fixing date is.

Lockout Period in working days: Period at the end of the interest period where the reference rate isn’t adjusted anymore. For these last days of the interest period, the last reference rate adjusted one day before the lockout period is used.

Also define which calendars are relevant for determining the date as a working day.

Example Settings for Daily Interest Rate Adjustment, with Lookback Days and Lockout Period

[figure TRM06-F054 - Example Settings for Daily Interest Rate Adjustment, with Lookback Days and Lockout Period]

4. Using the Date preview button, you can display the interest rate adjustment dates. The system displays the following dates per interest rate adjustment:

Effective From date of the new interest rate (interest rate adjustment date)

Interest Fixing Date

Percentage Fixing Date

This can differ from the interest fixing date if no entry has been made in the reference interest rate table. The system therefore chooses the previous entry.

Percentage: In this field, you can see the interest rate that is read from market data table.

Example 1: Date Preview for Daily Interest Rate Adjustments with 2 Lookback Days

[figure TRM06-F055 - Example 2:]

Example 2:

The interest rate is adjusted at the start of a period on February 1, 2016 (Monday). The interest rate has to be fixed two working days before the interest rate is adjusted, which means that the interest rate fixing date is January 28, 2016 (Thursday). If a reference interest rate hasn’t been entered for this date, the system uses the reference interest rate fixed for the last time on January 27, 2016. The date on which the reference interest rate is fixed for the last time is documented as the percentage fixing date.

**Overview of Interest Rate Adjustments**

On the Int. Rate Adj. tab in the financial transaction data, you obtain an overview of all data relevant for interest rate adjustments for the variable interest conditions. The data is grouped according to due date, adjustment date, reference interest rate, interest rate, and the date of the rate fixing.

**Execute Interest Rate Adjustments**

- At the interest rate adjustment dates, you must fix the interest rates for the interest flows. For more information, see also Adjust Variable Rates/Prices.

###### FX Rate Adjustment Data

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > FX Rate Adjustment Data | L6 | trm06 p.118 | loio `7215e4c4a0e04fbb9059406af59e6655` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7215e4c4a0e04fbb9059406af59e6655.html?locale=en-US)

On this tab, you see the FX rate adjustment data for your cross-currency interest rate swaps and settlement currency in interest rate instrument.

**Context**

For netting of the flows of cross-currency interest rate swaps and settlement currency in interest rate instrument, the flows need to be translated into the same currency. This currency is the settlement currency. For the translation, you need to fix the FX rate. The FX rate needs to be adjusted at any time flows are generated. The FX rate fixing dates are determined from your settings in the

settlement area on the Structure tab, where you enter plus/minus and a number of days, which refer to either the due date or the period end of the flows to determine the FX rate fixing date. The fixing date is the date for which you manually enter the FX rate using the Create Adjustment - Rates/Prices app.

**Note:**

For the calculation and display of the planned/ future flows of the swap on the Cash Flow tab, system reads the FX rate for the fixing date in market data tables and also the FX rates that were already determined by manual FX rate adjustments. If the system doesn’t find an FX rate for the fixing date the latest FX rate in the market data table before the fixing date is read (the date of the FX rate read is shown in field Date of FX Rate Read).

On the FX Rate Adj. tab, you see the following two areas:

In the FX Rate Fixing: Overview area, a table listing all FX rate adjustments relevant for the cross-currency interest rate swap and settlement currency in interest rate instrument, provides the following information:

Fixing Date

Weekday (of the fixing date)

Fixing Reference

An icon showing the status of the adjustment:

(not fixed)  Not Fixed

(fixed)  Fixed

FX Rate

Here you can see the FX rate for all adjustments in status Fixed.

Trigger

In this field, you can see if the adjustments have been done manually or automatically.

**Note:**

For the FX rate adjustment, it’s only possible to use the Create Adjustment - Rates/Prices app, where you enter the FX rate for the fixing date manually.

In the FX Rate Fixing: Details area, you can see the details for a specific adjustment. The following fields are shown:

Fixing Date

Fixing Ref. ID

FX Rate

Ratio

Fixed By

Effective From

Fixing Status

Trigger

Rate Fix. Date

Rate Fix. Time

**Procedure**

- 1. Use this tab to check the fixing dates resulting from your settings in the Settlement area on Structure tab.
- 2. Use this tab to check the current status of the FX rate adjustments.

###### Memos (2 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Memos | L6 | trm06 p.119 | loio `d1b8752c20f147e5bc52fa08eb001d8e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d1b8752c20f147e5bc52fa08eb001d8e.html?locale=en-US)

Definition

The Memos tab page provides additional information about a transaction that has been created.

**Use**

You can create a memo both during and after the creation of a transaction. You define memo types in Customizing to enter the memos structurally in the system. In Customizing for Transaction Manager, choose General Settings Transaction Management Define Memo Book .

Operating Notes:

Use S to select the memo type(s).

If the indicator M is set, you cannot see all the text defined in the entry field.

The S indicator shows that memos of this type are available in other languages.

Use the Editor to enter the memo.

###### Analysis Parameter (RM) (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create IR Derivatives > Analysis Parameter (RM) | L6 | trm06 p.121 | loio `19202081775e4ef694e5188b13f224fe` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/19202081775e4ef694e5188b13f224fe.html?locale=en-US)

- 1. Choose Analysis Parameters (RM) to add to the contract data the information necessary for transaction valuation.

- a. Set the Analysis Active indicator.

All financial objects to be taken into account when evaluations are run in Risk Analysis have to be flagged in this way.

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

- b. Enter a summarization rule for transactions that you want to summarize.

The system uses the summarization rule to aggregate the balances of accounts, fully disbursed loans, and variable transactions in the database. The Summarization Rule field does not appear on the screen for any of the other transactions.

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

- c. Set the balance sheet indicator for the transaction on which the financial object is based.

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

- d. Enter the valuation rule.


The valuation rule controls how the transaction is treated in the individual risk evaluations.

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

- 2. You can define precisely the validity of the financial object by entering the validity period.


- 3. In the data group Analysis Characteristics, define the characteristic values for the financial object.


Generated Analysis Structure

**Recommendation:**

You can define the sequence of the RM analysis characteristics and how they appear on the screen by choosing Financial Supply Chain Management Treasury and Risk Management Basic Analyzer Settings


Reporting Characteristics Define Generated Analysis Structure . You can enter values for hidden characteristics only by using derivation strategies. If a characteristic is hidden by linking, then the other characteristics in the linking will also be hidden.

**Note:**

If you want to know how characteristics are derived when you save and run checks on a financial object, choose

Extras Characteristic Derivation Log . A list then shows you the source fields along with the corresponding target fields.


Static Analysis Structure

Business Partner

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

Trader

Automatically derived by the system from the corresponding field in the financial transaction data.

Contract Type

Automatically derived by the system from the corresponding field in the financial transaction data.

Product Category

Automatically derived by the system from the corresponding field in the financial transaction data.

Product Type

Automatically derived by the system from the corresponding field in the financial transaction data.

Security ID

Automatically derived by the system from the corresponding field in the financial transaction data.

Securities Acct

Automatically derived by the system from the corresponding field in the financial transaction data.

Futures Account

Automatically derived by the system from the corresponding field in the financial transaction data.

Currency

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

Portfolio

Automatically derived by the system from the corresponding field in the financial transaction data.

Country/Region

Transaction

Automatically derived by the system from the corresponding field in the financial transaction data.

Contract Number

Automatically derived by the system from the corresponding field in the financial transaction data.

Position ID

Automatically derived by the system from the corresponding field in the financial transaction data.

Characteristics

You can fill this field manually or define a derivation rule in Customizing to fill it automatically.

If you decided to use the generated and the static analysis structure, you can toggle between the analysis parameters for the different analysis structures.

**Related Information**

Analysis Structure

###### Create Security Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Security Transaction | L5 | trm06 p.124 | loio `d218da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d218da531198434de10000000a174cb4.html?locale=en-US)

App ID: TS01

**Use**

You can create a security transaction as an order or as a contract.

**Note:**

Some of the input fields will depend on the Customizing settings you made for the Transaction Manager under General Settings Transaction Management Define Field Selection . You can configure each of these fields to appear as an optional, required or display field, or hide the field entirely.

**Note:**

You can also create a new security transaction by copying an existing security transaction for the following product categories:

010 Stock

020 Investment Fund

030 Subscription Right

- 040 Bond

- 041 Drawable Bond


160 Shareholding

To copy a security transaction, open the Manage Financial Transactions app (App ID: F6157) or the Process Security Transactions - Collective Processing app (App ID: TS00) and filter the relevant security transaction.

- 1. Mark the security transaction which you want to copy.
- 2. Choose the Copy button.
- 3. The Copy or Change Data dialog box appears.


In the fields Company Code, Business Partner, and Security ID the values of the copied financial transaction are displayed. You can now change the company code, the business partner, or the security ID and choose Continue or you continue the copy process without changing these values.

- 4. You see the data of the new security transaction. The data correspond with the copied transaction.
- 5. Make the required changes.
- 6. Save your entries.


**Note:**

Usually, the trader is also copied and only if the Trader field is not filled, the trader is derived. However, if you always want to derive the trader when you copy a financial transaction, you must set the indicator Der.Trader in the Define User Data app.

**Procedure**

- 1. Choose Trading Transaction Create .

The Create Security Transaction: Initial Screen appears.

- 2. Enter the Company code, Security ID number, Transaction type and the Business partner (counterparty).
- 3. Choose Order or Contract.
- 4. If you have set up external number assignment, enter the number of the security transaction.
- 5. Choose (Enter).


- 6. The screen for creating order/contract data for a security transaction appears.

The top part of the screen displays the Company Code, the ID Number (choose to display the class master data), the Transaction Type and the current Activity Category.

The screen contains various tab pages on which you enter the transaction information. The tab pages displayed for the activities Order and Contract will depend on the field selection settings you make in Customizing for the Transaction Manager under General Settings Transaction Management Define Field Selection .

- 7. Enter the transaction data on the various tab pages.


**Note:**

However, you cannot suppress the display of the Structure tab page.

Structure

Administration

Trading Data - Bonds Only

Editing Other Flows for the Transaction

Payment Details

Transaction Cash Flow

Memos

Partner Assignment

Status

The following tab pages are available if you use the Market Risk Analyzer and the Credit Risk Analyzer and have activated automatic financial object integration in Customizing. The relevant sections in Customizing are Basic Analyzer Settings

Automatic Integration of Financial Objects in Transaction Master Data and Credit Risk Analyzer Basic Settings

Automatic Integration of Financial Objects. For more information, see the documentation for the Customizing activities.

See also: Automatic Integration of Financial Objects and Integrated Default Risk Limit Check

Create Analysis Parameters (RM)

Create Data for Default Risk Limit

- 8. Choose Position Cash Flows (in the upper part of the screen) to display the position cash flows for the securities account in the various valuation areas, including the transaction currently being processed.

See also : Cash Flow

- 9. Choose to branch to the correspondence overview for this transaction. There you can see the correspondence that was generated for the transaction and its status. You can also see the leading correspondence medium for the status. Choose


to check that your entries for the transaction are complete. A message appears if certain settings are missing.

- 10. Save your entries.


- 11. As long as the activity is not relevant for posting, you can change it using the Change Security Transaction function. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are Flagged for posting.

- 12. Choose to branch to the initial screen for creating a security transaction.
- 13. Choose to branch to your worklist.


- 14. To post the transaction, choose Transaction Post .

###### Structure (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Security Transaction > Structure | L6 | trm06 p.126 | loio `6d18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6d18da531198434de10000000a174cb4.html?locale=en-US)

**Use**

On the Structure tab, you enter the actual transaction data for the purchase or sale.

**Structure**

|Partner|Choose to branch to the master data for the counterparty.|
|---|---|
|Flow Type|The flow type that is used to write the main flow to the financial transaction (purchase or sale flow type). If there are several suitable flow types for the transaction type you have selected, you can choose any one of them. You would do this, for example, if two flow types have been assigned to a sale transaction type in Customizing with the flow category Capital Reduction. To branch to the details of the main flow, choose . |
|The following entry areas are available when you create an order:| |
|Basic Data|The securities account to which / from which you buy / sell the security Choose to branch to the securities account master data. |


| |Order Date Nominal amount/number of units that you want to purchase or sell  When you execute the order, these values automatically appear as proposals in the Structure tab of the contract.|
|---|---|
|Limit|Select the desired limit type. You define the limit types in Customizing for the Securities area by choosing “Define Order Limit Checks”. The limit type determines the values for which the limit check takes place. Limit Date Limit price  When you execute the order, these entries appear on the Trading Data tab.|
|Trading|Trader Exchange  When you execute the order, these entries appear on the Trading Data tab.|
|Closing|Contact person - this can be the name of the person with whom the transaction has been concluded. This person does not need to be entered as the business partner in the system. External Reference You can enter your own data in this field. Here, you can enter the number used by the business partner to manage the transaction or the number from your source list.  When you execute the order, these entries appear on the Trading Data tab.|
|Reservation|Date Choose one of the reasons available. You define the reservation reasons in Customizing by choosing Define Reservation Reasons.  When you execute the order, these entries appear on the Trading Data tab.|
|The following entry areas are available when you create a contract:| |
|Position|Here you find: The securities account to which / from which you buy / sell the security. Choose to branch to the securities account master data. |


| |Enter the general valuation class. A default value may have been defined in Customizing. You can overwrite this. By choosing the Quantity Position pushbutton, you can view the class position in the securities account including the transaction currently being processed.  Choose the Position Cash Flows pushbutton (in the upper part of the screen) to display the cash flows of the different valuation areas for the securities account, including the transaction currently being processed.|
|---|---|
|Date Details|Position value date = date on which a position change takes effect This field automatically shows the current date. However, you can overwrite it. Calculation date = date from which the position changes are interest-effective If you set the Include indicator, the interest for the calculation date is allocated to the selling contract partner. Payment date = date on which the payment is made **Note:** You can use the following possible entries here: * = the date in the Position Value Date field plus one day + 1 = the date in the Position Value Date field plus one day + 2 = the date in the Position Value Date field plus two days ++ 1 = the date in the Position Value Date field plus one month|
|Amounts|Nominal amount/number of units that you want to purchase or sell Rate/price at which the transaction was concluded (and the currency of the notation) If a market price has been maintained in the system, it is displayed with the source data next to the Price field. Market value = nominal amount multiplied by the price/number of units and multiplied by the rate/price Payment amount = the market value in the currency used for payment Further, you can display the following amounts that are calculated from the payment amount: Amount in local currency Amount in position currency If the position currency and the payment currency differ, or the position currency and the local currency are not the same, the system uses the exchange rates in the general exchange rate table to calculate the amounts.|


| |If the rate has not been fixed, you have the option of changing the exchange rates manually.|
|---|---|
|For securities only:| |
|Trading Data|The Exchange on which the stock is traded The Expenses Key, which indicates how the expenses for the transaction are considered|
|Contract Conclusion|Contract Date The Contact Person, who is not necessarily entered as the partner The in-house Trader responsible for the transaction The External Reference used by the business partner to keep a record of transactions.|
|For bonds only:| |
|Accrued Interest Calculation|Interest Calculation Method The system does not display an interest calculation method. If you do not make any entries here for the interest calculation method, the accrued interest is calculated on the basis of the interest calculation method entered in the conditions for the relevant class. Only enter an interest calculation method here if you want to calculate the accrued interest using a different method (from the one entered in the class). See also: See also: The field help for this field explains the different DAYS/DAY BASIS combinations that can be used. Coupon The Next coupon will be delivered setting is set by default in this area. If you do not make any other settings here, the accrued interest is calculated under the assumption that you will receive the coupon for the next interest payment. (On the Other Flows tab, you can control the accrued interest flow that has been generated and correct it, if necessary). If you do not need to calculate accrued interest, for example, if it has already been included in the price, set the Without Accrued Interest indicator. The following settings are also available for the Coupon field: Next coupon will not be delivered The accrued interest is calculated accordingly. Partial right on next coupon, no accrued interest calculation No accrued interest is calculated. Coupon information from coupon|


| |Using the Coupon pushbutton, you enter the date on which the next coupon will be delivered. Only use this setting if the next coupon to be delivered is the next but one coupon or an even later one. The accrued interest is calculated accordingly. No coupon delivery The system generates an accrued interest flow as well as flows via the interest payments whose coupons will not be delivered.|
|---|---|
|Effectiveness Test|Effective interest method: The effective interest method is set by default from the class. You can, however, choose a different method.|

###### Administration (3 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Security Transaction > Administration | L6 | trm06 p.130 | loio `da16da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/da16da531198434de10000000a174cb4.html?locale=en-US)

**Use**

On this tab page you define data that you can use for administration purposes.

Procedure

|Position assignment| |
|---|---|
|Portfolio|This field displays the portfolio to which the position was assigned from this transaction. This field only appears if you have activated portfolio valuation.  If you have activated portfolio valuation, the securities account is assigned to the portfolio when you create the securities account.|
|Additional fields| |
|Assignment|You are free to make your own entries in these three fields. However, you can use these fields as selection criteria in the Securities: Collective Processing function. |
|Internal reference| |
|Characteristics| |
|Authorization| |
|Authorization group|You can assign the transaction to an authorization group so that only users that are authorized for this group are allowed to process the transaction. You define authorization groups in Customizing for Basic Functions by choosing Define Authorization Group for Transactions.|

###### Trading Data - Bonds Only

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Security Transaction > Trading Data - Bonds Only | L6 | trm06 p.130 | loio `e817da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e817da531198434de10000000a174cb4.html?locale=en-US)

**Use**

On this tab page, you define the additional data for the transaction that enhances the entries made on the Structure tab page or shows the order entries for this transaction.

**Structure**

|Contract data| |
|---|---|
|Contact person|This can be the name of the person with whom the transaction was concluded. This person is not necessarily entered as the business partner in the system.|
|External reference|You can enter your own data in this field. Here, you can enter the number that is used by the business partner to manage the transaction or the number from your source list.|
|Expenses key| |
|Trading| |
|Trader|Name of the trader who concluded the transaction.|
|Exchange| |
|Order:Here you see the limit data from the order (or you enter it later)| |
|Order date| |
|Limit price|Enter the limit price.|
|Limit type|Enter the required limit type. You create the limit types in Customizing for the securities area by choosing Define Order Limit Checks. The limit type determines the values for which the limit check takes place.|
|Limit date|Enter the limit date.  A warning message appears if you specified limit data when you entered the order, and your entries for the contract differ from these values.|
|Reservation| |
|Date| |
|Reason|Choose one of the reasons available. You define the reservation reasons in Customizing by choosing Define Reservation Reasons .|

###### Editing Other Flows for the Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Security Transaction > Editing Other Flows for the Transaction | L6 | trm06 p.132 | loio `a218da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a218da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Using this tab page, you can enter the other flows for the main flow (= purchase or sale flow) of a transaction manually and edit the other transaction flows that were generated automatically.

Examples of flows that are generated automatically for a transaction are accrued interest flows when a bond is purchased and/or flows generated by a derivation procedure.

The tab pages is divided into three areas:

|a) Main flow|At the top of the tab page you can see the purchase or sale flow type (main flow) and the related payment data.|
|---|---|
|b) Net payment amount|The field below displays the net payment amount of the transaction. This is the sum of the payment amounts for all the flows (in the currency of the main flow) for this transaction. Prerequisite In order to include a flow in the net payment amount calculation for a transaction, you must have set the Net payment amount indicator when you defined the transaction flow types in Customizing for the securities area. Example 1 Purchase of 100,000 EUR nominal of a fixed-interest security at 95%. Interest of 1,000 EUR is accrued and a commission of 142.50 EUR is charged. This generates the following flows: FType Name Pmnt amnt Curr. 0100 Purchase 95,000.00 EUR 0870 Accrued int. 1,7000.00 EUR 0302 Commission 142.50 EUR The net payment amount comes to 96,142.50 EUR. Example 2 Sale of 100,000 USD nominal of a fixed-interest security at 98.5%. The seller is entitled to accrued interest of 1,400 USD on which taxes of 420 USD are to be paid, and a commission of 142.50 EUR is charged. This generates the following flows: FType Name Pmnt amnt Curr. 0200 Sale 98,500.00 USD 0870 Accrued int. 1,400.00 USD 0306 Int. income tax 420.00 USD 0302 Commission 142.50 EUR|


| |The net payment amount comes to 99,480.00 USD.|
|---|---|
|c) Other flows|The lower part of the screen contains a table for creating, editing, and displaying other flows. The table tells you the flow type, direction, amount, currency and the posting status of the other flows.|


**Prerequisites**

You can only create flows here that were assigned to the transaction type in Customizing activity Assign Flow Types to Transaction Type, and which have flow category 90 (Other flows/condition) or 23 (Accrued interest).

**Procedure**

Creating other flows:

- 1. Using the F4 Help for the FTyp field, choose the flow type you require (e.g. commission not capitalized).
- 2. Enter the direction of the payment by indicating whether it is an incoming payment (+) or an outgoing payment (-).
- 3. Enter the amount of the flow and the currency in which the payment amount is due.


**Note:**

If none of the lines in the table are ready for input when you create a new flow, generate a new line by choosing .

Changing other flows that already exist

You can change the entries for the flows provided that the flows have not yet reached the Flagged for posting status.

To delete a flow, select the flow you want to delete and choose .

Choose to display the details for a flow and to change the entries, if required.


In the details screen for the accrued interest, you can see the calculation basis and can correct the payment amount, if necessary.

###### Payment Details (4 of 4)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Security Transaction > Payment Details | L6 | trm06 p.133 | loio `e8e0253b97364e51b77dfb33e14f40e6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e8e0253b97364e51b77dfb33e14f40e6.html?locale=en-US)

**Use**

You enter the data that is required for making transactions with your business partner in the payment details of a financial transaction.

**Note:**

The system provides these payment details by default when you create a transaction based on the product type, transaction type, and currency. Alternatively, you can also determine the payment details for the individual transactions. You enter the details in the system when you save the transaction.

For more information, see Input Help: Payment Details.

Prerequisites

You have created the payment details in the Standing Instructions. On the SAP Easy Access screen, choose Maintain Business Partner (BP) or Payment Details (TBI1).

**Features**

In addition to the Payer/Payee (business partner) field, you can also see the Alternative Payer/Payee field if you defined this in the system.

Payer/Payee and Alternative Payer/Payee

- 1. If the business partner is a house bank that supports clearing between the sender and receiver accounts, then payment using the payment programs and an entry in the Payer/Payee field are not required.
- 2. If the business partner is not a house bank, you must specify a payer/payee in the payment details for the transaction.


The business partner makes and receives payments:

The business partner is proposed by the system as the payer/payee provided that the bank details are recorded in the master data and no alternative payer/payee has been entered.

A third party makes and receives payments rather than the business partner:

If payment is not made by the business partner, a third party must be entered as an alternative payer/payee. These bank details must be entered in the system.


Payments:

If there is no alternative payer entered in the master record of the payer/payee, payment is made to the payee account for this payee.

If there is an alternative payer entered in the master record of the payer/payee, payment is made to the account of this alternative payee for the actual payee.

Regardless of whether or not the business partner makes/receives payment, the following applies:

The Payer/Payee field specifies for whom the payment is being made. The account to which payment is made depends on the master record of the business partner entered as the payer/payee in the payment details of the transaction.

Special Functions

You can define data for the state central bank indicator and the country/region of origin using the detailed screen of the Payment Details tab. This function is available only if it is released using the field modification.

For more information, see Repetitive Code.

###### Transaction Cash Flow

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Security Transaction > Transaction Cash Flow | L6 | trm06 p.134 | loio `3817da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3817da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The cash flow for the transaction contains all the flows that result from the financial transaction.

**Use**

When you enter a transaction, you can use the cash flow function to check whether your entries generate the flows you expect. You can also display more detailed information on the flows (such as payment and posting data) using various layouts.

**Structure**

The cash flow is a list displayed using the SAP List Viewer.

Using Layout Settings you can select one of the following predefined display variants:

Basic view

This is a default layout. It displays the following information for the flows:

Payment date, payment amount (in payment currency) and payment currency

Direction

Flow type and name

Change indicator (icon)

Release indicator (icon)

Reversal indicator (icon)

Due date view

Basic view plus due date

Calculation view

This view displays information on the interest rates, the calculation methods and the relevant calculation periods that were used to calculate the flow amount.

Local currency view

For transactions in a foreign currency, you can also display the payment amount in the local currency. In addition to the payment and local currency amounts, the system also displays the exchange rate, which is taken from the current exchange rate table.

Payment view

This view displays the flow data that is relevant for payment.

Posting view

In addition to the payment date, payment amount, payment currency, and flow type, the posting view displays the following:

Posting date

Posting status

Document number

Year (=for the document)

Assignment

You can, of course, define your own layouts. For more information on the options available when you use the SAP List Viewer, see the complete documentation on displaying lists. In the Cross-Application Components(CA) section of the SAP Library, choose General Application Functions (GTF) → SAP List Viewer (ALV): Classic .

**Integration**

The transaction cash flow does not show which of the flows for the position are generated by the conditions (in the case of a bond transaction, for example). This is indicated by the position cash flows.

Choose Position cash flows (in the upper part of the screen) to display the cash flows for the position, including the transaction currently being processed.


See also: Cash Flow for a Class in a Securities Account

###### Partner Assignment (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Security Transaction > Partner Assignment | L6 | trm06 p.136 | loio `9284a5d98c724d30b939b6e64ae20e6a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9284a5d98c724d30b939b6e64ae20e6a.html?locale=en-US)

**Use**

The tab page Partner assignment provides an overview of all of the relevant data for the partners assigned to the transaction. You can branch directly to the SAP business partner and change the data if necessary. You can also assign or create additional partners for the transaction.

**Prerequisites**

To make the necessary settings for the SAP business partner in Customizing, choose Basic Functions SAP Business Partner for Financial Services SAP Business Partner.

**Procedure**

Partner List

In addition to the partner's name and standard address, the partner list displays the address type relevant for correspondence, such as Business address . You define the default value for the address type in Customizing. The correspondence is sent to the address that has been assigned to this address type. You can select a different address type using the address type button, which

displays all of the address types that have been assigned to the partner. You assign the partner's addresses to address types using the Address Overview function in SAP business partner maintenance (section Address Usage ).

**Note:**

You assign a grouping and an address type for each role in the Customizing activity Assign Grouping and Address Type per Assignment Cat., Application Cat. and Role (SAP Business Partner Settings for Partner-Object Relationships) . This appears as the default address type in the partner list, provided you have also assigned an address to this address type in the Address Usage section of the Address Overview for the business partner. If no address has been assigned to this address type for the partner, the partner list defaults to the standard address type XXDEFAULT.

If you choose History , the partner list displays all the partners that have been assigned to the transaction so far , including those valid in the past and in the future. If you choose Date , the display reverts to the partners that are valid for the date you enter.

The partner list also contains the business partner key and the role category (field ObjectPart ). These appear as information fields that cannot be changed.

- 1. Select a partner from the Partner list . To display the data for the SAP business partner, choose Display .
- 2. To assign an existing partner to the transaction, choose Add Partner. The Object Part screen displays the roles delivered by SAP (such as counterparty). To display additional roles in this screen, you first need to define them. You can do this from the application menu by choosing Basic Functions Tools SAP Business Partner SAP Business Partner: Application Development BP Control BP Roles. You then have to assign these roles in the Customizing activity Assign Additional Roles per Assignment Category and Application Category (SAP Business Partner Settings for Partner-Object Relationships).


After selecting the role, enter the relevant data in the Business Partner Search screen. The partners you assign in this way are added to partner list .

To delete partner assignments from the partner list, choose Delete Assignment .

**Note:**

In the IMG activity Assign Additional Roles per Assignment Category and Application Category, you determine whether or not the additional roles that you have defined can be deleted. If you want to prevent a partner in a certain role from being deleted, flag the role as a required entry field. This also means that you cannot save the transaction unless a partner has been assigned in this role.

###### Status (3 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Security Transaction > Status | L6 | trm06 p.137 | loio `9fb9bfa901234ac9a70c12ff2b6d8b21` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9fb9bfa901234ac9a70c12ff2b6d8b21.html?locale=en-US)

**Definition**

This tab page shows you the current status of a financial transaction, which results from the Customizing settings for Correspondence, the product-specific Activity category and the processing category assigned to the Transaction type.

Correspondence

You can make external correspondences for a transaction for which you created business partners in the Standing Instructions . In these standing instructions, you specify for each product and transaction type whether a confirmation and a counterconfirmation are required for the particular transaction. You can choose from the following correspondence statuses: 0

(not required), 1 (required), 2 (confirmation executed). If the transaction has been carried out, the name of the user and the date are displayed.

Activity Alongside the current activity category (such as order or contract), the current status of the transaction (such as active or closed), the person who entered the transaction and the name of the last person to change it are displayed.

Example:

In the case of a retrospective rise in the interest rate, a new field appears with information about the last person to change the transaction, the date, time and the comment Activity change.

Transaction This area provides information about the entire transaction process (such as whether a settlement transaction is included).

The statuses predefined by the system are shown as the System Status in status management. You can also add to the transaction status by user-defined statuses ( user status).

**Structure**

A status can be set or deleted automatically as the result of a business activity. You use a status profile to do this. In Customizing for the Transaction Manager , choose General Settings Transaction Management Status Management

Define Status Profiles.


You can also enter the user status manually. To do this, choose Status Management and then the Business Activities tab page. This provides you with an overview of the activities that are permitted, or not permitted.



For more information about the user status, choose User Status .

**Use**

The transactions available in the transaction management functions (for example, settlement) are defined in the general status management as business activities. An activity can set or delete one or several statuses. The impact of business activities on the system status is predefined, but you can set up the user status management. You can therefore add extra statuses to a transaction type. These are managed centrally and displayed for the relevant financial transactions.


In Status Management you can specify that a transaction cannot be settled until it has been confirmed.

You can also trigger an event and workflows for the business object Financial Transaction by setting and deleting statuses. In Customizing for the Transaction Manager , choose General Settings Transaction Management Status Management

Define Event Creation.


Transferring a transaction from the trading area to the back office.

###### Create Facility

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Facility | L5 | trm06 p.138 | loio `e407da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e407da531198434de10000000a174cb4.html?locale=en-US)

App ID: TM_61

With this app, you can create facilities.

Facilities are agreements between a lender and a borrower, which control the general conditions for a series of drawings against a credit line. The lender can give drawing authorization to several people (= borrowers), who are entitled to draw varying amounts at any time up to the total approved credit line. The utilization of this credit option for a facility is called a drawing. The lender calculates charges for the borrower (commitment interest). The charges that incur are calculated according to different methods.

**Note:**

For the creation of facilities, you can also use the Manage Financial Transactions app or the Create Financial Transaction app.

**Features**

Create Bilateral Facilities.

Create Syndicated Facilities

**Related Information**

Creating a Bilateral Facility Creating a Syndicated Facility Conditions (Facilities) Define Credit Lines - Syndicated Facilities

###### Create Letter of Credit

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Letter of Credit | L5 | trm06 p.139 | loio `67becb55914a7b43e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/67becb55914a7b43e10000000a4450e5.html?locale=en-US)

App ID: FTRTLC01

With this app, you can create a letter of credit or a stand-by letter of credit.

For more information, see also

Letter of Credit

Processing Letters of Credit as an Importer

Processing Letters of Credit as an Exporter

Standby Letters of Credit

Creating Standby Letters of Credit

Processing Standby Letters of Credit as an Importer

Processing Standby Letters of Credit as an Exporter

**Activities**

- 1. Open the Create Letter of Credit app on SAP Fiori launchpad.
- 2. Choose the company code.


**Note:**

For the creation of financial transactions you can also use the Manage Financial Transactions app or the Create Financial Transaction app.

- 3. Choose the product type, such as 85A Normal Letter of Credit or 85B Standby Letter of Credit.
- 4. Decide whether the activity is an order or a contract.

You can create a letter of credit transaction directly as a contract. A transaction becomes legally binding with the activity category Contract.

If you work with external number assignment, you have to enter a key for the transaction in the corresponding field. This enables the transaction to be uniquely identified within a company code. Otherwise, the system assigns a number automatically and displays this number when you save the transaction.

- 5. Choose or press Enter to go to the basic data screen for letters of credit.


- 6. Enter required data for the letter of credit on the Structure tab. For more detailed information, see Basic Data - Trade Finance

- 7. Choose More Worklist to branch to your worklist.
- 8. Choose Documents to branch to the documents overview for this transaction.
- 9. Choose Save to save the letter of credit.


**Note:**

You can also branch to the entry screens for the general transaction management functions. To do this, you use tabs.

For more information, refer to Tab Pages.

To use additional functions, choose More Extras or More Environment .

**Supported Device Types**

Desktop

Tablet

###### Create Bank Guarantees

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Create Bank Guarantees | L5 | trm06 p.140 | loio `2089fa56ac7d6d38e10000000a44147b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2089fa56ac7d6d38e10000000a44147b.html?locale=en-US)

App ID: FTRTBG01

With this app, you can create bank guarantees.

**Activities**

Open the Create Bank Guarantee app on your SAP Fiori launchpad.

Enter the company code, product type, transaction type, and partner.

Make the following entries in the Specifications area:

Transaction Currency: If you do not specify a currency when you create a financial transaction, the system automatically uses the currency of the company code.

Portfolio: If you want to assign the transaction to a portfolio, enter this portfolio in the corresponding field.

Decide whether the activity is an order or a contract.

You can create a bank guarantee transaction directly as a contract. A transaction becomes legally binding with the activity category Contract.

If you work with external number assignment, you have to enter a key for the transaction in the corresponding field. This enables the transaction to be uniquely identified within a company code. Otherwise, the system assigns a number automatically and displays this number when you save the transaction.

Press Enter to go to the basic data screen for bank guarantees.

Enter required data for the bank guarantee on the Structure tab. For more detailed information, see Basic Data - Trade Finance

Choose Fee Calculation to calculate bank guarantee fees. For more information, see Calculating Fees for Bank Guarantees.

Choose Worklist to branch to your worklist.

Choose Save to save the bank guarantee.

You can also branch to the entry screens for the general transaction management functions. To do this, you use tabs.

For more information, refer to Tab Pages.

To use additional functions, choose Extras and Environment from the menu.

**Supported Device Types**

Desktop

Tablet

**Related Information**

Bank Guarantees Processing Bank Guarantees as an Importer Processing Bank Guarantees as an Exporter

###### Process Spots/Forwards - Collective Processing

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Process Spots/Forwards - Collective Processing | L5 | trm06 p.141 | loio `76c6ad36ae2044658d953d1b1a0d3d18` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/76c6ad36ae2044658d953d1b1a0d3d18.html?locale=en-US)

App ID: TX06

With this app, you can manage your spot and forward transactions. Besides functions that allow you to select and display transactions, you can also go to the individual screens for processing the financial transactions.

**Activities**

- 1. Open the Process Spots/Forwards - Collective Processing app on SAP Fiori launchpad.
- 2. The screen for collective processing appears, which is divided into two areas:


**Note:**

You could also use the Manage Financial Transactions app, which enables collective processing of all kinds of financial transactions. To process a single financial transaction, you could use the Process Financial Transaction app.

The area to the left of the screen shows the selection variants in a tree view, which you can configure yourself.

The area to the right of the screen displays the last selection of transactions the user made.

- 3. Collective processing enables you to generate a list of transactions according to selection criteria that you define. To enter the selection criteria on an entry screen.
- 4. Choose Worklist New
- 5. The initial screen for collective processing appears. Here, you enter the selection criteria according to which you want to create the list of business transactions (for example, general selections, position assignment, additional fields, entered on/last changed).
- 6. Choose Execute pushbutton (in the lower part of the entry screen).
- 7. The system displays a list of the selected transactions.
- 8. The list of transactions is displayed with the help of the SAP List Viewer, which provides extensive options for structuring the list rows and columns, and for sorting and displaying totals.
- 9. You also have the option of processing the transactions from the collective processing list.


- a. Position your cursor on the transaction you want to process.
- b. Open the context menu using the right mouse button. From the menu, you can select one of the functions with which you can process the selected transaction. Alternatively, you can go these functions using the buttons above the list display.
- c. When you select a function, the corresponding processing mode appears, from which you can perform the necessary steps.


**Note:**

You can also store any number of selections as variants and manage them in collective processing in a tree view for specific users or for all users. You can access all the management functions for variants via a context menu in the tree view.

To add a variant that has already been defined to the tree view:

- 1. To open the context menu, right-click with the mouse on the node in the tree below which you want the variant to appear.
- 2. Then choose Insert Variant .
- 3. Enter the name of the variant you want to add and confirm your entry with ENTER.
- 4. The variant now appears as a separate node below the tree node you selected. By double-clicking this node, you can execute the assigned selection for the variant.


**Supported Device Types**

Desktop

Tablet

**Related Information**

Processing Spot/Forward Transactions Processing a Non-Deliverable Forward

**Process OTC Options - Collective Processing**

App ID: TI91

With this app, you can process OTC options. Besides functions that allow you to select and display transactions, you can also go to the individual screens for processing the financial transactions.

Collective processing enables you to generate a list of transactions according to selection criteria that you define.

**Note:**

You can also navigate from the Structure screen of an exercised option to the corresponding underlying transaction by choosing Detail next to the exercise transaction number.

**Procedure**

- 1. Open the Process OTC Options - Collective Processing app on SAP Fiori launchpad.
- 2. The initial screen for collective processing appears. Here, you enter the selection criteria according to which you want to create the list of business transactions (for example, general selections, position assignment, additional fields, entered on/last changed).
- 3. Choose Execute.
- 4. The system displays a list of the selected transactions.
- 5. The list of transactions is displayed using the SAP List Viewer, which provides extensive options for structuring the list rows and columns, and for sorting and displaying totals.
- 6. You have the option of processing the transactions from the collective processing list.


**Note:**

You could also use the Manage Financial Transactions app, which enables collective processing of all kinds of financial transactions. To process a single financial transaction, you could use the Process Financial Transaction app.

- a. Select the transaction that you want to process from the list.
- b. Select one of the functions with which you want to process the selected transaction.
- c. When you select a function, the corresponding processing mode appears from which you can perform the necessary steps.


**Note:**

You can also store any number of selections as variants and manage them for specific users or for all users. You can access all the functions for variants by choosing More Goto Variants .

**Processing Functions available for OTC Option**

For further information, on the available processing functions for options see also:

Processing an FX Option

Processing Swaptions

Supported Device Types

Desktop

Tablet

###### Process OTC Options - Collective Processing

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Process OTC Options - Collective Processing | L5 | trm04 p.104 | loio `cc15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cc15da531198434de10000000a174cb4.html?locale=en-US)

You can also overrule the termination request to create an offsetting transaction.

**Overrule a Termination Request**

- 1. Since a termination request is a type of hedge request, open the Process Hedge Requests app and enter your hedging area to show all termination requests belonging to this hedging area. You can also search directly for the Hedge Request ID of your termination request.
- 2. In the search results table, select the checkbox for your termination request.
- 3. Choose   Editto edit the termination request.
- 4. If overruling is allowed and the Hedge Request Status is Released, you can now choose Overrule. The status should change to Overruled and you see a message that a new hedge request for the offsetting transaction was created.
- 5. The offsetting transaction appears on the Process Hedge Requests main screen. It has the category FX Hedge, the status Released, and the description indicates that it is an offsetting transaction.
- 6. The offsetting hedge request automatically generates a trade request. You can navigate to the trade request from the Display Hedge Request view.


**Note:**

Make sure to enter the hedging classification before you choose Overrule.

If the hedging area is not differentiated by portfolios, you can enter a target portfolio for the offsetting transaction. If the hedging area is differentiated by portfolios, the target portfolio is preset and cannot be changed.

**Related Information**

Creating a Termination Request

###### Process IR Derivatives - Collective Processing

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Process IR Derivatives - Collective Processing | L5 | trm06 p.144 | loio `f814da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f814da531198434de10000000a174cb4.html?locale=en-US)

**Procedure**

Open the Process IR Derivatives - Collective Processing app on SAP Fiori launchpad or use function Collective Processing: Interest Rate Derivatives (transaction TI92) in the back-end system to process multiple interest rate derivatives at the same time.

|Function|Entries|Comment|
|---|---|---|
|Create|Create IR Derivatives| |
|Copy (product category 620) **Note:** This function is available in the Manage Financial Transactions app (App ID: F6157) and Process IR Derivatives Collective Processing app (App ID: TI92).|1. Mark the IR swap which you want to copy. 2. Choose the Copy button. 3. The Copy or Change Data dialog box appears. In the fields Company Code and Business Partner the values of the copied financial transaction are displayed. You can now change the company code or the business partner and choose Continue or you continue the copy process without changing these values. 4. You see the data of the new IR swap. The data correspond with the copied transaction. 5. Make the required changes. 6. Save your entries. **Note:** Usually, the trader is also copied and only if the Trader field is not filled, the trader is derived. However, if you always want to derive the trader when you copy a financial transaction, you must set the indicator Der.Trader in the Define User Data app.|You can create a new IR swap by copying an existing financial transaction. This function enables you to fasttrack the entry of a new financial transaction.|
|Change| |You can now overwrite the active entry fields or enter data in the empty fields on the different tabs available.|


|Function|Entries|Comment|
|---|---|---|
| | |You can use this function to change an activity, provided that it isn’t relevant for posting. The last activity in the activity chain is relevant for posting. When you save an activity that is relevant for posting, the transaction is fixed (the flows become actual records in the Treasury subledger) and the flows are flagged for posting.|
|Interest Rate Adjustment|Process Adjustments Manually Rates/Prices Process Automatic Adjustments Rates/Prices |You can adjust interest rates for financial instruments based on variable interest rates either manually or automatically in order to calculate interest payables or receivables. With both methods, a reference interest rate is linked to an interest rate value for a specific date. Interest rates need to be adjusted for all interest- and pricerelevant financial transactions on the planned determination date. With the interest rate adjustment, flows are created in the cash flow, and you can post these flows in FI.|
|FX Rate Adjustment|Process Adjustments Manually Rates/Prices |For netting of the flows of cross-currency interest rate swaps and settlement currency in interest rate instrument, the flows need to be translated into the same currency. This currency is the settlement currency. For the translation, you need to fix the FX rate. The FX rate needs to be adjusted at any time flows are generated. The FX rate fixing dates are determined from your settings in the settlement area on the Structure tab, where you enter plus/minus and a number of days, which refer to either the due date or the period end of the flows to determine the FX rate fixing date. The fixing date is the date for which you manually enter the FX rate using the Create Adjustment - Rates/Prices app.|
|Settle|1. Choose Settle. 2. The Settle (Contract, Exercise, Notice, Expiration) screen appears. 3. Choose the area from the menu for which you want to enter or change the settlement data. 4. When you save a settlement activity, the system changes the activity category of the transaction to record how it’s monitored and processed in the back-office area. |Using the Settle function, you can mark transactions to document that they’ve been processed in the back office. At this stage, the system checks the financial transaction data and adds any missing data. Also, when you save the transaction, the system fixes the transaction (actual records) and marks the transaction flows as Flagged for Posting.|


|Function|Entries|Comment|
|---|---|---|
| |5. The contract can only be posted after it has been settled.|This function enables you to settle financial transactions that belong to the Contract activity. The flows for the purchase/sale of transactions with status Planned acquire the status Actual. The back-office area, like the trading area, enables you to call up information on existing transactions and make changes to them at a later date. You can monitor and check transaction activities with the settlement function. You can also add any missing data, such as payment instructions or posting details.|
|Termination|Choose Give Notice.|You can choose from the following strategies for final repayment and an interest rate flow: Default – changes end date to the termination date. Conditions base flows are created to the termination date Without Interest – all planned interests are deleted. New zero conditions for interest and capitalized interests are generated Without Interest and Repayment – all planned interests and repayments are deleted. New zero conditions for all conditions are generated Manual – conditions are adjusted by user|
|Reverse|When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not been settled and that you must settle again (in the back office).|1. Choose Reverse. 2. The Reverse Financial Transaction: Management screen appears. 3. To reverse a transaction, you have to enter a reversal reason in the corresponding field. Enter the key for the reversal in the Reversal Reason field. |


|Function|Entries|Comment|
|---|---|---|
| |Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to release the flows before you post or reverse them.| |
|Display| |The entry fields aren’t active. You can use the tab pages to navigate between the various screens and display the other data relating to the transaction. By choosing tab pages, you can go to the master data for the business partner. You can use the tab pages to navigate between the various screens and display the other data relating to the transaction. |
|Display History|1. Choose History. 2. The system lists the activities that have been activated, reversed, or replaced by a follow-up activity. From this list, you can display the individual activities. You also see their status and the user who processed them. |The history displays the sequence of previous activities related to a selected transaction.|


**General Functions**

The following general functions are supported:

You can display a detailed view of the interest rate derivative by choosing the Details pushbutton

You can set a processing indicator.

You can navigate to the related correspondence for the interest rate derivative.

You can display the conditions of the interest rate derivative, both the incoming and the outgoing side.

You can save in a local file from the menu by choosing More List Export Local File .

You can display the business partner from the menu by choosing More Goto Display Partner .

You can save your preferred layout settings as a variant.

**Supported Device Types**

Desktop

**More Information**

For more information on interest rate derivatives, see Swaps.

For more information about how the individual tabs are structured, see Tabs.

###### Process Security Transactions - Collective Processing

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Process Security Transactions - Collective Processing | L5 | trm06 p.148 | loio `2719c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2719c55368511d4be10000000a174cb4.html?locale=en-US)

With this app, you can display and process several securities transactions at once.

App ID: TS00

**Use**

The collective processing app enables you to process your security transactions. Besides functions that allow you to select and display transactions, you can also go to the individual screens for processing the financial transactions.

**Activities**

- 1. Open the Process Security Transactions - Collective Processing app on SAP Fiori launchpad or in the area menu of the Securities area under Back Office Collective Processing Securities (transaction TS00).
- 2. The initial screen for collective processing appears. Here, you enter the selection criteria according to which you want to create the list of business transactions (for example, general selections, position assignment, additional fields, entered on/last changed).


|Areas|Selection options|
|---|---|
|Transaction Category|Purchase and/or Sale Usually when you call up this app, the Purchase and Sale fields are both selected.|
|Current Activity Category|Order, Settlement, Contract, and/or Expired Order As a rule, all the activity categories are selected when you call this app.|
|General Selections|Company Code Transaction Security ID Number Securities Account Product Type Business Partner Trader Portfolio|
|Additional Fields (= field names are the same in transaction entry screens)|Assignment|


| |Internal reference Characteristics|
|---|---|
|Entered/Last Changed By|User Date  Here, for example, you can display all the transactions that a particular user has entered/changed.|
|Output Control|Here, you can choose a display variant with which you want to display the transactions.|


- 3. Choose the Execute pushbutton (in the lower right of the entry screen).
- 4. The system displays a list of the selected transactions.
- 5. The list provides extensive options for structuring the rows and columns, and for sorting and displaying totals.
- 6. You also have the option of processing the transactions from the collective processing list.


- a. Select the transaction you want to process from the list.
- b. From the menu bar above the list display, you can select one of the buttons with which you can process the selected transaction:


|Create|You can also create new security transactions from the collective processing function. See also: Create Security Transaction Once you have created a new transaction and returned to the collective processing screen, the new transaction does not appear in the list at first. To display the new transaction in the list, choose (Update).|
|---|---|
|Copy You can create a new security transaction by copying an existing security transaction for the following product categories: 010 Stock 020 Investment Fund 030 Subscription Right 040 Bond 041 Drawable Bond 160 Shareholding This function enables you to fast-track the entry of a new financial transaction. This function is also available in the Manage Financial Transactions app (App ID: F6157).|i. Mark the security transaction which you want to copy. ii. Choose the Copy button. iii. The Copy or Change Data dialog box appears. In the fields Company Code, Business Partner, and Security ID the values of the copied financial transaction are displayed. You can now change the company code, the business partner, or the security ID and choose Continue or you continue the copy process without changing these values. iv. You see the data of the new security transaction. The data correspond with the copied transaction. **Note:** Usually, the trader is also copied and only if the Trader field is not filled, the trader is derived. However, if you always want to derive the trader when you copy a financial transaction, you must|


| |v. Make the required changes. vi. Save your entries. set the indicator Der.Trader in the Define User Data app.|
|---|---|
|Change|You can use this function to change the current data of a security transaction if the transaction flows still have the Blocked for Posting status. When you have made your changes, the security transaction stays in the activity as before. **Example:** If the current activity of the transaction you want to change is Order, you can only transfer it to the Contract activity using the Execute function.|
|Display You can double-click a transaction to display it.| |
|Order Expiration|If the order requirements are not fulfilled, the order expires. You can represent this activity in the system using the Expiration of Security Order function. Once you have executed the function, the Order activity becomes an Order - Expiration activity.|
|Execute|The function for executing an order transfers a security transaction from the Order activity to the Contract activity. You can add missing details and change the order data to reflect the actual transaction data.|
|Settle|When you settle a transaction, you check the security transaction and add any missing data. When you save the transaction, the transaction flows are assigned the status Flagged for Posting.|
|Fixing Available for money market funds with variable NAV (product category 020 Investment Fund) using processing categories 00003 Order - Contract - Contract Priced) or 00004 Order - Contract - Settled - Contract Priced - CP Settled.|Fixing allows you to enter the exact price and quantity for money market security transactions that are priced after the payment. You can adjust the number of units and price per unit in this step. You then need to settle the contract before posting it.|
|Reverse|When you reverse a transaction, you reset the most recent change made to the transaction that is identified by the system as an activity. If postings are linked to the reversed activity, these are flagged for reversal. The reversal function reverses the last active activity and reactivates the previous activity. When you reverse a contract that has been settled, you carry out the reversal in a contract that has not|


| |been settled and that you must settle again (in the back office). Documents that cannot be reversed automatically (for example, if they have been cleared in FI) must be reversed manually. These flows are automatically assigned a reversal indicator. If you work with release management, you may have to release the flows before you post or reverse them.|
|---|---|
|History|Use this function to display the history of a transaction.|
|Refresh|If you choose this pushbutton, the transactions are updated or refreshed and the processing indicator reset.|
|Cash flow|Display the cash flow of the class in the securities account|
|Set Processing Indicator|Use this function to set the processing indicator for a transaction in the list manually without having edited the transaction.|
|By choosing Goto , you can perform the following actions:| |
|Cash Flow|Branch to the cash flow of the class in the securities account|
|Display Class Data|Branch to the security class data display|
|Display Partner|Branch to the business partner data screen|
|Display Securities Account|Branch to the securities account master data screen|


- c. When you select a function, the corresponding processing mode appears, from which you can perform the necessary steps.

###### Process Trade Finance Transactions - Collective Processing

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Process Trade Finance Transactions - Collective Processing | L5 | trm06 p.151 | loio `0739fbebaa054fb38db3155df114ad46` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0739fbebaa054fb38db3155df114ad46.html?locale=en-US)

App ID: FTRTLC00

With this app, you can collectively process trade finance transactions. Collective processing enables you to process trade finance transactions. Besides being able to use functions to select and display transactions, you can also go to the individual screens for processing the trade finance transactions.

**Features**

Display the related correspondence from the processing screen of the individual financial transaction.

View the details of a specific trade finance transaction by selecting a row in the table and choosing the Details icon in the header bar.

Export the results list to a spreadsheet by choosing More List Export Spreadsheet .

Save a specific variant and/or layout according to your preferred settings.

**Activities**

- 1. Open the Process Trade Finance Transactions - Collective Processing app on SAP Fiori launchpad.


**Note:**

You could also use the Manage Financial Transactions app, which enables collective processing of all kinds of financial transactions. To process a single financial transaction, you could use the Process Financial Transaction app.

- 2. The initial screen for collective processing appears. Here, you enter the selection criteria according to which you want to create the list of financial transactions.
- 3. Choose the Execute pushbutton (in the lower right of the entry screen).
- 4. The system displays a list of the selected transactions.
- 5. The list provides extensive options for structuring the rows and columns, and for sorting and displaying totals.
- 6. You also have the option of processing the transactions from the collective processing list.


- a. Select the transaction you want to process from the list.
- b. From the menu bar above the list display, you can select one of the buttons with which you can process the selected transaction:
- c. When you select a function, the corresponding processing mode appears, from which you can perform the necessary steps.


For more information about how to issue or receive trade finance transactions, see the following documentation:

Processing Letters of Credit as an Importer

Processing Letters of Credit as an Exporter

Processing Bank Guarantees as an Exporter

Processing Bank Guarantees as an Importer

Processing Standby Letters of Credit as an Importer

Processing Standby Letters of Credit as an Exporter

**Supported Device Types**

Desktop

Tablet

###### Time Deposit - Fast Processing

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Time Deposit - Fast Processing | L5 | trm06 p.152 | loio `4b07da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4b07da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The Time Deposit - Fast Processing function allows you to create a financial transaction directly without having to go through the initial screen. Money Market transactions are listed in a short overview. You can add the amount data, interest rate and the new end of term. This function enables you to process the transactions that are waiting to be rolled over or given notice on very quickly.

**Features**

The fast-processing function allows you to select and process fixed-term deposits and deposits at notice for several company codes in one step. This function is restricted to certain key fields. It helps you save time by enabling you to carry out the majority of the repetitive daily tasks from one entry screen. You can also branch to the detail screen for normal entry.

**Activities**

To use the Fast processing function:

- 1. Choose Trading Collective Processing Time Deposit - Fast Processing
- 2. Enter your selection criteria on the initial screen. Choose Program Execute or press the Execute button.
- 3. On the following screen, you see a list of the key data for the money market transactions selected. Now you can add the total amount, interest rate, end of term and the interest handling for rollover (payment, capitalization or deferral).
- 4. From this list, you can branch to the various processing functions shown at the top of the screen.


Carry out the following steps:

Position the cursor on a line of the list, in other words, on a transaction.

Then choose one of the processing functions in the application toolbar at the top of the screen.

By choosing Goto Change Statistics , you can get an overview of the changes made in time deposit fast processing function.

###### Define Credit Lines - Syndicated Facilities

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Define Credit Lines - Syndicated Facilities | L5 | trm06 p.153 | loio `3727bbd1f3684f2f82ee426fc777ddb8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3727bbd1f3684f2f82ee426fc777ddb8.html?locale=en-US)

Use this app (app ID: TCL1) to define the credit lines that appear under the Other Lines button in the General Details section (Structure tab) of a syndicated facility transaction.

Here you define the names of the credit lines available in a syndicated facility and whether drawings are permitted. To define a credit line as a parent line or subline, use the Other Lines button in the facility transaction.

The Drawing Permissible indicator lets you specify whether drawings are permitted for a credit line. The usual case is that drawings are only permitted for sublines, so you would leave the indicator unchecked for parent lines.

**Related Information**

Creating a Syndicated Facility Conditions (Facilities) Define Credit Lines - Syndicated Facilities

###### Change Counterparties for Financial Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Change Counterparties for Financial Transactions | L5 | trm06 p.153 | loio `7b9aecdd2bcf4c3f8f9be9db2cd1e197` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7b9aecdd2bcf4c3f8f9be9db2cd1e197.html?locale=en-US)

**Use**

Under usual circumstances, it is not possible to change the counterparty of a financial transaction. However, some circumstances may arise in which it becomes necessary to replace the counterparty. You use this program in such exceptional cases.

If you use Trade Repository Reporting (TRR), the system creates a trade repository object (TARO) with the action type 40Error or 45Notice and a TARO with the action type 10New. In this function, you specify in the Trade Repository Reporting area the type of notification that you would like to communicate the change in business partner to the trade repository. You also specify here the external transaction ID that is used by the financial transaction after novation.

If, when novation is performed, the financial transaction has not yet been reported to the trade repository (and consequently there is no TARO with the status Sent for this financial transaction), only the existing TARO is updated.

**Integration**

To change the counterparty, you need the following authorizations:

You need to have authorization for the transaction TRTM_CHG_PARTNER. (Authorization object F_T_TRANSB)

You need to have authorization to change the relevant financial transaction. (Authorization object T_DEAL_PD)

You need to have authorization for the business partner.

**Features**

The program replaces the counterparty of the financial transaction as well as the payment details and all relevant transaction flows.

Selection

General Selections

You use the following criteria for specify the financial transactions for which you want to replace the counterparty (business partner in role "0151 Counterparty"):

Company Code

Financial Transaction

Product Type

Transaction Type

Business Partner

Control

In the New Partner field, you specify the business partner that you want to be the new counterparty of the financial transaction.

In the Change Effective From field, enter the date from which the change in counterparty is effective.

If you set the Keep Payment Details of Previous Partner checkbox in the Payment Details, the payment details in the financial transaction are not changed.

You can execute the program first in a test run. To do so, set the relevant checkbox and execute the program.

When you run the program as an update run, the system saves the changes to the business partner in table TRTM_CHG_PARTNER.

You can use the program Display Financial Transactions with Changed Counterparty (transaction TRTM_CHG_PARTNER_DIS) to find all financial transactions for which the counterparty has been changed.

In the Trade Repository Reporting area, you first decide how you would like to communicate to the trade repository the change in counterparty in the financial transaction. You can choose between sending a TARO with action type 40Error or a TARO with action type 45Notice.

Further, you can choose between the following options regarding the external trade ID:

New external trade ID

If you already know the new external trade ID of the financial transaction, you can enter it directly for the specific trade repository.

Delete External Trade ID

Select this option if the financial transaction needs to acquire a new external trade ID after novation but you do not yet know the new external trade ID. The system then deletes the assignment of the existing external trade ID for the financial transaction. If you have set up the use of an interim trade ID in Customizing for Trade Repository Reporting, the system generates an interim trade ID and assigns it to the financial transaction.

Keep External Trade ID

Select this option if the financial transaction needs to retain the existing external trade ID.

In addition to the error/notice TARO, the system generates a TARO with the action type 10New. This TARO then contains the changed financial transaction data.

Output

The program issues a results list using the SAP List Viewer for SAP GUI (Classic). This list contains all affected financial transactions and shows the previous counterparty and the new counterparty.

**Activities**

- 1. Call the function Change Counterparty of a Financial Transaction (transaction TRTM_CHG_PARTNER) in the area menu of the Transaction Manager under Money Market/Foreign Exchange/Derivatives/Debt Management Back Office

Tools .

- 2. Select the affected financial transaction(s).
- 3. Enter the new counterparty.
- 4. Enter the date on which the change takes place.
- 5. If the payment details are not affected by this change, set the Keep Payment Details of Previous Partner checkbox.
- 6. Execute the program first in a test run.
- 7. When you are satisfied with the results displayed in the results list, execute the program in an update run.


The system makes the changes and generates the TAROs.

**More Information**

At any time, you can use the program Display Financial Transactions with Changed Counterparty to display all financial transactions for which you have replaced the counterparty.

###### Display Financial Transactions with Changed Counterparty

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Display Financial Transactions with Changed Counterparty | L5 | trm06 p.155 | loio `fd862b6e3d1d4afdb6cf51bca7c0f95b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fd862b6e3d1d4afdb6cf51bca7c0f95b.html?locale=en-US)

**Use**

You can use this program to display all financial transactions for which the counterparty has changed.

The results list contains the financial transaction number and data relating to the financial transaction, the new partner, the previous partner, and the change date.

The list is issued using the SAP List Viewer for SAP GUI (Classic).

**More Information**

Change Counterparties for Financial Transactions

###### Reference

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Reference | L5 | trm06 p.156 | loio `3919c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3919c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

A reference between Treasury transactions documents a relationship between “n” transactions. The reference category determines the type of reference.

References are supported in the money market, foreign exchange, derivatives, securities, and loans areas. In the securities and loans areas there is a General Reference category, which you can use to represent relationships between transactions in these areas. In other words, you can use this reference category to link any transactions you choose in these areas.

**Features**

Some references are created automatically when a certain activity is carried out. Others have to be created by the user. Reference categories, which are created automatically when you enter a transaction, can also be created manually.

|Reference category|Description|Comments|
|---|---|---|
|BID|Offer|Generated automatically|
|CON|SWIFT Confirmation Files|Generated automatically|
|EUR|Euro Transaction Currency Changeover|Generated automatically|
|MIR|Mirror Transaction - Link|Not supported|
|KMP|Netting|Create manually using the Netting function |
|OPT|Option Reference - Derivatives|Generated automatically|
|PRL|Rollover of Forex Transactions|Generated automatically|
|REF|General Reference|Create manually|
|SWP|Foreign Exchange Swap|Generated automatically|
|ICH|Issuance Contract Hedge|Create manually|
|IRE|Interest Rate Exposure|Create manually Use this reference category, for example, to reference a securities account position of an issued bond with variable interest flows with the interest rate swap which is used to hedge the variable interest flow. You can analyze financial transactions/securities account positions related by this reference category in the Debt and Investment Maturity Profile app.|


You can also use the Change Reference function (TBR7) to process existing references. You can also create references for reference categories that are normally generated automatically. This is the only function you can use, however, to create and process references manually. (Exception: You use the netting function to create and process references from reference category KMP (netting). You can, however, also use the collective processing function for references to edit existing references from this category).

The following functions are available for references:

Create Reference (App ID: TBR6)

You can create a reference between two or more transactions that are related to one another.

The system performs an internal check when you create references for the Option Reference - Derivatives, Rollover of Forex Transactions, and the Forex Swap categories.

You can create a general reference between any transactions you choose.

Edit existing references

You can change (TBR7 transaction code), display (TBR8 transaction code), or undo (TBR9 transaction code) existing references. These functions are also available from the Create Reference (App ID: TBR6)

**Note:**

Only in exceptional circumstances is it necessary to manually edit a reference that was created automatically. For example, if an option belonging to an option spread had to be reversed and you have to assign the new option to the other option again.

Collective Processing (only available in the back-end system with TBRL transaction code)

The collective processing report program enables you to display a list of references in one or several application areas. You can restrict your selections according to the following criteria:

Reference category

Reference

Status

Company code

Transaction

Order number

Loan number

Other selection parameters for netting transactions:

Business partner

Due date

An overview list is generated that displays the transactions selected for each reference.

From here you can jump to the detailed screen for the transaction you want to edit by positioning your cursor on the transaction and choosing Reference Change/Display/Undo . You can add individual transactions to a reference, or remove them.

To obtain an overview of all netting transactions with particular business partners involved in money market transactions:

- 1. Choose the Money Market application.
- 2. Choose the KMP (netting) reference category.
- 3. Restrict your selections to one or several partners
- 4. Run the program.


To obtain an overview of all references for a particular transaction:

- 1. Do not enter a reference category.
- 2. Enter the company code and the transaction number.
- 3. Run the program.


**Example:**

- (1) Interest Rate Exposure

- 1. Choose the Reference Category: IRE - Interest Rate Exposure
- 2. In the Object 1 to Be Linked area, choose the Company Code and the enter the Transaction.

For example, enter the financial transaction number of an interest rate swap used to hedge the variable interest flow of an issued bond.

- 3. In the Object 2 to Be Linked area, choose the Company Code and the enter the Securities Account and the Security Class.

For example, the issuance securities account and the security class ID of the issued bond hedged by the interest rate swap.

- 4. Save your entries.


You can analyze the references of the reference category in the Debt and Investment Maturity Profile app.

**Example:**

- (2) You run hedge accounting and want to hedge your currency risks with the help of a collar FX option. To do this, you first need to create two simple foreign exchange option transactions, which you link together manually in a second step. Proceed as follows:


- 1. Execute the function Create Financial Transaction.
- 2. Enter the following parameters:

Company Code

Product Type: 76A - OTC Forex Option

Transaction Type: 100 - OTC Forex Option Purchase

Partner

- 3. Select the flow type of your option premium:

1300 - Option Premium - Profit/Loss

1302 - Option Premium - Position

- 4. On the Structure tab, fill the following areas:


Exercise

Exercise Period

Exercise Type: European

Settlement

Premium

Payment Date

Currency

Amount

Contract

Contract Date

- 5. Go to the Underlying tab and enter the following parameters of your spot exchange transaction:

Purchase Currency: Risk currency (outgoing exposure) or local currency (incoming exposure)

Purchase Amount: Filled automatically

Sales Currency: Local currency (outgoing exposure) or risk currency (incoming exposure)

Sales Amount

Rate

Value Date: Filled automatically

Contract Date: Filled automatically

- 6. Go to the Administration tab and enter your hedging classification.
- 7. Now create a second FX option with Transaction Type 200 - OTC Forex Option Sales.

Enter the same parameters as for the first option.

- 8. Link both of the created FX options by using the Create Reference function (transaction TBR6). This creates a collar FX option.
- 9. Enter the following parameters:


**Note:**

The hedging classification must be flagged as hedge accounting relevant and must have the hedging profile for FX options and the designation type Two Instruments.

Reference Category: OPT - Option Reference - Derivatives

- Object 1 to Be Linked:

Company Code

Transaction

- Object 2 to Be Linked:


Company Code

Transaction

- 10. Save your entries.
- 11. The automatic designation is then triggered automatically and one or more hedging relationships are created. Together with the hedging classification, the reference category controls the designation process.


**Related Information**

Create Reference

###### Netting (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Netting | L5 | trm06 p.160 | loio `3619c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3619c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

The Netting function allows you to group together transactions from the Money Market, Foreign Exchange, Derivatives, and Securities areas and to pay them collectively. It is used to simplify payment processing.

Situations can arise where several financial transactions are to be paid collectively; this happens especially in the case of transactions with business partners that are not house banks, i.e payments need to be exchanged.

**Example:**

Fixed-term investment in EUR and fixed-term borrowing in EUR

You balance the open payment amounts and only pay or receive the net amounts

Advantage: Saving of transaction costs or bank charges

**Prerequisites**

The transactions need to have the following matching characteristics:

Company code

Business partner

(Payment) currency

Value Date: Recipient

Identical payment details

Payment methods must be the same

Payee (bank details in the item)

It is particularly important to note that all the transactions you want to net must be able to generate payment requests since netting transactions are paid using the Payment Program for Payment Requests.

Individual payments cannot be made.

The financial transactions must have obtained Settlement status.

Features

Assigning individual transactions to a netting transaction enables the payment program to process the payment requests collectively. To do this, all the payment flows or requests involved in the same netting transaction are assigned the same unique key. This key is written in the Grouping field and replaces the existing field contents. This ensures that the payment

requests belonging to one netting transaction are not grouped with other payment requests. The Payment Program for Payment Requests only groups requests that have the same company code and business partner (as mentioned in the prerequisites section) and the same Grouping field entry.

See also: Payment Requests

You cannot make subsequent changes to netting-relevant data in the individual transactions (especially due dates, amounts, house bank data, and payment data).

A transaction linked to a netting transaction is shown when processed. To display this, choose Environment Object Links .

In the Cash Flow for the transaction, in the Payment View layout, you can see the grouping key in the Grouping column.

When the transactions are confirmed (correspondence), they are assigned a reference to the other transactions involved.

|Function|Features|
|---|---|
|Proposal list for netting transactions|You can use this function to select transactions for netting. You can carry out the following functions: Create netting transactions. Display and edit netting transactions. Branch to transaction editing to enhance or adjust payment data. To do this, position the cursor on the transaction number and choose Goto Transaction  Display/Change/.... . For more information, refer to the program documentation for this report in the system.|
|Create|Create a netting transaction by directly entering a transaction for netting.|
|Change|Remove transactions from netting or include additional transactions.|
|Display|Display existing netting transactions.|
|Undo|Use this function to undo netting transactions.|


**Integration**

Netting transactions are Object Links used to link financial transactions (reference key: KMP).

**Activities**

Call the functions by choosing Transaction Manager Money Market/Foreign Exchange/Derivatives/Securities Back Office Netting .

###### Adjust Variable Rates/Prices

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Adjust Variable Rates/Prices | L5 | trm06 p.162 | loio `511c5f22c3db2919e10000000a421bc1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/511c5f22c3db2919e10000000a421bc1.html?locale=en-US)

**Use**

Interest Rate Adjustments

You can adjust interest rates for financial instruments based on variable interest rates either manually or automatically in order to calculate interest payables or receivables. With both methods, a reference interest rate is linked to an interest rate value for a specific date. Interest rates need to be adjusted for all interest- and price-relevant financial transactions on the planned determination date. With the interest rate adjustment, flows are created in the cash flow, and you can post these flows in FI (where applicable in combination with a posting release).

Foreign Exchange Rate Adjustments

For the netting of the flows of cross-currency interest rate swaps the flows need to be translated into the same currency. This currency is the settlement currency. For the translation to the settlement currency, you need to adjust/fix the related FX rate.

Price Index Adjustments

For price-index-related interest rate transactions, the interest amounts and repayment amounts are adjusted based on the price index fixing dates Low and High. The fixing dates for the price index values are determined from the Index Adjustment data on the Structure tab of the financial transactions.

Example: Determination of the price index value at calculation date of the flow

Assume the price index values are always entered on the first day of a month.

The interest period is the same as the price index calculation period.

Term start is 05/01/2021.

Term end is 07/01/2021.

Interest and the price index have a monthly frequency with the calculation date 06/01/2021.

Exponential interpolation is set for the price index adjustment condition.

Price index fixing date low is 04/01/2021.

Price fixing date high is 05/01/2021.

Price index base date is 05/01/2021.

The price index factor will be interpolated as follows:

For the flows within the first period between 05/01/2021 and 06/01/2021, using the price index values on 04/01/2021 and 05/01/2021

- For the flow with the calculation date 05/01/2021, using the value on 04/01/2021

- For the flow with the calculation date 06/01/2021, using the value on 05/01/2021


For the flows in between, using exponential interpolation. For example, for a flow with the calculation date 05/10/2021 with 10 days between 05/01/2021 and 05/10/2021, and 31 days for the whole interpolation period

- between 05/01/2021 and 06/01/2021.


For the flows within the next period between 06/01/2021 and 07/01/2021, using the price index values on

- 05/01/2021 and 06/01/2021.


- For the flow with the calculation date 06/01/2021, using the value on 05/01/2021.


- For the flow with the calculation date 07/01/2021, using the value on 06/01/2021.


For the flows in between, using exponential interpolation. For example, for a flow with the calculation date

- 06/20/2021 with t20 days between 06/01/2021 and 06/20/2021, and 30 days for the whole interpolation period


- between 06/01/2021 and 07/01/2021.


Price index adjustments are executed using the Process Automatic Adjustments - Rates/Prices app.

Securities Price Adjustments

Commodity Price Adjustments

When trading transactions are concluded for commodities in a currency that differs from the quotation currency of the related commodity-relevant financial instruments, the quoted price is automatically translated into the payment currency for commodity price fixing.

In transaction management, you specify the type of translation individually for each financial transaction. You can decide whether the currency translation occurs for each individual price (on the exact day) or at the end of quotation when the average price has been created.

Example:

If two business partners conclude transactions in EUR relating to the sale or purchase of commodities for which the derivatives (such as a commodity swap) are listed in USD on an exchange in the US, commodity price fixing requires the quotation currency USD to be translated into the payment currency USD.

For swaps with variable interest calculation, interest rate adjustments are made periodically over the term. For cross-currency interest rate swaps in settlement currency interest rate instrument, the FX rate also needs to be fixed.

The following apps are provided to carry out the process steps:

Create Adjustment - Rates/Prices

Display Adjustment - Rates/Prices

Change Adjustment - Rates/Prices

Reverse Adjustment - Rates/Prices

Run Automatic Adjustments - Interest Rates/Prices

Reverse Automatice Adjustments - Interest Rates/Prices

**Related Information**

Process Adjustments Manually - Rates/Prices Process Automatic Adjustments - Rates/Prices

###### Process Automatic Adjustments - Rates/Prices

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Adjust Variable Rates/Prices > Process Automatic Adjustments - Rates/Prices | L6 | trm06 p.163 | loio `d9c51b519f79fe74e10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d9c51b519f79fe74e10000000a423f68.html?locale=en-US)

**Use**

Interest rates, FX rates and prices can also be adjusted and reversed automatically. The following two apps are provided for this purpose and are described here:

Run Automatic Adjustments - Rates/Prices

With this app, you can adjust interest rates and prices automatically.

Enter the company code and fixing date.

**Note:**

The fixing date is the date up until and including which interest rates or prices are adjusted.

You can select all transactions or individual transaction numbers.

The subsequent log displays which interest rate adjustments were made, with which interest rate, and for which transactions, as well as for which transactions no adjustments were made.

One reason why an interest rate adjustment was not made is that there was no interest rate available.

Reverse Automatic Adjustments - Rates/Prices

With this app, you can reverse interest rate adjustments that have been created automatically. If an interest rate adjustment has been processed manually, the function can be reversed manually only.

**Caution:**

You can reverse interest rate adjustments only if the related interest flows haven't yet been posted.

Enter the company code and fixing date.

**Note:**

The fixing date is the date up until which the reversal applies. It is only possible to reverse backwards chronologically.

You can select all transactions or individual transaction numbers.

The system issues a log containing details on the financial transactions.

**General Features**

Call up the relevant transaction by selecting a row in the table and choosing the Details icon in the header bar

Display the long text of an error message by selecting an entry from the log and choosing Long Text in the header bar

Save a specific variant and/or layout according to your preferred settings

Export the log to a spreadsheet by choosing More List Export Spreadsheet

**Related Information**

Adjust Variable Rates/Prices

###### Process Adjustments Manually - Rates/Prices

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Adjust Variable Rates/Prices > Process Adjustments Manually - Rates/Prices | L6 | trm06 p.164 | loio `3fc51b519f79fe74e10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3fc51b519f79fe74e10000000a423f68.html?locale=en-US)

**Use**

Rate/price adjustments need to be made in order to calculate variable flows, such as interest flows..

With the following apps, you can manually process interest rate, FX rate, security price, or commodity price adjustments:

Create Adjustment - Rates/Prices

Display Adjustment - Rates/Prices

Change Adjustment - Rates/Prices

Reverse Adjustment - Rates/Prices

Key Features

|App|Functions|Comments|
|---|---|---|
|Create Adjustment - Rates/Prices|Adjust interest rates/FX rates/security price/commodity price.|Examples: Interest Rate Adjustment 1. Choose Interest Rate Adjustment in the Kind of Adjustment area. 2. Enter the Company Code. 3. Enter the number of the Financial Transaction. 4. You can also enter the specific Reference Interest Rate. 5. On the following Create Rate/Adjustment screen, you can see on the top the data of the financial transaction. In the Interest Rate Adjustment: Overview area, a table listing all interest rate adjustments relevant for the financial transaction provides the following information: Fixing Date Weekday (of the fixing date) RefIntRate Here you see the name of the reference interest rate. An icon showing the status of the adjustment: (not fixed)  Not Fixed (fixed)  Fixed Being processed Interest Rate Here you can see the interest rate for all adjustments in status Fixed. Start Payment Rate In the Interest Rate Adjustment: Details area, you can see the details for a specific adjustment. The following fields are shown: Int. Fixing Date Ref. Interest Rate Interest Rate|


|App|Functions|Comments|
|---|---|---|
| | |Fixed By Effective From Status Trigger IR Adjust. date/time 6. The Interest Rate Adjustment: Details for the upcoming interest rate adjustment in status Not Fixed is shown. 7. Choose Enter. FX Rate Adjustment 1. Choose FX Rate Adjustment in the Kind of Adjustment area. 2. Enter the Company Code. 3. Enter the number of the Financial Transaction. 4. Choose Enter. 5. On the following Create Rate/Adjustment screen, you can see on the top the data of the financial transaction. In the FX Rate Fixing: Overview area, a table listing all FX rate adjustments relevant for the cross-currency interest rate swap and settlement currency in interest rate instrument, provides the following information: Fixing Date Weekday (of the fixing date) Fixing Reference An icon showing the status of the adjustment: (not fixed)  Not Fixed (fixed)  Fixed FX Rate Here you can see the FX rate for all adjustments in status Fixed. Trigger In this field, you can see if the adjustments have been done manually or automatically. **Note:** For the FX rate adjustment, it’s only possible to use the Create|


|App|Functions|Comments|
|---|---|---|
| | |In the FX Rate Fixing: Details area, you can see the details for a specific adjustment. The following fields are shown: Fixing Date Fixing Ref. ID FX Rate Ratio Fixed By Effective From Fixing Status Trigger Rate Fix. Date Rate Fix. Time 6. The fixing details for the upcoming FX rate adjustment in status Not Fixed is shown. 7. Enter the FX Rate. You can enter FX rates with more than 30 digits, before or after the decimal point. 8. Save your entries. 9. The payment amount is recalculated with the entered FX rate. The adjustment status is changed to Fixed and the flows are relevant for posting. Adjustment - Rates/Prices app, where you enter the FX rate for the fixing date manually.|
|Display Adjustment - Rates/Prices|Display adjustment according to a specified company code, transaction number, and reference interest rate. Displays an overview of interest rate/FX rate adjustments sorted by fixing date for which the following statuses are possible: Fixed Not Fixed| |


|App|Functions|Comments|
|---|---|---|
| |In Processing| |
|Change Adjustment - Rates/Prices|Change an adjustment according to a specified company code, transaction number, and reference interest rate. Enter and fix an interest rate or FX rate for a selected flow.|**Note:** Interest rate or FX rate adjustments can be changed directly if the related interest flow hasn’t been posted, yet.|
|Reverse Adjustment - Rates/Prices|Reverse adjustments according to a specified company code, transaction number, and reference interest rate. The system then automatically resets the status from Fixed to Not Fixed.|**Note:**|


**More Information**

The following two apps allow you to automatically adjust rates and prices:

Run Automatic Adjustments - Rates/Prices

Reverse Automatic Adjustments - Rates/Prices

For more information, see Process Automatic Adjustments - Rates/Prices

For general information, see Adjust Variable Rates/Prices.

###### Updating Planned Records

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Updating Planned Records | L5 | trm06 p.168 | loio `b515da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b515da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use the Update Planned Records function for the derivatives Caps, Floors, Swaps, and Forward Rate Agreements (FRAs). You use this function to determine all planned records that are relevant or still exist.

Future interest payments are transferred to Cash Management so that the liquidity status is correct and up to date.

Flows with a fixed interest rate are transferred to Cash Management as soon as the transaction is created. The amounts for flows with variable interest rates need to be estimated because the percentage values of reference interest rates can change daily.

**Prerequisites**

In Customizing for Treasury and Risk Management under Transaction Manager General Settings Define Company Code Additional Data , in the menu Settings for Variable Interest Rates, you have specified in the Planned Record Update field the location from where the system takes the interest data.

To update the data to Cash Management, you have made the following Customizing settings:

In the activity Product Types, you have created a planning level to be assigned to the business transaction in Cash Management.

In the activity Define Flow Types, you have marked the interest flow as Relevant to Cash Management. If you do not set this indicator, a Cash Management block is applied.

**Activities**

- 1. Choose SAP Easy Access Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Derivatives Back Office Variable Interest Calculation Update Planned Records .
- 2. Enter the required data and choose Execute.


The system calculates the most recent interest rate.

###### Rate Fixing

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Rate Fixing | L5 | trm06 p.169 | loio `ac14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ac14da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You must fix FX rates for certain derivatives and foreign exchange transactions.

**Features**

You can fix FX rates manually or have the system fix them automatically. In foreign exchange trading there are two functions available:

When you opt for Automatic Fixing the system first imports the corresponding rate (as a rule the average rate) from the rates table. Subsequently, a premium/discount to the value of the separately defined fixing margin is calculated. This method allows you to use spreads that differ from the ask/bid spread.

If you use the Manual Fixing Processing function, you set the exchange rate manually.

You can use the Fix Average Rates report to determine FX rates for creating average rates or the Reset Average Rate Fixing to delete these rates.

When you fix FX rates, the transaction is transferred to the Contract activity.

###### Automatic Processing for FX Fixing

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Rate Fixing > Automatic Processing for FX Fixing | L6 | trm06 p.169 | loio `af14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/af14da531198434de10000000a174cb4.html?locale=en-US)

**Prerequisites**

Before you can use automatic processing for FX fixing, the FX rate table (TCURR) must be filled. The middle rate entered in the table for the fixing date is entered in the fixing transaction, and the fixing transaction is then transferred to the Contract activity.

**Procedure**

In the case of automatic fixing, the system first reads the corresponding rate (usually the middle rate) from the FX rate table. It then calculates a premium/discount to the value of the fixing margin defined in Customizing. This method allows you to use spreads that differ from the ask/bid spread.

For more information, see also the Customizing activity Assign Fixing Margins in the Implementation Guide (IMG).

- 1. Choose Back Office Rate Fixing Automatic Fixing Processing (transaction TBCS).
- 2. The Automatic Processing for Forex Fixing Transactions screen appears.
- 3. Enter the required selection parameters, for example:

Company code

Transaction

Portfolio

Treasury finance project

Date of rate fixing

- 4. You start the automatic processing of FX fixing transactions by choosing Program Execute .

###### Fix FX Rates

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Rate Fixing > Fix FX Rates | L6 | trm06 p.170 | loio `b214da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b214da531198434de10000000a174cb4.html?locale=en-US)

You must fix rates for derivatives and foreign exchange transactions that you have created.

The manual fixing app enables you to correct certain transactions or add additional data manually.

- 1. Open the Fix FX Rates app on the SAP Fiori lauchpad or choose Back Office Rate Fixing Manual Fixing (transaction TXV5) in the back-end system.
- 2. On the screen that follows, enter the company code and the transaction you want to process.
- 3. The data screen for spot/forward transactions appears.
- 4. You can now make any changes or add new entries in the active fields. For example, you set the exchange rate manually here.
- 5. The spot/forward transaction is now saved as a contract.

###### Fix Average Rates

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Rate Fixing > Fix Average Rates | L6 | trm06 p.170 | loio `cb14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cb14da531198434de10000000a174cb4.html?locale=en-US)

**Purpose**

This report is used to fix exchange rates for Average Rate Option , Basket Option or Correlation Option currency options.

For these types of currency options, dates are entered when the transaction is created. The exchange rates must be fixed for these dates. The settlement amount is determined from these dates when the option is exercised.

**Prerequisites**

All relevant exchange rates must be defined in the system for the key date.

**Process flow**

By means of selection parameters you can fix rates for separate transactions or for a number of transactions at the same time.

General selections:

You use determine the key date up to which rates must be fixed with the "up to and including rate date" parameter. For more information, see the example.

Indicator for only exact day rates:

If you set this indicator, rates are only taken into consideration when the exchange rate is determined if their date corresponds to the fixing date entered when the transaction was created. An error message is output if the system is unable to find any exchange rates for the relevant date.

If this indicator is not set, the system will first try to determine an “exact day” exchange rate. If this is not possible, rates that are in the past from the perspective of the default fixing date are also taken into account.

Log: Only display errors indicator:

If this indicator is set, information about successfully determined exchange rates is not displayed.

If you have not set this indicator, the log will include information about the exchange rates that were determined successfully in addition to errors.

**Example**

The following dates were defined for an average rate option. On these dates the exchange rate is to be determined between the leading currency EUR and the following currency USD for rate type A.

05/03/2004

05/10/2004

05/17/2004

05/25/2004

The report is started with the parameters

Up to and including rate date 05/10/2004

Only exact day rates X

The system contains all relevant rates for all dates up to and including 05/08/04.

**Result**

On the basis of the values in the up to and including rate date parameter, the report determines that 05/03/2005 and 05/10/2005 are to be fixed.

Fixing date 05/03/2005 is found in the table of exchange rates with a rate of 1.2083. This rate is stored in the database table for fixed exchange rates and can be seen in the relevant transaction dialog box.

No entry is found in the table of exchange rates for fixing date 05/10/2005. This error is written to the log. If the report had been started without the only exact date rates indicator being set, the system would have taken the next rate from 05/08/2005 instead of the 05/10/2005 rate and not it would not have output an error.

###### Reset Average Rate Fixing

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Apps for Processing Financial Transactions > Rate Fixing > Reset Average Rate Fixing | L6 | trm06 p.172 | loio `1814da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1814da531198434de10000000a174cb4.html?locale=en-US)

**Purpose**

You can use this report to delete fixed exchange rates for Average Rate Option , Basket Option or Correlation Option currency options.

**Prerequisites**

You fix rates with the Fix Average Rates report. If incorrect rates are fixed, you can delete them with this report. You can then fix the rates again with the Fix Average Rates report.

**Process flow**

By means of selection parameters you can delete the fixed rates for separate transactions or for a number of transactions at the same time.

As of and including rate date parameter:

This parameter determines as of what key date the fixed rates should be deleted.

**Example**

The following dates were defined for an average rate option. On these dates the exchange rate is to be determined between the leading currency EUR and the following currency USD for rate type A.

05/03/2004

05/10/2004

05/17/2004

05/24/2004

The rates were fixed using the Fix Average Rates report up to and including 05/10/2004.

The report is started with the parameters

As of and including rate date 05/10/2004

**Result**

On the basis of the values in the as of and including rate date parameter, the report determines that the fixed rates for 05/10/2005 are to be deleted. This rate is removed from the database table for fixed exchange rates. If you check the dates for rate fixing in the corresponding dialog window of the transaction, the deleted rate is no longer visible.

The log shows that the rate fixing for 05/10/2004 has been deleted.

##### Regulatory Reporting (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Regulatory Reporting | L4 | trm06 p.173 | loio `7d19da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7d19da531198434de10000000a174cb4.html?locale=en-US)

The premium reserves are created from insurance premiums and are disclosed as liabilities in the balance sheets of insurance companies. The premium reserves cover the assets belonging to the premium reserve fund.

This premium reserve fund must be created in order to fulfill German supervisory requirements. It is used to ensure that claims from insurance policyholders can be met.

The assets of the premium reserve fund are documented in premium reserve fund lists ( PRF Lists ). In general, a separate premium reserve fund is set up for each branch of insurance operated by an insurance company.

The premium reserve fund is divided into various asset categories. Examples of possible asset categories:

|Asset Category|Description|
|---|---|
|PRF 1|Registered bond|
|PRF 2|Registered debt|
|PRF 8|Bonds|
|PRF 9|Stocks|
|...|...|


The Stock Indicator and the insurance branch for each securities account are available in the SAP system. All values related to the securities account are assigned to the relevant asset grouping and insurance branch.

See also:

Regulatory Reporting

Premium Reserve Fund: Transfer

Premium Reserve Fund: Information

##### Manual Maintenance of Payment Reason in Financial Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Manual Maintenance of Payment Reason in Financial Transactions | L4 | trm06 p.173 | loio `c4f06afdfe844741ab91e5957ee3537e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c4f06afdfe844741ab91e5957ee3537e.html?locale=en-US)

You can manually determine payment reason for the purpose code.

**Context**

Manual maintenance of the payment reason is available for flows that can be manually changed.

Prerequisite

You have defined all required payment reasons using the Define Payment Reason configuration activity available in your configuration environment.

You can maintain payment reason manually in Create Financial Transaction (FTR_CREATE) app and Process Financial Transaction (FTR_EDIT) app under the Cash Flow tab

for individual maintenance of the payment reason choose Edit Flow from the context menu

maintain payment reason in the PaytReason field under the Payment area

for mass maintenance of payment reasons select Editing Mode and choose Edit Payment Reason

maintain payment reasons in the Payment Reason column of the Cash Flow table

**Note:**

System displays only the flows, for which the payment reason can be maintained. Mass change is enabled in financial transaction with many flows, for example Interest Rate Instruments andSwaps.

##### Situation Template: Processing of Financial Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Situation Template: Processing of Financial Transactions | L4 | trm06 p.174 | loio `4948d4df94f342c89546e89977c221d1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4948d4df94f342c89546e89977c221d1.html?locale=en-US)

Situation Template ID: FIN_TRM_FINTRANS_PROCG

**Business Value**

This template for situation handling informs users about any events in financial transactions that require action, such as maturing, fixing, expiration.

You want to notify business users if financial transactions acquire a specific status that requires further action. For example, if a foreign exchange option (product type 76A) expires today and needs to be exercised, a notification is sent.

Several channels are available, such as the notification area on the SAP Fiori launchpad or e-mail. In-app notifications in the Manage Financial Transactions app are currently not supported.

**Note:**

For customers choosing a hub deployment for their SAP S/4HANA system, e-mail notifications are only supported for front-end and back-end systems with SAP gateway component SAP_GWFND release 754 or higher.

**Default Settings**

The template comes with predefined settings. For the settings that aren't visible or self-explanatory, you can find information in the following sections. For generic information about how to configure situations based on this template, refer to the documentation of the Manage Situation Types app with which you can display and use the template.

Situation Trigger Object and Anchor Object

These technical settings define for which object a situation is displayed (anchor object) and the object based on which a situation is triggered (trigger object):

|Trigger Object|Financial Transaction|
|---|---|
|CDS View for Trigger Object|C_FinancialTransactionSitn|
|Anchor Object|Financial Transaction|
|CDS View for Anchor Object|C_FinancialTransactionSitn|
|Trigger Type|Batch|


The situation is triggered if the criteria you define apply to a financial transaction.

**Note:**

These settings aren't visible in the template in the Manage Situation Types app and cannot be changed when you create a situation type based on this template. All of the following settings are visible in the template and you can adapt them when you copy the template to create a situation type.

Conditions

The condition in this situation template defines that a situation is created with the status Open when a financial transaction is changed and that a notification is sent when this happens. Various filter parameters, such as Activity Category, Company Code, Product Type, and Contract Date, are also predefined in the situation template. You can use the Company Code filter, for example, if you want situations to be triggered only for a specific company code. A typical use case is to choose a date several days in advance of the term end to notify users about the due date of a transaction. The full list of fields is listed in the corresponding CDS view Financial Transaction Situation.

For more information, see Conditions.

Situation Display

When situations occur, users are informed about them by various texts. Note that this situation template supports only notifications by e-mail and on the SAP Fiori launchpad. Note that any information entered in the In-App Situation Message section is not shown in the Manage Financial Transactions app, because in-app notifications are currently not supported by this template.

**Note:**

When you copy the template and adapt it to your needs, you can define the notification settings and change all text elements in this section. After making the changes in the original language, please remember to translate these changes into the other languages that you want to use. The template comes with translations that can be changed directly when you copy the template.

For more information, see Situation Display.

Recipients

In this section, you see the predefined settings for determining who is responsible for a situation instance. Based on these, you can define who receives a notification when a situation instance is triggered (if enabled) or who sees the instance in the My Situations app.

You can restrict the responsibilities to specific teams and team members in the Responsibility by Teams field.

For more information, see Recipients.

Situation Monitoring

If you enable this option for a situation type, you can track the activities that are performed for situation instances with the Monitor Situations app. This option also enables the creation of business situation events.

**Related Information**

My Situations Financial Transaction Situation Situation Handling

###### How to Create a Custom Situation Type for Processing Financial Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Situation Template: Processing of Financial Transactions > How to Create a Custom Situation Type for Processing Financial Transactions | L5 | trm06 p.176 | loio `0105b9b4075244089132bdeea1305e98` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0105b9b4075244089132bdeea1305e98.html?locale=en-US)

Use the template FIN_TRM_FINTRANS_PROCG to create custom situation types for financial transactions.

**Use**

In this situation template, you can define events that trigger notifications by email or on the SAP Fiori launchpad to get the attention of business users, such as traders who are working with financial transactions.

Users are notified automatically about transactions that need immediate action because of approaching events like maturities or expiration dates. Additional fields let you narrow down the transactions by company code, counterparty, portfolio, and various other attributes.

**Effects on Configuration**

You need to perform several configuration steps before you can use this situation template:

In this situation template, you must use FSCM_TRM wherever a team category is required during the configuration of a custom situation type.

If the scope item 20J is activated, content for Responsibility Management is predelivered. If the scope item is not activated, a key user must configure the configuration activities listed under Configuration Options for Key Users.

You must also configure authorizations to use this situation template. Refer to Define Authorizations for Apps (Optional) to configure the authorizations for Situation Handling.

**Note:**

Note: The following multimedia content displays screens and interfaces in English only.

[figure TRM06-F090]

Open this video in a new window

**Create Ready-to-Use Situation Types with the Manage Situation Types App**

|Step|Description|
|---|---|
|1|On the SAP Fiori launchpad, log on with the user BPC_EXPERT.|
|2|Open the Manage Situation Types app.|
|3|Search for the FIN_TRM_FINTRANS_PROCG (Processing of Financial Transactions) template.|
|4|To copy this standard situation template, select it and choose Copy.|
| |The system creates a new situation type.|
|Admin Information| |
|5|In the New Situation Type screen on the Admin Information tab, enter an ID for the new situation type, for example TERM_END_CC_1010.|
| | |
|Conditions| |
|6|Name / Value: Company Code 1010; Product Category 780 - Forward; Product Type 60A - Foreign Exchange; Term End NEXT14DAYS. The Conditions section shows a list of conditions and a list of filters. In the list of filters, you can set values for notifications using the value help (F4). To trigger a notification for any FX forward by company code 1010 ending in the next 14 days, enter the following values: Condition 1 To add more conditions, choose Create in the list of conditions. Notifications will be triggered if any single one of the conditions applies.|
|Batch Job Scheduling| |
|7|Field Name / Value: Time Zone UTC; Start Batch Job At 15:00. Here you define how often your system checks the conditions. You can enter a time zone and a start time (24-hour format), for example:|


|Step|Description|
|---|---|
|Situation Display| |
|8|This section contains two subsections: The In-App Situation Message subsection is for in-app notifications. The fields here are mandatory, but anything you enter here will not be used, since this template does not support in-app notifications. In the Notification subsection, you can define notifications for the SAP Fiori launchpad in the Secure Notification Details input box and email notifications in the Public Notification Details input box. The two checkboxes let you control the sending behavior: Resend Notifications If activated, notifications for the same event are resent every day. Aggregate Notifications If, for example, you have 6 transactions that will expire in the next 14 days, 6 notifications are sent. Select this box to combine these notifications into a single one.|
|Recipients| |
|9|In this section, you see the predefined settings from the Manage Teams and Responsibilities app. Based on these settings, you can define who receives a notification when a situation instance is triggered (if enabled) or who sees the instance in the My Situations app. You can restrict the responsibilities to specific teams and team members in the Responsibility by Teams field.|
|Situation Monitoring| |
|10|Enable the Monitor Instances option to track the activities that are performed for your defined instances in the Monitor Situations app. This option also enables the creation of business situation events. |
|11|Choose Create to save this situation type. A text box appears that lets you choose whether to enable the situation type right away.|
|Result: You can now find the situation type Y_TERM_END_CC_1010 in the Manage Situation Types app under Situation Types. Here you can enable or edit it or navigate directly to the Monitor Situations app. | |


**Define a Team with the Manage Teams and Responsibilities App**

|Step|Description|
|---|---|
|1|Open the Manage Teams and Responsibilities app from your SAP Fiori launchpad. |
|2|Choose Create to create a new team.|


|Step|Description|
|---|---|
|Team Information| |
|3|Field / Value: Name FSCM_TRM; Description Treasury and Risk Management Team; Type STRM_FOE or STRM_BOE. Under Team Information General Information , enter a name and a description, such as:|
|Responsibility Definitions| |
|4|To restrict this team to the same company code that you set in the situation, choose Responsibility Definitions and enter company code 1010, for example.|
|Team Owners| |
|5|Under Team Owners, choose Create to add the team owner(s).|
|Team Members| |
|6|Under Team Members, choose Create to add team members.|
|7|Choose Save and make sure that your defined situation is ready to use.|
|8|Under Team Information General Information , set the status to Enabled.|
|Result: You can now wait for the batch job to run or start the batch job immediately with the Manage Situation Types app. Search for the situation type you have just created (Y_TERM_END_CC_1010), select it, and choose Trigger Now. The system now creates situations and sends automatic notifications to the team members.| |


**Check Sent Notifications for a Situation Type**

On the SAP Fiori Launchpad

|Step|Description|
|---|---|
|1|Log on with a user that is defined as a team member.|
|2|On the SAP Fiori launchpad, simply click the notification icon to see the available notifications. You can click each of them to see which transaction is about to expire and needs immediate action. You can click the notification to navigate directly to the Manage Financial Transactions app.|


E-Mail Notifications

|Step|Description|
|---|---|
|1|Check the email inbox of a user that is defined as a team member.|
|2|The public notification defined in the situation type appears, containing a link to the SAP Fiori launchpad where the recipient can check the Manage Financial Transactions app for further details.|

##### Feature Comparison for Collective Processing Apps for Financial Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Feature Comparison for Collective Processing Apps for Financial Transactions | L4 | trm06 p.180 | loio `ef7f3a881b514f24a826becbfa43c3b6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ef7f3a881b514f24a826becbfa43c3b6.html?locale=en-US)

The following table compares the features offered by various apps in the area of Treasury and Risk Management for managing financial transactions. The column headings contain links to the app documentation and the app's entry in the SAP Fiori apps reference library.

|App Name|Collective Processing: Transaction Management |Manage Financial Transactions|
|---|---|---|
|App ID|Transaction code: FTR_00|App ID: F6157 |
|Supported product categories|All product categories supported in SAP S/4HANA. For the full list, see Overview of Financial Instruments. |For the full list, see Manage Financial Transactions. |
|Number of available filter attributes|12|More than 100|
|Sorting of attributes|Attributes shown in combined columns|One column per attribute for easy filtering|
|Create new financial transaction|No|Yes|
|Quick filter bar by product category|No|Yes|
|Simplified toolbar for further processing of transactions|No|Yes|
|Transaction amounts split into different columns for better overview|No|Yes|
|Save variant as tile on SAP Fiori launchpad|Not applicable|Yes|
|Situation handling: Custom notifications for transactions that need further processing with direct link to transaction|Not applicable|Yes|


**Related Information**

Collective Processing: Transaction Management Manage Financial Transactions

##### Intercompany Trading Process

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Intercompany Trading Process | L4 | trm06 p.180 | loio `1508da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1508da531198434de10000000a174cb4.html?locale=en-US)

Use

This process enables you to create mirror transactions in order to avoid the double entry of transactions that are concluded between two companies (parent and subsidiary) within a group. When you create a transaction in the company code of the issuing company, the mirror transactions are automatically generated in the company code of the receiving company.

This mirror function is available in only one direction. For example, the parent company can place a fixed-term deposit with its subsidiary, but not the other way around.

**Prerequisites**

The parent company and its subsidiaries are separate company codes within the same client.

Each business partner is a company code in the system.

You must enter the required settings in Customizing for Treasury and Risk Management under Transaction Manager General Settings Transaction Management Distribution of Mirror Transactions .

**Activities**

After you have created a financial transaction, the structural data of the transaction is mirrored 1:1, that is, the payment flows are mapped in the opposite direction to those of the original transaction. In display mode, a message appears saying that a mirror transaction now exists.

**Example**

Original Transaction

|Purchase USD 1 m for EUR at 1.00|Counterparty B|
|---|---|
|Company code A01| |


Mirror Transaction

|Counterparty A|Sale USD 1 m for EUR at 1.00|
|---|---|
| |Company code B01|


The mirrored transactions are linked to each other and also reference each other. The reference belongs to the MIR type (Mirror Trans. - Link).

You can display this linkage from the financial transaction by choosing Environment Object Links . You display the references by double-clicking Mirror Trans. - Link, and you can go to the corresponding transactions from here.

After you have entered a mirror transaction, SAP recommends that you leave the transaction and then go back to the display of the transaction where you can check the object links.

You can also view object linkages by choosing Back Office Reference Collective Processing .

**Note:**

Mirror transactions cannot be created retroactively for existing transactions.

Note regarding foreign exchange swaps:

You do not need to make any special Customizing settings for forex swaps. You need to change the Customizing settings for other transactions in foreign exchange trading.

Four transactions arise when a forex swap is mirrored. A spot transaction and a forward transaction are created in each of the two company codes involved.

The reference category SWP (forex swap) also appears in this context. The spot transaction and forward transaction in one company code are linked by the SWP reference.

###### Intercompany Trading Process for Debt and Investment Management

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Intercompany Trading Process > Intercompany Trading Process for Debt and Investment Management | L5 | trm06 p.182 | loio `cf2650dce2c84937a3f1af4e0b096914` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cf2650dce2c84937a3f1af4e0b096914.html?locale=en-US)

Intercompany trading process for interest rate instrument and current account-style instrument transactions

**Use**

This process enables you to enter debt and investment transactions if the counterparty is an affiliated company. When you create a debt and investment transaction (interest rate instrument and current account-style instrument transactions) in the company code of the issuing company, mirror transactions will be generated automatically in the company code of the receiving company.

**Integration**

For more information, see also Creating and Changing Mirror Transactions.

**Features**

Once a debt and investment transaction is created in the issuing company, a mirror transaction is created automatically in the receiving company. Changes made to mirror-relevant fields in one of the two related transactions are mirrored automatically in the other transaction, but only for product category 550. For details, see Creating and Changing Mirror Transactions.

The intercompany trading process is only available for the following product type and transaction type combinations:

55I Interest Rate (IR) Instrument transactions with the following transactions types:

100 Investment

200 Borrowing

58I Current Account-Style Instrument(CA-Style Instrument) transactions with transaction type 300 Investment/Borrowing

**Related Information**

Create Current Acct-Style Instruments Processing Current Account-Style Instruments Creating an Interest Rate Instrument Processing Interest Rate Instruments

###### Changing Mirror Transactions (Foreign Exchange)

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Intercompany Trading Process > Changing Mirror Transactions (Foreign Exchange) | L5 | trm06 p.182 | loio `deb4e6456c594e7d887f57eab6a3101f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/deb4e6456c594e7d887f57eab6a3101f.html?locale=en-US)

This section describes the process for mirroring changes to existing intercompany transactions for foreign exchange transactions.

**Prerequisites**

Make sure you have made settings in the following Customizing activities::

- 1. ICT - Maintain Relevant Product Types and Transaction Types

You determine the product types and transaction types for which mirror transactions can be created between the affiliated companies.

- 2. ICT - Assign Company Code to Partners

You have different company codes representing the affiliated companies of your enterprise. If you want to use the mirror transaction functionality, you have to create a business partner for each affiliated company code.

- 3. ICT - Specify Mirroring Mode for Processing of Financial Transactions

Specify whether you also want to mirror changes made to existing mirrored intercompany transactions or not. This means that all mirror-relevant field values are changed automatically in the related transaction when you make changes to an intercompany transaction.

- 4. ICT - Map Product Types and Transaction Types

Define a mapping table for different product and transaction types.

- 5. ICT - Map Flow Types


Map the flow type for intercompany trading.

**Changing Mirror Transactions for Foreign Exchange Instruments**

Creating mirror transactions is possible for all foreign exchange (product category 600) transactions.

Changes to the following fields can be mirrored:

All fields on the Structure tab, except Contact Person and External Reference

Other flows based on your configuration

The following actions can be mirrored:

Change

Settle

Terminate

Reverse

Fixing (for NDF)

**Note:**

If the mirroring mode is set to Mirror Processing of Financial Transactions, settlement and reversal of a settled transaction are not mirrored. If the mirroring mode is set to Mirror Processing of ICo Transactions incl. Settlement, all actions are mirrored.

**Note:**

The transaction type of the original transaction and the transaction type of the mirror transaction must have the same processing category. This means either both of them are waiting to be settled or neither of them is waiting to be settled.

**Customizing Details**

**Note:**

Depending whether the processing category configured in the configuration activity Define Transaction Types - FX Transactions includes settlement, transactions may have a settlement activity status or not. The settlement activity statuses are Contract Settlement, Fix Settlement (for NDF) and Terminate Settlement. The activity status influences the mirroring behavior.

In the configuration activity ICT - Specify Mirroring Mode for Processing of Financial Transactions, you can set the mirroring mode to Mirror Processing of Financial Transactions to activate mirroring for already created intercompany transactions. This means that if an intercompany transaction is processed as described below, the related mirror transaction is also updated automatically. This option does not mirror settlement acitivities.

To mirror settlement activities, set the mirroring mode to Mirror Processing of ICo Transactions incl. Settlement. If you choose this setting, all actions including settlement and reversal of settlement are mirrored for intercompany transactions.

For example, if you change the value of the Amount field for an intercompany transaction based on product category 600 from 100 to 200, the amount will also change in the corresponding mirror transaction.

Check for Settlement of a Mirror Transaction

There are two special checks for the Settle action, if the transactions are mirror-relevant:

- 1. If you try to edit mirror-relevant fields during settlement, you get an error message.
- 2. In the following cases, you must first reverse the mirror transaction before settlement:


- a. The transaction to be settled does not have a settlement activity status.
- b. The mirror transaction has a settlement activity status.
- c. The values of mirror-relevant fields in the two transactions are incompatible.


**Example:**

Transaction A and transaction B are a pair of mirror transactions. They have the Contract activity status and the values in all mirror-relevant fields are compatible. The following steps explain the second error case:

- 1. Settle transaction A and transaction B individually. They will both have the Contract Settlement activity status.
- 2. Change mirror-relevant fields in transaction A. For example, change one other flow and save it. This update will also apply to transaction B. The other flow will change in both transactions.
- 3. Reverse transaction A. Because transaction A has a settlement activity status, only transaction A will be reversed back to the Contract activity status, where the changed other flow does not exist. Transaction B remains in the Contract Settlement activity status, and the other flow is unchanged. Now the other flows in the two transactions are incompatible.
- 4. Settling transaction A will be forbidden, because if it were to be settled, transaction A and transaction B would have the same activity status, even though mirror-relevant fields (other flows) are incompatible. The solution is to also reverse


transaction B back to the Contract activity, where the new other flow does not exist. This way, the mirror-relevant fields will be compatible again.

Mapping of Flow Types

There are two steps to map flow types in mirror transactions, based on the flow type in the original transaction: First, the system checks which flow type is mapped in the configuration activity ICT - Map Flow Types , based on combinations of product types and transaction types.

If a matching flow type is found here, this flow type is used for the mirror transaction. If no flow type is found, a default flow type is used for the mirror transaction.

The system then runs a check on the mapped flow type in the mirror transaction to see if the result matches the original transaction's flow type.

**Example:**

The original transaction has the flow type A.

Flow type A is mapped to flow type B in the mirror transaction.

The system now checks how flow type B is mapped - the result is flow type C.

If flow type C equals flow type A, the check is passed. If not, you get a message informing you that the flow types don't match. In this case, check your configuration under ICT - Map Flow Types and make sure that the flow types of the mirror transaction and the original transaction have a 1:1 relationship.

Mirroring of Other Flows

If you make any changes to a flow on the Other Flows tab when changing, rolling over or terminating an intercompany transaction for an interest rate instrument, you will see a confirmation message that the corresponding mirror transaction will be changed, but only if the flow type is mapped in the configuration activity ICT - Map Flow Types. Other flows that are not mapped here are not mirrored, and you will not see a confirmation message if you change such flow types. Other flows cannot be changed during settlement or reversal, so no changes to other flows are mirrored here.

To edit existing other flows, double click the relevant line in the table and make your changes in the dialog that appears. Click Copy in this dialog to save your changes. If the other flow is mirror-relevant, you see a message that the mirror transaction will be changed. For more information, see Other Flows.

Locking Behavior

For the following actions, both transactions are locked and your changes are mirrored. Note that you need to set the mirroring mode to Mirror Processing of ICo Transactions incl. Settlement, if you want to mirror settlement activities:

Change

Settle

Terminate

Reverse

Fixing (for NDF)

**Related Information**

Intercompany Trading Process Process Spots/Forwards - Collective Processing

###### Creating and Changing Mirror Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Financial Transaction Management > Intercompany Trading Process > Creating and Changing Mirror Transactions | L5 | trm06 p.186 | loio `e9b21ee6497b453e9540059103ee4d94` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e9b21ee6497b453e9540059103ee4d94.html?locale=en-US)

This section describes the process for mirroring intercompany transactions for debt and investment transactions.

**Use**

You can use the mirror transaction function to avoid the double entry of transactions that are concluded between two companies within a group (intercompany transactions). When you create a debt and investment transaction with a business partner that is an affiliated company, another transaction is automatically created with opposing payment flows in the other company code.

**Customizing**

Make sure you have made settings in the following Customizing activities:

- 1. ICT - Maintain Relevant Product Types and Transaction Types

You determine the product types and transaction types for which mirror transactions can be created between the affiliated companies.

- 2. ICT - Assign Company Code to Partners

You have different company codes representing the affiliated companies of your enterprise. If you want to use the mirror transaction functionality, you have to create a business partner for each affiliated company code.

- 3. ICT - Specify Mirroring Mode for Processing of Financial Transactions

Specify whether you also want to mirror changes made to existing mirrored intercompany transactions or not. This means that all mirror-relevant field values are changed automatically in the related transaction when you make changes to an intercompany transaction.

- 4. ICT - Map Product Types and Transaction Types

Define a mapping table for different product and transaction types.

- 5. ICT - Map Flow Types


Map the flow type for intercompany trading.

**Creating Mirror Transactions**

Creating mirror transactions is possible for interest rate instrument (product category 550) and current account-style instrument (product category 580) transactions in the Debt and Investment area. Mirroring of changes to existing transactions is only available for interest rate instruments (product category 550).

After you create a debt and investment transaction, the structural data of the transaction is mirrored 1:1, that is, the payment flows are mapped in the opposite direction to those of the original transaction.

Original Transaction

|Borrow 1 m USD|Counterparty B|
|---|---|


|Company code 1010| |
|---|---|


Mirror Transaction

|Counterparty A|Invest 1 m USD|
|---|---|
| |Company code 1020|


After entering a mirror transaction, SAP recommends that you leave the transaction and then go to the Process MM Transactions

- Collective Processing app to display the transaction, where a message appears saying that a mirror transaction now exists in the company code of the counterparty.

**Mirroring of Changes in Intercompany Transactions**

**Note:**

Depending whether the processing category configured in the configuration activity Define Transaction Types - MM Transactions includes settlement, transactions may have a settlement activity status or not. The settlement activity statuses are Contract Settlement, Rollover Settlement and Give Notice Settlement. The activity status influences the mirroring behavior.

In the configuration activity ICT - Specify Mirroring Mode for Processing of Financial Transactions, you can set the mirroring mode to Mirror Processing of Financial Transactions to activate mirroring for already created intercompany transactions. This means that if an intercompany transaction is processed as described below, the related mirror transaction is also updated automatically. This option does not mirror settlement acitivities.

To mirror settlement activities, set the mirroring mode to Mirror Processing of ICo Transactions incl. Settlement. If you choose this setting, all actions including settlement and reversal of settlement are mirrored for intercompany transactions.

For example, if you change the value of the Amount field for an intercompany transaction based on product category 550 from 100 to 200, the amount will also change in the corresponding mirror transaction.

The following requirements apply for mirroring of changes in intercompany transactions:

If a transaction has the product category 550, the following actions can be mirrored:

Change

Settle

Roll Over

Give Notice / Terminate

Reverse

**Note:**

If the mirroring mode is set to Mirror Processing of Financial Transactions, settlement and reversal of a settled transaction are not mirrored. If the mirroring mode is set to Mirror Processing of ICo Transactions incl. Settlement, all actions are mirrored. The particularities for these actions are described below.

Mirroring of changes is only implemented for intercompany transactions based on product category 550.

The transaction type of the original transaction and the transaction type of the mirror transaction must have the same processing category. This means either both of them are waiting to be settled or neither of them is waiting to be settled.

Only mirror-relevant field values are mirrored. This includes all fields on the Structure tab, except Contact Person and External Reference, all conditions and all main flows (changes in capital structure).

Check for Settlement of a Mirror Transaction

There are two special checks for the Settle action, if the transactions are mirror-relevant:

- 1. If you try to edit mirror-relevant fields during settlement, you get an error message.
- 2. In the following cases, you must first reverse the mirror transaction before settlement:


- a. The transaction to be settled does not have a settlement activity status.
- b. The mirror transaction has a settlement activity status.
- c. The values of mirror-relevant fields in the two transactions are incompatible.


**Example:**

Transaction A and transaction B are a pair of mirror transactions. They have the Contract activity status and the values in all mirror-relevant fields are compatible. The following steps explain the second error case:

- 1. Settle transaction A and transaction B individually. They will both have the Contract Settlement activity status.
- 2. Change mirror-relevant fields in transaction A. For example, add one new main flow and save it. This update will also apply to transaction B. They will both have one new main flow.
- 3. Reverse transaction A. Because transaction A has a settlement activity status, only transaction A will be reversed back to the Contract activity status, where the new main flow does not exist. Transaction B remains in the Contract Settlement activity status, and the main flow is unchanged. Now the main flows in the two transactions are incompatible.
- 4. Settling transaction A will be forbidden, because if it were to be settled, transaction A and transaction B would have the same activity status, even though mirror-relevant fields (main flows) are incompatible. The solution is to also reverse transaction B back to the Contract activity, where the new main flow does not exist. This way, the mirror-relevant fields will be compatible again.


Mapping of Flow Types

There are two steps to map flow types in mirror transactions, based on the flow type in the original transaction: First, the system checks which flow type is mapped in the configuration activity ICT - Map Flow Types , based on combinations of product types and transaction types.

If a matching flow type is found here, this flow type is used for the mirror transaction. If no flow type is found, a default flow type is used for the mirror transaction.

The system then runs a check on the mapped flow type in the mirror transaction to see if the result matches the original transaction's flow type.

**Example:**

The original transaction has the flow type A.

Flow type A is mapped to flow type B in the mirror transaction.

The system now checks how flow type B is mapped - the result is flow type C.

If flow type C equals flow type A, the check is passed. If not, you get a message informing you that the flow types don't match. In this case, check your configuration under ICT - Map Flow Types and make sure that the flow types of the mirror transaction and the original transaction have a 1:1 relationship.

Synchronization of Main Flows

Only the first main flow is mirrored during creation of a mirror transaction. Additional main flows are not mirrored. In addition, some fields inside the first main flow are also not mirrored when you create a mirror transaction, for example Exclusive Indicator and Month-End Indicator.

Therefore, the system tries to synchronize the main flows automatically. It runs a check to detect whether the main flows in the two mirror transactions match. If they don't match, the system will synchronize them.

This synchronization only runs during the first update on a newly created pair of mirror transactions. If the synchronization is successful, you will see a message informing you that the mirror transaction was synchronized.

Locking Behavior

For the following actions, both transactions are locked and your changes are mirrored. Note that you need to set the mirroring mode to Mirror Processing of ICo Transactions incl. Settlement, if you want to mirror settlement activities:

Change

Roll Over

Give Notice / Terminate

Settle

Reverse

**Related Information**

Create IR Instrument Processing Interest Rate Instruments Intercompany Trading Process for Debt and Investment Management

