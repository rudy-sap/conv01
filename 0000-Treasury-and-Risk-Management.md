# Treasury and Risk Management - SAP TRM Knowledge Base (branch split)

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

## Treasury and Risk Management

> **Path:** Treasury and Risk Management | L1 | trm01 p.1 | loio `3b3e7e53c4d1cc26e10000000a4450e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3b3e7e53c4d1cc26e10000000a4450e5.html?locale=en-US)

**Treasury and Risk Management**

Provides comprehensive features and functions to secure against financial risks (liquidity risks, FX risks, counterparty risks, and further market risks). Accurate registration and a comprehensive view of all business activities aligned with (inter)national accounting principles such as IFRS and US GAAP is included.

**Use**

The Treasury and Risk Management component is a subarea of the Treasury Management solution area. It provides the solution capabilities Debt and Investment Management and Financial Risk Management, being based on a series of solutions that are geared towards analyzing and optimizing business processes in the finance area of a company. The different components of Treasury and Risk Management provide the functions for both of these solution capabilities.

Whereas, on the one hand, you can use the functions for Treasury and Risk Management in the back-end system, the offering is complemented, on the other hand, by apps that are available on the SAP Fiori launchpad. In this way, you can choose from a broad range of functions both in the back end as well as on the SAP Fiori launchpad.

**Note:**

Business Partners in Treasury and Risk Management:

Treasury and Risk Management is intended for mapping B2B transactions between your enterprise and banks, financial institutions, brokers, and other enterprises. The financial transactions mapped in the Transaction Manager are B2B transactions between your enterprise and banks, financial institutions, brokers, and similar enterprises. The master data required for the Transaction Manager processes also relates to enterprises and financial institutions. In the Transaction Manager, checks are run to ensure that you do not use natural persons as business partners. If you use a business partner that is a natural person, the following error message is issued: You cannot assign bus. partner &1 because the partner is a natural

person (message class TI, message number 031). This means that the simplified blocking and deletion of personal data in the Transaction Manager through SAP Information Lifecycle Management (SAP ILM) is not necessary. Nevertheless, an end-ofpurpose check (function module TRTM_BUPA_EOP_CHECK) is available for this purpose.

If, for example, you use the Transaction Manager to map financial transactions with natural persons or your use of the Transaction Manager otherwise involves natural persons, you must ensure you adhere to the retention period for personal data and its subsequent deletion by taking appropriate technical and administrative measures of your own. When these preconditions are fulfilled, you can manage the error message for checking the use of natural persons. You do this in Customizing under Treasury and Risk Management Transaction Manager General Settings Tools Configurable Messages Change Message Control .

If you use Risk Management to analyze Transaction Manager data only, it also applies that the simplified blocking and deletion of personal data in the Transaction Manager through SAP Information Lifecycle Management (SAP ILM) is not necessary. Nevertheless, a where-used check (function module RM_BUPA_WUC_CHECK) is also available for this purpose.

If you use Risk Management to analyze data that also contains data on natural persons or your use of Risk Management otherwise involves natural persons, you must ensure you adhere to the retention period for personal data and its subsequent deletion by taking appropriate technical and administrative measures of your own.

Treasury and Risk Management offers you archiving functions.

**Note:**

Data Controller Assignment to Business Partners:

Since the business partners in Treasury and Risk Management are organizations, it is not necessary to assign a data controller to them. Therefore, if you are using Treasury and Risk Management, you must not activate the data controller functions in the business partner in the Customizing activity Activate Business Partner Data Controller.

**Integration**

Treasury and Risk Management: Integration Scenarios

The Treasury and Risk Management is integrated with components of SAP S/4HANA such as Financial Accounting, Cash and Liquidity Management, In-House Cash, and Public Sector Management. Additionally, it offers integration scenarios with other SAP solutions, such as SAP Trading Platform Integration, SAP Market Rates Management, SAP Multi-Bank Connectivity, and SAP Trade Repository Reporting by Virtusa.

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM01-F001]

Please note that image maps are not interactive in PDF outputs.

**Treasury and Risk Management: Components and Business Processes**

The SAP Treasury and Risk Management consists of various functionally structured components that provide all functions for the various SAP Treasury and Risk Management processes. This connection is illustrated in the following graphic. The figure shows only the most important functional areas and main processes.

This image is interactive. Hover over each area for a description. Click highlighted areas for more information.

[figure TRM01-F002]

Please note that image maps are not interactive in PDF outputs.

**Market Data Management**

The treasury and risk management process requires current and historical market data, such as the values of exchange rates, interest rates, credit spreads, volatilities, and so on.

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

**Transaction Manager**

The core task in many finance departments is concluding financial transactions. Depending on the company policy, the emphasis can be on either providing an internal service for the affiliated group companies or participating actively in the financial markets in order to invest liquid assets, finance planned investment, or hedge existing risks.

Transaction Manager component provides the instruments for processing the related financial transactions, from deal capture through to transferring the relevant data to Financial Accounting. The system supports both traditional treasury departments that focus on trading as well as asset management departments. This enables you to use the same platform for various types of transactions - from short-term financing to longer-term strategic investments.

Transaction Manager also provides functions for managing and valuing financial operations throughout their lifecycle. Using the valuation areas, you can map parallel accounting according to different accounting rules. You post the valuation results separately for each depreciation area. For parallel accounting, treasury positions are required. Each treasury position represents a financial transaction or securities position in a specific valuation area. The treasury position is the most detailed level to which you can break down the balance sheet accounts of the treasury subledger.

**Risk Management**

Besides traditional finance management tasks, such as cash management and liquidity assurance, effective market risk management is a decisive factor in securing your company’s competitive position. In this field, Treasury and Risk Management offers extensive position evaluations, such as mark-to-market valuations of financial transactions. It also includes tools for calculating risk and return figures, including exposure, future values, and sensitivities. The valuations can be based on both real and market data scenarios. Treasury and Risk Management provides a reliable evaluation basis for market risk controlling.

Market Risk Analyzer

Besides traditional finance management tasks such as cash management and liquidity assurance, effective market risk management is a decisive factor in securing your company’s competitive position. In this field, the Market Risk Analyzer offers extensive position evaluations, such as mark-to-market valuations of financial transactions. It also includes tools for calculating risk and return figures, including exposures, future values, sensitivities, and value at risk. When you run these reports, you can incorporate both contracted positions and fictitious financial transactions into the calculations. The valuations can be based on both real and simulated market prices. Together with a high degree of flexibility for creating reports, the Market Risk Analyzer provides a reliable evaluation basis for market risk controlling.

Credit Risk Analyzer

The Credit Risk Analyzer focuses on measuring, analyzing, and controlling counterparty default risk. The first phase aims to cover the specific risks associated with financial transactions in a company. The Credit Risk Analyzer enables you to control risks actively by setting limits. This is supported by flexible limit management functions with online monitoring as well as by extensive reporting options. As a result, managers are in a position to identify credit risks as they occur and take evasive action.

Portfolio Analyzer

Given that the funds available for investment are usually limited, and that there are numerous investment options to choose from, the crucial question for investment policy decisions is how well the investments have actually performed. The economic success of an investment is therefore a critical factor when it comes to making investment policy decisions. The Portfolio Analyzer is designed to provide the answers regarding the economic success of investments. The focus lies on

analyzing performance, that is, in precisely measuring the success of investments as well as comparing the success against the targets set. Furthermore, it is now possible to view the details of performance achieved according to their cause, that is, the contribution of each portfolio element to overall performance. The basis for these evaluations is the portfolio structure, which lets you group investments into different categories. You can run evaluations for portfolios at different levels in the portfolio hierarchy, or for an asset category across several portfolios.

Accounting Analyzer

The Accounting Analyzer enables you to evaluate positions and subpositions in the Transaction Manager with regard to their position component values.

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

**Implementation Considerations**

In the area of SAP Treasury and Risk Management, there are some enterprise business functions that you can use only after you have activated the relevant enterprise business function in the Customizing activity Activate Business Functions (transaction SFW5).

See also: SAP Help Portal http://help.sap.com/s4hana under Product Assistance [choose language] CrossComponents Business Functions Enterprise Business Functions Accounting Financial Supply Chain Management SAP Treasury and Risk Management (SAP Treasury and Risk Management)

To be able to use the functions of the individual components of SAP Treasury and Risk Management, you need to make the required settings in Customizing for Treasury and Risk Management.

You make the settings for the SAP Business Partner function in Customizing under Treasury and Risk Management Basic Functions SAP Business Partner for Financial Services .

To make the settings for market data, go to Customizing and choose Treasury and Risk Management Basic Functions Market Data Management .


**Related Information**

Roles in Treasury and Risk Management Market Data Management Master Data Foreign Exchange Risk Management Market Risk Analyzer Credit Risk Analyzer Portfolio Analyzer

Accounting Analyzer Transaction Manager Apps for Treasury and Risk Management Archiving Data in Treasury and Risk Management

