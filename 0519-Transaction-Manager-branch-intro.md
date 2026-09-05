# Transaction Manager > (branch intro) - SAP TRM Knowledge Base (branch split)

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

### Transaction Manager

> **Path:** Treasury and Risk Management > Transaction Manager | L2 | trm04 p.164 | loio `f827c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f827c753b1081d4be10000000a174cb4.html?locale=en-US)

**Use**

The core task in many finance departments is concluding financial transactions. Depending on the company policy, the emphasis can be on either providing an internal service for the affiliated group companies or participating actively in the financial markets in order to invest liquid assets, finance planned investment, or hedge existing risks.

Transaction Manager component provides the instruments for processing the related financial transactions, from deal capture through to transferring the relevant data to Financial Accounting. The system supports both traditional treasury departments that focus on trading as well as asset management departments. This enables you to use the same platform for various types of transactions - from short-term financing to longer-term strategic investments.

Transaction Manager also provides functions for managing and valuing financial operations throughout their lifecycle. Using the valuation areas, you can map parallel accounting according to different accounting rules. You post the valuation results separately for each depreciation area. For parallel accounting, treasury positions are required. Each treasury position represents a financial transaction or securities position in a specific valuation area. The treasury position is the most detailed level to which you can break down the balance sheet accounts of the treasury subledger.

The Transaction Manager helps you in the following ways:

It helps you manage your financial transactions and positions. This covers not only trading and processing of financial transactions, but also payment and posting in Financial Accounting.

It helps you utilize existing potential for rationalization and enables you to automate typical processes.

It provides flexible reporting and evaluation structures for analyzing your financial transactions, positions, and portfolios.

The integration with Treasury and Risk Management enables you to measure directly the effects of financial transactions on liquidity or interest rate risks.

The Transaction Manager can be used in companies and asset management areas as well as in traditional Treasury departments.

**Note:**

Business-to-Business (B2B)

The financial transactions portrayed in the Transaction Manager are B2B transactions between your company and banks, financial institutions, brokers, or similar institutions. Likewise, the master data required for the processes in the Transaction Manager relate to companies and financial institutions. In the Transaction Manager, checks are implemented that do not allow the use of business partners who are natural persons. If you use business partners who are natural persons in the Transaction Manager, you will get the following error message: You cannot assign bus. partner &1 because the partner is a natural person (message class TI, message number 031). Consequently, the simplified blocking and deletion of personal data in Transaction Manager using SAP Information Lifecycle Management (SAP ILM) is not needed in the Transaction Manager, but this is also supported with an end-of-purpose check (function module TRTM_BUPA_EOP_CHECK).

If you use the Transaction Manager to portray financial transactions with natural persons or your usage of the Transaction Manager involves natural persons in other ways, you need to deploy separate supplementary technical and organizational measures to ensure that you respect the deadlines governing the storage and deletion of personal data. If these prerequisites are fulfilled, you can suppress the error message issued during these checks for natural persons by deactivating the configurable message 031 of application area TI in the Customizing activity Change Message Control under Treasury and Risk Management Transaction Manager General Settings Tools Configurable Messages .

The Transaction Manager does, of course, offer archiving functions.

**Implementation Considerations**

You make the settings for the SAP Business Partner in Customizing for Treasury and Risk Management under Basic Functions SAP Business Partner for Financial Services .

You make the settings for market data management in Customizing for Treasury and Risk Management under Basic Functions Market Data Management .

To use the Transaction Manager functions, make the required settings in Customizing for Treasury and Risk Management under Transaction Manager.

If you upgrade from Release Enterprise 1.10 or lower, you need to migrate your dataset due to a change in data model. You can perform the upgrade using transaction TPM_MIGRATION. See the documentation for the transaction, SAP Note 706952 .

There are a number of functions that allow you to transfer your legacy data from feeder systems.

See also:Legacy Data Transfer

**Integration**

The Transaction Manager is a component of Treasury and Risk Management.

For more information, see also Treasury and Risk Management (TRM).

**Features**

Straight-Through Processing

The Transaction Manager deploys the straight-through processing (STP) principle from the entry of the different transaction types through to their transfer to Accounting. For this purpose, the front-end area has been continuously enhanced, while

functions and basic structures have been standardized for financial transactions (Money Market, Foreign Exchange, Derivatives, Securities, Debt Management, Trade Finance) in the areas of correspondence, payment processing, accounting, and valuation procedures.

Transaction and Position Management Process

[figure TRM04-F033 - Overview]

Overview

You can configure the transaction and position management processes flexibly for each product type. You do this using rationalization. At the same time, you can increase process security by implementing organizational requirements. The dual control principle, for example, is used as an important security measure for controlling releases.

You can use different criteria to split and manage positions that you have in parallel valuation areas as well as valuate them using different accounting principles. Furthermore, positions form the basis for performance and benchmark analyses in the Portfolio Analyzer. The Accounting Analyzer offers you the following option:

Front Office

You can map financial transactions and exercise rights in the Trading area. The following functions are available:

Entering and evaluating offers (competitive bids)

Fast entry for the most common transactions

Order limit checks

Date checks

Expiration and barrier checks for options

Price calculators (for example, cross-rate, option price, and NPV calculators)

Back Office

You have the following options in the Back Office area:

Managing account assignment information

Creating payment details

Correspondence functions (for example, automatic confirmations and counterconfirmations)

See also: Treasury Correspondence

Securities account transfers and processing corporate actions for your positions

If you have financial transactions that are relevant for clearing, you can use the functions for the Central Clearing Monitor.

Accounting

You can use the following functions in Accounting:

Managing your positions in parallel (for example, according to the German Commercial Code and US GAAP)

Automatic posting functions for transferring data to Financial Accounting

Updating the general ledger in real time

Flexible functions for processing payment transactions

Valuation procedures and accrual/deferral procedures

Complete documentation of business transactions

Authorization Concept and Release

You can use the authorization concept to separate your trading, back office, and accounting tasks. You assign user authorizations to the individual activities in the transaction and position management process and assign authorization profiles to each employee according to his or her organizational area. You use the authorization concept to define releases. The financial transaction can be checked, for example, by one or more employees before being transferred to Accounting.

See also:Release Workflows in Treasury and Risk Management

Roles

The roles represent the different functions and positions of your employees according to the specific organizational structure of your company. The system provides roles with which you can define user menus for employees. You can base your role definition and menu structure on the standard roles that are provided in the Transaction Manager.

For more information, see Roles in Treasury and Risk Management.

**Master Data**

Securities Account

Futures Account

External Account

Manage Securities Classes

Position Indicator

Central Functions

The following central functions and tools are important in the Transaction Manager:

Status-controlled transaction processing

Real-time reporting

Cross-application functions of the Information System provide you with a comprehensive overview of your business relationships. The use of standard organizational elements and their integration with the Transaction Manager allow you to portray them in other SAP applications.

Market Data Entry

The SAP real-time datafeed is a universal, open interface that can be used to import data from any information provider or datafeed platform.

You can also import current and historical market data later using a file interface. In addition, you can transfer the market data from a spreadsheet or enter it manually.

The Market Data Management functions are available across Treasury and Risk Managements. You can find functions for Market Data Management on the SAP Easy Access screen by choosing Treasury and Risk Management Basic Functions .

See also:Market Data Management

The "Open System"

Standardized interfaces (Business Application Programming Interfaces (BAPIs)) turn SAP applications into open systems. These interfaces allow the consistent exchange of data across system boundaries. The Transaction Manager provides you with BAPIs for creating, changing, displaying, reversing, and counterconfirming financial transactions.

See also:BAPIs for the Transaction Manager

Information System

The efficient information and reporting system within the Transaction Manager provides you with the following functions:

Central access to information

Direct and restricted data selection

Various evaluation options

Linking reports

Structuring and defining the data hierarchy

Hierarchical arrangement of the report structure

Clear presentation of information

Evaluation and presentation of results in graphical form

Drilldown navigation for viewing detailed information

Aggregated view of the total commitment of a business partner

Reproduction of the history of financial transactions, payment flows, and activities in Financial Accounting

Deadline monitoring of financial transactions

Transfer of results to PC applications

Support in fulfilling legal reporting requirements:

