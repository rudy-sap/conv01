# Transaction Manager > Terms in Financial Transaction Management - SAP TRM Knowledge Base (branch split)

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

#### Terms in Financial Transaction Management

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management | L3 | trm04 p.169 | loio `e806da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e806da531198434de10000000a174cb4.html?locale=en-US)

Here you get more details about terms used in financial transaction management..

|Term|Definition|
|---|---|
|Contract Type|The contract type is an internal key used for the different application areas in Treasury. Available contract types for Treasury and Risk Management: 2 = Securities 4 = Foreign Exchange 5 = Money Market 6 = Derivatives E = Exposure Positions T = Trade Finance X = External Accounts|
|Product Category|The product category is a predetermined classification of the financial products in the transaction management. Examples: FX transaction, interest rate instrument, stock, bond, OTC option, letter of credit For more information, see also Product Categories. |
|Product Type|You define product types in Customizing. Each product type is assigned to exactly one product category. Product types are used to further segment financial products assigned to a product category according to company-specific requirements.  Domestic stock, foreign stock|
|Transaction Category|The financial transaction category controls the transaction type. In the system is predefined which transaction categories are available for a certain product category.  Fixed-term deposit investment, fixed-term deposit borrowing|
|Transaction Type|The transaction type determines how a financial transaction is processed. The transaction types can group transaction categories according to company-specific requirements.  Investing or borrowing fixed-term deposits or deposits at notice or purchasing and selling bonds.|
|Transaction Activity|Key which uniquely identifies the activity of a financial transaction. The procesing category assigned in the transaction type definition decides on the activity chain of a financial transaction.|
|Condition|A condition is a contractually agreed element of a financial instrument. It describes the structure of the transaction in terms of the period and amount (interest, repayment, and so on).|


|Term|Definition|
|---|---|
|Flow|Flows are assigned to the transactions and positions in the Transaction Manager. These flows document changes to the transactions. Flows contain attributes for date, amount and calculation information among other things.  Repayment flow, purchase flow, valuation flow|
|Flow Type|Each flow has exactly one flow type which classifies the flow. You define these flow types in Customizing. Besides the key and a text, other flow type characteristics are also defined, for example, whether or not the flow type is relevant for posting or whether flows with this flow type should be included in cash management and forecast. A flow type is only unique per contract type (contract type 2: securities, contract type 4: foreign exchange, contract type 5: money market trading, contract type 6: derivatives). This means that flow type 1000 for contract type 2 is different from flow type 1000 for contract type 4.  Contract type 5, flow type 1100 (money market: fixed asset/increase)|
|Update Type|There are also flows for updating positions and transactions in parallel position management. These flows have an update type instead of a flow type. The main difference between flow types and update types is that the definition of update types is not limited to the contract type.  Example: Update type V152 (one-step rate/price valuation: write-up foreign exchange)|
|Cash Flow|A cash flow contains flows (planned and actual records) that are generated from the conditions of a class, a financial transaction, or by functions such as accrual/deferral or key date valuation, as well as flows that are entered manually. They all appear in chronological order. For more information, see also Cash Flows. |

##### Product Categories

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Product Categories | L4 | trm04 p.170 | loio `11521471717f48b7898fb618f90fd31c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/11521471717f48b7898fb618f90fd31c.html?locale=en-US)

The product category is a predetermined classification of the financial products in the transaction management.

In the Customizing you define your product types based on the available porduct categories.

The following product categories are avilable in SAP S/4HANA:

FX

600 FX Transactions

760 OTC Options

**Money Market**

530 Commercial Papers

540 Cash Flow Transactions

550 Interest Rate Instruments

560 Facilities

580 Current Acct-Style Instruments

Securities

010 Stock

020 Fund

030 Subscription Right

040 Bond

042 Installment Bond

060 Bond with Warrant

070 Convertible Bond

- 111 Index Warrant

- 112 Equity Warrant

- 113 Currency Warrant

- 114 Bond Warrant


160 Shareholding

Derivatives

610 Cap and Floor

620 Swap

630 Forward Rate Agreement

640 Total Return Swap

740 Forward Securities Transaction

760 OTC Option

770 Securities Lending

780 Forward

790 Forward Loan

690 External Account

Listed Derivatives

700 Future

750 Listed Options

Trade Finance

850 Letter of Credit

860 Bank Guarantee

- 990 Exposure

relevant for Exposure Management 2.0

- 991 Exposure Item


relevant for Hedge Accounting for Exposure Items process

##### Securities Account

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Securities Account | L4 | trm04 p.172 | loio `1f1ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1f1ada531198434de10000000a174cb4.html?locale=en-US)

**Definition**

You use securities accounts to manage and value your positions. You need securities accounts for all transactions which require position management. The securities accounts created in the system usually correspond to actual securities accounts at a bank.

**Integration**

You must have a securities account if you want to purchase or sell a security.

You have to define securities account types based on the default securities account categories provided in the system. In Customizing for Transaction Manager, choose Securities Position Management Securities Account Management Define Securities Account Categories.

The following securities account categories are available:

Asset Securities Account

Liability Securities Account

Lending Securities Account

For more information, see the Implementation Guide (IMG) of Transaction Manager. Choose Securities Position Management Securities Account Management Define Securities Account Categories.


In the securities area, the security account also acts as a means of differentiating subledger positions.

**Use**

You can choose from the following functions:

Editing a Securities Account

Securities Account List

Securities Account Transfer

To transfer (all or part of) a position from one securities account to another.

Cash Flow for a Class in a Securities Account

You can call up the securities account cash flow in the trading and back office areas to display the planned or executed flows for a particular security in a securities account.

##### Cash Flows (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Cash Flows | L4 | trm04 p.173 | loio `2d18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2d18da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

A cash flow contains flows (planned and actual records) that are generated from the conditions of a class, a financial transaction, or by functions such as accrual/deferral or key date valuation, as well as flows that are entered manually. They all appear in chronological order.

We distinguish between the following types of cash flow:

Cash flow in the class data

In master data maintenance for the classes, you can display a fictitious cash flow showing all the flows that would be generated for a fictitious purchase either with a nominal value of 100,000 or consisting of 100,000 units, depending on the conditions entered.

Cash flow for the transaction

This cash flow shows you all the flows that were generated for a particular financial transaction.

Position cash flows

Cash Flow for a Class in a Securities Account

This cash flow displays all the planned or executed flows for a class in a securities account, in chronological order. These flow records can be generated in various ways:

Flows entered manually (investment amounts, charges, unscheduled repayments)

Flow records (usually generated from the conditions)

Accrual/deferral flows that result from the periodic assignment of outgoing and incoming payments

Valuation flows (for example, price gains and losses)

Cash flow of a parallel valuation area (Subledger Cash Flow)

For more information, see Treasury Position Flows - Classic.

**Use**

The cash flow documents all the flows for a financial transaction, in a securities account, or for a position.

From the cash flow, you can access all the details relating to these flows (even the order data for a purchase flow).

You can use the cash flow to check whether the data that you have entered is correct.

###### Cash Flow for the Class

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Cash Flows > Cash Flow for the Class | L5 | trm04 p.173 | loio `22fdc753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/22fdc753b1081d4be10000000a174cb4.html?locale=en-US)

Use

In master data maintenance for the classes, you can display a fictitious cash flow showing all the flows that would be generated for a fictitious purchase with a nominal value of 100,000 or 100,000 units, based on the conditions entered.

You can use this cash flow to check if the conditions you have entered are correct.

By choosing Goto Effective Interest Rate , you can view the interest scale for the effective interest calculation.

The cash flow is displayed using the SAP List Viewer. The features offered by the SAP List Viewer are described in the documentation SAP List Viewer (ALV): Classic .

See also:

Cash Flow

###### Cash Flow for a Class in a Securities Account (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Cash Flows > Cash Flow for a Class in a Securities Account | L5 | trm04 p.174 | loio `1b19c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1b19c55368511d4be10000000a174cb4.html?locale=en-US)

Use

The Cash Flow for a Class in a Securities Account (TPM40) report provides a chronological quantity view of the positions. It shows incoming payment flows and any tax flows that may have to be generated. The cash flow for a class in a securities account is based on update types.

**Note:**

The report does not show any price gains or losses.

Future cah flows are displayed for the number of years defined in Customizing under Treasury and Risk Management

Transaction Manager Securities Master Data Product Types Define Company Code-Dependent Settings for the Product Type in the CM period field for the product type.


See also:

Cash Flows

##### Manage Securities Classes

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes | L4 | trm04 p.174 | loio `4daed06542326636e10000000a42189b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4daed06542326636e10000000a42189b.html?locale=en-US)

App ID: FWZZ

With this app, you can create, change, display, and delete security class master data. A security class is a security. The security class data includes all the structure characteristics of a security.

**Example:**

You can portray stocks (product category 010 Stocks). Also the product category 030 Subscription Rights can be used so you can portray a capital increase. For more information, see also Execute Capital Increase.

You can portray money market funds using the product category 020 Investment Fund.

You use the product category 040 Bond for bonds you want to invest in as well as for a bond you want to issue.

**Prerequisites**

Issuer. To enter new class data, you first have to create the issuer of the security as the SAP business partner in the role of an

In Customizing for securities, you need to have defined the number range intervals as external number ranges. To do this, choose Define Number Ranges for Product Types in Customizing.

For more information, see Customizing for Securities.

**Procedure**

- 1. Choose Transaction Manager Securities Master Data Class (transaction FWZZ) or Transaction Manager Derivatives Master Data Listed Derivatives Class . Alternatively, call the Manage Securities Classes app on the SAP

Fiori launchpad.

- 2. Enter the ID number of the security class.

This number uniquely identifies the security.

You can use input help to search for classes that have already been created in the system. You can search according to the following criteria:

- 3. If you want to have all classes displayed that have a specific secondary index as well as an ID number, enter the secondary index number and enter an asterisk (*) in the Index Class field. A list appears containing all classes for which this secondary index has been maintained.
- 4. Now choose one of the following functions:


|Classification:|Status|Search Terms:|ID Number|
|---|---|---|---|
| |Product Type| |Short Name|
| |Product Category| |Long Text|
| |Issuer| |Secondary Index Number|
| |Issue Currency| |Index Class|
| |Security Classification| | |
| |Quotation| | |
| | | | |
|Search Using Rating|ID Number|Search Using Commodity|ID Number|
| |Rating| |Commodity ID|
| | | |Product Type|


**Example:**

If you want to search for a specific class using the secondary index, enter the secondary index number and enter the number you are looking for in the Index Class field.

|Function|Input|Comments|
|---|---|---|
|Create Create without reference|Product type Short name Long text Choose Create.|After you have chosen Create, the system prepares the relevant tabs for the product type.|
|Create|Product type|After you choose Copy, the class is created according to the reference you|


|Function|Input|Comments|
|---|---|---|
|Create with reference|Short name Long text In the area headed Create, choose the setting With Template. Enter the ID number of the copy reference You can decide whether you also want to copy the following: Basic Data Conditions Exchanges Choose Copy.|are copying. You can now add any missing data and/or change the data from the copy reference.|
|Change|Make the changes required. Save your entries.|Some changes are not permitted. Examples: Changing the issue currency Changing the conditions that have already generated flows The system informs you when this occurs.|
|Display| | |
|Print|Choose Class Data Print . A list of the class data is printed.| |
|Delete| |The system deletes the class, unless the following applies: Position indicators exist Flows (either plan records or actual records) exist or have existed References exist Transactions for this class exist or have existed|


More Functions

Switching between security classes

You can switch between classes by entering a new security ID number in the selection field and choosing a processing function (display, change, and so on). By choosing Enter, after entering a new security ID number, you can switch to the new class and remain in the same processing mode (for example, Change Change ).

Check

This function checks the class for consistency. Any errors that occur here are displayed in a dialog box. The same checks are performed when you save the class.

Reset

You can use this function when you are in the change mode. It resets the class data to the status it had just after it was last saved.

Cash Flow

For stocks and bonds, the system displays a simulated cash flow based on a purchase with a nominal value of 100,000.

References

Here, the system displays a list of the class data that uses the current security ID number as the underlying. For more information, see Class: Reference.

**Structure**

Class data is entered on different tabs. The product categories dictate which tabs are used.

Search Terms

Short and Long Description, Secondary Indexes, Rating, Classification

Basic Data (available for all product categories but specific to certain categories)

Basic Data: Stocks/Shareholdings/Investments

Basic Data: Subscription Rights

Basic Data: Bonds

Basic Data: ABS/MBS

For more information, see also:

Warrants

Futures

Listed Options

Asset Pool Data (only for ABS/MBS)

Conditions

Conditions for Bonds

Conditions for Stock/Shareholding

Conditions for Investment Certificates

Conditions for ABS/MBS With Parallel Interest Conditions

Conditions for ABS/MBS With Single Interest Conditions

Exchanges

Stock Swap (only for stocks)

Notice (only for bonds)

Regulatory Reporting (Germany Only)

Custody Type, Securities Account Statistics, Tax Treatment, and so on

User Data

You can branch from the class data to the Issuer data of each business partner: Choose Environment Display Issuer .

A class can have the status Active, Inactive, or Obsolete. When you first enter the master data for a class, you can choose only the status Inactive until you have finished entering all the data. Note: Inactive classes cannot be purchased. You select the Obsolete status for classes that are no longer used and that are not to be selected for evaluation reports.

The status of a class is displayed at the top right-hand side of the basic data screen. There you can also change the status. Alternatively, choose Edit Change Status . A class can have the status Obsolete, Inactive, or Active.

In the class data, you can display the cash flow for a class produced from the conditions entered for a fictitious purchase of 100,000 nominal value or 100,000 pieces.

**Integration**

Before you can process a securities financial transaction in transaction management, you must first enter the following master data:

Business partner data (issuer, counterparty)

Class data

Securities account data / futures account data

Position indicator

When you create an order to buy or sell a security or issue a bond, the system copies the securities class data needed. You add the specific transaction data (such as the amount or price of a stock purchased) to this data.

The system uses the details of the class conditions and specific transaction details (such as the nominal value and price) to calculate the cash flow of the transaction.

You can also use class data for evaluation purposes (for example, when you create lists or when you determine an account assignment reference) automatically.

###### Customizing for Securities

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Customizing for Securities | L5 | trm04 p.178 | loio `40c111aaff294148b3e3c172c7f4b831` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/40c111aaff294148b3e3c172c7f4b831.html?locale=en-US)

Make the following Customizing settings before managing securities in the system.

Product Types

Since you create financial transactions and manage your positions in the Transaction Manager on the basis of product types, you must assign each class to a product type. To create product types and assign the product categories defined by SAP, go to Customizing and choose Financial Supply Chain Management Treasury and Risk Management Securities or Listed Derivatives Transaction Management Product Types Define Product Types . You can define more than one product type for a product category.

The various product types are indicated by specific characteristics. You enter these characteristics and master data on entry screens for specific product types.

**Note:**

In the product type definition of the Securities area, you can choose Parallel Interest Conditions in the Cash Flow Generation field.

This setting enables the usage of extended financial mathematic functions (New FiMa), such as parallel conditions and the assignment of up to 5 calendars for the working day check. This influences how conditions are managed and therefore how cash flow is calculated.

If you make this settings you also get the Condition Details: Interest (New FiMa) screen to enter the interest conditions, this includes additional interest calculation types, such as Exponential Interest Calculation with Factors, Compound Interest Calculation, and Average Compound Interest Calculation. So, you can enter variable interest conditions with risk-free reference rates. For more information, see also Interest Calculation Types. In addition, parallel interest conditions are possible.

In the Customizing activity Define Product Types, you can use the field selection to define for each product type the entry fields that are displayed and which fields appear as optional, required, or display fields.

Under Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities or Listed Derivatives Transaction Management Product Types and under Financial Supply Chain Management

Treasury and Risk Management Transaction Manager Securities or Listed Derivatives Transaction Management Specific Class Data , you make many settings for the securities, such as defining a general security classification,

defining the connection to the classification tool, or creating a secondary index and custody types. For some securities, such as redemption bonds, you can access specific Customizing activities under Settings for Special Types of Securities.

Additional Tab Pages in Class Data

You can also activate additional tabs for the Class function (transaction FWZZ) or the Manage Securities Classes app on your SAP Fiori launchpad.

Predefined Tab Page

The standard delivery already contains the tab and the fields, but you need to configure and activate the tab.

In Customizing under Transaction Manager Securities Master Data Specific Class Data Additional Tab Pages in Class Data Predefined Tab Page , enter the heading, the names of the fields, and - in the case of some of the fields - the values for input help.

Define Heading for Tab Page

Define Names for Currency Attributes (here you find two currency fields)

Define Names for Date Attributes (here you find two date fields and one field for a period)

Define Names for Free Text Attributes (here you find five user-defined text fields)

Define Names and Values for Short Attributes (here you find 10 short attribute fields with input help)

Define Names and Values for Long Attributes (here you find 10 long attribute fields with input help)

Under Transaction Manager Securities Master Data Product Types Define Product Types , you use the function Field Selection (in the Customer Data area) to decide which fields are displayed for each product type.

If you don’t select a field here, the tab for this product type doesn’t appear in the class data.

User-Defined Tab Page

Using the user-defined tab, you can create your own tab in the class data. For this, you use the BAdI: Additional Tab Page in Class Data TPM_SEC_CUST_DATA.

**Related Information**

Product Categories for Securities Manage Securities Classes

###### Product Categories for Securities

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Product Categories for Securities | L5 | trm04 p.180 | loio `cd1ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cd1ada531198434de10000000a174cb4.html?locale=en-US)

The following product categories are delivered for the Securities area:

|Product category|Description|
|---|---|
|010|Stock Fully and partially paid stocks Common stocks and preference stocks|
|020|Investment certificate|
|030|Subscription right|
|040|Bond The following bonds are differentiated according to the interest calculation type: Fixed-interest bonds Variable-rate bonds (floating rate notes) Non-interest bearing bonds The following bonds are differentiated according to the currency: Local currency bonds Foreign currency bonds Dual currency bonds|
|042|Bond with installment repayment The following bonds are differentiated according to the repayment type: Installment bonds Bullet bonds Perpetual bonds|
|060|Warrant bonds|
|070|Convertible bonds|
|111|Index warrants|
|112|Equity warrants|
|113|Currency warrants|
|114|Bond warrants|
|160|Shareholdings|


The following product categories are delivered for listed derivatives:

|Product category|Description|
|---|---|
|700|Futures Securities futures Interest futures Index futures Stock futures|
|750|Listed options Stock options Index options Future options|


**Related Information**

Convertible bonds

Warrant bonds

Warrants

Subscription rights

Futures

Listed options

###### Free Text Search

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Free Text Search | L5 | trm04 p.181 | loio `cc369a51021a9302e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cc369a51021a9302e10000000a44538d.html?locale=en-US)

**Use**

When you enter a text as a search term, the system looks for the term in the short descriptions, the long descriptions, and the names of the issuers of the classes created in the system. For the search, any similar texts are also returned as hits to allow for inverted characters, the use/absence of accents, and so on.

**Integration**

This free text search is integrated with the securities search help in the Transaction Manager and can be used in various functions, such as the following:

Class (transaction FWZZ)

Create Financial Transaction (transaction FTR_CREATE)

**More Information**

Append Search Helps

###### Search Terms

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Search Terms | L5 | trm04 p.182 | loio `9b18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9b18da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

Using this data as the selection criteria for a class, you can search for classes by ID number and evaluate them.

**Structure**

You can use the following search terms:

Name of the class (short and long name)

Secondary indexes

You can enter secondary indexes in addition to the security ID number for a class.

In Customizing, choose Define Secondary Index to define additional secondary indexes (such as EUROCLEAR or ISIN), which you then assign to the individual product types by choosing Define Product Types.

Tax Classification

Indicates different financial instruments based on their taxation.

Product category

Product type

General securities classification

This classification enables you to divide securities into different categories. You define these in Customizing by choosing Define General Classification for Securities.

You can use the field selection function when you choose Define Product Types to determine for each product type whether you want the field to be an optional or required entry, or whether you just want to display or suppress it.

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


In the Customizing activity Make General Settings for Rating available under Treasury and Risk Management

Transaction Manager General Settings Organization Rating/Credit Standing , you decide which rating function you want to use for the rating of financial transactions, security classes, and asset pools in Treasury and Risk Management. You can decide between the following rating functions:

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

###### Basic Data: Stocks/Shareholdings/Investments

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Basic Data: Stocks/Shareholdings/Investments | L5 | trm04 p.183 | loio `8118da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8118da531198434de10000000a174cb4.html?locale=en-US)

Data can be entered in the following fields on the Basic Data tab:

|Issue|Issuer (required entry) Choose Detail to display the business partner data of the issuer, or double-click the Issuer field. Issue currency (required entry) Nominal value and Nominal Value per Trading Unit Issue Start and End of Term Issue Rate|
|---|---|
|Structure|Quotation (required entry) - percentage-quoted or unitquoted Percentage-quoted Unit-quoted Security Type (required entry) You define the selection groups in Customizing under Settings for Special Types of Securities. Stock Type (required entry) Stock Form|
|Shareholding (for shareholding only)|Type The shareholding types you choose from are created in the securities area in Customizing under Define Shareholding Types.|
|Fund (for shareholding only)|Fund Type You define the selection groups you require in Customizing under Settings for Special Types of Securities. Fund Category Fund Volume Issuing Premium in Percent The issuing premium in percent corresponds to the difference between the redemption price and the issuing price; it’s normally 4%.|
|Information|Foreign Investment Law indicator This indicator shows whether the investment fund comes under the Foreign Investment Law. Public Fund indicator This indicator shows what type of capital procurement is used, that is, whether the fund is offered publicly or not. Joint Partner Vote indicator This indicator tells you whether certain transactions require a vote, for example with supervisory bodies.|


Number of issued stocks

Other tabs:

Search Terms

Exchanges

For more information about entering conditions, see Conditions and Stock/Shareholding/Investments: Editing Conditions

Entering Stock Swap Data

Regulatory Reporting

User Data

###### Basic Data: Subscription Rights

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Basic Data: Subscription Rights | L5 | trm04 p.185 | loio `5bf1d6e2f2064155977093833e9069e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5bf1d6e2f2064155977093833e9069e5.html?locale=en-US)

**Prerequisites**

The underlying (= the new stock to be used via the subscription right) for the subscription right must already have been created as a class.

**Context**

Subscription rights grant the stockholder the option of retaining the old share of capital stock when the company performs capital increases (against cash contributions and certain capital increases).

**Procedure**

- 1. Create the subscription right with a product type for product category 030 Subscription Right.
- 2. Enter the basic data for the subscription right:


- a. Enter the Issuer of the subscription right.
- b. Enter the Issue Currency of the subscription right.
- c. Enter the Issue Price.
- d. In the Subscription Periods area, enter the relevant data for each subscription period, such as the ID number of the underlying, subscription ratio (that specifies how many subscription rights are required for how many new stocks), the numerator / denominator = number of subscription rights / number of new stocks, purchase price, currency of purchase price, and the subscription period from and subscription period to. The subscription period from date is the date from which the subscription rights are valid. This means that they can be posted to the securities account and then processed further. You also can enter a name for the subscription period.
- e. On the Exchanges tab, enter the exchanges where the subscription is traded. For more information, see also Exchanges.


**Results**

The subscription right is created as a security class in the system. You post the subscription right into the system via a corporate action. The subscription right also appears in the function Exercise Rights (transaction FWER) under the right category Subscription Rights.

**Related Information**

Subscription Rights Exercise Rights Corporate Action

###### Basic Data: Bonds

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Basic Data: Bonds | L5 | trm04 p.186 | loio `071ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/071ada531198434de10000000a174cb4.html?locale=en-US)

Data can be entered in the following fields on the Basic Data tab:

|Issue|Issuer (required entry) Choose Detail to display the business partner data of the issuer, or double-click the Issuer field. Issue Currency (required entry) Nominal Value and Nominal Value per Trading Unit Start of Term and End of Term for the issue Issue Rate|
|---|---|
|Structure|Quotation (required entries) Percentage-quoted Unit-quoted Security Type You define the selection groups in Customizing under Settings for Special Types of Securities .|
|Drawing (doesn’t apply to convertible bonds)|Drawing indicator Date of the next drawing on principal payments|
|Conversion (for convertible bonds)|ID Number of the reference security Choose Detail to display the class data for the selected reference security, or double-click the ID Number field. Premium (amount and currency): The premium is the amount that must be paid for every conversion over and above the conversion ratio. Conversion Period The period in which a conversion can be made. Conversion Ratio The numerator in the conversion ratio specifies how many units are involved (or which nominal value is involved) in a conversion. The denominator specifies how many new securities in total are issued.|


|Option (for warrant bonds)|Cum or Ex indicator for the bonds Number of warrants for a specified nominal value With the class data for a warrant bond (cum), you also have to specify the ID number of the corresponding classes: EX bond Warrant|
|---|---|


Other tabs

Search Terms

Exchanges

For more information about entering conditions, see Class: Conditions and Bonds: Editing Conditions

Entering Data for Giving Notice

User Data

Regulatory Reporting

###### Basic Data: ABS/MBS

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Basic Data: ABS/MBS | L5 | trm04 p.187 | loio `37a75352284fd030e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/37a75352284fd030e10000000a44538d.html?locale=en-US)

- 1. Choose the relevant Tranche Classification for the ABS/MBS. This setting is relevant for the redemption schedule.
- 2. In the Issue area enter the following data:

Issuer

Issue Currency

Issue Rate

Issue Start

Compatible End of Term

Orig. Nominal

Expected End of Term

CalculationFrom

Nominal per Trading Unit

- 3. In the Partner Assignment table, you can enter the business partners and their ranks within the ABS/MBS on a timedependent basis (by entering the start date and the end date).


**Note:**

A class represents a tranche of an ABS/MBS.

**Note:**

You can define the partner ranks in the Define Partner Ranks configuration activity available in your configuration environment. The rank contains information about the task of the business partner in connection with asset-

backed/mortgage-backed security.

**Related Information**

Manage Securities Classes

###### Asset Pool Data

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Asset Pool Data | L5 | trm04 p.188 | loio `4ecf6e84414c4c1d880e449ee47f67f1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ecf6e84414c4c1d880e449ee47f67f1.html?locale=en-US)

- Relevant for ABS/MBS -

- 1. Enter the General Asset Pool Data:

Enter the Pool ID.

Choose the Pool Class..

Enter the Nominal Amount.

- 2. In the Rating table, you can enter the rating for the asset pool.


You either enter the Rating or the Credit Standing, this depends on the general setting for rating in Treasury and Risk Management made in the Customizing.

Rating

- a. Choose the Rating Procedure.

Indicates the used rating procedure.

- b. Choose the Rating.

Indicates the result of a rating carried out with a rating procedure.

- c. Choose the Trend for the rating.

Indicates the trend of an existing rating so that expected changes to the business partner can be displayed.

- d. Enter the validity for the rating using the Valid From and Valid To fields.
- e. Save your entries.


**Note:**

You can enter the ratings of different rating procedures.

Credit Standing

- a. Choose one of the predefined internal classificationsCredit Standing.
- b. In the Dt.Cred.Stndg field, you can enter the date on which credit standing information on the business partner was provided.
- c. You can enter the Status of the credit standing information.
- d. In the Cred.Stndg Text field, you can add additional information for the credit standing.
- e. In addition, you can enter one external provided rating information for the business partner. Choose the credit standing institute in Cred.Stndg Inst field and enter the Rating result provided by the credit standing institute.


- f. In addition, you can set the following indicators and enter a corresponding date:

Affidavit

Bankruptcy Proceed.

Foreclosure

- g. You can enter the status of legal proceedings and the corresponding date.
- h. Save your entries.


In the Customizing activity Make General Settings for Rating available under Treasury and Risk Management

Transaction Manager General Settings Organization Rating/Credit Standing , you decide which rating function you want to use for the rating of financial transactions, security classes, and asset pools in Treasury and Risk Management. You can decide between the following rating functions:

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

- 3. In the Comments table, you can enter time-dependent comments.

###### Conditions

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions | L5 | trm04 p.189 | loio `0a1ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0a1ada531198434de10000000a174cb4.html?locale=en-US)

**Definition**

A condition is a contractually agreed element of a financial transaction or financial instrument. It describes the structure of the transaction in terms of the period and amount (such as interest and repayment).

**Note:**

In the product type definition of the Securities area, you can choose Parallel Interest Conditions in the Cash Flow Generation field.

This setting enables the usage of extended financial mathematic functions (New FiMa), such as parallel conditions and the assignment of up to 5 calendars for the working day check. This influences how conditions are managed and therefore how

cash flow is calculated.

If you make this settings you also get the Condition Details: Interest (New FiMa) screen to enter the interest conditions, this includes additional interest calculation types, such as Exponential Interest Calculation with Factors, Compound Interest Calculation, and Average Compound Interest Calculation. So, you can enter variable interest conditions with risk-free reference rates. For more information, see also Interest Calculation Types. In addition, parallel interest conditions are possible.

Condition Type

You define conditions using condition types. You assign flow types to condition types in the Customizing activity Define Condition Types. These flow types display changes to the payment flows and are part of the cash flow. You assign the flow categories and calculation categories, which are predefined in the system, to the flow types you define yourself in the Customizing activity Define Flow Types.

**Note:**

SAP delivers flow types for the common business transactions. You can use these flow types without making changes to them.

Since flow types can be complicated to set up, we recommend that you copy an existing flow type when you create a new flow type and then that you make changes to that copy. It’s a good idea to print out the current flow type definitions before you change the flow types.

Typical condition types are interest, dividends, and final repayments.

Condition Group

Several condition types form a condition group.

Each product type requires only a selection of condition types. Create different condition groups, such as a condition group for percentage-quoted securities or fixed-interest securities. To do this, choose Define Condition Groups in Customizing for securities. Group together the different condition types by choosing Assign Condition Types to Condition Groups. You then assign these condition groups to the individual product types using the Define Product Types function.

**Use**

Conditions include all the data that is relevant for generating condition-based flows in the cash flow. The different entries for the individual condition types determine exactly how the flows are calculated.

Conditions in the securities area are individual conditions. This means that a condition cannot exist independently of a class.

**Structure**

The conditions are part of the class data. Call them up by choosing the Conditions tab.

Condition Header (general condition characteristics)

The condition header displays the basic data for the security, which applies to all condition items or which enhances the individual condition items.

You can determine the fields you want to display to some extent in the Customizing activity Define Product Types and using the field selection function.

Condition Items

You can choose from several condition types for each product type according to the settings you make in Customizing.

Effective From, Calculation Date, Due Date, and Percentage Rate.

**Note:**

When you create a new class, the system displays different condition items according to the entries you made in the Customizing activity Assign Condition Types to Condition Groups. If a condition type was set to Hide in Customizing, it isn’t displayed, and you have to call it up by choosing (Insert Additional Items).


If a condition item isn’t filled, it isn’t displayed in the change mode. You can, however, include it again by choosing (Insert Line).


To enter a condition type more than once - for example, to portray a staggered rate of interest - go to the corresponding condition item and choose (Insert Line).

The first condition item is valid until the effective-from date of the second condition item.

By choosing (Duplicate Line), you can make it easier to enter the second condition item for the same condition type. The selected condition item is copied, and you simply have to enter the effective-from date and other changes (for example, the new interest rate and/or a new interest payment frequency).


To add a zero condition, for example, to suspend an interest payment for one year before the final due date, add a new condition item. Enter the effective-from date for the zero conditions, and go to the condition details. There, you set the indicator for zero conditions in the Condition Form field.

Choose the Cash Flow button in the upper part of the screen and check your entries. The fictitious entry in the Cash Flow field shows whether the entries result in the required flows.

The cash flow is displayed in position currency only. The local currency isn’t translated because no company code is recognized within the class data.

To delete a condition item, select it and choose (Delete Line).


You can see a padlock icon in front of every condition line. The padlock is either open or closed .

open means that the condition item can still be changed.


closed means that it cannot be changed because some flows have already been posted for this condition item.


You can set most of the entry fields for each condition type as an optional entry or a required entry, or you candisplay fields using the field selection function in the Customizing activity Define Condition Types.

By double-clicking a condition item or selecting the condition item and choosing Detail, you can display the detail screens for the conditions.

Condition Details

Here, you find the effective-from date again for the condition item, the Condition Form field, and the Amounts, Dates and Payment Data / Other tabs, depending on the condition type.

Using the three values for the Condition Form field, you define how the relevant flows of the condition item influence the cash flow:

- 1. Active

The condition item is relevant for the cash flow calculation.

- 2. Zero Condition


When you enter a zero condition, you can end the effectiveness of a condition item at any date. Enter a new condition item of the same condition type, enter the required effective-from date, and mark it as a zero condition. The zero condition enables you to represent, for example, the suspension of interest payments one year before the final due date. To reactivate calculations for this condition type, you enter a subsequent condition item.

- 3. Fixed Condition

Fixed condition means that the relevant condition item isn’t recalculated for an alternative effective interest rate or term end.

- 4. Statistical Condition


A statistical condition item is ignored. In other words, no flow records are generated in the cash flow.

The Amounts, Dates, and Payment Data / Other tabs show you exactly how the conditions are structured. The screen contains additional fields to those on the initial Conditions screen, depending on which fields you select for the condition.

Amounts

This tab includes entries for the amounts and/or the amount of a condition type. For the Nominal Interest condition type, these include more detailed entries for the interest calculation. The Reference Interest Rate field is also included here when you have a variable interest rate.

Dates

- 1. Calendar
- 2. If you always want to shift the due date to a working day, enter the calendar you want to use to calculate the working day (Factory Calendar).
- 3. Calculation Date/Due Date

The calculation date is the last day of the current interest period. The due date is the day on which the interest payment is due.

This area includes the fields for determining the exact calculation dates and due dates of the condition item.

- 4. Calculation Modes


Here, you define the method used to determine the next calculation date or due date.

**Note:**

You can make defaults settings for these fields for each condition group and condition type in the Customizing activity Assign Condition Types to Condition Groups.

Choose Date Preview to display a list of the dates for the flows of the relevant condition type. The list includes the due date, the payment date, the calculation period, and the resulting number of days (interest days), as well as the interest calculation method.

The entry options in the condition details differ depending on the condition type.

**Related Information**

Conditions for Bonds Conditions for Stock/Shareholding Conditions for Investment Certificates Conditions for ABS/MBS With Parallel Interest Conditions Conditions for ABS/MBS With Single Interest Conditions

###### Conditions for Bonds

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds | L6 | trm04 p.193 | loio `2617da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2617da531198434de10000000a174cb4.html?locale=en-US)

When you enter conditions, you enter the general condition characteristics followed by the individual condition items of the various condition types.

As far as the general condition characteristics are concerned, we distinguish between the fields that you can set up yourself using the field selection function in Customizing and those that are predefined in the system. The latter type includes fields in which you’re required to enter data for technical reasons (required entry fields). In the Customizing of Treasury and Risk Management under Transaction Manager Securities Master Data Product Types Condition Types Define Condition Types , you define the field selection for each condition type.

[figure TRM04-F048 - On top of the Conditions tab for bonds in the Cash Flow Generation area, you can choose Parallel Interest Conditions in the Cash Flow Calculation field. With this setting, you enable the following functions:]

On top of the Conditions tab for bonds in the Cash Flow Generation area, you can choose Parallel Interest Conditions in the Cash Flow Calculation field. With this setting, you enable the following functions:

You can enter fixed and variable interest conditions in parallel for a bond.

The interest condition details screen provides more settings (new FiMa), such as additional interest calculations types for variable interest conditions. For more information, see also Creating Variable Interest and Interest Rate Adjustment Condition Items (New FIMA)

For unit-quoted bonds with parallel interest conditions, use the nominal interest for percentage-quoted bonds. In addition, you can enter installment repayment as a condition type. Define the Condition Amount field as the value of one installment repayment per unit. Condition amount is deducted from original nominal value per unit with each installment repayment. Frequency of installment repayment should have same frequency as interests.

**Note:**

If you choose the Single Interest Conditions, you can only create one interest condition for the bonds and the condition detail screens do not provide interest calculation types like Compound Interest Calculation and Average Compound Interest Calculation. Refer to the following topic for the creation of variable interest and interest rate adjustment conditions: Variable Interest and Interest Rate Adjustment

General Condition Characteristics

Interest Calculation

Interest Calculation method - the system provides you with a selection of methods (required entry):

The interest calculation method is defined by the ratio TAGE / TAGEBASIS (days / day basis).

See also: Using the input help for the Interest Calculation Methods field, you can see the definitions of the different methods used to calculate the values in the Days and Day Basis fields.

**Note:**

In the condition details, you specify for each condition item whether you want interest to be calculated linearly or exponentially.

Repayment

The following repayment types (required entry) are supported for bonds:

Final Due Date

Perpetual Bonds

Installment repayment

Effective interest rate

Effective Interest Rate Method - the system provides a selection of five methods:

Price specification

AIBD/ISMA

MOOSMULLER

BRAES

US method

Interest Calculation Frequency:

Specified in months, the frequency is required for the interest calculation methods for Moosmuller and for the US Treasury procedure.

Effective Interest Rate:

Use the button (Calculate Effective Interest Rate) to display the effective interest rate calculated from the class conditions.


**Note:**

The effective interest rate is calculated for the cash flows that are marked as relevant.

See also: The documentation for the Customizing activity Define Flow Types in the securities area.

Condition Items

The following sections describe how to enter condition items for bonds, convertible bonds, and warrant bonds.

You assign a range of different condition types to the various product types from these product categories in Customizing.

You can represent fixed-interest, percentage-quoted, and unit-quoted bonds as well as variable-interest bonds using these condition types.

You can set most of the entry fields for each condition type as optional or required, and you can display fields using the field selection function in Customizing by choosing Define Condition Types. The sample Customizing settings delivered with the system allow you to enter the condition types described in this section.

Nominal Interest for Percentage-Quoted Bonds

###### Nominal Interest for Percentage-Quoted Bonds

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds > Nominal Interest for Percentage-Quoted Bonds | L7 | trm04 p.195 | loio `c717da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c717da531198434de10000000a174cb4.html?locale=en-US)

Required entries:

Effective from date

Interest rate ( percentage )

Frequency in months ( Frq ) in which the interest is paid

Calculation date (=last day of the current interest period)

First due date (=day of the first interest payment)

Currency (of the interest payment)

Additional entry fields:

Select fields MC and ED to specify whether you want the calculation date or the due date to fall on the last day of the month. If you select these fields, the respective day is always the last day of the month, even if you enter another date somewhere else.

Field CR enables you to choose whether to shift the calculation date or the due date to a working day if the date entered is not a working day. If you opt to shift the due date, you must select an appropriate calendar from the Dates screen .

**Caution:**

Since the calculation date is used as a basis for calculating financial mathematical transactions, you are advised not to choose a shift rule.


You can display the due date, the payment date, the calculation period and the days that result from the interest payments by choosing the Dates button on the Amounts screen .

**Nominal Interest for Unit-Quoted Bonds**

Required entries:

Effective from date

Interest payment amount per unit

Frequency in months ( Frq ) in which the interest is paid

Calculation date (= last day of the current interest period)

First due date (= day of the first interest payment)

Currency (of the interest payment)

Additional entry fields:

You flag fields MC and ED to determine whether you want the calculation date or the due date to fall on the last day of the month. If you select these fields, the respective day is always the last day of the month, even if you enter another date somewhere else.

Field CR enables you to choose whether to shift the calculation date or the due date to a working day if the date entered is not a working day. If you opt to shift the due date, you have to select an appropriate calendar from the Dates screen .

**Caution:**

Since the calculation date is used as a basis for calculating financial mathematical transactions, you are advised not to choose a shift rule.


You can display the due date, the payment date, the calculation period and the days that result from the interest payments by choosing the Dates button on the Amounts screen .

**Note:**

For unit-quoted bonds with parallel interest conditions, use the nominal interest for percentage-quoted bonds. In addition, you can enter installment repayment as a condition type.

###### Nominal Interest for Unit-Quoted Bonds

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds > Nominal Interest for Unit-Quoted Bonds | L7 | trm04 p.195 | loio `ca17da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ca17da531198434de10000000a174cb4.html?locale=en-US)

Final Repayment

Repayment Rate

Repayment Price

Creating Variable Interest and Interest Rate Adjustment Condition Items (New FIMA)

Variable Interest and Interest Rate Adjustment

Price Index Adjustment Condition

###### Creating Variable Interest and Interest Rate Adjustment Condition Items (New FIMA)

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds > Creating Variable Interest and Interest Rate Adjustment Condition Items (New FIMA) | L7 | trm04 p.196 | loio `d617da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d617da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Two types of condition item are required to represent the variable interest rate condition.

- 1. You must define the underlying reference interest rate and the calculation method for the variable interest rate in the condition item Variable Interest.
- 2. You define the frequency with which you want the new variable interest to be recalculated or become effective, and you specify the day om which you want to establish the reference interest rate value for determining the variable interest rate in the condition item Interest Adjustment.


Prerequisites

We recommend that you maintain the reference interest rate table regularly to ensure that current data is available for interest rate fixing.

**Procedure**

Create the variable interest condition item.

Enter the reference interest rate, the plus/minus sign and the percentage rate, the calculation date, the due date, and the frequency. Using the indicators, such a MC, CR, and MEID, you can specify the concrete interest period.

Set the MC and MEID indicators to specify whether you want the calculation date or the due date to fall on the last day of the month. If you set these indicators, the respective day is always the last day of the month, even if you enter another date elsewhere.

The CR indicator enables you to choose whether to shift the calculation date or the due date to a working day if the date entered is not a working day. If you opt to shift the due date, you must select an appropriate calendar from the Dates screen.

By double-clicking a condition, you open the condition details.

The details screen comprises the following areas:

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

Scaled Calc.

By setting this indicator, you can enter scaled conditions. See also: Scaled Conditions

Formula

You can enter a formula for the interest rate calculation. Choose a formula and enter the values for the variables.

Ref. Int. Rate

For variable interest conditions, you can enter a sign (+ or -) and a reference interest rate.

Percentage Rate

Enter the percentage rate for the interest condition.

**Note:**

For variable interest conditions, you can also add here a percentage that is a spread on top of the variable interest rate.

Payment Rate

The payment rate indicates a percentage rate that is applied to the condition amount calculated previously. The cash flow therefore does not display the condition amount calculated, but the condition amount multiplied by the payment rate in percent. For more information, see the field help.

The Average Interest Rate area contains specific settings for the average interest rate calculation of the average compound interest calculation. You see this area only if you have chosen this interest calculation type.

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

In this area, you define the rounding rules (rounding category and the number of decimal places) for the calculated factors. Which factors are available here depends on the interest calculation type you have chosen:

Base Factor

Interest Factor

Flow Factor

Example:

For the average compound interest calculation, you can enter a rounding category and the number of rounding decimal places for the interest factor.

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

You can find a more detailed description of the methods in the field help.

Date tab

On this tab, you define the interest calculation periods.

**Note:**

For variable interest rates, you define in addition the interest rate adjustment condition, where you define the interest rate adjustment periods. You can have several interest rate adjustments within an interest period.

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

Set the Month End indicator if needed.

Other calculation data

Shift due date

First period

Last period

For more information, see the field help.

**Note:**

Since the calculation date is used as the basis for calculating financial mathematical transactions, you are advised not to choose a shift rule.

You can display the due date, the payment date, the calculation period, and the days that result from the interest payments by choosing the Dates button on the Amounts screen.

Create the interest rate adjustment condition item.

- 1. Enter the effective-from date.
- 2. Branch to the Condition Detail Screen.
- 3. The screen is divided into the Amounts and Dates tabs.


On the Amounts tab, you enter the interest calculation method.

The Dates tab is divided into two areas: Interest Rate Adjustment and Interest Rate Fixing Date:

In the Interest Rate Adjustment area, you enter the frequency with which you want the variable interest to be recalculated or become effective. The following alternatives are available:

At Start of Period

Regular

You define the frequency using the available fields.

Single Dates

The Single Dates function displays the interest rate adjustments that recur annually and that you cannot display via At Start of Period and Regular.

Example:

Interest rate adjustment takes place annually on 03/15 and 10/15.

You can show this irregular sequence of interest rate adjustment dates only with the Single Dates function.

For reference interest rate entry

Enter the calendar rule, which specifies how to handle the date if it falls on a day that is not a working day.

Also define which calendars are relevant for determining the date as a working day.

In the Interest Rate Fixing Date area, you define when you want to determine the interest rate value from the market data table. You can choose from the following:

Relative to interest rate adjustment date

Relative to start of period

Relative to period end

Relative to due date

Enter the lookback period, which defines how many working days before hand the interest rate fixing date lies.

Lockout Period in Working Days: Period at the end of the interest period where the reference rate is not adjusted anymore. For these last days of the interest period, the last reference rate adjusted to one day before the period start is used.

Also define which calendars are relevant for determining the date as a working day.

4. Using the Dates button, you can display the interest rate adjustment dates. The system displays the following dates per interest rate adjustment:

Effective-from date of the new interest rate (interest rate adjustment date)

Interest fixing date

Percentage fixing date (this can differ from the interest fixing date if no entry has been made in the reference interest rate table. The system therefore chooses the previous entry).

New interest rate amount

###### Creating Accumulating Interest Condition Items (Securities)

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds > Creating Accumulating Interest Condition Items (Securities) | L7 | trm04 p.201 | loio `4b3074b6a0fd4f37820638738c025a5a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4b3074b6a0fd4f37820638738c025a5a.html?locale=en-US)

Create an accumulating condition in order to accumulate multiple interest flows into one.

**Procedure**

Prerequisites

You have created variable interest and interest rate adjustment condition items for your securities class, as described under Creating Variable Interest and Interest Rate Adjustment Condition Items (New FIMA). To accumulate these flows, proceed as follows:

- 1. On the Conditions tab, go into edit mode and select the row of the variable interest condition you want to accumulate.
- 2. Choose Insert Row ( ).
- 3. In the Add Condition Items popup, choose the condition type 104 and choose Copy.
- 4. In the Condition Details view, make sure the accumulating condition item has the same dates as the condition item you want to accumulate.
- 5. Leave the Condition Details view.


Result

A new accumulating condition item now appears under Condition Items on the Conditions tab.

In the Cash Flow section of the securities class, you now see the accumulated flows instead of the single variable flows. The Show Single Flows button lets you switch between single flows and accumulated flows. For details on cash flows for securities classes, see Cash Flow for the Class.

**Related Information**

Manage Securities Classes Cash Flow for the Class

###### Variable Interest and Interest Rate Adjustment

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds > Variable Interest and Interest Rate Adjustment | L7 | trm04 p.202 | loio `1228b942c51e4eff95b083310e7e0dfa` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1228b942c51e4eff95b083310e7e0dfa.html?locale=en-US)

**Use**

Two types of entries are required to represent the variable interest rate.

- 1. You must define the underlying reference interest rate and the calculation method for the variable interest rate in the condition item Variable interest.
- 2. You define the frequency with which you want the new variable interest to be recalculated or become effective, and the day you want to establish the reference interest rate value for determining the variable interest rate in the condition item Interest adjustment.


**Prerequisites**

We recommend that you maintain the reference interest rate table regularly to ensure that current data is available for interest rate fixing.

**Procedure**

- 1. Variable interest
- 2. By inserting a simple plus sign to link the variable interest and the reference interest rate in condition type Variable interest, you can enter these directly in the initial entry screen or in the Condition Details screen .

To define more complicated calculation formulas, choose the Formula button at the top of the Condition Details screen . Select a formula in the next screen by double-clicking one. In the following screen, enter the variables.

The remaining entry fields in this condition item are the same as those for entering nominal interest for fixed-interest percentage-quoted bonds.

- 3. Interest rate adjustment
- 4.


- a. Enter the Effective from date.
- b. Branch to the Condition Detail Screen 1.
- c. The screen is divided into two areas: Interest rate adjustment and Interest fixing :


- d. In the Interest rate adjustment area, you enter the frequency with which you want the variable interest to be recalculated or become effective. The following alternatives are available:

- i. at start of period
- ii. frequency with fixed date
- iii. single dates
- iv. for each table entry


- e. The Single dates function displays the interest rate adjustments which recur annually and which you cannot display via At start of period and Frequency with fixed date.


Interest rate adjustment takes place annually on 03/15 and 10/15.

You can only show this irregular sequence of interest rate adjustment dates via Single dates.

- f. In the Interest rate fixing area, you define when you want to determine the interest rate value for calculating the new variable interest rate. You can choose from the following:
- g.

- i. Relative to interest rate adjustment date
- ii. Relative to start of period
- iii. Relative to period end
- iv. Relative to due date


In the field below, enter how many days beforehand the interest rate fixing is to take place.

Also define which calendar you want to use for determining the date.

- h. Using the Dates button you can display the interest rate adjustment dates. The system displays the following dates per interest rate adjustment:
- i.


- i. Effective from date of the new interest rate (interest rate adjustment date)
- ii. Interest fixing date
- iii. Percentage fixing date (this can differ from the interest fixing date, if no entry has been made in the reference interest rate table. The system therefore chooses the previous entry).
- iv. New interest rate amount

###### Final Repayment

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds > Final Repayment | L7 | trm04 p.203 | loio `cd17da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cd17da531198434de10000000a174cb4.html?locale=en-US)

You do not have to enter the final repayment yourself. The system calculates it automatically using the due date in the conditions header. The system, however, assumes it to be a 100% repayment.

If you enter a different repayment rate, the system disregards the entry. Use condition type Repayment Rate to enter a deviant repayment rate.

###### Repayment Rate

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds > Repayment Rate | L7 | trm04 p.203 | loio `d017da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d017da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You have to define the repayment rate of the security in this condition item if it deviates from 100%.

**Procedure**

Enter the Effective from date and the deviant repayment rate in Percent.

###### Repayment Price

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds > Repayment Price | L7 | trm04 p.204 | loio `d317da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d317da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You have to define the repayment price of the security in this condition item if it differs from the issue price.

**Procedure**

Enter the Effective from date and the deviant repayment price .

###### Price Index Adjustment Condition

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Bonds > Price Index Adjustment Condition | L7 | trm04 p.204 | loio `7b377fb935f340edb15923f6c88a0ea8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7b377fb935f340edb15923f6c88a0ea8.html?locale=en-US)

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

[figure TRM04-F053 - Valid From: November 15th]

Valid From: November 15th

Calculation Date: December 12th

Fixing Date Low: October 1st

Fixing Date High: November 1st

Inflation in October is used for calculation period till December 15.

In case the index key date falls between two index calculation dates, the system calculates the price index factor based on the value of interpolation.

Rounding

You can define rounding during price index factor calculation. The following formulas show how the rounding is applied:

Off/Linear

[figure TRM04-F054 - Exponential]

Exponential

[figure TRM04-F055 - Ik – price index for key date (after linear interpolation)]

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

###### Conditions for Stock/Shareholding

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Stock/Shareholding | L6 | trm04 p.206 | loio `7e18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7e18da531198434de10000000a174cb4.html?locale=en-US)

When you enter conditions, you enter the general condition characteristics followed by the individual condition items of the various condition types.

A distinction is made between the fields in the general condition characteristics that you can set up yourself using the field selection function in Customizing and those that are predefined in the system. The latter type includes fields in which you’re required to enter data for technical reasons (required entry fields).

General Condition Characteristics

Partly Paid indicator

If you set the Partly Paid indicator for a class, the table Payment Rates/Installments appears, where you can set the data for the partial payment.

Additional payments can be structured using the condition type Additional Payment.

Dividend authorization

Dividend authorization Effective From date

Percent: The percentage dividend authorization for each unit specifies how much of a dividend will be paid for a new issue as opposed to the old issue.

Condition Items

The following section describes how to enter condition types for the product categories Stock and Shareholding.

You assign a range of these condition types (that is, a condition group) to the various product types from these product categories in Customizing.

You can use the field selection function to set the entry fields for each condition type as optional, required, or display fields in Customizing for Securities by choosing Define Condition Types. The Customizing settings delivered with the system allow you to enter the condition types described in this section.

You can also assign default conditions for some fields in the Customizing activity Assign Condition Types to Condition Groups:

Dividends

Bonus

Supplementary Payments

###### Dividends

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Stock/Shareholding > Dividends | L7 | trm04 p.207 | loio `d917da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d917da531198434de10000000a174cb4.html?locale=en-US)

Enter the following data:

Due date

Estimated dividend amount

Currency

Number of the dividend coupon next due

###### Bonus

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Stock/Shareholding > Bonus | L7 | trm04 p.207 | loio `df17da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/df17da531198434de10000000a174cb4.html?locale=en-US)

Enter the following data:

Due date

Estimated amount of the distributions

Currency

**Note:**

We do not recommend that you enter a monthly frequency.

###### Supplementary Payments

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Stock/Shareholding > Supplementary Payments | L7 | trm04 p.207 | loio `e217da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e217da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Initially, only a certain percentage of the nominal amount is paid for partially-paid stocks (not listed). To do this, choose condition type supplementary payment, which corrects the initial amount paid by means of a supplementary payment.

**Procedure**

The supplementary payments condition consists of a due date and a supplementary payment amount.

- 1. Enter the Due date of the supplementary payment
- 2. Enter the Amount or Percentage rate of the supplementary payment. If you enter a percentage rate the system can calculate the amount automatically, and vice versa.


**Note:**

The pay-in rate and the total supplementary payments must not exceed 100%.

###### Conditions for Investment Certificates

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for Investment Certificates | L6 | trm04 p.208 | loio `a9dd5aec49d045668da887d2f2acf2dc` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a9dd5aec49d045668da887d2f2acf2dc.html?locale=en-US)

Enter conditions for investment certificates.

When you enter conditions, you enter the general condition characteristics followed by the individual condition items of the various condition types.

A distinction is made between the fields in the general condition characteristics that you can set up yourself using the field selection function in Customizing and those that are predefined in the system. The latter type includes fields in which you’re required to enter data for technical reasons (required entry fields).

General Condition Characteristics

Reinvestment area

Reinvestment indicator

Reinvestment discount

You assign a range of these condition types (that is, a condition group) to the various product types from these product categories in Customizing.

You can use the field selection function to set the entry fields for each condition type as optional, required, or display fields in Customizing for Securities in the Define Condition Types function. The Customizing settings delivered with the system allow you to enter the condition types described in this section.

You can also assign default conditions for some fields in the Customizing activity Assign Condition Types to Condition Groups.

Profit Distribution

This is a dividend condition where you can either enter value factor types with variable dividends or choose a fixed amount.

If you choose to use variable dividends, you select a factor type in the Data for Percentage Calculation area on the Amount tab and specify the number of calendar days or months in the Calculation Date area on the Date tab.

If you choose to use fixed amounts, enter the following data:

Due date

Estimated amount of the distributions (Condition Amount field)

Currency

Dividend Adjustment (Monthly)

In addition, the adjustment condition takes effects if you choose to use variable dividends. You can adjust the dividend calculation frequency and get the right dividend factor value. You chooseRegular, for example, to select the number of calendar days or months in the Interest Rate Adjustment area and the Interest Rate Fixing Date area on the Date tab.

Accrued Dividend

This is a daily dividend condition where you can either enter value factor types with variable dividends or choose a fixed amount.

If you choose to use variable dividends, you select a factor type in the Data for Percentage Calculation area on the Amount tab and specify the number of calendar days or months in the Calculation Date area on the Date tab.

If you choose to use fixed amounts, enter the following data:

Due date

Estimated amount of the distributions (Condition Amount field)

Currency

Dividend Adjustment (Daily)

In addition, the adjustment condition takes effects if you choose to use variable dividends. You can adjust the dividend calculation frequency and get the right dividend factor value. You choose Regular, for example, to select the number of calendar days in the Interest Rate Adjustment area and the Interest Rate Fixing Date area on the Date tab.

Accumulated Dividend

This condition sums up the dividend that includes all the dividend flows during the period. For example, you can calculate the dividend monthly if you use the daily accrued dividend and dividend adjustment. You choose the number of months in the Calculation Date, 1st Date, Due Date areas on the Date tab.

###### Conditions for ABS/MBS With Parallel Interest Conditions

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for ABS/MBS With Parallel Interest Conditions | L6 | trm04 p.209 | loio `a74c14ff15cc462b87242cd221cf8f62` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a74c14ff15cc462b87242cd221cf8f62.html?locale=en-US)

The conditions of the ABS/MBS are the versioned redemption schedules, that contain beside the redemption schedule, also the interest conditions, and the calculations parameters that can change continuously over the course of the term of the security, meaning that the conditions (calculation parameter, redemption schedules, etc.) in the class data must be adjusted regularly.

The active version of the redemption schedules is the basis for the cash flows for ABS/MBS positions.

On the Conditions tab, you can make general setting for the Interest Calculation (Interest Calculation Method and Rounding Rule) and for the calculation of the Effective Interest Rate (Eff.Int.Meth., Int.Sttlm.Freq, Effect.Int.Rate).

The Repayment Type is set to Inst.Repaymt.

All other settings are made in the redemption schedules, which you can access by choosing the Red.Schedules button.

**Overview: Redemption Schedule**

[figure TRM04-F056]

**Version**

Here you get the following basic data for the shown redemption schedule version:

Sec. Class

Shows the security ID number of the ABS/MBS.

Valid From

Valid-from date of the version.

Valid To

Valid-to date of the version

**Note:**

When you create a new version for the security ID, the 'old' version is valid to the valid-from date of the new version. The new version is valid to the end of the security until the next version is created.

Key date

The current key date

From this area, you can Create, Activate, or Delete the shown version.

**Version Overview**

In this table, you can see the existing redemption schedule versions, their status (editable or active), and their basic data.

The blocking status can have the following values:

No blocking business transactions exist

Version is blocked by a business transaction

In this case, you can display the blocking business transaction.

The version number is set by the system after saving and referenced in the cash flow.

You can select a version by clicking on a table line.

You can only delete a version that are not blocked by business transactions or posted flows. Deleted versions can not be restored.

You can activate an editable version. Once activated, the version cannot be changed. Only active versions are used for the cash flows of the securities positions.

**Version Details**

Schedule You first select the Entry Type. You can choose between entering the factor, the current face value, or the repayment. You make this setting once in the first version, which means that it is also defined for all subsequent versions.

To simplify the entry of the redemption schedule, you can copy the dates from a condition and apply them to the repayment flows by selecting the corresponding condition in the Redemption Template field. You can choose between the fixed interest condition (Int. (perc.-quoted)), the Variable Interest condition, or a ABS/MBS Inst.Repaymt condition. For the chosen template a corresponding condition must be defined on the Conditions tab. If the fixed or variable interest condition does not fit as template for the redemption schedule, you can define a installment redemption condition with condition form 4 - Template, to define the redemption dates.

For each 'template' condition flow, the system creates a corresponding repayment flow with the following dates:

Calculation date of the repayment = calculation date of the template condition flow

Payment date of the repayment = due date of the template condition flow

**Note:**

When you create a new version of the redemption schedule, you must enter first the new calculation parameter and the interest conditions (especially important for the entry of the first redemption schedule version) and afterward, enter the new factor on the Schedule tab.

Use the Generate Schedule button, to generate the redemption schedule.

The table for the redemption schedule consists of many columns, the most important columns are as follows:

Calculation date

Payment date

Status of the factor

The status of the factor is either estimated or published.

Redemption factor

The system calculates the estimated repayment factors for the dates of the template condition based on the calculation parameters. When the factor for redemption is published, you create a new version and enter the published factor manually.

Current face

| |Face value change Principal payment The value in this column is controlled by the payment (amount) calculation method, that you have chosen for the tranche category. The following settings are available: Zero Payment Amount In this case, the value in the principal payment field is always set to zero. You cannot change the calculated principal payment amount. Equal to Change in Nominal In this case, the value in the principal payment field is equal to the change in nominal. The change in nominal is calculated to ensure that original nominal * current face factor = current nominal is satisfied. You cannot change the calculated principal payment amount. Using Fraction of Issued Nominal (Fixed) The payment amount for the redemption in a position is calculated by multiplying the ratio of the original position nominals to the total of the issued nominal by the total repayment amount of the redemption schedule. This can differ from the nominal change due to different rounding results. You cannot change the calculated principal payment amount. Using Fraction of Issued Nominal (Variable) The payment amount for the redemption in a position is calculated by multiplying the ratio of the original position nominals to the total of the issued nominal by the total repayment amount of the redemption schedule. This can differ from the nominal change due to different rounding results. You can manually change the calculated principal payment amount after the values have been calculated by the system. **Note:** If you choose this setting, you must take care to post the repayments with other flows.|
|---|---|
|Conditions|On this tab, you enter the interest conditions for the ABS/MBS. This is similar to interest conditions of bonds, for example. 100 (Int. (Perc.-Quoted)) You use this condition type for bonds with fixed interests. Enter the percentage rate, calculation date, due date, and frequency. Using the indicators, such as MC, CR, and MEID, you can specify the concrete interest period.|


Set the MC indicator to specify whether you want the calculation date or the due date to fall on the last day of the month. If you set this indicator, the respective day is always the last day of the month, even if you enter another date somewhere else.

The CR indicator enables you to choose whether the calculation date or the due date is shifted to a working day if the date entered is not a working day. If you opt to shift the due date, you must select an appropriate calendar from the Dates screen.

By double-clicking a condition, you open the condition details.

The details screen comprises the following areas:

Header data of the condition at the top of the screen.

Amount tab

Data for Percentage Calculation

Interest calculation method and the type of interest calculation

The interest calculation method is a procedure for counting the days for the interest calculation. Therefore, it is also often called thedays count method. This is defined by a quotient of days method and a base days method.

The following types of interest calculation are available:

Linear Interest Calculation

Amount = capital * percentage rate / 100 * days / base days

Exponential Interest Calculation

Interest amount = Base amount * ( q ** (days / base days) - 1 )

where

q = 1 + percentage rate / 100 (compounding factor)

** = power operator

Percentage Rate

[figure TRM04-F057]

Enter the percentage rate for the interest condition.

Currency-Related Data

Currency

Exchange Rate

Date tab

On this tab, you define the interest calculation periods.

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

First, you choose the rule for date updates. The default value is Regular, which means that the frequency of the calculation date is also relevant for the due date.

Enter the frequency by entering the unit for the frequency (Months or Calendar Days) and the cycle.

Enter the first date.

Set the Month End indicator if needed.

Other calculation data

Shift due date

First period

Last period

For more information, see the field help.

**Note:**

Since the calculation date is used as the basis for calculating financial mathematical transactions, you are advised not to choose a shift rule.

You can display the due date, the payment date, the calculation period, and the days that result from the interest payments by choosing the Date Preview button at the top of the screen.

101 (Variable Interest)

You use this condition type for bonds with floating rates.

Enter the reference interest rate, the plus/minus sign and the percentage rate, the calculation date, the due date, and the frequency. Using the indicators, such a MC, CR, and MEID, you can specify the concrete interest period.

Set the MC and MEID indicators to specify whether you want the calculation date or the due date to fall on the last day of the month. If you set these indicators, the respective day is always the last day of the month, even if you enter another date elsewhere.

The CR indicator enables you to choose whether the calculation date or the due date is shifted to a working day if the date entered is not a working day. If you opt to shift the due date, you must select an appropriate calendar from the Dates screen.

By double-clicking a condition, you open the condition details.

**Note:**

Since the calculation date is used as the basis for calculating financial mathematical transactions, you are advised not to choose a shift rule.

You can display the due date, the payment date, the calculation period, and the days that result from the interest payments by choosing the Dates button on the

Amounts screen.

For more information, see also Creating Variable Interest and Interest Rate Adjustment Condition Items (New FIMA)

209 (Int. Rate Adjustment)

In addition, the interest rate adjustment condition takes effect if you use variable interest. You can adjust the interest calculation frequency. If you choose Regular, for example, the number of

| |calendar days or months in the Interest Rate Adjustment area and the Interest Rate Fixing Date area are displayed on the Date tab. By double-clicking a condition, you open the condition details. For more information, see also Creating Variable Interest and Interest Rate Adjustment Condition Items (New FIMA) You can also create a ABS/MBS Inst.Repayt, automatically with the condition form 4, to be used as template for the redemption schedule. This condition does not trigger additional repayment flows.|
|---|---|
|Calculation Parameters|In this area, you enter the specific ABS/MBS calculation parameter relevant for the calculation of the repayment flows. Prepayment Calc. Method Linear Method CPR Method The CPR method specifies the probable amount of the monthly advance repayment. The value is determined using the historic market data for similar loans. The CPR value is quoted in percent. PSA Method The PSA method assumes that the amount of the advance repayments of loans increases over the first 30 months before becoming constant thereafter. Prepayment Speed Interval Choose the prepayment speed interval to identify the CPR/PSA value that you want to use for the redemption calculation. When you choose Monthly, the system performs the calculation using the CPR1 or PSA1 value. When you choose Quarterly, the system calculates the CPR3 or PSA3 value. When you choose Semi-Annually, the system calculates the CPR6 or PSA6 value. When you choose Yearly, the system calculates the CPR12 or PSA12 value. When you choose Life, the system calculates the CPRL or PSAL value. **Note:** The mathematical relationship between the PSA method and the CPR method is as follows: If the age of the MBS is less than 30 months, the relationship between PSA and CPR is expressed thus: PSA = CPR / (0.002*number of the repayment month) If the age of the MBS is equal to or greater than 30 months, the relationship between PSA and CPR is expressed thus: PSA = CPR/0.06|


| |Other than the CPR/PSA value, the following values are also required in calculating the advance repayments: Original Values at the Time of Issue Original WAC Weighted gross average interest of the loans in the MBS Original Net Interest Net interest at the time when the security was issued Original WAM Weighted number of months until the loans have been paid back completely at the time of issue Current values that are valid when the factor is published WAC Weighted gross average interest of the loans in the MBS Net interest Current net interest of the security Age (only required for the PSA method) Specifies for how many months the ABS/MBS has been running WAM Weighted number of months until the loans have been paid back completely You enter these values when factors are published in the CPR/PSA Parameters table. **Note:** These values are entered when you create the security class and enter the first data in the CPR/PSA Parameters table. When you save these data, the system copies the values to the fields WAC Original, Net Original, and WAM Original.|
|---|---|
|User Data| |


Message Log

In this area, you can see the error and warning messages for the entered condition data.

**Changes during the term of the ABS/MBS bond**

If the values for the redemption schedule of an ABS/MBS subsequently change and the previous redemption schedule is already fixed in the system, you need to create a new redemption schedule version. In the new version, you can change the redemption schedule, the interest conditions, and the calculation parameters, for example:

When a payment date is reached, you change the factor in accordance with the actual amount of the repayments made and change the factor status from Estimated to Published.

The special key figures for the CPR/PSA calculation method change over time. You leave unchanged the original values at the time of issue in the general redemption schedule data. The current values are stored in the redemption schedule on the ABS/MBS tab. If you have made changes, you need to regenerate the repayment flows.

For every change, the system recalculates the subsequent flows.

###### Conditions for ABS/MBS With Single Interest Conditions

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for ABS/MBS With Single Interest Conditions | L6 | trm04 p.218 | loio `14e94b521dd16b67e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/14e94b521dd16b67e10000000a441470.html?locale=en-US)

On the Conditions tab, you can make general setting for the Interest Calculation (Interest Calculation Method and Rounding Rule) and for the calculation of the Effective Interest Rate (Eff.Int.Meth., Int.Sttlm.Freq, Effect.Int.Rate).

Interest Calculation

Effective Interest Rate

Repayment

For ABS/MBS bonds, the default setting for the repayment type is Installment Repayment. To access the general repayment schedule data for this class, choose the Repayment Schedules pushbutton.

See also:Creating Repayment Conditions for ABS/MBS

Condition Items

In this area, you define for ABS/MBS product types for which you have not activated the special conditions for ABS/MBS in Customizing, and other conditions (such as interest conditions) for this bond other than repayment.

For ABS/MBS product types for which you have activated the special conditions for ABS/MBS in Customizing, data cannot be entered in this area. All conditions are entered for these product types at the repayment schedule level.

###### Creating Repayment Conditions for ABS/MBS

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for ABS/MBS With Single Interest Conditions > Creating Repayment Conditions for ABS/MBS | L7 | trm04 p.218 | loio `cd0d6d517b09250ae10000000a445394` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cd0d6d517b09250ae10000000a445394.html?locale=en-US)

**Context**

The general redemption schedule data contains the following general data for the repayment of the bond:

General Data

Enter the issue currency.

The system displays the number of the redemption schedule.

Dates of Redemption Schedules

Select Distribute Repayments.

On the right-hand side of the screen, choose the calculation method for the repayments. In the case of product types for which the CPR/PSA calculation methods are not activated, this step does not apply.

The payment calculation method determines how the payment amount of a redemption flow is calculated. The following payment calculation methods are available:

Zero Payment Amount

The payment amount of the redemptions is set to zero.

Equal to Change in Nominal

The payment amount of the redemptions corresponds to the nominal change. The nominal change is calculated so that the following formula is met: Original nominal * current face factor = current nominal.

The calculated payment amount is not editable in the redemption schedule.

Using Fraction of Issued Nominal (Fixed)

The payment amount for the redemption in a position is calculated by multiplying the ratio of the original position nominals to the total of the issued nominal by the total repayment amount of the redemption schedule. This can differ from the nominal change due to different rounding results.

The calculated payment amount is not editable in the redemption schedule.

Using Fraction of Issued Nominal (Variable)

The payment amount for the redemption in a position is calculated by multiplying the ratio of the original position nominals to the total of the issued nominal by the total repayment amount of the redemption schedule. This can differ from the nominal change due to different rounding results.

The calculated payment amount can be edited in the redemption schedule.

Using Fraction of Issued Nominal for Modified Payment Amount

This method is similar to the Equal to Change in Nominal method. However, it allows you to modify the payment amount in the same way as in the Using Fraction of Issued Nominal (Variable) method. As with the latter method, if the payment amount is modified, the redemption in a position is calculated by multiplying the ratio of the original position nominals to the total of the issued nominal by the total repayment amount of the redemption schedule. The purpose of the Using Fraction of Issued Nominal for Modified Payment Amount method is to minimize rounding differences due using the fraction of the issued nominal.

The calculated payment amount can be edited in the redemption schedule.

**Note:**

The PSA calculation method is relevant for bonds with an amortization exceeding 30 months. In such cases, it is assumed that the CPR value increases over the first 30 months but then remains constant thereafter.

Enter the start date.

**Note:**

Typically, publication of the redemption schedules starts before the first repayment date. To be able to portray this initial period without repayments, you can enter a start date that is not the same as the first repayment date. During the period between the start date and the date of the first repayment, the factor remains constant at 1.

Enter the date of the first repayment.

Enter the date of the last repayment.

To simplify entering interest flows and repayment flows, you have the option of copying the dates from the interest condition and applying them for the repayment flows (using the Int.Cond.Template indicator). For each interest flow, the system creates a corresponding repayment flow with the following dates:

Effective date of the repayment = (changed) calculation date of the interest flow

The effective date of the repayment flow is the start date of the next month in which the interest calculation date falls on the month-end date (since repayments are published on the first day of the month).

Payment date of the repayment = due date of the interest flow

If you do not want to use the interest condition as a template, you have to make the settings for the repayment condition (payment frequency and rounding rule) here.

**Note:**

CPR and PSA calculation methods use repayment frequencies of a month.

Payment Currency

Here you enter the payment currency if it differs from the issue currency.

Choose the input type for the redemption schedule. You can choose between the following input types:

Enter Factors

Enter Current Nominal Values

Enter Repayments

Specify the number of relevant decimal points for the repayment factors.

Maturity Dates

This area is only activated if you do not use the Int.Cond.Template function.

In this area, you specify the factory calendar as well as the correction rule for the maturity dates of the repayments.

See also Date Determination Options for Interest Flows and Repayment Flows.

ABS/MBS

In this area, you enter the initial values for calculating the repayments using the CPR/PSA calculation methods.

For the CPR calculation method, you need to enter the following values:

WAC Original

Weighted average interest of the bond at the time when the bond is issued.

Net Original

The estimated net interest revenue at the time when the bond is issued.

WAM Original

The weighted average time (in months) until the final maturity date of all loans.

Enter the speed of advance repayments.

For the PSA calculation method, you need to enter the following values:

WAC Original

Net Original

WAM Original

Repayment Speed Interval

This interval is used to identify the CPR/PSA value that you would like to use to calculate repayments.

If you use Monthly, the system uses the value CPR1 or PSA1 for the calculation.

If you use Quarterly, the system applies the value CPR3 or PSA3.

If you use Semi-Annually, the system applies the value CPR6 or PSA6.

If you use Annually, the system applies the value CPR12 or PSA12.

If you use Life, the system applies the value CPRL or PSAL.

**Note:**

The mathematical relationship between the PSA value and the CPR value is as follows:

If the age of the MBS is less than 30 months, the relationship between PSA and CPR is expressed thus: PSA = CPR / (0.002*number of the repayment month)

If the age of the MBS is equal to or greater than 30 months, the relationship between PSA and CPR is expressed thus: PSA = CPR/0.06

Other than the CPR/PSA value, the following values are also required in calculating the advance repayments:

Original Values at the Time of Issue

Original WAC

Weighted gross average interest of the loans in the MBS

Original Net Interest

Net interest at the time when the security was issued

Original WAM

Weighted number of months until the loans have been paid back completely at the time of issue

Current values that are valid when the factor is published

WAC

Weighted gross average interest of the loans in the MBS

Net interest

Current net interest of the security

Age (only required for the PSA method)

Specifies for how many months the ABS/MBS has been running

WAM

Weighted number of months until the loans have been paid back completely

Save your entries.

In the Redemption Schedules area, create the redemption schedule by choosing .


The screen for entering the redemption schedule appears. Enter a short and a long description for the redemption schedule.

You use the following tabs for entering the redemption schedule:

ABS/MBS

For the CPR calculation method, enter the following values:

WAC

Net interest

WAM

CPR values

For the PSA calculation method, enter the following values:

WAC

Net interest

Age

WAM

PSA values

Redemption Schedule

In the Condition Positions area, first enter the interest condition. This is because the interest positions are included in the calculation of the repayment flows.

Then choose Create Repayments for Redemption Schedule.

The system now uses the data that you have entered to calculate the capital repayments as follows:

[figure TRM04-F059 - The system now uses the data that you have entered to calculate the capital repayments as follows:]

The redemption schedule contains the following columns:

Effective Date

Payment Date

Factor

Current Nominal Value

Nominal Value Reduction

Factor Status

Capital Repayment

Comment Field

**Note:**

You can make manual changes to the values calculated for the redemption schedule. Depending on the entry type selected, you can either change the factors, the current nominal value, or the capital repayment amounts.

Save your entries.

In the Date Preview, you see the calculation dates and maturity dates for the capital repayments.

**Note:**

If you have allowed factor increases in Customizing, a factor can also increase (that is, the nominal value increases during the term). This is the case, for example, when interest payments are capitalized. In such cases, no capital repayment occurs (that is, the capital repayment amount is zero).

###### Date Determination Options for Interest Flows and Repayment Flows

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for ABS/MBS With Single Interest Conditions > Date Determination Options for Interest Flows and Repayment Flows | L7 | trm04 p.223 | loio `9f0a4c52f720f67fe10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9f0a4c52f720f67fe10000000a441470.html?locale=en-US)

**Use**

To simplify entering interest flows and repayment flows, you have the option of copying the dates from the interest condition and applying them for the repayment flows (using the Int.Cond.Template indicator). For each interest flow, the system creates a corresponding repayment flow with the following dates:

Effective date of the repayment = (changed) calculation date of the interest flow

The effective date of the repayment flow is the start date of the next month in which the interest calculation date falls on the month-end date (since repayments are published on the first day of the month).

Payment date of the repayment = due date of the interest flow

**Note:**

The position date of a repayment corresponds to the effective date of the repayment flow; this ensures that the nominal value of the position is reduced on the effective date of the repayment. The same needs to apply for the interest flow (that is, the position date for the interest flow needs to match the calculation date). As described above, the effective date of the repayment flow is not identical to the calculation date of the interest flow. Consequently, both flows have different position dates when the interest condition is used as the basis.

Example

The payment date of both the interest flow and the repayment flow is 02/05/XXXX.

The interest flow has as its calculation date 01/31/XXXX (= last day of the month), but the corresponding repayment factor has as its effective date 02/01/XXXX (since repayment factors are valid from the start of the month).

This means that both flows have a different position date and have not been adjusted to match completely.

For this reason, the system adjusts the position date of the interest flow so that it matches the position date of the repayment flow provided that the following applies: 1) The Use Calculation Date as Position Date indicator has been set for the repayment flow as well as for the interest flow in the Customizing activity Specify Update Types for Securities Account Management, and 2) You have activated the CPR/PSA method for the product type in the activity Activate Special Condition for ABS/MBS.

In the above example, the position date of the interest flow is also 02/01/XXXX.

In addition, in the Customizing settings for the tranche, you can set the Force First Redemption on First Redemption Date indicator. This indicator affects the position date of a repayment when the interest condition is used as the template. For this reason, it is possible that the first repayment is not made on the start date (or on the first repayment date when the start date is left empty), for example, when the calculation date of the interest condition falls after the start date (or after the first payment date). This indicator can be used to close any gaps between the first repayment date and the effective date of the first repayment:

If the calculation date of the first interest flow falls after the start date (or after the first repayment date) but the valid-from date (the start of the calculation) of the first interest condition falls on or before the start date (or on or before the first repayment date), an additional repayment is generated for the valid-from date of the first interest condition. Consequently, the redemption schedule starts on the start date defined.

**Example:**

Start date (in the general redemption schedule data): 01.01.2013

Interest condition:

Valid from: 01.01.2013

Calculation date: 01/31/2013 => First interest flow has as its calculation date 01/31/2013.

The indicator is not set:

First repayment has the effective date 02/01/2013 = calculation date of the interest flow (due to the month-end closing adjustment)

The indicator is set:

The first repayment has as its a valid-from date 01/01/2013 = Valid-from date of the interest condition (in addition to the repayment on 02/01/2013).

If you do not want to use the interest condition as a template, you have to make the settings for the repayment condition (such as the payment frequency) separately.

In addition, you can set the indicator in the Customizing settings for the tranche. This indicator affects how the due date/payment date is determined for a repayment:

In general, the system first uses the working day shift and then the calendar day shift. If you set this indicator, the calendar shift is applied before the working day shift.

**Example:**

Working day shift: Shift to Next Workday

Calendar days: + 10 days

Effective date of the repayment: 14.03.2013

Default logic (the indicator is not set):

- 1. Working day shift: 03/14/2013 is a Thursday, no working day shift
- 2. Calendar day shift: 03/14/2013 + 10 days = 03/24/2013


=> payment data is 03/24/2013

The Delayed Working Day Shift setting (the indicator is set)

- 1. Calendar day shift: 03/14/2013 + 10 days = 03/24/2013
- 2. Working day shift: 03/24/2013 is a Sunday; the payment date is postponed until Monday 03/25/2013.


=> payment data is 03/25/13

**Prerequisites**

If you want to use the interest condition as a template for the repayment flows, you need to activate the special conditions for ABS/MBS for the product type in Customizing.

**More Information**

ABS/MBS: Customizing

###### ABS/MBS: Retrospective Changes to Repayments

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for ABS/MBS With Single Interest Conditions > ABS/MBS: Retrospective Changes to Repayments | L7 | trm04 p.225 | loio `b2134b52dd6f6a67e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b2134b52dd6f6a67e10000000a441470.html?locale=en-US)

**Use**

When the issuer of an ABS/MBS position publishes a respective change to a factor for repayments that have already been posted, you can reflect this change in the system.

**Prerequisites**

In the Customizing activity Define Tranche, you need to allow retrospective changes to repayments. You also need to create the required update types and make the necessary settings. See also: ABS/MBS: Customizing

**Activities**

- 1. Create a new redemption schedule.
- 2. Select the completed repayment that you would now like to change and choose the pushbutton in that row.

The system issues a message telling you that the factor has already been fixed.

To make the retrospective change, choose Adjust.

- 3. Enter the changed values for the repayment.
- 4. Save your entries.
- 5. The system then creates the following adjustment flows for the nominal amount:


A flow that writes off the previous nominal amount

A flow that posts the new nominal amount (resulting from the changed redemption schedule).

For changed interest payments, only one adjustment flow is created. However, this flow does not change the book value because it is not connected to any payment. In the next interest payment, the issuer takes into account the effect of the change on interest amounts. With the next amortization/valuation, the book value is adjusted on the basis of the new redemption schedule.

Redemption Schedule Set

**Definition**

A redemption schedule set (RS set) contains a group of redemption schedules for a particular class. In conjunction with the ID number, the redemption schedule set identifies a specific set of redemption schedules.

**Note:**

Only relevant for ABS/MBS with single interest conditions.

**Structure**

Repayment schedule sets are uniquely identified by their key and the ID number of the class.

They consist of header data and the assigned redemption schedules.

Key header data of a redemption schedule set:

Date of first redemption

Date of last redemption

Redemption frequency

**Integration**

You assign the redemption schedule sets to the individual bonds in the class data on the Conditions tab. You enter the header data when you create the first redemption schedule for a particular class.

You can assign various redemption schedule sets to a class. If you assign only one RS set to a class, this automatically becomes the active RS set. If more than one redemption schedule set exists, you can choose which of them is to be the active set.

The cash flow for the class shows the planned records for the redemption flows. These are taken from the data for the active redemption schedule in the active redemption schedule set.

Once you have created the header data for a redemption schedule set, you can enter one or more redemption schedules.

###### Redemption Schedule (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Conditions > Conditions for ABS/MBS With Single Interest Conditions > Redemption Schedule | L7 | trm04 p.226 | loio `8c49ae56e6174a698da8ec31e17720ec` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8c49ae56e6174a698da8ec31e17720ec.html?locale=en-US)

**Definition**

A redemption schedule contains the dates and amounts of the planned or expected redemptions for a bond.

**Note:**

For the redemption schedules of ABS/MBS with parallel interest conditons, see also Conditions for ABS/MBS With Parallel Interest Conditions.

**Structure**

Redemption schedules are uniquely identified by:

The ID of the class

The name of the redemption schedule

A redemption schedule consists of:

Dates

Effective from date of the redemption schedule

Date of the first redemption in the schedule (this can be selected from a list proposed on the basis of the data from the related redemption schedule set).

These dates and the details for the redemption schedule set are used to determine the redemption dates and the corresponding publication data for the redemption schedule.

Redemption schedule

Adds the redemption amounts for the respective dates

Quantities

Number of redemption payments

Total redemption amount

**Integration**

You can assign different redemption schedules to a single redemption schedule set. The redemption schedules must have different short names and different Effective from dates.

The active redemption schedule is the schedule that has the most recent Effective from date within a redemption schedule set. The system sets the Active redemption schedule indicator on the basis of the current system date and the Effective from dates of the redemption schedules.

The cash flow for the class shows the planned records for the redemption flows. These are taken from the data for the active redemption schedule in the active redemption schedule set.

Example

Current date: 02/25

The following redemption schedules for redemption schedule set 'Data Provider' were assigned to class A:

- Redemption schedule 1, effective from 01/01

- Redemption schedule 2, effective from 02/20

- Redemption schedule 3, effective from 06/30


This means that redemption schedule 2is the active redemption schedule.

###### Exchanges

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Exchanges | L5 | trm04 p.227 | loio `e016da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e016da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Here, you assign for each class the exchanges at which you want to trade that class.

You have to make this setting so that you can enter prices for this class later on.

See also: Editing Security Prices Manually

**Prerequisites**

You need to have created exchanges in Customizing for the Transaction Manager under Securities Basic Settings Define Exchange .

**Procedure**

- 1. In the Create or Change mode for the class data, go to the Exchanges tab.
- 2. Choose Insert Row. Assign one of the exchanges available in the input help.
- 3. You can enter the following data for the security price at an exchange:

Currency (if it’s a unit-quoted security)

Select the Flat Price indicator if the accrued interest is already included in the price.

Select the Home Exchange indicator to specify that an exchange is the home exchange.

Listing Key (used to specify that a security can be traded officially at an exchange)

You define the listing keys in the Customizing activity Maintain Stock Market Tiers. If no listing key has been defined, you can branch to the Customizing activity from the input help for that field and maintain the listing key there.

You can enter a percentage price deviation or alternatively an absolute price deviation. If you use the manual price maintenance function to enter a price, a warning message appears if you enter a price deviation that is greater than the last one entered.

- 4. Save your entries.

###### User Data

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > User Data | L5 | trm04 p.228 | loio `5e18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5e18da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The user data tells you when the class was entered, who entered it, and when class data was changed and by whom.

**Structure**

Entry Data

|Created By|User name of the person who entered the class|
|---|---|
|Date|Date when the class was first entered|
|Time|Time when the class was first entered|
|Source|Contains the screen or program ID that was used when the information was entered for the first time.|


Change Data

|Last Changed By|User name of the person who last changed the class|
|---|---|
|Date|Date when the last change was made|
|Time|Time when the last change was made|
|Source|Contains the ID of the transaction or program that was used to change the table entry|


Display Change Documents

When you choose this pushbutton, you branch to the change documents display for the class data.

The change documents tell you which changes were made to the class.

###### Regulatory Reporting (Germany Only)

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Regulatory Reporting (Germany Only) | L5 | trm04 p.229 | loio `ead1c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ead1c753b1081d4be10000000a174cb4.html?locale=en-US)

(Please note that these functions are primarily designed to meet German reporting requirements and may not be relevant to your country/region.)

**Definition**

The regulatory reporting data is special information for a class. These details supplement the class data for regulatory reporting at higher levels.

**Structure**

You can set up all the fields in the Regulatory Reporting area in the field selection control settings. You can enter the following data:

For stocks (product category 010) and bonds (product category 040):

The custody type of a security

A key for your securities account statistics

An indicator for the tax treatment of the security

An indicator for reporting obligations under the German Securities Trading Law (STL)

For bonds (product category 040), you can also enter:

Whether the bond is funded

Whether it is a secondary loan

For convertible bonds and warrant bonds (product categories 070 and 060), you can only enter the tax treatment and the secondary loans data.

For stocks, there is an additional section for stock capital and voting rights. The entries you make here are needed to run the Report on Voting Rights and Common Stockholder Equity Shares.

You enter the following information relating to a stock:

Number of stocks issued

Nominal value of the stocks (this can also be entered on the Basic Data tab page)

Voting rights per stock

Additional capital amount (where relevant, cannot be controlled by field selection)

You can use an aggregation key to group different classes that you want to value together. This may be necessary if a company has issued both common stock and preference stock, for example. (You cannot use field selection to control this field.)

The system automatically enters the business partner number of the issuer in the Aggregation key field.

This field is a required field.

If you do not want to evaluate all the stocks from the same issuer together, enter a different aggregation key manually. Because the aggregation key is a required field, you cannot just delete it. You have to overwrite it with another value. When you assign the aggregation keys, make sure that you do not assign the same key twice.

**Note:**

SAP recommends that you accept the business partner number of the issuer as the aggregation key, since this number uniquely identifies the issuer. You should only use a different aggregation key in exceptional cases.

You must enter the details for stock capital and voting rights manually and keep them up-to-date. They are linked to an Effective from date. If you perform a corporate action (such as a stock split), you may need to change the data manually. You can do this by adding a new line with a new Effective from date containing the changed data.

**Note:**

When you make your entries, not that the limit fields contain default proposals in percent.

###### SPPI

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > SPPI | L5 | trm04 p.230 | loio `d5435347e4c2424f973bd4dd779edda9` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d5435347e4c2424f973bd4dd779edda9.html?locale=en-US)

SPPI classification is only available for interest-bearing financial instruments such as bonds.

The SPPI (solely payments of principal and interest) is relevant for IFRS 9. The field expresses whether the financial transaction passed an externally executed SPPI test or not.

- 1. Choose the Valid-From Date.
- 2. Enter the Passed or Failed value in the SPPI Criterion field.

###### Class: Reference

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Class: Reference | L5 | trm04 p.230 | loio `0d1ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0d1ada531198434de10000000a174cb4.html?locale=en-US)

Use

Choose References in the class data with which to display the classes from which a relationship was created for the relevant security.

The table displays the ID number and the short name of the underlying security and the reference category that was used.

You can display the following reference categories:

Equity warrant

Bond warrant

Subscription right

Convertible bond

Warrant bond

Stock swap

###### Entering Data for Giving Notice

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Entering Data for Giving Notice | L5 | trm04 p.231 | loio `b018da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b018da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Some bonds include call rights for the issuer and/or for the bondholder.

You enter the call rights agreed in the terms of the issue on the Notice tab page in the class data.

You represent the exercise of these call rights within the agreed notice periods in the system using the Exercise Rights function.

**Procedure**

The screen for entering notice data is divided into two parts:

A table for entering the notice periods of the issuer

A table for entering the notice periods of the bondholder

The procedure for entering the notice periods is the same for both the issuer and the bondholder:

- 1. Choose .
- 2. Enter the notice period from/to.
- 3. Enter the Notice rate . This is the rate (or price, for unit-quoted securities) at which you repay the bond when you give notice.
- 4. Enter a description for the notice.
- 5. Save your entries.


**Note:**

You can enter any number of notice periods for a class.

**Result**

When you save the notice data in the class data, the system generates the relevant rights in the Exercise Rights function, regardless of whether a position already exists for this class.

There, you find the call rights of the issuer under Callable bond. You find the call rights of the bondholder under Puttable bond.

###### Entering Stock Swap Data

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Entering Stock Swap Data | L5 | trm04 p.232 | loio `1b18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1b18da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Some stocks vest the right to swap a stock for another stock within a certain period for a fixed swap ratio.

See also:

Stock Swap

**Prerequisites**

You must have created the class for the stock you want to receive from the swap.

**Procedure**

- 1. Choose ( Insert line ).
- 2. In the New ID number field, enter the ID number of the class to which you can swap the stock.
- 3. Swap numerator: Here, you enter the number of old stocks that you need to receive the number of new stocks entered in the Swap ratio - denominator field.
- 4. Swap ratio - denominator : This field tells you how many new stocks you will receive for a number of old stocks (stored in the numerator).
- 5. Clearing amount/currency : The clearing amount is the additional amount that must be paid for each new stock.
- 6. Effective from / Effective to : Here, you enter the swap period.
- 7. Description: Here, you define an appropriate name for the stock swap.
- 8. To navigate within the table:


Use the small arrows to display the following columns.


- 9. Choose to delete a selected line again.
- 10. Choose to save your entries.



**Result**

As soon as you have created the data for the stock swap in the class data, this right appears amongst the executable rights for the rights category Stock swap in the Exercise Rights function, and you can exercise it within the swap period.

###### Participation Certificates

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Classes > Participation Certificates | L5 | trm04 p.232 | loio `1717da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1717da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Since the composition of participation certificates can vary considerably, they do not have a specific product category. You define a product type that suits the type of participation certificate you want to represent. You can choose from the following specific product category structures:

|Product Category|Name|Unit-Quoted|Percentage-Quoted|Conditions|Reference|
|---|---|---|---|---|---|
|010|Stock|X| |X|X|
|020|Investment Certificate|X| |X| |
|030|Subscription Right|X| | |X|
|040|Bond|X|X|X|X|
|060|Warrant Bond|X|X|X|X|
|070|Convertible Bond|X|X|X|X|
|111|Index Warrant|X| | | |
|112|Equity Warrant|X| | |X|
|113|Currency Warrant|X| | | |
|114|Bond Warrant|X| | |X|
|160|Shareholding|X|X|X|X|


Notation:X= Function is supported

It is conceivable that you define two different product types for participation certificates. You may define one with product category 010 (Stock), and another with product category 040 (Bond).

**Procedure**

- 1. Create one or more product types for the participation certificates in Customizing for the securities area.
- 2. Create a class.


See also:

Manage Securities Classes

For more information about defining product types, see the Customizing activity Define Product Types in the securities area.

##### Manage Securities Accounts

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Securities Accounts | L4 | trm04 p.233 | loio `8a18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8a18da531198434de10000000a174cb4.html?locale=en-US)

App ID: TRS_SEC_ACC

With this app, you can define, change, display, and delete securities accounts. If you want to purchase or sell a security or issue a bond, you must have a securities account. The securities account usually corresponds to actual securities accounts at a bank.

In the predefined content, the securities account acts as a differentiation term for securities positions. For more information, see Differentiation Terms.

**Prerequisites**

Before you can create a securities account, you first have to create the depository bank as a business partner in the role of depository bank.

If you use the security account groups as differentiation criterion for your security positions (you make the required setting

in the Customizing of the Transaction Manager under Define and Assign Differentiations) you need to define the security account groups in Customizing. In this case the Security Account Group field is a mandatory field in the security account master data.

If you want to run reporting across several securities accounts, you could assign a portfolio to the security account. Therefore the Portfolio field has to be made available in the field selection for the security accounts Customizing and portfolios also need to be defined.

**Note:**

If you have chosen the portfolio as differentiation criterion for your security positions, the assignment to the portfolios is done in the financial transaction data on the Administration tab of the purchase transaction of the security. If you have assigned portfolios to security accounts these settings can act as proposal during the creation of a purchase transaction but this proposal can be changed.

**Procedure**

- 1. Open the Manage Securities Accounts app under the Securities Account Management group the SAP Fiori launchpad or in backend choose Securities Master Data Securities Account Edit in the area menu of the Transaction Manager.
- 2. Choose a securities account. You choose the securities account in the tree structure on the left-hand side of the screen. Enter the company code and the data for the securities account on the right-hand side.
- 3. Use the pushbuttons to choose one of the functions and follow the appropriate instructions:


|Function|Entries|Remarks|
|---|---|---|
|Create|Securities account ID|Securities account ID = detailed|
| |Choose the Security Account Type:|description of the securities account.|
| |SAC Asset Securities|Bank information|
| |Account (with securities|Here you enter the depository|
| |account category Asset|bank, the securities account|
| |Securities Account)|number, the bank clearing|
| |In securities accounts of this type, all positions can be managed except for|account number in the depository bank, and the bank clearing account in FI.|
| |issue positions or| |
| |positions belonging to| |
| |securities lending| |
| |transactions.| |
| |SLC Issuance Securities| |
| |Account (with securities| |
| |account category| |
| |Liability Securities| |
| |Account)| |
| |Only positions for| |
| |securities issues can be| |
| |in issuance securities| |


accounts. The system makes sure that issue positions cannot be transferred to asset securities accounts or lending securities accounts. It also ensures that asset positions or positions that belong to securities lending transactions are not transferred to an issuance securities account.

**Note:**

A security account always belongs to a securities account category. By default, a new securities account gets the securities account category Asset Securities Account. You can change the securities account category by choosing a securities account type that refers to another securities account category.

Enter the following data:

Bank Data tab

Bank information

Depository bank

Securities Account Number

Enter payment instructions for the different currencies

The house bank account is used by functions that make payments via the securities account, as is the case for dividend payments. You can define an alternative house bank account for payments in a specific currency. FI account determination uses this account as a parameter.

Make one entry with an empty currency field. This account is then used for all the currencies that have not been specifically defined.

Other tab

Beneficiary

| |Disposition Block Lock type and Lock flag until You can block the securities account with a lock flag. Assignments a. Business area b. Securities account group Securities account group The Securities Account Group is only shown if you have defined the securities account group as a differentiation term for a valuation area. You can define securities account groups in the Define Securities Account Groups configuration activity. c. Portfolio User Data tab Other functions Save securities account data.| |
|---|---|---|
|Change|a. Company code b. Securities account ID c. Enter |You can overwrite everything in the change mode, except for the company code, securities account ID, and lock flag.|
|Display|a. Company code b. Securities account ID c. Enter |The system displays the data for the securities account.|

##### Futures Account

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Futures Account | L4 | trm04 p.237 | loio `4c6a986de73b71d0e10000000a15822b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c6a986de73b71d0e10000000a15822b.html?locale=en-US)

**Definition**

A futures account is a management unit that allows you to manage your positions. You need this type of account for listed options and futures, since these require position management.

The futures accounts created in the system usually correspond to actual futures accounts.

**Use**

If you want to buy a listed option or a future, you need to have created them in the system as a class (transaction FWZZ), as well as having created a futures account (transaction TPM4).

For more information, see also Manage Securities Classes.

**Note:**

Before you can set up a futures account, you need to create the bank at which you keep your futures account as a business partner in the role of Depository Bank.

When you enter the purchase in the system, you select the class and the futures account.

Two report programs are available in the back office area for listed derivatives: Futures Account Cash Flow and Position in Futures Account. For more information about margin calculation, see the Master Data area by choosing Class Position in Futures Account.

**Structure**

A futures account is identified by the company code and the futures account ID for which you can also enter a name.

The master data of a futures account is stored on the following tabs:

Bank Data

Here, you specify at which depository bank, with which external clearing account, and on which broker account the positions for the futures account are managed. You also specify the relevant house bank details and the business area. If you have portfolios, you assign the futures account to the portfolios on this tab.

Additional Data

You make the entries in all fields on this tab, thereby allowing you to enter additional information about the futures accounts. There are a total of 12 fields of differing length. You define the field pairs for the short, medium, and long attributes in the application menu under Derivatives Master Data Listed Derivatives Settings for Additional Data

Tab in Futures Account Master Data , and you define the other two fields in Customizing for the Transaction Manager under Listed Derivatives Master Data Futures Account Management Settings for Additional Data Tab Page . For the fields, you enter the names that are to appear beside the fields on the tab, and you also enter the values that can be selected for each field using input help.

User Data

**Integration**

For more information, see the relevant section in the Implementation Guide under Listed Derivatives Position Management Futures Account Management .

###### Class Position in Futures Account

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Futures Account > Class Position in Futures Account | L5 | trm04 p.238 | loio `5a15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5a15da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

To manage classes in a futures account, you have to define the class position in the futures account.

**Prerequisites**

To manage a position with margin calculation, you have to select Future style as the settlement category when you define product types in Customizing for futures. If you select Normal style the position is managed without margin calculation.

Here, you also have to define the exchange and the price type. In the case of a variation margin run, the settlement price is calculated using these entries.

**Activities**

- 1. Choose Master Data ListedDerivatives Class Position in Futures Account . Enter the company code, the ID number and the futures account.
- 2. For all open and close transactions the same Account Assignment Reference is used for a class position in a futures account.
- 3. When you enter the transaction, you can also choose Environment Position Indicator to go to the class position in the futures account.

###### Futures Account Cash Flow

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Futures Account > Futures Account Cash Flow | L5 | trm04 p.239 | loio `e614da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e614da531198434de10000000a174cb4.html?locale=en-US)

**Use**

This report program provides you with an overview of the single positions you request.

In the case of a position with margin calculation, you create a single position for each open transaction, whereas the long and short single positions are created automatically for positions without margin calculation.

**Activities**

Choose Listed Derivatives and enter the company code, the futures account and the ID number. An overview of the single positions appears. You can display the cash flow either by double-clicking the relevant line or choosing the Cash Flow pushbutton. You can use the Business transaction pushbutton or double-click the relevant line to branch to the transaction processing screen.

###### Position in Futures Account

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Futures Account > Position in Futures Account | L5 | trm04 p.239 | loio `ef14da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ef14da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You run this report program to obtain an overview of all the positions in your futures account.

**Activities**

Enter your selection criteria in the General selections area. The system displays an overview of your positions ( class positions in futures account ) . The long and short positions are displayed separately in the list (number of units, book value of forward transaction and position currency) because of their different legal positions.

By double-clicking the relevant line or by clicking the Display single positions pushbutton, the screen for displaying the single positions appears (= Futures Account Cash Position ).

##### Edit Exchanges

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Edit Exchanges | L4 | trm04 p.239 | loio `a817da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a817da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to define an exchange for each company code and class.

**Integration**

The exchange is used to determine the market value in the valuation ( Security Valuation ) and the Position List .

**Note:**

If the exchange has not been assigned, the system reads the most recent exchange rate from the exchange rate table to determine the market value. If the table contains two or more current rates the same, the rate is taken from the table at random.

Prerequisites

The exchanges need to be assigned to a class in the class data on the Exchanges tab page.

**Activities**

- 1. Call the function by choosing Transaction Manager Securities Master Data Position Indicator Maintain Exchange for Each Company Code and ID Number .
- 2. Choose New Entries.
- 3. Enter the Company code and the ID number . Assign the exchange using the input help.
- 4. Save your entries.

##### Manage Position Indicator

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Manage Position Indicator | L4 | trm04 p.240 | loio `ded93cb7a138414987c53931223972f8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ded93cb7a138414987c53931223972f8.html?locale=en-US)

App ID: TPM57A

With this app, you can display and change the position indicator of a position.

The position indicator of a subledger position contains the Position Management Procedure and the Account Assignment Reference, along with the balance sheet indicator.

In the securities account position indicator you specify information, such as the custody type, at the level of the company code, security ID number, and securities account.

**Activities**

- 1. Open the Manage Position Indicator app on SAP Fiori launchpad.
- 2. Select the relevant product group: Securities or OTC Transactions
- 3. Enter the General Selections:


Company Code

General Valuation Class

If you use the following fields as differentiation terms for your position, you can select positions by these fields:

WBS Element

Cost Center

Profit Center

Functional Area

If you have defined your own differentiation terms (in the Define Custom Differentiation Terms configuration activity) and you use the fields as differentiation terms for your treasury positions, these fields are also available as selection criteria.

The following fields are available if Public Sector Management is used. When flows are posted to Financial Accounting, the values of the account assignments are also transferred to the journal entry:

Fund

Grant

- 4. For the product group Securities, you can enter the ID Number, Securities Account, and the Portfolio.

For the product group OTC Transactions, you can enter the Transaction Number.

For the product group Loans, you can enter the loan contract.

For the product group Listed Derivatives, you can enter the ID Number, Futures Account and the Long/Short indicator.

For the product group External Accounts, you can enter the External Account and the Position Currency.

- 5. Choose the function you want to execute, using one of the following the paths


Position Indicator Create


Position Indicator Change


Position Indicator Display


Position Indicator Delete

- 6. Choose Enter.
- 7. On the next screen, the values of the subledger position indicators of the corresponding positions of the selected financial transaction in the different valuation areas are displayed in a list.

Additionally, for securities, the values of the position indicator of the corresponding securities account are displayed in a list.

- 8. You can display the details of the relevant position management procedure of a position indicator. To do so, mark the position indicator and choose Position Management Procedure.


**Note:**

As long as there are no posted flows for a position, you can change the assignment of the position management procedure and account assignment reference in the position indicator using the app Manage Position Indicator. However, as soon as there is a posted flow, it is no longer possible to change the position management procedure or the account assignment reference there.

To change the position management procedure in that case, you must execute a valuation class transfer.

To change the account assignment reference, you must execute an account assignment reference transfer.

**Note:**

When you have only one valuation area, only one position indicator is displayed in the list.

Additional Features

Display the user data

Select the relevant position indicator from the list and choose   User Datato get detailed information about the user.

Display the cash flow

Select the relevant position indicator from the list and choose  Cash Flow. A list of corresponding position flows is displayed.

Display the financial object

Select the relevant position indicator from the list and choose   Financial Objectto get detailed information on the corresponding financial object.

Display the securities account

Select the relevant position indicator from the list and choose Securities Account to get detailed information on the corresponding securities account.

**Supported Device Types**

Desktop

Tablet

**Related Information**

Position Management Procedure Account Assignment References

##### Assign Position Management Procedure

> **Path:** Treasury and Risk Management > Transaction Manager > Terms in Financial Transaction Management > Assign Position Management Procedure | L4 | trm04 p.242 | loio `d50dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d50dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to see which position management procedures are assigned to the existing positions.

If the flows for a position have all been reversed, you can also use this function to change the assigned position management procedure.

**Features**

Selection

General Selections

Output

The system lists all the positions that correspond to the selection criteria, and displays the position management procedure assigned to each position. The Position management procedure field is ready for input all the flows relating to a position have been reversed.

You define how the position management procedures are assigned in Customizing by choosing Transaction Manager General Settings Accounting Parallel Valuation Areas Settings for Position Management Assign Position Management Procedure

. The assignment is based on the factors accounting code, valuation area, valuation class, product category, product type, transaction type, portfolio and securities account group.


In the application function Edit Position Management Procedure , you can select a position according to the following criteria: Accounting code, valuation area, valuation class, transaction type, portfolio, securities account group, securities account, futures account, ID number, contract number, transaction, trader. This function enables you to make finer distinctions when assigning the position management procedure, since additional criteria are available (= securities account, futures account, ID number, transaction, trader ).

**Caution:**

You should only use this function to change the position management procedure assignment in exceptional circumstances.

**Activities**

In the application menus of the Money Market , Foreign Exchange , Securities , Derivatives and Loans areas, choose the following path: Master Data Position Indicator Account Assign Position Management Procedure.

