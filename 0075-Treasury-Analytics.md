# Treasury Analytics - SAP TRM Knowledge Base (branch split)

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

### Treasury Analytics

> **Path:** Treasury and Risk Management > Treasury Analytics | L2 | trm01 p.128 | loio `fc1ebb0d30ac4749ae41aa642ac9cdc7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fc1ebb0d30ac4749ae41aa642ac9cdc7.html?locale=en-US)

Treasury and Risk Management provides you with a wide range of ready-to-use analytical apps. In addition, you can use a range of CDS views for your own customer-specific analytical reporting.

**Treasury Analytics**

Apps

In the Treasury Reporting business group on the SAP Fiori launchpad, you find various apps that provide you with comprehensive information about the financial status and the current status of your credit lines as well as apps that you can use to analyze your financial transactions, treasury positions, and market data.

For the available reporting funtionality of the Transaction Manager in the back end system, see also Information System.

CDS Views

In addition to the reporting apps delivered, a broad range of CDS views have been provided. Using released CDS views as a basis, you can create your own query views. CDS query views can be used by any tool that supports CDS views, such as the Analysis for Microsoft Office, Design Studio, SAP Lumira, or SAP Analytics Cloud. For more information about CDS views, see also CDS Views. To get an overview of the CDS views released for Treasury and Risk Management, see also CDS Views for Treasury and Risk

Management.

Treasury Executive Dashboard in SAP Analytics Cloud application

You will find the Treasury Executive Dashboard story as example content in the SAP Analytics Cloud application. The story is based on the available CDS query views for Treasury Management in the back-end system. The following two packages for Treasury and Management are available in SAP Analytics Cloud:

Treasury Management for SAP S/4HANA 2022 and Cloud

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2022 and subsequent releases and SAP S/4HANA Cloud Public Edition.

Treasury Management for SAP S/4HANA 2020

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2020 and subsequent releases.

The two packages both contain a story for the Treasury Executive Dashboard. The difference is that two CDS views have been replaced with a new version with some technical improvement. The exchange of some CDS views in the package Treasury Management for SAP S/4HANA 2022 and Cloud has improved the performance of the Treasury Executive Dashboard.

For more information, see also Treasury Executive Dashboard Available in SAP Analytics Cloud.

#### Financial Status

> **Path:** Treasury and Risk Management > Treasury Analytics > Financial Status | L3 | trm01 p.129 | loio `fff288578e956a2be10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fff288578e956a2be10000000a441470.html?locale=en-US)

**Use**

This analytical app displays the financial status of a company or group of companies on a specific key date and allows you to drill down to individual financial positions. These financial positions can have either of the following data sources based on userdefined parameters:

Treasury position management for treasury positions from Treasury and Risk Management

One exposure for bank account balances from Cash Management

One document balances for account balances from the general ledger

Each financial position represents either a specific asset or liability position. Financial position groups are used to structure how financial positions are displayed in the Financial Status app. The financial position groups of the assets are displayed followed by the financial position groups for the liabilities and the not specified positions.

**Note:**

The financial positions and financial position groups defined for the data source Facilities for the credit lines from Treasury and Risk Management, are not relevant for the financial status app. For these financial positions representing the credit lines from

Treasury and Risk Management the asset liability indicator is not specified. You can report these financial positions using the CDS query Financial Status Query (C_FinancialStatusQuery).

How-to Video: Working with Reports (Multidimensional Data Grid Apps) (English Only)

[figure TRM01-F032]

Open this video in a new window

**Note:**

Captions are available for multiple languages. Use the CC (Closed Captions) button in the video player to see which languages are supported.

You can also use the Search within video field to search for specific text in the English or German captions.

**Key Features**

Provide two tiles to derive financial status:

Financial Status – Book Value (SAP Fiori ID F2136.)

This tile displays the financial status based on book values of treasury positions, bank account balances from Cash Management, and account balances from the general ledger.

Financial Status – Nominal Amount (SAP Fiori ID W0122)

This tile displays the financial status based on nominal amounts of treasury positions, bank account balances from Cash Management, and account balances from the general ledger.

Calculate amounts based on user-defined financial positions, which use as their data sources treasury positions (from TRM), bank account balances (from Cash Management), and account balances (from the general ledger).

Display amounts in transaction currency and reporting currency.

Analyze the details of the financial positions by adding the attributes related to treasury positions, bank accounts, and general ledger postings to the table as rows or columns. The financial positions are then split according to these attributes.

For example, you can use the product type or the additional differentiation terms of your treasury positions, such as cost center, WBS element, profit center, and functional area.

Sort, group and calculate subtotals for the results.

Navigate to master data such as securities account, security class, futures account, issuer and counterparty, using Jump To functionality.

Export results to Microsoft Excel.

**Customizing**

To be able to use the app, you must perform the following configuration:

Define Financial Positions

Define the financial positions and financial positions groups that compose the financial status in the tile Define Financial Positions. Each financial position has a specific data source and is assigned to a financial position group. For each data

source there are specific fields to select the relevant data which composes the financial position (for example, product type, transaction type, or general ledger account).

Enter Exchange Rates (transaction TMDFX)

The app uses exchange rates to convert the amounts in transaction currencies to the reporting currency. Ensure that you keep the market data up-to-date.

Extensibility

**Note:**

These apps are not suitable to be extended.

Supported Device Types

Desktop

Tablet

##### Define Financial Positions

> **Path:** Treasury and Risk Management > Treasury Analytics > Financial Status > Define Financial Positions | L4 | trm01 p.131 | loio `ee19d844c4d8464aaff770537a437459` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ee19d844c4d8464aaff770537a437459.html?locale=en-US)

With this app, you define the financial position groups and financial positions to be displayed in the Financial Status app.

**Key Features**

Maintain Financial Position Groups

You can use financial position groups to group together your financial positions. In a financial position group, you specify whether the assigned financial position represents assets or liabilities.

In the Financial Status app, the assets or liabilites of a company code are totaled at the level of the company code and over all company codes.

- 1. Open the Define Financial Positions app on the SAP Fiori launchpad.


- 2. Switch to the change mode.
- 3. In the Maintain Financial Position Groups screen, choose New Entries.
- 4. Assign a name (not exceeding 20 characters) and a unique description for the financial positon group.
- 5. Further, specify whether the financial position group represent assets or liabilities.

For financial position groups representing credit lines of the Treasury and Risk Management, choose the Not Specified value in this field.

- 6. Save your entries.


**Note:**

Financial position groups are used to structure how financial positions are displayed in the Financial Status app. In this app, the financial position groups of the assets are displayed followed by the financial position groups for the liabilities.

The financial position group is displayed in the app with its description, and not with the maximum 20 character name.

The fiancial positions and financial position groups defined for the data source Facilities for the credit lines from Treasury and Risk Management, are not relevant for the Financial Status apps. For these financial positions representing the credit lines from Treasury and Risk Management the asset/liability indicator is not specified. You can report these financial positions using the CDS query Financial Status Query (C_FinancialStatusQuery).

Maintain Financial Positions

- 1. Switch to the Maintain Financial Positions screen.
- 2. Choose New Entries.
- 3. Choose a name (not exceeding 20 characters) and a description for the financial position that reflects its business purpose.
- 4. Assign the financial positions group.
- 5. Specify the data source from which the key figure is to be calculated:

Treasury position management

Get the book values or nominal values of treasury positions managed in Treasury and Risk Management.

Facilities

Get the credit line amounts, the utilized amounts, and the available amounts in display currency of the facilities managed in Treasury and Risk Management.

One Exposure

Get the house bank account balances of the Cash Management.

One document balances

Get the account balances from the general ledger.

- 6. Save your entries and return to the previous screen.
- 7. Select the financial position and choose Maintain Selections. Here, you specify how the key figure is calculated.


**Note:**

Maintaining the selections is mandatory for each financial position. If you do not maintain selections, no data will be selected for the financial position in the Financial Status app.

For financial positions usingTreasury position managementas their data source, the following fields are available:

Product Type

Transaction Type

Valuation Class

Valuation Area

**Note:**

You must choose the relevant valuation areas. Make sure that you do not select the data of a company code twice. This means:

If you decide to see the values according to IFRS standard, do not select also the local gaap valuation areas.

If you decide to see the values according to the local regulations select the relevant valuation areas, but do not select the valuation areas for group reporting.

Security Class ID Number

Securities Account

Futures Account

Business Area

Portfolio

Posting Status

You can restrict the selection of financial positions by their posting status. You can now choose between the selection of Scheduled and Fixed business transactions or only the Fixed business transactions.

For the financial positions usingFacilitiesas their data source, the following fields are available:

Product Type

Only the product types with product category Facilities are available.

Transaction Type

For financial positions usingOne Exposureas their data source, the following fields are available:

G/L Account

House Bank

Account ID

Business Area

Portfolio

For financial positions usingOne document balancesas their data source, the following fields are available:

Account Number

Chart of Accounts

Document type

Ledger

**Note:**

You must choose the relevant ledger.

Business Area

Save your entries.

**Supported Device Types**

Desktop

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

#### Review Balance Sheet FX Risk (1 of 2)

> **Path:** Treasury and Risk Management > Treasury Analytics > Review Balance Sheet FX Risk | L3 | trm04 p.125 | loio `c5469e6a0fab47f2a8468e02b81023cd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c5469e6a0fab47f2a8468e02b81023cd.html?locale=en-US)

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

[figure TRM04-F022 - Formulas: Calculation of Balance Sheet FX Risk Measures]

where

NE(abs.) = Balance sheet net open exposures (absolute) = Total of absolute amounts of balance sheet net open exposures for each transaction currency in the display currency

E(abs.) = Balance sheet exposures (absolute) = Total of absolute amounts of balance sheet exposures for each transaction currency in the display currency

H(abs.) = Hedges (absolute) = Total of absolute amounts of hedges for each transaction currency in the display currency

TC = Transaction currency

DC = Display currency

r = Exchange rate (transaction currency in display currency)

TC/DC

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

#### Foreign Exchange Overview

> **Path:** Treasury and Risk Management > Treasury Analytics > Foreign Exchange Overview | L3 | trm01 p.137 | loio `3306919f61824e0b8cced7a3b4e77d60` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3306919f61824e0b8cced7a3b4e77d60.html?locale=en-US)

App ID: F2331

With this app, you can display an overview of the foreign exchange related financial risks including FX instruments, financial status, cash position, and liquidity forecast at a selected key date.

**Key Features**

Analyze several key performance indicators displayed as separate cards:

Financial Status in Display Currency

Credit Line Overview in Display Currency

Cash Position in Display Currency

FX Forwards

FX Options

Non-Deliverable Forwards

Foreign Exchange Rate

Absolute Net FX Exposure

Specify default values for the app using the following parameters:

Company Code

Exchange Rate Type

Key Date

Display Currency

You'll find this function in the user actions area by choosing the user icon in the upper left hand corner. There, choose Settings and select Default Values. Once you have specified your preferred default values, you no longer have to enter any values in the filter bar.

Filter the cards by various categories such as key date, display currency, exchange rate type, company code, and transaction currency

Navigate from the different cards to the target apps by clicking on the header, line item, or data point to get more detailed information

For more information, see How to Navigate from a Card to the Target App.

Customize the overview page using the Manage Cards function. You'll find this function in the user actions area by choosing the user icon in the upper left hand corner. There, select Manage Cards. This function allows you to hide and show the cards you want to see.

Rearrange the overview page by dragging and dropping the cards to another position and thus reflecting a sequence most convenient for you.

**Supported Device Types**

Desktop

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

##### Define Display Order

> **Path:** Treasury and Risk Management > Treasury Analytics > Foreign Exchange Overview > Define Display Order | L4 | trm01 p.138 | loio `f58a39c844144bddbd5af40b24a2a2d7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f58a39c844144bddbd5af40b24a2a2d7.html?locale=en-US)

With this app, you define the display order for the currency pairs used in the Foreign Exchange Overview app.

**Key Features**

Define the order in which the curreny pairs comprising a leading and a following currency are displayed in the Foreign Exchange Overview app.

Create and manage variants for your preferred settings.

**Supported Device Types**

Desktop

##### How to Navigate from a Card to the Target App

> **Path:** Treasury and Risk Management > Treasury Analytics > Foreign Exchange Overview > How to Navigate from a Card to the Target App | L4 | trm01 p.138 | loio `ddba8f9704804f62b6ac4d1af14dd50f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ddba8f9704804f62b6ac4d1af14dd50f.html?locale=en-US)

This topic describes how to navigate from one card in your Foreign Exchange Overview app to the corresponding target app.

With the Foreign Exchange Overview app, you get an overview of the foreign-exchange-related financial risks and in addition, you can navigate from one card to the respective target app.

Procedure

To navigate to the target app of the respective key performance indicators, proceed as follows:

- 1. Choose a card from which you want to navigate to the target app.
- 2. Select the header, line item, or data point of the respective card.
- 3. The corresponding target app opens.
- 4. To navigate back to the Foreign Exchange Overview app, choose   Back.


Here's what that looks like (English only):

[figure TRM01-F034 - Here's what that looks like (English only):]

**Example:**

In the FX Forwards card, choose one of the line items.

The Process Spots/Forwards - Collective Processing app opens.

In the Credit Line Overview in Display Currency card, select one of the bars.

The Credit Line Analysis app opens.

**More Information**

For more information, see Foreign Exchange Overview

#### Interest Rate Overview

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview | L3 | trm01 p.139 | loio `9a6016237596418bba8312f9e9d8ce5a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9a6016237596418bba8312f9e9d8ce5a.html?locale=en-US)

With this app, you get an overview of your debt and investment related financial risks, including maturity profile, total debts and investments by key date, debt and investment by interest category and reference interest rate at a selected key date. Additionally, you can see the key figures of the market risk according to the configuration settings you made in the market risk analyzer area and the current interest rates, historic interest rates, and yield curves.

**Key Features**

Analyze several key performance indicators displayed as separate cards:

Debt/Investment Maturity Profile

Total Amount of Debts by Key Date (Top 5 Product Types)

Total Amount of Investments by Key Date (Top 5 Product Types)

Debt and Investment by Interest Category (Including IR Swap)

Debt and Investment by Reference Interest Rate (Including IR Swap)

IR Swaps by Key Date

Current Interest Rate

Historic Interest Rate

Yield Curves

Macaulay Duration (Deprecated)

Modified Duration (Deprecated)

Basis Point Value (Deprecated)

Specify default values for the app using the following parameters:

Key Date

Display Currency

Exchange Rate Type

Yield Curve Type

Number of Years

Counterparty

Key Figure for Mac. Duration

Key Figure for Mod. Duration

Key Figure for Basis Point Value

You'll find this function in the user actions area by choosing the user icon in the upper left hand corner. There, choose Settings and select Default Values. Once you have specified your preferred default values, you no longer have to enter any values in the filter bar.

Filter the cards by various categories using the values above, such as key date, display currency, and exchange rate type.

Navigate from the different cards to the target apps by clicking on the header, line item, or data point to get more detailed information.

Navigate to the Debt and Investment Analysis app to check the details of the outstanding debts and investments.

Customize the overview page using the Manage Cards function. You'll find this function in the user actions area by choosing the user icon in the upper left hand corner. There, select Manage Cards. This function allows you to hide and show the cards you want to see.

Rearrange the overview page by dragging and dropping the cards to another position and thus reflecting a sequence most convenient for you.

In addition, the app supports the following technical features and options:

This app uses the following CDS views:

C_MaturityProfile

C_DebtInvestmentNominal

I_DebtInvmtFixedVariable

C_DebtInvmtRefInterest

C_RefInterestRateHistory

C_RefInterestRateRank

Additional Details

The following product categories are available:

020 Investment Certificate

040 Bond

042 Bond with installment repayment

510 Fixed-term Deposits

520 Deposits at Notice

530 Commercial Paper

540 Cash Flow Transaction

550 Interest Rate Instrument

580 Current Account Style Instrument

620 Interest Rate Swap

**Supported Device Types**

Desktop

**More Information**

Debt and Investment Maturity Profile

Reference Interest Rates.

Yield Curves

Debt and Investment Analysis

##### Debt/Investment Maturity Profile

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Debt/Investment Maturity Profile | L4 | trm01 p.141 | loio `6ae793ced8904729b86f0d8013af3337` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6ae793ced8904729b86f0d8013af3337.html?locale=en-US)

With this card, you can see the nominal amount of debt/investment transactions which will mature in the future, whose start date are earlier than the key date and end date are greater than the key date.

**Key Features**

You can see the nominal amount by calendar year, which is defined in the Number of Years field.

You can switch between three views:

By Debt and Investment

By Debt

By Investment

The following product categories are available:

020 Investment Certificate

040 Bond

042 Bond with installment repayment

510 Fixed-term Deposits

520 Deposits at Notice

530 Commercial Paper

540 Cash Flow Transaction

550 Interest Rate Instrument

580 Current Account Style Instrument

The calculation logic is based on repayment flows, nominal decrease flows and nominal increase flows.

You can navigate to the Debt and Investment Maturity Profile app.

For more information, see Interest Rate Overview.

##### Total Amount of Debts by Key Date (Top 5 Product Types)

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Total Amount of Debts by Key Date (Top 5 Product Types) | L4 | trm01 p.142 | loio `fee655ec26a74de490828f227a5645fc` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fee655ec26a74de490828f227a5645fc.html?locale=en-US)

With this card, you can see the nominal amount of debt transactions by the top five product types which are currently open on the specified key date, whose start date are earlier than the key date and end date are greater than the key date.

**Key Features**

You can see the amounts of the top five product types by the key date that you define.

The following product categories are available:

020 Investment Certificate

040 Bond

042 Bond with installment repayment

510 Fixed-term Deposits

520 Deposits at Notice

530 Commercial Paper

540 Cash Flow Transaction

550 Interest Rate Instrument

580 Current Account Style Instrument

**More Information**

Debt and Investment Maturity Profile

Interest Rate Overview

##### Total Amount of Investments by Key Date (Top 5 Product Types)

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Total Amount of Investments by Key Date (Top 5 Product Types) | L4 | trm01 p.143 | loio `3658a650c6524942920e6d945fe18910` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3658a650c6524942920e6d945fe18910.html?locale=en-US)

With this card, you can see the nominal amount of investment transactions by product type which are currently open on the specified key date, whose start date are earlier than the key date and end date are greater than the key date.

**Key Feature**

You can see the amounts of the top five product types by the key date that you define.

The following product categories are available:

020 Investment Certificate

040 Bond

042 Bond with installment repayment

510 Fixed-term Deposits

520 Deposits at Notice

530 Commercial Paper

540 Cash Flow Transaction

550 Interest Rate Instrument

580 Current Account Style Instrument

**More Information**

Debt and Investment Maturity Profile

Interest Rate Overview

##### Debt and Investment by Interest Category (Including IR Swap)

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Debt and Investment by Interest Category (Including IR Swap) | L4 | trm01 p.143 | loio `682014a4287e4711805407d56276da18` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/682014a4287e4711805407d56276da18.html?locale=en-US)

With this card, you can see the nominal amount of Debt/Investment transactions that are bearing fixed or variable interest category. This card differs from the Total Amount of Debts by Key Date card and the Total Amount of Investments by Key Date card when money market transactions have parallel fixed and variable interest conditions.

**Key Features**

You can switch between the following four views based on the fixed and variable interest rates:

By Debt and Investment

In this view, you can see the nominal amount of debt, the nominal amount of investment, and the Net Debt Investment which is the nominal amount of investment minus debt.

By Debt

In this view, you can see the nominal amount of debt, the Total Amount which is the nominal amount of debt based on fixed interest rate plus the nominal amount of debt based on variable interest rate, and the percentage ratio.

By Investment

In this view, you can see the nominal amount of investment based on the fixed interest rate, the amount based on variable interest rate, the Total Amount which is the nominal amount of investment based on fixed interest rate plus the nominal amount of investment based on variable interest rate,and the percentage ratio.

Risk Reduction by IR Swap

In this view, you can see the following figures:

Net Debt Investment: The nominal amount of investment minus debt.

Net IR Swap: The nominal amount of receive leg minus the nominal amount of pay leg of interest rate.

Net Open: The sum of Net Debt Investment plus Net IR Swap which means open amount.

The calculation logic is based on the nominal changes.

Capitalized cash flows as well as installment repayment are considered as nominal changes. To keep consistency with position flows, the Start Date Inclusive and End Date Exclusive rule applies, which means the nominal amounts happening on the activity start date are counted, while those flows on activity end date are ignored.

The following product categories are available:

020 Investment Certificate

040 Bond

042 Bond with installment repayment

510 Fixed-term Deposits

520 Deposits at Notice

530 Commercial Paper

540 Cash Flow Transaction

550 Interest Rate Instrument

580 Current Account Style Instrument

620 Interest Rate Swap

**More Information**

Reference Interest Rates

Interest Rate Overview

##### Debt and Investment by Reference Interest Rate (Including IR Swap)

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Debt and Investment by Reference Interest Rate (Including IR Swap) | L4 | trm01 p.144 | loio `768d695daa3a4fcdb9e417f969470831` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/768d695daa3a4fcdb9e417f969470831.html?locale=en-US)

With this card, you can see the nominal amounts of debt and investment including IR Swap by reference interest rate.

**Key Features**

You can see the top 5 amounts by reference interest rate.

You can switch between the following four views based on the reference interest rate:

By Debt and Investment

By Debt

By Investment

Risk Reduction by IR Swap

The value of Net Open based on variable interest rate in the Debt and Investment by Interest Category (Including IR Swap) card is always matched with the total net open amount for the reference interest rate in the Risk Reduction by IR Swap view.

The following product categories are available:

020 Investment Certificate

040 Bond

042 Bond with installment repayment

510 Fixed-term Deposits

520 Deposits at Notice

530 Commercial Paper

540 Cash Flow Transaction

550 Interest Rate Instrument

580 Current Account Style Instrument

620 Interest Rate Swap

**More Information**

Reference Interest Rates

Interest Rate Overview

##### IR Swaps by Key Date

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > IR Swaps by Key Date | L4 | trm01 p.145 | loio `12a01127c3c0466389932d87122bf44c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/12a01127c3c0466389932d87122bf44c.html?locale=en-US)

Total nominal amount on the entered key date in the display currency.

**Key Features**

See the total nominal amount for the Outgoing Side and the Incoming Side of the selected IR swaps on the entered key date in the display currency.

The following product types are relevant for this card:

- 62A Interest Rate Swap

- 62B Cross Currency Interest Rate Swap


IR swaps of these product types, which meet the following conditions, are selected:

If the entered key date is later or equal to the term start date and earlier than the term end date of the IR swap.

Either the currency of the outgoing side or the currency of the incoming side is one of the selected transaction currencies.

The company code of the IR swap has been selected.

**Note:**

If you haven't filled the Company Code and Transaction Currency fields, all company codes and transaction currencies are relevant.

On top of the card, you either see the total nominal amount of the outgoing side or of the incoming side of all selected IR swaps in display currency.

You can switch between the Outgoing Side and Incoming Side.

On the displayed bar chart, you see bars representing the nominal amounts of the IR swaps for each nominal currency on each side. Tooltips are available for each bar, where you can see the exact nominal amounts in display currency.

By clicking on the bar chart, you can navigate to the Process IR Derivatives - Collective Processing app, where you get a list of the selected IR swaps. You can display or change the financial transaction data of an IR swap. It is also possible to create IR swaps from the collective processing app.

**Note:**

This function is only available, if you are authorized for the Process IR Derivatives - Collective Processing app.

##### Current Interest Rate

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Current Interest Rate | L4 | trm01 p.146 | loio `139adf9e2ace4d5693e31f55c9e4c419` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/139adf9e2ace4d5693e31f55c9e4c419.html?locale=en-US)

With this card, you can see the value of reference interest rate which is effective on the specified key date. You can also see the value of the deviation rate, which is the deviation of a effective reference interest rate from a previously effective reference interest rate.

You can extend the table to see more rows by dragging the table.

For more information, see Interest Rate Overview.

##### Historic Interest Rate

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Historic Interest Rate | L4 | trm01 p.146 | loio `91518dfed49043c7885bb064e7b4040c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/91518dfed49043c7885bb064e7b4040c.html?locale=en-US)

With this card, you can choose to see the daily or monthly reference interest rate trend in the past. You can switch between the following two views:

Daily

Historic reference interest rates in the last 7 days are displayed.

Monthly

Historic reference interest rates in the last 12 months are displayed.

For more information, see Interest Rate Overview.

##### Yield Curves (1 of 2)

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Yield Curves | L4 | trm01 p.146 | loio `3c04567a28ce40599aa88fb8bed4ffa1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3c04567a28ce40599aa88fb8bed4ffa1.html?locale=en-US)

With this card, you can see yield curves by interest rate date in yield curve currency.

**More Information**

Yield Curves

Yield Curve Type

Interest Rate Overview

##### Macaulay Duration (Deprecated)

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Macaulay Duration (Deprecated) | L4 | trm01 p.147 | loio `d69a245354454698af0e57496149ff48` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d69a245354454698af0e57496149ff48.html?locale=en-US)

With this card, you can see the macaulay duration by portfolio hierarchy. According to configuration settings of key figures and evaluation procedures you made, you get calculation results from the result database.

**More Information**

Market Risk Analyzer

Portfolio Hierarchies

Interest Rate Overview

##### Modified Duration (Deprecated)

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Modified Duration (Deprecated) | L4 | trm01 p.147 | loio `ea47ff4be1c04733a3f1c8774e0eac23` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ea47ff4be1c04733a3f1c8774e0eac23.html?locale=en-US)

With this card, you can see the modified duration by portfolio hierarchy. According to configuration settings of key figures and evaluation procedures you made, you get calculation results from the result database.

**More Information**

Market Risk Analyzer

Portfolio Hierarchies

Interest Rate Overview

##### Basis Point Value (Deprecated)

> **Path:** Treasury and Risk Management > Treasury Analytics > Interest Rate Overview > Basis Point Value (Deprecated) | L4 | trm01 p.147 | loio `6c708d08e39644c994a1fe2138e9eefd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6c708d08e39644c994a1fe2138e9eefd.html?locale=en-US)

With this card, you can see the basis point value by portfolio hierarchy. According to configuration settings of key figures and evaluation procedures you made, you get calculation results from the result database.

**More Information**

Market Risk Analyzer

Portfolio Hierarchies

Interest Rate Overview

#### Market Data Overview

> **Path:** Treasury and Risk Management > Treasury Analytics > Market Data Overview | L3 | trm01 p.147 | loio `e676d1d1062541b8b1dc9d934cd76064` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e676d1d1062541b8b1dc9d934cd76064.html?locale=en-US)

With this app, you can display an overview of financial risks relating to foreign exchange (FX), including the current FX spot rate, historic FX spot rate, and FX swap rate for a selected key date. You can also get an overview of financial risks related to market

data, including the historic reference interest rate, current security price, and historic security price.

**Key Features**

Analyze several key performance indicators displayed on separate cards:

FX Spot Rate

Historic FX Spot Rate

FX Swap Rate

Historic Reference Interest Rate

Current Security Price

Historic Security Price

Specify default values for the app using the following parameters:

Key Date

Exchange Rate Type

Price Type

Currency Pair

Reference Interest Rate

Security Class

Favorite Security Class

With this filter, you can see the current security prices according to the favorite security classes that you selected.

Favorite Currency Pair

With this filter, you see the current FX spot rates according to the favorite currency pairs that you selected.

You find this function in the user actions area by choosing the user icon. There, choose Settings and select Default Values. Once you have specified your preferred default values, you no longer have to enter any values in the filter bar.

Filter the cards by various categories using the values above, such as key date, currency pair, and exchange rate type.

Navigate from the different cards to the target apps by clicking on the header, line item, or data point to get more detailed information.

Navigate to the corresponding market data apps to check the details of the rates and prices.

Customize the overview page using the Manage Cards function. You find this function in the user actions area by choosing the user icon. There, select Manage Cards. This function allows you to hide and show the cards you want to see.

Rearrange the overview page by dragging and dropping the cards to another position and thus reflecting a sequence most convenient for you.

In addition, the app supports the following technical features and options:

Navigation to the Enter FX Spot Rates app

Navigation to the Enter FX Swap Rates app

Navigation to the Enter Reference Interest Rates app

Navigation to the Enter Security Prices app

This app uses the following CDS views:

C_FXSwapRateKeyDate

C_FXSpotRateDeviation

C_SecurityPriceReporting

C_MarketDataOverViewSel

C_MktDataRefIntrstRateRptg

**Supported Device Types**

Desktop

Tablet

**More Information**

Editing Exchange Rates Manually

Enter FX Swap Rates

Editing Security Prices Manually

##### FX Spot Rate

> **Path:** Treasury and Risk Management > Treasury Analytics > Market Data Overview > FX Spot Rate | L4 | trm01 p.149 | loio `8c403979af844276b66d68e72acada18` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8c403979af844276b66d68e72acada18.html?locale=en-US)

The card displays FX spot rates for currency pairs on a specific key date and its percentage difference to the day before.

On this card, you can see the KPI of FX spot rates for different currency pairs on a specific key date. By default, the top 6 currency pairs of the FX spot rates are displayed. You can display more values by dragging the card.

You can also limit the number of FX spot rates by filtering for your favorite currency pairs.

You can also see the percentage difference of the exchange rate key figure to the rate on the day before the key date. By default, the data displayed is for % Difference from Yesterday only. You can also display the data for Difference from Yesterday by dragging the card.

##### Historic FX Spot Rate

> **Path:** Treasury and Risk Management > Treasury Analytics > Market Data Overview > Historic FX Spot Rate | L4 | trm01 p.149 | loio `2b9ea8a334fa4c67bc81dfab3f1a9d24` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2b9ea8a334fa4c67bc81dfab3f1a9d24.html?locale=en-US)

The card displays the historic FX spot rate of a currency pair before the key date.

With this card, you can see historic FX spot rates of a currency pair before the key date. You can display the historic exchange rate by period using the following drill-down options:

- 5 Days

1 Month

3 Months

- 6 Months


1 Year

##### FX Swap Rate

> **Path:** Treasury and Risk Management > Treasury Analytics > Market Data Overview > FX Swap Rate | L4 | trm01 p.150 | loio `a6edd42a8b85451285a58a3cd8743be1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a6edd42a8b85451285a58a3cd8743be1.html?locale=en-US)

This card displays the development of FX swap rates over a term (in days).

With this card, you can see the development of FX swap rates over a specific term starting from the key date. By default, 540 days are displayed as the term for the FX swap rates. You can display more values by dragging the card.

##### Historic Reference Interest Rate

> **Path:** Treasury and Risk Management > Treasury Analytics > Market Data Overview > Historic Reference Interest Rate | L4 | trm01 p.150 | loio `7321b40330ee4c33960fbb75a706c1c1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7321b40330ee4c33960fbb75a706c1c1.html?locale=en-US)

This card displays historic reference interest rates before the specified key date.

With this card, you can see reference interest rates before the key date. You can display the historic reference interest rates by period using the following drill-down options:

- 5 Days

1 Month

3 Months

- 6 Months


1 Year

##### Current Security Price

> **Path:** Treasury and Risk Management > Treasury Analytics > Market Data Overview > Current Security Price | L4 | trm01 p.150 | loio `bece2764dffa483f9b0fb03e4691f962` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bece2764dffa483f9b0fb03e4691f962.html?locale=en-US)

This card displays the current security price of your favorite security classes.

With this card, you can see the current security price of your favorite security classes in the corresponding exchange on the specified key date. By default, the top 6 security classes and exchange data are displayed. You can display more values by dragging the card.

You can also see the percentage difference of the security price to the price on the day before the key date.

##### Historic Security Price

> **Path:** Treasury and Risk Management > Treasury Analytics > Market Data Overview > Historic Security Price | L4 | trm01 p.150 | loio `16979359884f460886aed503e3637b9c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/16979359884f460886aed503e3637b9c.html?locale=en-US)

This card displays the historic security prices by period.

With this card, you can see the security prices in the corresponding exchange before the key date. You can display the security price by period using the following drill-down options:

- 5 Days

1 Month

3 Months

- 6 Months


1 Year

#### Debt and Investment Analysis

> **Path:** Treasury and Risk Management > Treasury Analytics > Debt and Investment Analysis | L3 | trm01 p.151 | loio `6e1fe28dea2644aa8d5f62765ca22600` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6e1fe28dea2644aa8d5f62765ca22600.html?locale=en-US)

With this app, you can have a quick visual overview of the outstanding debts and investments in your company and subsidiaries. It illustrates the nominal amounts in display currency by default. You can also customize your analysis with several filtering options in chart or table views. For example, you can display book values in position currency and net present values (NPV) in valuation currency. This allows the corporate treasury to monitor their debt and investment closely and precisely.

**Key Features**

You can use this app to

Filter default values for the app using the following parameters:

Key Date

Display Currency

Exchange Rate Type

Debt/Investment

With this filter, you can determine whether debts or investments, or both of them are to be displayed.

Interest Category

With this filter, you can determine whether fixed or variable interest, or both of them are to be displayed.

Display the nominal amount in display currency by company code, transaction currency, product type, and counterparty, in the visual filter view.

Adapt your filters, for example, Issuer for securities and Rating Agency for credit rating.

Switch to the compact filter view from the visual filter view in case you need to change your filter options.

Use the chart view to have a visual overview of the debt and investment details in your company.

Change the dimension of the chart in the View By area, for example, by product type or by security account.

Display the chart in other chart types, such as line chart, bar chart, and so on.

Use the table view for more granular analysis.

Display a list of transactions in a table, with line item details such as the transaction number and nominal amount in display currency.

Navigate to the original transactions to check the details of the transactions.

Navigate to the collective processing app to process the original transactions in case of any financing decisions in the Process Transaction area.

This app uses the C_DebtAndInvestmentAnalysis CDS view.

**Additional Details**

The following product categories are available:

020 Investment Certificate

040 Bond

042 Bond with installment repayment

510 Fixed-term Deposits

520 Deposits at Notice

530 Commercial Paper

540 Cash Flow Transaction

550 Interest Rate Instrument

580 Current Account Style Instrument

**Supported Device Types**

Desktop

#### Debt and Investment Maturity Profile

> **Path:** Treasury and Risk Management > Treasury Analytics > Debt and Investment Maturity Profile | L3 | trm01 p.152 | loio `68f8a3665d5c48008fef0c45b5e74812` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/68f8a3665d5c48008fef0c45b5e74812.html?locale=en-US)

App ID: F3130

With this app, you can have a quick visual overview of the outstanding debts and investments in your company and subsidiaries. The maturity profile illustrates the nominal amounts and their time left to maturity. It gives a summary of breakup of the value of the debts and investments with different specific maturities. You can also customize your analysis with several filtering options. This allows the corporate treasury to monitor their debt and investment maturity profile closely and precisely.

In addition to the repayment flows, you can also include interest flows in your analysis. Therefore, also interest rate swaps can be included. Using the filter Reference Number, you can analyze a specific reference or multiple references with the reference category Interest Rate Exposure (IRE).

**Key Features**

Filter Bar

You can use the filter options to determine which parameters are to be displayed.

Group outstanding debts and investments by maturity date by defining the number of years to be displayed in the profile.

**Example:**

For example, if you set 3 as the number of years to be displayed, and the Key Date is Dec. 23, 2017, you then get outstanding transactions by a 3-year consecutive calendar years of 2017, 2018 and 2019 and also an aggregated year greater than 2019 in which the transaction maturity are aggregated.

Filter whether debts or investments, or both of them are to be displayed.

With the Interest/Repayment filter, you can filter only the repayment flows for the classic use of the app, filter only the interest flows to get an overview of the interest exposure, or filter repayments and interest flows for the overall overview.

Use the filter Interest Category to filter only fixed interest flow, only variable interest flows or both kinds of interest flows.

You can also filter by the Reference Interest Rate.

Filter outstanding debts and investments by company code, counterparty, product types, and nominal currency.

If you have assigned the interest rate swaps to their hedged interest rate exposures with the new reference category Interest Rate Exposure, you can use the new filter Reference Number to report this single interest rate exposure hedging. For more information, see also Reference.

Switch between visual filter view and compact filter view

Chart View

You can use the chart view to have a visual overview of the profile.

Breakout each period in the chart with drill down options. For example, you can drill down to the year month view to display the profile by calendar month.

Display the profile with other chart types, such as line chart, bar chart, and so on.

Select a value in the chart and display the maturity flows in the table within the chart.

Table View

You can use the table view for more granular analysis.

Display the profile in a table of a list of maturity flows, with line item details such as the transaction number and payment date.

Navigate to the original transactions to check the details of the transactions.

Navigate to the Collective Processing app to process the original transactions in case of any financing decisions.

**Additional Details**

The following product categories are available:

040 Bond

042 Bond with installment repayment

510 Fixed-term Deposits

520 Deposits at Notice

530 Commercial Paper

540 Cash Flow Transaction

550 Interest Rate Instrument

580 Current Account-Style Instrument

620 Swap

Calculation Logic

The calculation logic is based on repayment flows that contain the payment date, payment amount and currency. In addition to the repayment flows, nominal decrease should also be considered for the following product categories:

520 Deposit at Notice

540 Cash Flow Instrument

550 Interest Rate Instrument

In addition to the repayment flows and nominal decrease, nominal increase should also be considered for the product type 580 Current Account-Style Instrument.

**How-To Video (English Only)**

Debt and Investment Maturity Profile

[figure TRM01-F035]

Open this video in a new window

**Supported Device Types**

Desktop

**More Information**

For more details, see the following video on how to use analytical list page apps.

[figure TRM01-F036]

[figure TRM01-F037]

8/27/26, 2:18 AM

Open this video in a new window

#### Credit Line Analysis

> **Path:** Treasury and Risk Management > Treasury Analytics > Credit Line Analysis | L3 | trm01 p.155 | loio `69a43158edcc9144e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/69a43158edcc9144e10000000a4450e5.html?locale=en-US)

**Use**

You can use this app to obtain an overview of the trend of the total credit line, the available amounts, and the amounts consumed by money market and trade finance transactions. These key performance indicators are displayed for a specific period, key date, company code, currency, and counterparty for the purpose of making future funding decisions.

You can view the total credit line and the available and utilized amounts in a chart or a table according to predefined dimensions: company code, counterparty, key date and reporting period.

How-to Video: Working with Reports (Multidimensional Data Grid Apps) (English Only)

[figure TRM01-F038]

Open this video in a new window

**Note:**

Captions are available for multiple languages. Use the CC (Closed Captions) button in the video player to see which languages are supported.

You can also use the Search within video field to search for specific text in the English or German captions.

**Calculation Logic**

For more information about how the numbers on the app tile are calculated, see Calculation Logic: Credit Line Analysis

**Key Features**

View the key figures Total Credit Line, Available Amount, and Utilized Amount in the display currency on the tile

View the trend of the total credit line, the available amount, and the utilized amount for a specified period

Analyze the utilization and underutilization rate, expressed as a percentage

The app calculates the utilization and underutilization rate of the total credit line

Adjust filtering dimensions dynamically according to your own reporting format

Drill down to the transaction level of a credit line to analyze the detailed information on the credit line

Navigate directly to another app: Display Facility

For more information, see Facilities

**Supported Device Types**

Desktop

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

##### Calculation Logic: Credit Line Analysis

> **Path:** Treasury and Risk Management > Treasury Analytics > Credit Line Analysis > Calculation Logic: Credit Line Analysis | L4 | trm01 p.156 | loio `9efd12614c054f798f63d31cd59c3169` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9efd12614c054f798f63d31cd59c3169.html?locale=en-US)

**On the App Tile**

On the app tile, the app displays three numbers that represent the credit line, the utilized amount, and the available amount, all in reporting currency.

The equation below illustrates how these numbers are calculated:

[figure TRM01-F039 - How the KPIs on the App Tile Are Calculated]

How the KPIs on the App Tile Are Calculated

The logical relationship among these key figures is:

[figure TRM01-F040 - The logical relationship among these key figures is:]

How the Credit Line Is Calculated

**Note:**

In some cases, the credit line is overdrafted, meaning that the utilized amount is greater than the total available amount of the credit line, the available amount is set to zero instead of setting it to minus. The sum of the utilized amount and the available amount is greater than the credit line.

In these cases, the utilization rate and underutilization rate do not equal 100 percent.

In the App

With the app you can also analyze the utilization and underutilization rate of the total credit line. The rates are expressed as a percentage.

The equations below illustrates how these rates are calculated:

[figure TRM01-F041 - How the Utilization Rate of the Credit Line Is Calculated]

How the Utilization Rate of the Credit Line Is Calculated

Example

For example, company A has two credit lines: one with a total credit line of 1M EUR and a utilized amount of 500K EUR, and the second with a total credit line of 2M EUR and a utilized amount of 2M EUR. The utilization rate for company A is calculated as follows: (500K+2M)/(1M+2M)*100 = 83.33%

[figure TRM01-F042 - How the Underutilization Rate of the Credit Line Is Calculated]

How the Underutilization Rate of the Credit Line Is Calculated

Example

For example, company A has two credit lines: one with a total credit line of 1M EUR and a utilized amount of 500K EUR, and the second with a total credit line of 2M EUR and a utilized amount of 2M EUR. The underutilization rate for company A is calculated as follows: (500K)/(1M+2M)*100 = 16.67%

##### Configuration Settings: Credit Line Analysis

> **Path:** Treasury and Risk Management > Treasury Analytics > Credit Line Analysis > Configuration Settings: Credit Line Analysis | L4 | trm01 p.158 | loio `5abf31584a6e9344e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5abf31584a6e9344e10000000a4450e5.html?locale=en-US)

**Use**

This document contains information about how to configure the Credit Line Analysis app.

**Prerequisites**

OData Service /sap/opu/odata/sap/C_FTR_CL_UTIL_ANALYTICS_CDS needs to be activated.

**SAP Jam Integration**

For information on how to configure SAP Jam, see http://help.sap.com/sapjam .

**SAP Smart Business Modeler**

Before you can use this app, you need to configure it using the SAP Smart Business Modeler. For more information, see SAP Smart Business Modeler Apps.

**Note:**

You can edit the following details related to an SAP-delivered evaluation:

Parameters values

Filter values

Thresholds

Semantic object and action

You can also revert the changes you make to SAP-delivered evaluations. When you upgrade to the next version of SAP Smart Business Modeler apps, the changes made to the SAP-delivered evaluation in the existing version will be merged with the new version.

KPI: Credit Line Analysis

**KPI ID: .SFIN.TREASURYRISKMGR.CRDTLINEANALYSIS**

KPI Description: <empty>

Goal Type: Maximizing

Data Source

|Parameter|Value|
|---|---|
|CDS View|C_FTR_CL_UTIL_ANALYTICS|
|OData Service|/sap/opu/odata/sap/C_FTR_CL_UTIL_ANALYTICS_CDS|
|Entity Set|C_FTR_CL_UTIL_ANALYTICSResults|
|Value Measure|AvailableAmountInDisplayCrcy|
|Semantic Object/Action|<FinancialTransaction - analyzeCreditLine>|


The following templates for evaluations, drill-downs, and tiles are provided.

Evaluation

Evaluation ID: .SFIN.TREASURYRISKMGR.CRDTLINEANAEVA

Evaluation Description: Today

Data Source

|Parameter|Value|
|---|---|
|CDS View|C_FTR_CL_UTIL_ANALYTICS|
|OData Service|/sap/opu/odata/sap/C_FTR_CL_UTIL_ANALYTICS_CDS|
|Entity Set|C_FTR_CL_UTIL_ANALYTICSResults|
|Value Measure|AvailableAmountInDisplayCrcy|
|Semantic Object/Action|<FinancialTransaction - analyzeCreditLine>|
|Scaling Factor|Auto|
|Decimal Precision|Auto|


Targets, Thresholds, and Trend

The following table contains some example values:

|Parameter|Value|
|---|---|
|Goal Type|Maximizing|
|Value Type|Fixed Value|
|Critical|1000000.000|
|Warning|500000.000|
|Target|1000000.000|
|Trend|<empty>|


Input Parameters and Filters

The following tables show the input parameters, filters, and some preconfigured example values. Use your own values where required, according to the data in your backend system.

Input Parameters

|Input Parameter|Operator|Example Value|Explanation|
|---|---|---|---|
|P_DisplayCurrency|Equal to|USD|Choose a currency in which to display the currency amounts. Ensure that exchange rates for this currency exist in your system. An entry in this field is required.|
|P_ExchangeRateType|Equal to|M|Choose an exchange rate type with which to convert the currency into the display currency. An entry in this field is required.|


|Input Parameter|Operator|Example Value|Explanation|
|---|---|---|---|
| | | |You can view the available exchange rate types in Customizing in the system under SAP NetWeaver SAP NetWeaver General Settings  Currencies Check Exchange Rate Types .|


Drill-Down

Not applicable.

Tile

Title: Credit Line Analysis

Subtitle: (Note: Please enter a space character here.)

|Parameter|Value|
|---|---|
|Tile Format|Dual Tile Comparison Tile With Multiple Measures|
|Navigation|Other Drill-Down|
|Semantic Object|FinancialTransaction|
|Action|analyzeCreditLine|


**Note:**

Please ensure that you set the value for the parameter Navigation to Other Drill-Down as the navigation target will otherwise be an empty Smart Business app.

##### App Extensibility: Credit Line Analysis

> **Path:** Treasury and Risk Management > Treasury Analytics > Credit Line Analysis > App Extensibility: Credit Line Analysis | L4 | trm01 p.161 | loio `7e5f7758b8cd9244e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7e5f7758b8cd9244e10000000a4450e5.html?locale=en-US)

**Use**

You can extend the Credit Line Analysis app according to your business needs for different aspects. For this purpose, the following extensibility option is available:

|Extension Options|Use|
|---|---|
|Extension point EFINANCIALTRANSACTION associated with CDS view IFTRCLUTILCUBE|Allows you to add additional columns to display credit line transaction information.|


**More Information**

For a general description of the extensibility options and procedures of SAP Fiori apps, see Extend SAP Fiori Apps.

#### Treasury Position Reporting

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting | L3 | trm01 p.162 | loio `e74d7c5894eaa207e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e74d7c5894eaa207e10000000a441470.html?locale=en-US)

##### Display Treasury Position Flows

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Display Treasury Position Flows | L4 | trm01 p.162 | loio `9a409f57e7356d10e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9a409f57e7356d10e10000000a441470.html?locale=en-US)

Use

With this app you can track the position flows for financial transactions and positions. This app provides a list of flows of selected positions in the treasury subledger, as well as detailed information on the flows and navigation possibilities.

**Note:**

This app does not consider sub-positions, so flows from Hedge Accounting for Positions and value adjustment flows regarding P-GAAP are not selected.

**Key Features**

This app supports the following features:

Shows detailed information on the posted, scheduled and reversed flows of selected treasury transactions and positions with the possibility for further navigation; for example, navigation to the original business transaction and to the app Display Treasury Posting Journal

Enables navigation to master data; for example, Business Partner, Futures Account, Securities Account, Security Class

Provides readily the count of position flows in the content area header

Enables sorting, grouping, and subtotals

Enables triggering of emails and exporting of results to a Microsoft Excel spreadsheet

Extensibility

**Note:**

This app is not suitable to be extended.

Supported Device Types

Desktop

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

##### Display Treasury Posting Journal

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Display Treasury Posting Journal | L4 | trm01 p.162 | loio `8d469f57e7356d10e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8d469f57e7356d10e10000000a441470.html?locale=en-US)

**Use**

With this app you can display the detailed accounting information of financial instrument postings. This app displays a list of posting line items and additional details of posted and reversed flows of financial transactions and positions.

**Note:**

This app does not consider sub-positions, so flows from Hedge Accounting for Positions and values adjustment flows regarding P-GAAP are not selected.

**Key Features**

This app supports the following features:

Shows detailed information on the posted and reversed flows of selected treasury transactions and positions with the possibility for further navigation; for example, navigation to the original business transaction and to the app Manage Journal Entries

Enables navigation to master data; for example, Business Partner, Futures Account, Securities Account, Security Class

Enables sorting, grouping, and subtotals

Enables triggering of emails and exporting of results to a Microsoft Excel spreadsheet

Extensibility

**Note:**

This app is not suitable to be extended.

Supported Device Types

Desktop

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

##### Display Treasury Position Values

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Display Treasury Position Values | L4 | trm01 p.163 | loio `eb489f57e7356d10e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/eb489f57e7356d10e10000000a441470.html?locale=en-US)

App ID: F1867

With this app, you can display a list of positions in the treasury subledger and their position component values on any selected key date. Examples of position component values include book value, purchase value, write-up/write-down in valuation, and position currency.

This app supports the following features:

Shows detailed information on selected treasury positions with the possibility of further navigation; for example, navigation to the corresponding position management procedure and the following apps:

**Display Treasury Position Flows**

Manage Position Indicator

Enables navigation to master data; for example, Business Partner

Enables sorting, grouping, and subtotals

Provides readily the count of positions in the content area header

Enables triggering of emails and exporting of results to a Microsoft Excel spreadsheet

**Note:**

Positions for which the position component values on the key date are zero (the so-called zero positions) are not displayed.

**Note:**

This app contains in-app help for key fields and concepts. To display the help while working in the app, press F1 or click the question mark displayed in the app header.

**Activities**

- 1. Open the Display Treasury Position Values app.
- 2. Enter your criteria to select the positions you require in the available filter fields:


Basic Data

Key Date

Enter the key date. By default, the system enters the current date.

Date Field for Sel.

Choose whether the entered key date should refer to the Treasury Position Ledger Date (Default) or the Position Date.

Planned Data incld.

You can choose whether the business transactions that affect the position and still have the status Planned are to be included in the selection or excluded.

Company Code

Valuation Area

Business Area

Using the Adapt Filters button, you can choose additional fields to filter the treasury positions.

Examples:

Product Group

Choosing one or more product groups selects the positions for these groups.

The differentiation terms used for your treasury positions and other fields are also available for filtering by choosing Adapt Filters.

**Example:**

Product type

Valuation class (special valuation class)

Security Class

Securities Account

If you use the following fields as differentiation terms for your position, you can select positions by these fields:

WBS Element

Cost Center

Profit Center

Functional Area

If you have defined your own differentiation terms (in the Define Custom Differentiation Terms configuration activity) and you use the fields as differentiation terms for your treasury positions, these fields are also available as selection criteria.

The following fields are available if Public Sector Management is used. When flows are posted to Financial Accounting, the values of the account assignments are also transferred to the journal entry:

Fund

Grant

You can select exposure item data and exposure subitem data using the following fields:

Exposure Item ID

Exposure Subitem ID

To see hedge-accounting-relevant values, choose Adapt Filters and then choose the relevant filters, such as Hedged Item and Hedging Instrument, from the Hedge Accounting subarea.

- 3. Choose Execute.
- 4. The system displays a list of the treasury positions you selected.


To see the relevant position component values for your financial transactions and your exposure subitems, choose Settings and select the relevant values from the dialog box.

By selecting a position from the list and choosing Position Indicator, you can jump to the position indicator for that position (display mode of Manage Position Indicators app).

By selecting a position from the list and choosing Position Flows, you can jump to the flows of the relevant position in Display Treasury Position Flows app.

**Supported Device Types**

Desktop

Tablet

**Related Information**

Display Treasury Position Flows Position Indicator Manage Position Indicator

##### Treasury Position Analysis

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Treasury Position Analysis | L4 | trm01 p.166 | loio `79d483576ea1a96be10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/79d483576ea1a96be10000000a4450e5.html?locale=en-US)

**Use**

This analytical app displays the position values for selected treasury positions on a user-defined key date, on a highly aggregated level. It also allows you to get more detailed information on position level.

How-to Video: Working with Reports (Multidimensional Data Grid Apps) (English Only)

[figure TRM01-F044]

Open this video in a new window

**Note:**

Captions are available for multiple languages. Use the CC (Closed Captions) button in the video player to see which languages are supported.

You can also use the Search within video field to search for specific text in the English or German captions.

**Key Features**

Provide five tiles to display the position values:

Treasury Position Analysis (SAP Fiori ID W0049)

Display position values for all treasury positions.

Treasury Position Analysis – Accounting View (SAP Fiori ID W0118)

Display position values for all treasury positions, from accounting point of view.

Treasury Position Analysis – OTC Transactions (SAP Fiori ID W0121)

Display position values for treasury positions of product group OTC Transactions.

Treasury Position Analysis – Securities (SAP Fiori ID W0120)

Display position values for treasury positions of product group Securities.

Treasury Position Analysis – Listed Derivatives (SAP Fiori ID W0119)

Display position values for treasury positions of product group Listed Derivatives.

Allow quick, ad hoc and flexible reporting in a flexible list.

Present results in a high-level aggregated form, with the possibility to go to position-level details by adding attributes as rows or columns to the content area.

Navigate to master data such as securities account, security class, futures account, issuer, or counterparty, using the Jump to functionality.

Navigate to originating financial transaction, using the Jump to functionality.

Sort, group and calculate subtotals for the results.

Export results to Excel.

Extensibility

**Note:**

This app is not suitable to be extended.

Supported Device Types

Desktop

**More Information**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. The SAP Fiori apps reference library is available here: https://fioriappslibrary.hana.ondemand.com

To see this app’s Fiori content, search for the app. Then select SAP S/4HANA as the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

##### Treasury Position History

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Treasury Position History | L4 | trm01 p.167 | loio `16f4ce5fcba54a41a8753ba0c84c6d46` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/16f4ce5fcba54a41a8753ba0c84c6d46.html?locale=en-US)

App ID: F3966

With this app, you can analyze the changes of important Treasury position values such as the book value or the amortized acquisition value over one or multiple periods at a glance. The key date together with one of the various available periods defines the dates, for which the position values are calculated. The Treasury Position History allows you to display the position values for one single date, for one period, or for multiple periods such as End of Last Year, Year to Date, or Last 4 Quarters.

You can compare the position values of a valuation area at the different dates on a high aggregation level or break down the position values into dimensions like company codes, currencies, valuation classes, and account assignment references. The breakdown on a more detailed level provides you more insight about the reconciliation between the Treasury subledger and the general ledger. In addition, you gain deeper insight by navigating to the contributing single Treasury positions / financial transactions for further analysis.

The aggregated position values are calculated according to your settings in the filters. In the filters, you define for which dates the position values are calculated. You also define which Treasury positions are selected using dimensions such as company code, product type, position currency, and valuation area. In addition, you decided on the display currency and the relevant exchange rate type for the currency translation.

Which positions components are displayed depends on the chosen view. Using the   Settingsbutton, you can choose the position values (type Measure) from the list.

Examples:

Purchase Value in DC

Acquisition Value DC

**Note:**

For more information for the position components, see also Position Components.

**Note:**

Do not choose position values in another currency than the display currency.

The app calculates the chosen position values in the display currency and shows them in a chart view and a table view. You can switch between the different view types using the following buttons:

  Chart andTableView

  ChartView

  TableView

**Note:**

For the chart view you can switch between different chart types, such as Bar Chart and Column Chart.

The table view allows the drill down to the single Treasury positions/financial transactions contributing to the displayed position value.

**Filters**

The Treasury positions are selected and the position values are calculated according to your settings for the filters.

Standardfilters:

Key Date

The key date is the reference date within the app. Together with the period it defines for which dates the position values are calculated.

When you call the app, the key date field is filled with the current system date, but you can overwrite the default entry.

Period

The period together with the key date defines the dates for which the position values are calculated and displayed in the Treasury Position History app.

You can calculate the position values only for one single date, for one period, or for multiple periods.

Single Date

If you choose one of the following periods, the app calculates the position values for one specific date:

Key Date

The app calculates the position values for the key date.

End of Last Year

The app calculates the position values for the last day of the last year derived from the key date.

Example:

Key date: 2019-05-15

End of last year: 2018-12-31

End of Last Month

The app calculates the position values for the last day of the last month derived from the key date.

Example:

Key date: 2019-05-15

End of last month: 2019-04-30

End of Last Quarter

The app calculates the position values for the last day of the last quarter derived from the key date.

Example:

Key date: 2019-05-15

End of last quarter: 2019-03-31

One Period

For this kind of period, two dates are always determined to define the start date and the end date of the period.

Year to Date

The app calculates the position values for the last day of the last year derived from the key date and for the key date.

Example:

Key date: 2019-05-15

End of last year: 2018-12-31

Position values are calculated for both dates.

Month to Date

The app calculates the position values for the last day of the last month derived from the key date and for the key date.

Example:

Key date: 2019-05-15

End of last month: 2019-04-30

Position values are calculated for both dates.

Quarter to Date

The app calculates the position values for the last day of the last quarter derived from the key date and for the key date.

Example:

Key date: 2019-05-15

End of last quarter: 2019-03-31

Position values are calculated for both dates.

Last Quarter

The app calculates the position values for the last day of the last quarter derived from the key date and for the last day of the quarter before the last quarter.

Example:

Key date: 2019-05-15

End of last quarter: 2019-03-31

End of quarter before last quarter: 2018-12-31

Position values are calculated for dates 2019-03-31 and 2018-12-31.

Last Month

The app calculates the position values for the last day of the last month derived from the key date and for the last day of the month before the last month.

Example:

Key date: 2019-05-15

End of last month: 2019-04-30

End of month before last month: 2019-03-31

Position values are calculated for the dates 2019-04-30 and 2019-03-31.

Multiple Periods

For the following predefined periods, the app calculates the position values for a number of dates, spaced by the chosen period length, needed to describe the chosen number of periods:

Last 4 Quarters

The app calculates the position values for the last day of the last quarter derived from the key date and for the last days of the 4 quarters before the last quarter.

Example:

Key date: 2019-05-15

End of last quarter: 2019-03-31

End dates of the 4 quarters before the last quarter: 2018-12-31, 2018-09-30, 2018-06-30, 2018-03-31

Position values are calculated for dates 2019-03-31, 2018-12-31, 2018-09-30, 2018-06-30, and 2018-03-31.

Last 3 Months

The app calculates the position values for the last day of the last month derived from the key date and for the last days of the 3 months before the last month.

Example:

Key date: 2019-05-15

End of last month: 2019-04-30

End dates of the 3 months before last month: 2019-03-31, 2019-02-28, 2019-01-31

Position values are calculated for the dates 2019-04-30, 2019-03-31, 2019-02-28, and 2019-01-31.

Last 6 Months

The app calculates the position values for the last day of the last month derived from the key date and for the last days of the 6 months before the last month.

Last 12 Months

The app calculates the position values for the last day of the last month derived from the key date and for the last days of the 12 months before the last month.

Display Currency

Enter the display currency.

The display currency is the currency in which the position values are calculated and displayed in the app.

If the position currency is different from the display currency, the position values need to be converted to the display currency. The currency translation uses the current FX rate of the currency pair PC/DC of the exchange rate type that has also been entered.

Exchange Rate Type

Enter the exchange rate type.

The exchange rate type distinguishes between different kinds of rate. If you enter an FX rate in the market data table, you must assign the exchange rate type.

If the position currency is different from the display currency, the position values are translated into the display currency. The currency translation uses the current FX rate of the currency pair PC/DC of the exchange rate type specified.

Valuation Area

Enter the valuation area.

Company Code

You can restrict the selection of Treasury positions to one or more company codes.

Position Currency

The position currency is the original currency of a position in which the operative flows are posted.

Examples:

Positions of a bond issued in USD (nominal value in USD, interest flows paid in USD) have the position curreny USD.

For positions of money market transactions the position currency is equal to the transaction currency.

Product Type

The product type controls the structural characteristics (such as condition types and flow types) that are assigned to individual instruments.

Using the Adapt Filters button, you can use more criteria for Treasury position selection, such as the differentiation terms and other fields, and save a specific combination of filters.

**Example:**

Valuation Class

Security Class

Securities Account

If you use the following fields as differentiation terms for your position, you can select positions by these fields:

WBS Element

Cost Center

Profit Center

Functional Area

If you have defined your own differentiation terms (in the Define Custom Differentiation Terms configuration activity) and you use the fields as differentiation terms for your treasury positions, these fields are also available as selection criteria.

The following fields are available if Public Sector Management is used. When flows are posted to Financial Accounting, the values of the account assignments are also transferred to the journal entry:

Fund

Grant

You can select exposure item data and exposure subitem data using the following fields:

Exposure Item ID

Exposure Subitem ID

By choosing the   Visual Filterbutton, you get the Book Value in DC by Company Code as bar chart, Book Value in DC by Position Currency as donut chart, and the Book Value in DC by Product Type as bar chart. Using the Adapt Filter button, you can change the appearance of the visual filter by changing the Chart Type, the Measures or by deselecting the Show on Filter Bar indicator. In addition, you can change the filter values for company codes, position currencies, and product types.

Within the Adapt Filter function, you can save your settings.

After you have finished your filter settings, choose the Go pushbutton.

**Note:**

You can save your filter settings by choosing Select View Save As . Enter a name for the new view. You can mark the view as the default view and as public visible. If you do not mark the view, it will be saved as your private view.

**Chart View of Position Values**

For the chart view, the following predefined views are available:

Standard

This view displays the Book Value in DC of the selected positions for all relevant dates.

Book Value By Components

The book value is a composite position component that is calculated from different original position components. This view shows the values of the position components contributing to the book value of the analyzed Treasury positions for all relevant dates.

Amortized Costs By Components

The amortized costs is a composite position component that is calculated from different original position components. This view shows the values of the position components contributing to the amortized costs of the selected Treasury positions at all relevant dates.

Amortized Acquisition Value By Components

The amortized acquisition value is a composite position component that is calculated from different original position components. This view shows the values of the position components contributing to the amortized acquisition value of the analyzed Treasury positions for all relevant dates.

**Note:**

You can manually change the displayed position values (measures) and the characteristics (dimensions) by which you want to aggregate the values.

View By

Using this button, you can choose more characteristics to split the calculated values accordingly.

Examples:

Accounting Code

Product Type

Using the   Settingsbutton, you can choose extra characteristics of the positions (of type Dimension) from the list and also more position values in display currency (of type Measure).

Example:

You can choose the Partner (Commitment) dimension. This field is filled for each type of treasury position. The determination rules for this field are as follows:

For securities positions, the issuer of the security is displayed in the Partner (Commitment) field.

For all other treasury positions, the counterparty of the financial transaction is displayed in the Partner (Commitment) field.

You can save this view by choosing Select View Save As . Enter a name for the new view. You can mark the view as the default view and as public visible, if you do not mark the view it will be saved as your private view.

Using   Toggle LegendVisibility, you can display or hide the legend that explains the displayed position values.

**Table View of Position Values**

You can use the predefined Standard view to display the selected positions. This view displays the Book Value in Display Currency on the aggregation level Date / Company Code / Product Type.

For a detailed analysis, you can mark a row in the table and choose the Display Position Values button. You navigate to the Display Treasury Position Values app. The app lists the Treasury positions contributing to the value displayed in the row. You can see the position values in position currency and valuation currency. Further, you can use drill down functionality to position flows or you can view the position indicator or the position management procedure.

Using the   Settingsbutton, you can choose extra characteristics (of type Dimension) and position values in display currency (of type Measure) from the list.

You can save this view by choosing Select View Save As . Enter a name for the new view. You can mark the view as the default view and as public visible. If you do not mark the view, it will be saved as your private view.

Using   Export to Spreadsheetfunction, you can export your currently filtered results into a spreadsheet and save it to your computer.

**Supported Device Types**

Desktop

Tablet

##### Treasury Position Values - Classic

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Treasury Position Values - Classic | L4 | trm01 p.174 | loio `7c08da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7c08da531198434de10000000a174cb4.html?locale=en-US)

App ID: TPM12

This app provides you with an overview of your treasury positions for a particular key date. The following information is displayed for each position:

Differentiation terms (such as, company code, valuation area, valuation class, transaction number, ID number, securities account)

Position component values (units, nominal amounts, acquisition value, book value)

**Note:**

For positions of hedging instruments of the hedge accounting for exposure items process, also the positions components of the exposure subitems are shown. The exposure subitem is a position which is needed when you use the automated designation process for hedge accounting. It represents a valuation-area-specific hedged portion of the exposure item and it is also used as a carrier for the hedging reserve and cost of hedging reserve for the hedging instrument according to the relevant hedge accounting rule. The following position components are available for the exposure subitems:

- 1300 To-be-classified

- 1301 Hedge adjustment


- 1302 Effective

- 1303 Ineffective


- 1322 Effective Cost of Hedging Reserve

- 1323 Ineffective Cost of Hedging Reserve

- 1324 Effective Hedging Reserve


1334 Ineffective Hedging Reserve

- 1343 P&L Effective Designated

- 1344 P&L Effective Non-Designated

- 1345 Amortization Non-Designated


The values of the position components are shown in position currency and also in valuation currency.

For more information, see also Overview Hedge Accounting Rules.

Other position information (such as exchange, business partner)

**Features**

This app provides the following key features:

Shows detailed information on selected treasury positions with the possibility of further navigation; for example, navigation to the corresponding position management procedure and the following apps:

Treasury Position Flows - Classic

Manage Position Indicator

Enables navigation to master data such as business partner, position management procedure, or position indicator.

**Activities**

- 1. Open the Treasury Position Values - Classic app on SAP Fiori launchpad.
- 2. Choose the relevant product groups.
- 3. Enter the general selection criteria for the positions:


**Note:**

If you don’t choose a product group, no treasury positions are selected.

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

If you use the integration with Public Sector Management, the system automatically derives the values for the fields fund, grant, functional area, and profit center from the master data records of the assigned cost center or WBS element, when you enter the cost center and the WBS element,

For more information, see also Integration with SAP Public Sector Management (PSM).

**Note:**

WBS element, cost center, profit center, and functional area are additional differentiation criteria available for OTC transactions and securities.

**Note:**

The only product groups displayed are those that were selected in the Product Groups area.

Securities

ID number

Securities account

Securities account group

Portfolio (position)

Listed Derivatives

SecurityClass ID No.

Futures Account

Long/Short Position

For some reports, this field isn't available.

Lot-Generating Transaction No. (not in all reports available)

For some reports, this field isn't available.

OTC Transactions (MM, FX, OTC Derivatives, TF Transactions)

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

Exposure Items

Exposure Item ID

Exposure Subitem ID

Additional Selection Criteria

Financial Transaction

Hedging Relationship Number

**Note:**

For some reports, this area isn't available.

Select from OTC Transaction.

If you set this indicator, the field for entering financial transaction numbers is no longer ready for input. The system now searches for the exposure items by the financial transactions selected using the fields in the OTC Transactions group.

**Note:**

For some reports, this indicator isn't available.

- 4. Control Parameter


Enter the Key Date.

The treasury position values are determined by selecting all business transactions on/before the key date for the selected treasury positions.

You can set the Selection by Posting Date indicator.

If you set this indicator, he system considers only those business transactions that are fixed/posted and have a posting date on/before the key date. Therefore, reversed business transactions are included if the reversal date is after the key date.

The Exclude Special FI Period indicator only appears on the selction screen, when you set the Selection by Posting Date indicator.

If you additionally set the Exclude Special FI Periods indicator,the system will perform the following additional checks to exclude business transactions posted in special periods:

The system determines the fiscal period and fiscal year of the key date (for the corresponding company code and valuation area of the business transaction). If the key date is not within last fiscal period, the system does not perform additional checks (since posting to special periods is only possible if the posting date is in the last fiscal period of the fiscal year).

If the key date is in the last fiscal period of the fiscal year, the system derives the fiscal period and fiscal year of the posting date of the business transaction. If the derived fiscal period or fiscal year differ from the fiscal period or fiscal year of the key date, the system does not perform additional checks.

If the derived fiscal period and fiscal year of the posting date of the business transaction match the fiscal period and fiscal year of the key date, it may be necessary to exclude the business transaction. The system therefore compares the actual fiscal period that was used for the posting. If the fiscal period of the posting is different from the fiscal period of the key date, the business transaction is excluded (since in that case the posting was made using a special fiscal period).

No Zero Positions indicator

If this indicator is set, the data records containing key figures selected in the report definition with a key date value of zero are excluded from the report output.

Include Planned Data indicator

If this indicator is set, the business transactions with planned status that affect the position are included.

Hist.Acct Assgmt Ref

If you set this indicator, the system reads historical data instead of the current account assignment reference and G/L account when you run evaluations in the past. In other words, if an account assignment transfer has been carried out in the meantime, the system displays the account assignment reference and G/L accounts that were valid on the respective key date.

Subpositions in Flat List

If this indicator is set, the results are displayed on subposition level for different Treasury subledger positions.

If this indicator is not set, the main result list displays the Treasury subledger position details and you can navigate to the subpositions with the Display Subpositions pushbutton in the Subposition column.

- 5. Amount Scaling


Amount Scaling Is Active

Scaling

Decimal Places

Layout

Choose a layout for the result list.

Display List of Messages

If this indicator is set, the list of messages is displayed that occurred when executing the transaction or the program. The messages can be error messages but also warnings or information messages.

- 6. Market Values

Market value in position currency

Securities Exchange (optional)

If you have defined an exchange, the current exchange rate in this exchange is used to determine the market value.

If you have not entered an exchange, the system then determines whether one was defined for each company code and ID number using the function Edit Exchanges. If an exchange was not defined, the class data is read to see if a home exchange can be identified. If the system could not determine a home exchange, an exchange is then selected at random.

Security price type (optional)

You can specify the price type for the exchange to determine the market value.

If the price type has not been specified, the system attempts to determine one from a security valuation procedure assigned to the position.

Exchange rate type for translation into valuation currency

Specify an exchange rate type for translating into the valuation currency.

If you do not specify an exchange rate type, the system uses the standard M.

- 7. Choose Execute.


**Results List**

The position list is displayed using the SAP List Viewer. The list provides you with the values of the position components for the key date for the selected positions.

Standard layout variants are delivered for the different product categories. To view other position information (such as the exchange or business partner), call the Change Layout function and transfer the required fields.

The following functions are available from the result list:

Display flows

You can use this function to branch to the List of Position Flows for a selected position or transaction.

Display securities account group

Display Position Management Procedure

Display Position Indicator

Securities: Detail View

The detail view displays the differentiations and position components in the position currency and valuation currency including the price/rate in position currency and exchange rate, for the selected security position.

###### Product Groups (1 of 2)

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Treasury Position Values - Classic > Product Groups | L5 | trm01 p.179 | loio `c90ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c90ada531198434de10000000a174cb4.html?locale=en-US)

Securities

###### General Selections

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Treasury Position Values - Classic > General Selections | L5 | trm01 p.180 | loio `c00ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c00ada531198434de10000000a174cb4.html?locale=en-US)

You can use the following general selection criteria when selecting positions:

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

Listed Derivatives

SecurityClass ID No.

Futures Account

Long/Short Position

For some reports, this field isn't available.

Lot-Generating Transaction No. (not in all reports available)

For some reports, this field isn't available.

OTC Transactions (MM, FX, OTC Derivatives, TF Transactions)

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

**Loans**

Contract Number

External Accounts

External Account

Currency

Exposure Items

Exposure Item ID

Exposure Subitem ID

Additional Selection Criteria

Financial Transaction

Hedging Relationship Number

**Note:**

For some reports, this area isn't available.

Select from OTC Transaction.

If you set this indicator, the field for entering financial transaction numbers is no longer ready for input. The system now searches for the exposure items by the financial transactions selected using the fields in the OTC Transactions group.

**Note:**

For some reports, this indicator isn't available.

##### Treasury Position Flows - Classic

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Treasury Position Flows - Classic | L4 | trm01 p.182 | loio `b3a1c7531dc61d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b3a1c7531dc61d4be10000000a174cb4.html?locale=en-US)

**Use**

The Treasury Position Flows - Classic app lists all the flows for a position in chronological order. The valuation-area-independent operative business transactions are displayed as well as the valuation-area-dependent operative business transactions and the derived business transactions that they trigger. Movements that belong to a business transaction are highlighted.

**Integration**

See also: Cash Flows

**Features**

Selection

Product Groups

General Selections

Restriction of TRL Flows

TRL Date

Update Type

You can restrict the displayed flows to specific update types.

Last Edited On

Last Changed By

Besides using the above date information to restrict the selection, you can also use the flow status in the selection:

Status of flows in operative business transactions

|Blocked for Posting|This status is assigned to transaction flows in the following cases: The transaction activity is not relevant for posting. The activity designated as the Activity Relevant for Posting is the last activity in the activity chain. When you use processing category 00001, the activity relevant for posting is the contract, and, with processing category 00002, it is the settlement. The transaction has reached the activity that is relevant for posting, but the activity has not yet been saved. Instead, it has been put on hold ( Security Transaction Hold ). The transaction flows still have the status Planned Records, and the transaction can still be changed.|
|---|---|
|Flagged for Posting|If the transaction has reached the activity that is relevant for posting and has been saved, it is assigned the posting status Flagged for Posting.|
|Posted|If the flows have been updated to the general ledger by the posting function, the flows are assigned the status Posted and are converted from planned records to actual records (in other words, they are fixed).|
|Flagged for Reversal|If you reverse a transaction that has posted flows using the Transaction Reverse function, the flows are assigned the status Flagged for Reversal.|
|Reversed|If the flows that were reversed have been updated to the general ledger using the Accounting Transaction Reverse Documents function, the flows are assigned the status Reversed.|


Status of flows in derived business transactions

|Plan|If a flow has the status Plan, it has not yet been posted.|
|---|---|


|To Be Fixed| |
|---|---|
|Fixed|If a flow has the status Fixed, it has been posted (if it was relevant for posting).|
|To Be Reversed| |
|Reversed| |


From the Position Flow List, you can call up the following functions:

Display Posting Journal

Display Business Transaction Flows

The List of Flows for the Business Transaction appears.

Display Original Business Transaction

In the case of operative business transactions, you can branch to the function for generating the flows.

Position Display

The List of Position Values for Key Date appears.

See also: Treasury Position Values - Classic

Display Position Indicator

See also: Position Indicator

##### Flexible Position List

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Position Reporting > Flexible Position List | L4 | trm01 p.184 | loio `8a3d9a5181235905e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8a3d9a5181235905e10000000a44538d.html?locale=en-US)

**Use**

You use the flexible position list determines the position values (= values of the position components) for the positions of the Treasury subledger (OTC transactions, listed derivatives, securities positions, and loans) for a key date.

**Features**

Business transactions that change positions and that have the status Plan are included.

Zero positions are also displayed.

**Activities**

To call up the flexible position list, proceed as follows:

- 1. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Information System Position Flexible Position List (transaction TPM12H).
- 2. On the Position Value Monitor dialog box, you specify the key date on which you want to evaluate your positions.


**Note:**

You can change the key date later using the Change Key Date function.

- 3. On the left of the screen, first select the differentiation criteria for the evaluation of the position data.
- 4. Under Flow Data, you can select the treasury ledger date (= position date of the subledger), the update type, and the business transaction category.
- 5. Under Currencies, you can select the position currency, the valuation currency, and the nominal currency.
- 6. Choose the key figures that you want to display.


**Note:**

If you do not want to evaluate all positions, you can restrict the selection of the positions. To do this, choose . The Define Filter screen appears. On the left of the screen, select the differentiation criteria that you want to use to restrict the selection. On the right of the screen, you can now enter values. By choosing , you return to the position list.


**Note:**

You can also use the flexible position list to display the cash flow of a securities account, for example.

**Note:**

With the selection that you make here (in steps 3 – 5), you specify how the list or the aggregation levels are built.

Quantity Key Figures

Unit

Nominal Amount

Original Nominal Amount

Key figures in the valuation currency and position currency

Purchase Value

Security Valuation

Foreign Currency Valuation (not in position currency)

Capitalized Costs

Valuation of Capitalized Costs, Securities

Valuation of Capitalized Costs, Foreign Exchange (not in valuation currency)

Amortization

Premium/Discount (Clearing/Accrual Items)

Index Valuation

Accrual Items: Purchase Value

Foreign Currency Valuation of Amortized Acquisition Value (not in position currency)

Variation Margin

Security Valuation Not Affecting P/L

Foreign Currency Valuation Not Affecting P/L (not in position currency)

Index Valuation Not Affecting P/L

Costs: Security Valuation Not Affecting P/L

Costs: Foreign Currency Valuation Not Affecting P/L (not in position currency)

Accrued Interest

Amortization of Negotiation Spread

Repayment

Book Value

Book Value Without Costs

Acquisition Value

Amortized Acquisition Value

**Note:**

You can use the Save Variant function to save your selection criteria as a variant that you can use the next time that you call up the list.

- 7. Choose .
- 8. On the right of the screen, the results list appears.

The results list is issued using the SAP List Viewer for SAP GUI (Classic). You can use the standard functions of the List Viewer to edit the list.

- 9. On the left of the screen, you can change the selection criteria. After you choose , the changed list is displayed.

#### Display Treasury Alerts

> **Path:** Treasury and Risk Management > Treasury Analytics > Display Treasury Alerts | L3 | trm01 p.186 | loio `53449f57e7356d10e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/53449f57e7356d10e10000000a441470.html?locale=en-US)

**Use**

Financial instrument processes include the following: release and settlement of financial transactions, payment and posting of cash flows, sending correspondence for financial transactions, and fixing of interest rates. To support your processes and to ensure that the individual process steps are executed in time, you can use the following apps that inform you in time when one of the activities has not been executed as expected.

**Display Treasury Alerts - Correspondence**

- App ID: F4983


This app, supports your processes for your outgoing and incoming correspondence. You can define a specific number of hours after which you receive an alert if a counterconfirmation, an outgoing or an incoming correspondence are still pending.

The following filters are available

Issue Message For

Set by the system to display the pending alerts for your correspondence. If you want to see the alerts of another activity, you can change the activity. Alternatively, you can use the specific app for that activity.

Company Code

Transaction

Transaction Type

Product Type

Counterparty

Active Status

Set by the sytem to Active, this ensures that only flows for transactions/activities with active status are selected.

Counterconfirmation Open Since (Hours)

If the counterconfirmation of a counterparty is pending for the specified number of hours or longer, you receive an alert.

The default value for this field is 48 hours. You can change this value.

**Note:**

This is only relevant for financial transactions for which counterconfirmation is required. This depends on the settings in the Assign Attributes for Business Partner Groups Customizing activity.

Outgoing Confirmation Open (Hours)

If the outgoing confirmation for a financial transaction is pending for the specified number of hours or longer, you receive an alert.

The default value for this field is 24 hours. You can change this value.

Incoming Confirmation Open Since (Hours)

If the incoming confirmation for a financial transaction is pending for the specified number of hours or longer, you receive an alert.

The default value for this field is 24 hours. You can change this value.

**Display Treasury Alerts - Release**

- App ID: F4980


This app supports your release process.

The following filters are available

Issue Message For

Set by the system to display the pending alerts for the release of your financial transactions. If you want to see the alerts of another activity, you can change the activity. Alternatively, you can use the specific app for that activity.

Company Code

Transaction

Transaction Type

Product Type

Counterparty

Active Status

Set by the sytem to Active, this ensures that only flows for transactions/activities with active status are selected.

Release Pending Since (Days)

Enter the number of days after the start of term to specify the period within which transactions are usually released.

If a transaction is not released in the period between the start of term and n days after the start of term, a message is displayed in the alert monitor.

**Display Treasury Alerts - Settlement**

App ID: F4979

This app supports your settlement process. You can enter a specific number of days before the final due date or after the contract date to define when you want to be notified should a financial transaction not have been settled by that date.

The following filters are available

Issue Message For

Set by the system to display the pending alerts for the settlement of your financial transactions. If you want to see the alerts of another activity, you can change the activity. Alternatively, you can use the specific app for that activity.

Company Code

Transaction

Transaction Type

Product Type

Counterparty

Active Status

Set by the sytem to Active, this ensures that only flows for transactions/activities with active status are selected.

Open Days Before Final Due Date

Enter a number of days before the final due date to define when you want to be notified should a financial transaction not have been settled by that date.

If a financial transaction has not yet been settled n days before the final due date, a message is displayed in the Alert Monitor.

Open Days After Contract Date

In this field, you enter the number of days that are usually between the contract date and the settlement date.

The system selects only financial transactions that have not been settled after this number of days since the contract date.

This filter is not shown in the Standard view, but you can choose it using the Adapt Filters button.

**Display Treasury Alerts - Interest Rates**

App ID: F4982

This app supports your interest rate fixing process for financial transactions with variable interest conditions. You can enter the interest rate fixing date and the reference interest rate you are interested in. If you do not enter anything in the fields (default setting), you get a list with all financial transactions with pending interest rate fixings. The warning message tells yousince which due date the interest rate fixings are missing for the financial transaction.

The following filters are available

Issue Message For

Set by the system to display the pending alerts for the fixing of interest rates. If you want to see the alerts of another activity, you can change the activity. Alternatively, you can use the specific app for that activity.

Company Code

Transaction

Transaction Type

Product Type

Counterparty

Active Status

Set by the sytem to Active, this ensures that only flows for transactions/activities with active status are selected.

Int. Rate Fixing Open Since (Date)

Enter the interest rate fixing date. You get warning messages for all financial transactions with an open interest rate fixing at this date.

Reference Interest Rate

Enter the reference interest rate for which you would like to see financial transactions with pending interest rate fixings.

**Display Treasury Alerts - Posting**

- App ID: F4984


This app supports the posting process of the posting-relevant flows of financial transactions. By default, you receive a list of all financial transactions with pending posting-relevant flows with a due date that is before or equal to the current date. You can restrict which flows are checked by using the general filters available and additional filters, such as the affected payment currency, house bank, house bank account, and flow classification.

The following filters are available

Issue Message For

Set by the system to display the pending alerts for the posting of flows. If you want to see the alerts of another activity, you can change the activity. Alternatively, you can use the specific app for that activity.

Company Code

Transaction

Transaction Type

Product Type

Counterparty

Active Status

Set by the sytem to Active, this ensures that only flows for transactions/activities with active status are selected.

Up to and Including Due Date

Due date of a flow, the field value is set to the current date. Flows have a due date as of which they are effective. Therefore, the posting and payment of flows must be executed by this date at the latest.

You find all flows of financial transactions that have not yet been posted or paid and for which the due date is earlier than or the same as the date entered.

You can change the entered date.

Payment Currency

House Bank

House Bank Account

Classification

**Display Treasury Alerts - Payment**

- App ID: F4981


This app supports the posting of payments of payment-relevant flows of financial transactions. By default, you receive a list of all financial transactions with pending payment-relevant flows with a due date that is before or equal to the current date. You can restrict which flows are checked by using the general filters available and additional filters, such as the affected payment currency, house bank, and house bank account.

The following filters are available:

Issue Message For

Set by the system to display the pending alerts for the payment of flows. If you want to see the alerts of another activity, you can change the activity. Alternatively, you can use the specific app for that activity.

Company Code

Transaction

Transaction Type

Product Type

Counterparty

Active Status

Set by the sytem to Active, this ensures that only flows for transactions/activities with active status are selected.

Up to and Including Due Date

Due date of a flow, the field value is set to the current date. Flows have a due date as of which they are effective. Therefore, the posting and payment of flows must be executed by this date at the latest.

You find all flows of financial transactions that have not yet been posted or paid and for which the due date is earlier than or the same as the date entered.

You can change the date entered.

Payment Currency

House Bank

House Bank Account

**Key Features of All Tiles**

These apps support the following features:

Provides a dynamic count of all the alert messages of a particular alert category, even before you launch the respective tile.

Using the general filters Company Code, Transaction, Transaction Type, Product Type, and Counterparty, you can restrict how many financial transactions are checked.

Enables alert emails to be sent directly from the respective tile.

Export to Spreadsheet

You can export your currently filtered results into a spreadsheet and save it to your computer.

Using the Adapt Filters function, you can choose different filters to those selected in the Standard view.

You can define and save your own views for the apps.

**Note:**

This app contains in-app help for key fields and concepts. To display the help while working in the app, press F1 or click the question mark displayed in the app header.

**Supported Device Types**

Desktop

Tablet

#### CDS Views for Treasury and Risk Management (1 of 2)

> **Path:** Treasury and Risk Management > Treasury Analytics > CDS Views for Treasury and Risk Management | L3 | trm11 p.49 | loio `961bfa9bba614925a938b205ee2c5e2d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/961bfa9bba614925a938b205ee2c5e2d.html?locale=en-US)

The following table shows the CDS views available for Treasury and Risk Management. Based on the CDS views released, you can create your own query views.

The CDS query views can be used by any tool that supports CDS views, such as SAP Analysis for Microsoft Office, Design Studio, SAP Lumira, or SAP Analytics Cloud. For more information about CDS views, see also CDS Views.

**Note:**

You will find the Treasury Executive Dashboard story as example content in the SAP Analytics Cloud application. The story is based on the available CDS query views for Treasury Management in the back-end system. The following two packages for Treasury and Management are available in SAP Analytics Cloud:

Treasury Management for SAP S/4HANA 2022 and Cloud

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2022 and subsequent releases and SAP S/4HANA Cloud Public Edition.

Treasury Management for SAP S/4HANA 2020

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2020 and subsequent releases.

The two packages both contain a story for the Treasury Executive Dashboard. The difference is that two CDS views have been replaced with a new version with some technical improvement. The exchange of some CDS views in the package Treasury Management for SAP S/4HANA 2022 and Cloud has improved the performance of the Treasury Executive Dashboard.

For more information, see also Treasury Executive Dashboard Available in SAP Analytics Cloud.

Overview of CDS Views in Treasury and Risk Management

|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|System Data|Treasury Counterparty Limit Utilization Base |I_TrsyCtptyLmtUtilznBase| | |
|System Data|Product Category|I_FinancialInstrProdCat| | |
|System Data|Transaction Category |I_FinInstrTransCat| | |
|System Data|Option Settlement Type |I_OptionSettlementType| |I_OptionSettlementTyp|
|System Data|Option Exercise Type|I_OptionExerciseType| |I_OptionExerciseTypeT|
|System Data|Trade Finance Category |I_TradeFinanceCategory| |I_TradeFinanceCategor|
|Transactional Data|Financial Transaction |I_FinancialTransactionDEX|Only for data extraction| |
|System Data|Securities Account Category |I_SecurityAccountCategory| | |
|System Data|Security Class Stock Category |I_SecurityClassStockCategory| | |
|System Data|Security Class Quotation |I_SecurityClassQuotation| | |
|System Data|Listed Derivative Quotation |I_ListedDerivativeQuotation| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|System Data|Listed Derivative Category |I_ListedDerivativeCategory| | |
|System Data|Option Put/Call Code |I_OptionPutCallCode| | |
|System Data|Debt Investment Indicator |I_TrsyCshFlowDebtInvmtCode| | |
|System Data|Fixed Variable Interest Category |I_FixedVariableInterestCat| | |
|Configuration Data|Geographical Center of a Country/Region |I_TrsyFinStsCountryGeoPoint| | |
|System Data|Financial Transaction Processing Category |I_FinTransProcgCategory| |I_FinTransProcgCatego|
|System Data|Financial Instrument Activity Category |I_FinInstrActivityCategory| |I_FinInstrActivityCat|
|System Data|Financial Transaction Flow Category |I_FinTransFlowCategory| |I_FinTransFlowCategor|
|System Data|Financial Condition Condition Category |I_FinCndnConditionCategory| |I_FinCndnConditionCat|
|System Data|Treasury Contract Type |I_TreasuryContractType| |I_TreasuryContractTyp|
|System Data|Financial Instrument Status |I_FinInstrumentStatus| |I_FinInstrumentStatusT|
|System Data|Financial Transaction Release Status |I_FinTransReleaseStatus| |I_FinTransReleaseStat|
|System Data|Financial Transaction Central Clearing Option |I_FinTransCntrlClrgOption| |I_FinTransCntrlClrgOp|
|System Data|Financial Transaction Central Clearing Status |I_FinTransCntrlClrgStatus| |I_FinTransCntrlClrgSt|


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|System Data|Financial Transaction Confirmation Status |I_FinTransConfStatus| |I_FinTransConfStatusT|
|System Data|Financial Transaction Counterconfirmation Status |I_FinTransCntrconfStatus| |I_FinTransCntrconfSta|
|System Data|Financial Transaction Flow Posting Status |I_FinTransFlowPostgStatus| |I_FinTransFlowPostgSt|
|System Data|Status of Interest Rate Adjustment |I_FinIntrstRateAdjmtStatus| |I_FinIntrstRateAdjmtS|
|System Data|Treasury Payment Request Grouping |I_TreasuryPaytReqGrouping| |I_TreasuryPaytReqGrou|
|System Data|Financial Transaction Direction |I_FinTransactionDirection| |I_FinTransactionDirec|
|System Data|Financial Condition Interest Category |I_FinCndnInterestCategory| |I_FinCndnInterestCate|
|System Data|Financial Transaction Notice Period Unit |I_FinTransNoticePeriodUnit| |I_FinTransNoticePerio|
|System Data|Hedging Relationship Scenario |I_TrsyHedgingRelshpScenario| |I_TrsyHedgingRelshpSc|
|Configuration Data|Treasury Valuation Area |I_TreasuryValuationArea| | |
|Configuration Data|Treasury Valuation Class |I_TreasuryValuationClass| | |
|Configuration Data|Security Account Type |I_SecurityAccountType| | |
|Configuration Data|Product Type|I_FinancialinstrProductType| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Configuration Data|Security Class General Classification |I_SecurityClassGenClassfctn| | |
|Configuration Data|Bond Classification|I_BondClassification| | |
|Configuration Data|Security Class Fund Type |I_SecurityClassFundType| | |
|Configuration Data|Transaction Type|I_FinancialInstrTransType| | |
|Configuration Data|Portfolio|I_TreasuryPortfolio| | |
|Configuration Data|Treasury Hedging Classification |I_TreasuryHedgingClassfctn| | |
|Configuration Data|Treasury Account Assignment Reference |I_TreasuryGLAccountAssignRef| | |
|Configuration Data|Treasury Position Management Procedure |I_TrsyPosManagementProcedure| | |
|Configuration Data|Securities Account Group |I_SecurityAccountGroup| | |
|Configuration Data|Market Data: Basis Spread ID |I_MktDataBasisSpreadID| | |
|Configuration Data|Credit Spread ID|I_CreditSpreadID| | |
|Configuration Data|Reference Entity Attribute |I_ReferenceEntity| | |
|Configuration Data|Volatility Name Definition |I_VolatilityName| | |
|Configuration Data|Volatility Profile Information |I_VolatilityProfile| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Configuration Data|Volatility Type|I_VolatilityType| | |
|Configuration Data|Treasury Company Code Additional Data |I_TreasuryCompanyCodeSetting| | |
|Configuration Data|Treasury Counterparty Limit Type |I_TrsyCtptyLimitType| | |
|Configuration Data|Hedging Relationship Profile |I_TrsyHedgingRelshpProfile| |I_TrsyHedgingRelshpPr|
|Configuration Data|Treasury Reversal Reason |I_TreasuryReversalReason| |I_TreasuryReversalRea|
|Configuration Data|Financial Condition Condition Type |I_FinCndnConditionType| |I_FinCndnConditionTyp|
|System Data|Financial Transaction Flow Posting Blocking Reason |I_FinTransFlowPostgBlkgRsn| |I_FinTransFlowPostgBl|
|Master Data|Financial Status Financial Position |I_FinancialPosition| | |
|Master Data|Financial Status Financial Position Group |I_FinancialPositionGroup| | |
|Master Data|Treasury Security Account |I_SecurityAccount| | |
|Master Data|Security Class|I_SecurityClass| | |
|Master Data|Security Class Bond|I_SecurityClassBond| | |
|Master Data|Security Class Stock|I_SecurityClassStock| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Master Data|Security Class Listed Derivative |I_SecurityClassLstdDerivative| | |
|Master Data|Counterparty|I_Ftr_Counterparty| | |
|Master Data|Treasury Counterparty Limit Business Partner Rating Cube |I_TrsyCtptyLmtBPRatingCube| | |
|Master Data|Treasury Counterparty Limit Business Partner Rating Query |C_TrsyCtptyLmtBPRatingQry| | |
|Master Data|Treasury Market Risk Key Figure Set |I_TrsyMktRskKeyFigureSet| | |
|Master Data|Foreign Exchange Fixing Reference |I_FXFixingReference| |I_FXFixingReferenceTex|
|Transactional Data|Query for Bank Guarantee Overview |C_BankGuaranteeOverviewQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Cube View for Bank Guarantee Overview |I_BankGuaranteeOverview| | |
|Transactional Data|Cube View for Credit Line Utilization |I_CreditLineUtilCube| | |
|Transactional Data|Query for Credit Line Utilization |C_CreditLineUtilQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Financial Transaction |I_FinancialTransaction| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Transactional Data|Treasury Facility Contract |I_FacilityContract| | |
|Transactional Data|Fin. Trans.: Nominal Amount |I_FinTransNominal| | |
|Transactional Data|Fin. Trans.: Interest Information |I_FinTransInterest| | |
|Transactional Data|Fin. Trans.: Securities Information |I_FinTransSecurity| | |
|Transactional Data|Financial Transaction Condition |I_FinTransCondition| | |
|Transactional Data|Fin. Trans. Condition: Single Date |I_FinTransCndnSingleDate| | |
|Transactional Data|Fin. Trans. Condition: Scaled Interest |I_FinTransCndnScale| | |
|Transactional Data|Fin. Trans. Condition: Formula Variable |I_FinTransCndnFmlaVarbl| | |
|Transactional Data|Financial Transaction Flow |I_FinTransFlow| | |
|Transactional Data|Treasury Facility Utilization |I_FacilityUtilization| | |
|Transactional Data|Treasury Position Values Cube |I_TrsyPositionValueCube| | |
|Transactional Data|Hedging Relationship |I_HedgingRelationship| | |
|Transactional Data|Hedged Item|I_HedgedItem| | |
|Transactional Data|Hedging Instrument|I_HedgingInstrument| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Transactional Data|Financial Position Query |C_FinancialPositionQuery|This query view only reports financial positions of financial position groups with asset/liability indicator Asset and Liability, defined in the Define Financial Positions app.| |
|Transactional Data|Financial Status Query |C_FinancialStatusQuery|This query view reports all financial positions, defined in the Define Financial Positions app. This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application. (Package Treasury Management for SAP S/4HANA 2020)| |
|Transactional Data|Query View for Maturity Profile |C_MaturityProfileQuery|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Financial Status 2|C_FinancialStatusQuery2|This CDS view provides| |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
| | | |the same information as the Financial Status Query view, but uses only one filter for company code, which improves performance. This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application. (Package Treasury Management for SAP S/4HANA 2022 and Cloud)| |
|Transactional Data|Financial Status History 2 |C_HistFinancialStatusQry_2|This CDS view provides the same information as the Financial Status History Query view, but uses only one filter for company code, which improves performance. This query view is| |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
| | | |consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application. (Package Treasury Management for SAP S/4HANA 2022 and Cloud)| |
|Transactional Data|Maturity Profile Cash Flow Data Cube |I_MaturityProfileCashFlow| | |
|Configuration|Financial Instrument Product Type Supplement |I_FinInstrProdTypeSuplmnt| | |
|Transactional Data|Financial Transaction Situation |C_FinancialTransactionSitn| | |
|Transactional Data|Financial Transaction General Activity Category |I_FinTransGenActyCategory| |I_FinTransGenActyCate|
|Transactional Data|Financial Status Cube |I_FinancialPositionCube| | |
|Transactional Data|Treasury Counterparty Limit Overview Cube |I_TrsyCtptyLimitOverviewCube| | |
|Transactional Data|Treasury Counterparty Limit Overview Query |C_TrsyCtptyLimitOverviewQ|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Master Data|Financial Transaction Counterparty (Value Help) |I_FinTransacCounterPartyStdVH| | |
|Configuration Data|Financial Transaction Currency Pair (Value Help) |I_FinTransCurrencyPairVH| | |
|Transactional Data|Financial Transaction Activity |I_FinTransActivity| | |
|Transactional Data|Financial Transaction Current Activity |I_FinTransCurrentActivity| | |
|Transactional Data|Financial Transaction Contract Activity |I_FinTransContractActivity| | |
|Transactional Data|Financial Transaction Amount - Query|C_FinTransAmtQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud solution.| |
|Transactional Data|Fin. Trans. Amt on Single Date - Query |C_FinTransSingleDayAmtQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud solution.| |
|Transactional Data|Fin. Trans.: Histl/Fcstd Fee Amt - Query|C_FinTransFcstHistlFeeQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud solution.| |
|Transactional Data|Fin Trans Histl Fcst Fee - Cube |I_FinTransHistlFcstFeeCube| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Transactional Data|Treasury Financial Object |I_TrsyFinancialObject| | |
|Transactional Data|Treasury Market Risk Key Figure Value Cube |I_TrsyMktRskKeyFigValueCube| | |
|Transactional Data|Treasury Market Risk Key Figure Value Query |C_TrsyMktRskKeyFigValueQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Treasury Value at Risk Query |C_TrsyValueAtRiskQuery|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Financial Status History - Query |C_HistFinancialStatusQuery|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application. (Package Treasury Management for SAP S/4HANA 2020)| |
|Transactional Data|Bank Guarantee Type |I_BankGuaranteeType| |I_BankGuaranteeTypeTex|
|Transactional Data|Fin. Trans. Amount by Bank Group Query |C_FinTransBusVolBankGrpQry| | |
|Market Data|Market Data Reporting Date Function |I_MKTDATADATEFUNCTION| | |
|Market Data|Market Data Query for FX Rate |C_MktDataFXRateQuery|This query view is consumed in the Treasury Executive| |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
| | | |Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Market Data: FX Rate Cube View |I_MktDataFXRateCube| | |
|Configuration Data|Market Data: Currency Pair |I_MktDataCurrencyPair| | |
|Market Data|Market Data Query for Basis Spread |C_MktDataBasisSpreadQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Basis Spread Value Cube View |I_MktDataBasisSpreadCube| | |
|Market Data|Market Data Query for Credit Spread |C_MktDataCreditSpreadQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Credit Spread Value Cube View |I_MktDataCreditSpreadCube| | |
|Market Data|Market Data Query for Reference Interest Rate |C_MktDataRefIntrstRateQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Market Data Cube View for Reference Interest Rate |I_MktDataRefIntrstRateCube| | |
|Market Data|Reference Interest Rate |I_ReferenceInterestRate| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
| | | | | |
|Market Data|Market Data Query for Security Price |C_SecurityPriceQuery|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Market Data: Security Price Cube View |I_SecurityPriceCube| | |
|Market Data|Reference Interest Rate Value |I_ReferenceInterestRateVal| | |
|Configuration Data|Security Exchange|I_SecurityExchange| | |
|Configuration Data|Market Data: Security Price Type |I_SecurityPriceType| | |
|Market Data|Market Data Query for Implied Volatility |C_MktDataImpVolatilityQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Implied Volatility Cube View |I_MktDataImpliedVolatilityCube| | |
|Market Data|Historic Exchange Rate Volatility Query |C_HisExchRateVolatilityQry| | |
|Market Data|Historic Exchange Rate Volatility Cube |I_ExchangeRateVolatilityCube| | |
|Market Data|Historic Security Price Volatility Query |C_HisScrtyPrcVolatilityQry| | |
|Market Data|Historic Security Price Volatility Cube |I_ScrtyPrcVolatilityCube| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Market Data|Historic Interest Rate Volatility Query |C_HistIntRateVolatilityQry| | |
|Market Data|Historic Interest Rate Volatility Cube |I_InterestRateVolatilityCube| | |

#### Treasury Executive Dashboard Available in SAP Analytics Cloud

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Executive Dashboard Available in SAP Analytics Cloud | L3 | trm01 p.206 | loio `6c9a4be0b43844a5a80a2f1756bd2b44` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6c9a4be0b43844a5a80a2f1756bd2b44.html?locale=en-US)

The Treasury Executive Dashboard in SAP Analytics Cloud visualizes real-time insights into treasury operations for treasury executives. The app shows key performance indicators, such as liquidity, cash position, debt volume and structure, counterparty limits, volume of bank guarantees, and market trends.

The data presented from different application areas, such as Cash and Liquidity Management, Treasury and Risk Management, and Financial Accounting, is based on live data access to the back-end system without data replication. The data is shown in the display currency and presented in the most appropriate way using a broad range of graphs, such as bar chart, column chart, pie chart, heat map, tables, or line chart.

Here's an example of what a tab in the Treasury Executive Dashboard looks like (English only):

[figure TRM01-F046 - Here's an example of what a tab in the Treasury Executive Dashboard looks like (English only):]

You will find the Treasury Executive Dashboard story as example content in the SAP Analytics Cloud application. The story is based on the available CDS query views for Treasury Management in the back-end system. The following two packages for Treasury and Management are available in SAP Analytics Cloud:

Treasury Management for SAP S/4HANA 2022 and Cloud

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2022 and subsequent releases and SAP S/4HANA Cloud Public Edition.

Treasury Management for SAP S/4HANA 2020

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2020 and subsequent releases.

The two packages both contain a story for the Treasury Executive Dashboard. The difference is that two CDS views have been replaced with a new version with some technical improvement. The exchange of some CDS views in the package Treasury Management for SAP S/4HANA 2022 and Cloud has improved the performance of the Treasury Executive Dashboard.

**Configuration and Master Data**

The basic content with which to run this app is provided with scope item 49P. For more information, see also the set-up instructions for the scope item 49P in the SAP Best Practices Explorer.


In addition, running the app requires configuration settings to be made and master data to be available in Treasury Management.

For more information, see also Configuration and Master Data for the Treasury Executive Dashboard

**Prerequisites**

To ensure that current data is available on the Counterparty Risk tab, you must run the End-of-Day Processing on the same day and before you start the Treasury Executive Dashboard in SAP Analytics Cloud.

To ensure that current data are available on the Market Risk tab, you must calculate the market risk key figures in back-end system before you start the Treasury Executive Dashboard using the Calculate Market Risk Key Figures report (transaction RAEP1_KFSET), you can plan it as a periodic batch job.

**Additional Details**

The app has the following tab pages:

Liquidity

The liquidity is defined as the sum of financial positions representing assets. The tab shows the liquidity as a KPI and analyzed by different attributes, such as regions, company codes, financial position groups, financial positions, and currencies. In addition, the history of liquidity is shown.

Cash Management

Shows your cash position forecast, mid-term liquidity forecast, as well as actual cash flows.

Bank Relationship

Provides an overview of your banks and bank groups by different attributes, such as ratings, payment amounts, number of company codes, bank accounts, financial status, bank fees, amount of financial transactions, and fee of financial transactions.

Indebtedness

Monitors KPIs related to the debt of your company and analyzed by different attributes.

Counterparty Risk

Provides an overview of the limit utilization and free limits of a specific limit type by counterparty and counterparty ratings.

Market Risk

Provides you with the key perfomance indicators net present value and value at risk including charts analyzing these values by different aspects.

Bank Guarantee

Provides an overview of the volume and average fee rate of bank guarantees.

Market Overview

Shows the trend for different market rates as KPIs and analyzed by different attributes.

**Note:**

The Treasury executive dashboard reads available operational data from Cash Management, Treasury and Risk Management (financial transactions, treasury positions, limit data, and market data), and Financial Accounting in the back-end system. If the required data for a specific chart isn’t available in your back-end system, the chart or tab is visible, but no data is displayed and a message is shown.

**Technical Details**

The app is delivered with default values for the variables.

Overview: Input Parameters for the Data Sources of the Dashboard Tabs

|Dashboard Tab|Input Parameters for the Data Sources|Default Values for Variables|
|---|---|---|
|Liquidity|C_FINANCIALSTATUSQUERY_2|<Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate. <Key Date>is set to the current date.|
| |C_HISTFINANCIALSTATUSQRY_2|<Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate. <Key Date>is set to the current date. <Period>is Last 4 Quarters.|
|Cash Management|C_LIQUIDITYPOSITIONQUERY1|<Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate. <Key Date>is set to the current date.|
|Bank Relationship|C_PAYMENTBYBANKKPI: Defines settings for Total Incoming, Total Outgoing, Average Incoming, and Average Outgoing figures.|<Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate.|


|Dashboard Tab|Input Parameters for the Data Sources|Default Values for Variables|
|---|---|---|
| |C_PAYMENTBYBANKKPI: Defines settings for the Banks by Payment Amount card. C_FINANCIALSTATUSQUERY: Define settings for cards in the Financial Status group. C_FINTRANSSINGLEDAYAMTQRY: Defines settings for the Distribution of Product Group Amount by Bank Groups card in the Amount of Financial Transactions group. C_FINTRANSAMTQRY1: Defines settings for the History of Product Group Amount by Bank Groups card in the Amount of Financial Transactions group. C_FINTRANSFCSTHISTLFEEQRY: Define settings for the Fee of Financial Transaction group.|Specific variables forC_FINTRANSSINGLEDAYAMTQRY: <Start Date>and<End Date>are set to show the last year. <Reporting Frequency>is set to Daily Specific variable for C_FINTRANSFCSTHISTLFEEQRY: Reporting Period: Enter the start and end dates of the review period for the fees paid. The variables Historical Start Date (default date is the system date minus one year) and Historical End Date (default date is the system date) are available for this. Forcast Period: Enter the start and end dates of the forcast period for the forcasted fees. The variables Forcast Start Date (default date is the system date) and Forcast End Date (default date is the system date plus one year) are available for this.|
|Indebtedness|C_MATURITYPROFILEQUERY C_CREDITLINEUTILQRY|Default variable values for C_MATURITYPROFILEQUERY <Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate. <Number of Years>is set to 5. <Key Date>is set to the current date. Default variable values for C_CREDITLINEUTILQRY <Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate. <Start Date>is set to the current date. <End Date>is set to the date a year from now.|


|Dashboard Tab|Input Parameters for the Data Sources|Default Values for Variables|
|---|---|---|
|Bank Guarantee|C_BANKGUARANTEEOVERVIEWQRY|<Product Type>is set to Bank Guarantee. <Transaction Type>is set to Issue. <Key Date>is set to the current date. <Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate.|
|Counterparty Risk|C_TRSYCTPTYLIMITOVERVIEWQ2 C_TRSYCTPTYLMTBPRATINGQRY2|Default variable values for C_TRSYCTPTYLIMITOVERVIEWQ2 <Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate. <Limit Type>is set to BP./LPG. only assets. <Limit Utilization Base>is set to End-of-Day Processing, which shows the limit utilization determined in the last end-of-day processing. You can change the setting to Current Limit Utilization, which is based on last end-of-day processing plus any additional changes triggered by the single transaction check. <Determination Date>is set as a period as follows: From Current date - 1 year until Current date. But the interval is relevant only for the **Note:** The Counterparty Risk tab monitors limit utilizations and free limits of only one specific limit type. This limit type must use the characteristics Business Partner and Limit Product Group. Therefore, you can use only the limit types BP./LPG. only assets and CoCd./BP/LPG only assets.|


|Dashboard Tab|Input Parameters for the Data Sources|Default Values for Variables|
|---|---|---|
| | |line chart History of Free Limits by Counterparty; for all other charts, only the upper limit of the period - that is, the current date - is relevant. Default variable values for C_TRSYCTPTYLMTBPRATINGQRY2 are relevant only for the Counterparty Rating table: <Key Date>is set to the current date.|
|Market Risk|C_TRSYMKTRSKKEYFIGVALUEQUERY C_TRSYVALUEATRISKQUERY|Default variable values for C_TRSYMKTRSKKEYFIGVALUEQUERY <Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate. <MR Key Figure Set>is set to all members [] with evaluation currency EUR and evalautaion type 0001. <Key Date>is set to the 3 month period until current date. Default variable values for C_TRSYVALUEATRISKQUERY <Confidence Level (%)>is the to 95% <Key Date>is set to the current date. <Display Currency>is set to EUR. <Exchange Rate Type>is set to M Standard Translation at Average Rate. <MR Key Figure Set>is set to all members [] calculating net present value and value at risk key figures.|
|Market Overview|C_MKTDATAFXRATEQUERY1 C_MKTDATAREFINTRSTRATEQRY1 C_SECURITYPRICEQUERY C_MKTDATAIMPVOLATILITYQRY3|Default variable values for C_MKTDATAFXRATEQUERY1 <Exchange Rate Type>is set to M Standard Translation at Average Rate.|


|Dashboard Tab|Input Parameters for the Data Sources|Default Values for Variables|
|---|---|---|
| |C_MKTDATACREDITSPREADQRY2 C_MKTDATABASISSPREADQRY|<Currency Pair>is set to EUR/USD. <Calendar Date>is specified as lying between January 1 2018 and the current date. Default variable values for C_MKTDATAREFINTRSTRATEQRY1 <Reference Interest Rate>is set to EURBOND 2 Years. <Calendar Date>is specified as lying between January 1 2018 and the current date. Default variable values for C_MKTDATAIMPVOLATILITYQRY3 <Security Price Type>is set to Spot. The security class is set to EUR AXA Demo. <Calendar Date>is specified as lying between January 1 2018 and the current date. Default variable values for C_MKTDATAIMPVOLATILITYQRY3 <Volatility Name>is set to #. <Volatility Profile>is set to #. <Volatility Type>is set to Currency volatility ask, Currency volatility middle, and Currency volatility bid. <Calendar Date>is specified as lying between January 1 2018 and the current date. Default variable values for C_MKTDATACREDITSPREADQRY2 <Reference Entity>is set to Reference Entity for Partner BANK_DE. <Credit Spread ID>is set to 1 Year Spread. <Quotation Type>is set to Bid. <Calendar Date>is specified as lying between January 1|


|Dashboard Tab|Input Parameters for the Data Sources|Default Values for Variables|
|---|---|---|
| | |2018 and the current date. Default variable values for C_MKTDATABASISSPREADQRY <Quotation Type>is set to Middle. <Basis Spread ID>is set to Cross-Currency Spread EUR vs. USD, Tenor 3m, Maturity 1 Year. <Calendar Date>is specified as lying between January 1 2018 and the current date.|


You can change these variable values to suit your needs for a tab or also for a specific chart using the Edit Prompts/Edit Chart Prompts function.

- 1. If you want to change the variables for all charts of the story based on the specific data source, choose Edit Prompts in the right-hand corner.

If you want to change the variables only for a specific chart, you can also choose Set Chart Variable beside a specific chart.

- 2. Choose the relevant input parameter.
- 3. On the Set Variables for <Technical Name of Input Parameters> dialog box, you can delete the predefined member and enter a value of your choice using the value help.
- 4. When you have made all necessary changes to the values of the variables, choose Set.


For some charts, the predefined Standard view filters the values in such a way that, for example, only the Top 5 or Bottom 5 values of a specific measure are shown. In the chart action menu, you can change these settings to suit your needs:

You can remove the filter.

You can change the mode from Top to Bottom or the other way round.

You can change the number of values displayed.

The app is delivered with a default Standard view. You can save all your settings for the app by calling the Select View function and saving your own view.

The following CDS query views are used as data sources:

Package: Treasury Management for SAP S/4HANA 2022 and Cloud

Financial Status 2 (C_FINANCIALSTATUSQUERY_2)

Financial Status History 2 (C_HISTFINANCIALSTATUSQRY_2)

Cash Position and Liquidity Forecast Query (C_LiquidityPositionQuery)

Bank Group Query (C_BankProfileQuery)

Bank Group Profile Query (C_BankGroupProfileQuery)

Bank Payments Query (C_PaymentByBankQuery)

Total and Average Bank Payments Query (C_PaymentByBankKPI)

Query View for Maturity Profile (C_MaturityProfileQuery)

Query for Credit Line Utilization (C_CreditLineUtilQry)

Treasury Counterparty Limit Overview Query (C_TrsyCtptyLimitOverviewQ )

Treasury Counterparty Limit Business Partner Rating Query (C_TrsyCtptyLmtBPRatingQry)

Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry)

Treasury Value at Risk Query (C_TrsyValueAtRiskQuery)

Query for Bank Guarantee Overview (C_BankGuaranteeOverviewQry)

Market Data Query for Basis Spread (C_MktDataBasisSpreadQry)

Market Data Query for Credit Spread (C_MktDataCreditSpreadQry)

Market Data Query for Implied Volatility (C_MktDataImpVolatilityQry)

Market Data Query for FX Rate (C_MktDataFXRateQuery)

Market Data Query for Ref. Interest Rate (C_MktDataRefIntrstRateQry)

Market Data Query for Security Price (C_SecurityPriceQuery)

Fin. Trans. Amt on Single Date - Query (C_FinTransSingleDayAmtQry)

Financial Transaction Amount - Query (C_FinTransAmtQry)

Fin. Trans.: Histl/Fcstd Fee Amt - Query (C_FinTransFcstHistlFeeQry)

Package: Treasury Management for SAP S/4HANA 2020

Financial Status Query (C_FinancialStatusQuery)

Cash Position and Liquidity Forecast Query (C_LiquidityPositionQuery)

Bank Group Query (C_BankProfileQuery)

Bank Group Profile Query (C_BankGroupProfileQuery)

Bank Payments Query (C_PaymentByBankQuery)

Total and Average Bank Payments Query (C_PaymentByBankKPI)

Query View for Maturity Profile (C_MaturityProfileQuery)

Query for Credit Line Utilization (C_CreditLineUtilQry)

Treasury Counterparty Limit Overview Query (C_TrsyCtptyLimitOverviewQ )

Treasury Counterparty Limit Business Partner Rating Query (C_TrsyCtptyLmtBPRatingQry)

Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry)

Treasury Value at Risk Query (C_TrsyValueAtRiskQuery)

Query for Bank Guarantee Overview (C_BankGuaranteeOverviewQry)

Market Data Query for Basis Spread (C_MktDataBasisSpreadQry)

Market Data Query for Credit Spread (C_MktDataCreditSpreadQry)

Market Data Query for Implied Volatility (C_MktDataImpVolatilityQry)

Market Data Query for FX Rate (C_MktDataFXRateQuery)

Market Data Query for Ref. Interest Rate (C_MktDataRefIntrstRateQry)

Market Data Query for Security Price (C_SecurityPriceQuery)

Fin. Trans. Amt on Single Date - Query (C_FinTransSingleDayAmtQry)

Financial Transaction Amount - Query (C_FinTransAmtQry)

Fin. Trans.: Histl/Fcstd Fee Amt - Query (C_FinTransFcstHistlFeeQry)

Financial Status History - Query (C_HistFinancialStatusQuery)

##### Configuration and Master Data for the Treasury Executive Dashboard

> **Path:** Treasury and Risk Management > Treasury Analytics > Treasury Executive Dashboard Available in SAP Analytics Cloud > Configuration and Master Data for the Treasury Executive Dashboard | L4 | trm01 p.215 | loio `e5d049eb094c4150bdeed23ad4ab4fd6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e5d049eb094c4150bdeed23ad4ab4fd6.html?locale=en-US)

The following configuration settings and master data are mandatory in the back-end system to run the Treasury Executive Dashboard in SAP Analytics Cloud.

**Configuration**

Indicate the relevant company codes as treasury centers in the Customizing activity Define Company Code Additional Data.

This setting is relevant for the chart Liquidity by Treasury Center on the Liquidity tab.

In the Customizing activity Set Rating Procedures and Ratings, you can create rating procedures and assign ratings to them.

You can rate business partners by different means, such as their credit standing and payment history, or according to other criteria. Ratings can be performed according to your own rules, as well as through specialist service providers, such as Standard & PoorsorSchufa. Several rating procedures have already been delivered. You can define others according to

your requirements. You can also set one of the rating procedures as the standard rating procedure and flag this rating procedure as internal.

Customizing for the Cash Management tab:

The data from the Cash Management tab comes from the One Exposure from Operations hub. To view these figures, define the following configuration actvities in your configuration environment:

Edit Liquidity Items

Liquidity items represent the source and use of cash. This setting is required if you want to view cash and liquidity statuses by liquidity item.

Define Planning Levels

A planning level reflects a typical financial transaction, for example, posting to a bank account, posting to a clearing account, and confirmed or unconfirmed payment notes. It explains the origin of the data and thus enables you to better estimate its reliability and decide which financial transaction needs to be included in your cash position and liquidity forecast KPIs.

Assign Planning Levels to Profiles:

A balance profile defines a set of planning levels that reflect the original financial transactions. You can use balance profiles to filter the data sources that you want to display in the groups Cash Position Forecast and Liquidity Forecast.

To identify the relevant fee flows of your financial transactions reported in the Fee of Financial Transactions group on the Bank Relationship tab, you must set the Fee indicator for the relevant fee flows in the following Customizing activities:

Define Flow Types - MM Transactions

Define Flow Types - FX Transactions

Define Flow Types - OTC Derivatives

Define Flow Types - Trade Finance Transactions

Define Flow Types - Securities

If you want to use the market risk key figure sets relevant for the Market Risk tab, you must have chosen to use the static analysis structure. For more information, see also Analysis Structure.

Additional prerequisites for using the market risk key figure sets:

You must define your evaluation types in Customizing under Treasury and Risk Management Valuation Define and Set Up Evaluation Types .

You must define your value-at-risk types in Customizing under Treasury and Risk Management Market Risk Analyzer Value at Risk Define Value-at-Risk Type .

A value-at-risk type with VaR category Simulation must have the VaR method 1 VaR Determination Based on Profit and Loss.

A value-at-risk type with VaR category Variance/Covariance must have the item calculation 1 Delta Positions.

If you want to calculate market risk key figures based on a specific scenario and/or based on a market data shift, you must first define the scenarios and market data shifts.

For more information, see also

