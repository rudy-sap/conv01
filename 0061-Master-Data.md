# Master Data - SAP TRM Knowledge Base (branch split)

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

#### Define Traders

> **Path:** Treasury and Risk Management > Master Data > Define Traders | L3 | trm01 p.117 | loio `09bc501a83ef466b9df1adb8e5275431` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/09bc501a83ef466b9df1adb8e5275431.html?locale=en-US)

App ID: S_ALR_87009302

With this app, you can define traders for each company code.

After you have defined traders you can use Define User Data app to assign the traders to users, such as users in role Treasury Specialist - Front Office. Using the Manage Trader Authorizations app, you can restrict the transactions a trader may conclude to the individual values of:

Contract types

Product categories

Product types

Transaction types

**Supported Device Types**

Desktop

Tablet

**Related Information**

Manage Trader Authorizations

#### Manage Trader Authorizations

> **Path:** Treasury and Risk Management > Master Data > Manage Trader Authorizations | L3 | trm01 p.117 | loio `0b0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0b0eda531198434de10000000a174cb4.html?locale=en-US)

App ID: TBT1

With this app, you can restrict the financial transactions a trader may conclude to the individual values of the following fields:

Contract types

Product categories

Product types

Transaction types

**Note:**

The authorization at a higher level automatically includes the levels below it.

**Prerequisites**

You have defined the traders in the Define Traders app.

Supported Device Types

Desktop

Tablet

#### Business Partner

> **Path:** Treasury and Risk Management > Master Data > Business Partner | L3 | trm01 p.118 | loio `031ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/031ada531198434de10000000a174cb4.html?locale=en-US)

**Definition**

A business partner is

Natural person (private individual)

Organization (legal entity, or part of a legal entity)

Group (for example: married couple, shared living arrangement)

with whom a business interest exists.

**Use**

The Transaction Manager is based on the business partner concept. Financial transactions are concluded with business partners within the Transaction Manager. Typical business partners include banks or central treasury departments.

You have to assign roles to your business partners, which correspond to the partner’s function in the financial transaction. The main roles are “Issuer” (TR0150), “Counterparty” (TR0151), “Depository Bank” (TR0152), “Beneficiary” (TR0154), and “Guarantor” (TR0200).

**Example:**

Examples:

If the issuer of a security does not exist as a business partner in the role of “Issuer” (TR0150), you cannot create the security as a class.

To conclude a financial transaction with a business partner, this business partner must exist in the role of “Counterparty” (TR0151).

To create class master data for securities, the depository bank must exist as a business partner in the role of “Depository Bank” (TR0152).

In the class master data, you can assign a business partner to the securities account as a “Beneficiary” (TR0154).

The guarantor for a commercial paper must exist as a partner in the role of “Guarantor” (TR0200).

**Structure**

You define the business partner functions in the transaction using business partner roles, such as counterparty, issuer, payment bank, or depository bank. A business partner may have several roles.

You can define standing instructions for a business partner.

If you always use the same bank details and payment details with a business partner for certain product types, this data can be entered automatically.

Using transaction authorizations, you can set up your system so that you can only conclude transactions of a certain product type with your business partner.

You can define which derived flows you want the system to generate for each business partner.

Relationships can exist between different business partners. You can enter these on the Relationships tab.

**Integration**

See also:

Standing Instructions

Transaction Authorization

Payment Details

Derived Flows

##### Rating

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Rating | L4 | trm01 p.119 | loio `cc224e4abc3846bca916739f8ea91cdf` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cc224e4abc3846bca916739f8ea91cdf.html?locale=en-US)

Enter rating information for the business partner.

**Use**

You can rate business partners by different means, such as their credit standing and payment history, or according to other criteria. Ratings can be performed according to your own rules, as well as through specialist service providers, such asStandard & PoorsorSchufa. Several rating procedures have already been delivered.

The rating of a counterparty can change during the lifetime of your business connection. You can store the rating information timedependent for your counterparties.

- 1. Choose the Rating Procedure.

Indicates the rating procedure used to rate the business partner.

- 2. Choose the Rating.

Indicates the result of a rating for the business partner carried out with a rating procedure.

- 3. Choose the Trend for the rating.

Indicates the trend of an existing rating so that expected changes to the business partner can be displayed.

- 4. Enter the validity for the rating using the Valid From and Valid To fields.
- 5. Save your entries.


**Note:**

You can enter the ratings of different rating procedures.

Configuration

Your configuration expert can make the needed entries in the Set Rating Procedures and Ratings configuration step available under Manage Your Solution Configure Your Solution Finance Treasury and Risk Management General Settings .

Several rating procedures have already been delivered. You can define others according to your requirements. You can also set one of the rating procedures as the standard rating procedure flag this rating procedure as internal.

##### Creditworthiness Data

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Creditworthiness Data | L4 | trm01 p.120 | loio `99d318dbb72d4f0c997dd029c9aa03fd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/99d318dbb72d4f0c997dd029c9aa03fd.html?locale=en-US)

On the Creditworthiness Data tab, you can store information on the credit standing of your business partner. The data is entered time-independent.

**Note:**

If you want to store a number of time-dependent ratings for a business partner, use business partner ratings on the Rating tab.

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


**Note:**

If you want to store ratings of different credit standing institutes, you can use the Rating tab.

##### Company-Code-Dependent Data in Business Partner

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Company-Code-Dependent Data in Business Partner | L4 | trm01 p.120 | loio `7df9c5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7df9c5536a51204be10000000a174cb4.html?locale=en-US)

**Definition**

Data in the business partner that can be stored for a company code.

**Use**

Company-code-dependent data is stored in business partner maintenance under Company Code on a number of tabs. You can process company-code-dependent data as soon as you have defined under Company Code the company code to be used.

Within business partner maintenance you can create, adopt, and - as long as you have not yet saved them - delete several company codes. To do this, choose the Company Codes detail view. In the detail view, you can also configure for which master data (business partner, customer, supplier) the company code is created.

Under Switch Company Code, you can switch to other company codes during processing.

Which company-code-dependent data is processed depends on which business partner role is used and which business processes are required.

**Structure**

You can process the following data for a company code, for example:

Standing instructions for the business partner regarding

Payment details

Transaction authorization

Derived flow

Regulatory reporting data and liability risks in the company code

Posting locks on company codes (on the Status tab)

Data for a linked customer/supplier master record that is relevant for customer/supplier integration.

###### Standing Instructions

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Company-Code-Dependent Data in Business Partner > Standing Instructions | L5 | trm01 p.121 | loio `66efa4e2cefc4ae7a1e059cf53194369` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/66efa4e2cefc4ae7a1e059cf53194369.html?locale=en-US)

**Definition**

This is a collection of data relating to a business partner that is used on a recurring basis. This data is transferred automatically to the financial transactions.

**Use**

Standing instructions are used as general agreements made with a business partner for processing similar types of transactions.

They are used as default values when creating financial transactions.

The standing instructions form part of business partner data. They can be accessed from business partner maintenance via the Company Code.


The standing instructions are not used in Bank Customer Accounts (BCA) and SAP In-House Cash (FIN-FSCM-ICH). In Loans Management (FS-CML) they apply only for payment details.

**Structure**

The standing instructions comprise the following functions:

Transaction authorizations

Payment details of the business partner for incoming and outgoing payments

Derived flows

**Example**

Payments to a business partner are normally made using the same bank details each time.

###### Payment Details (1 of 4)

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Company-Code-Dependent Data in Business Partner > Standing Instructions > Payment Details | L6 | trm01 p.122 | loio `7cad7ed0974d4b80ad4765e766867e1e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7cad7ed0974d4b80ad4765e766867e1e.html?locale=en-US)

**Use**

Payment details are identified by the:

Business partner

Company code

Currency in which payment is made

You can see how the bank details are assigned by choosing Partner Bank Details where the bank details that are valid for a business partner are defined.

The partner bank details control which of the business partner's banks is used. You can enter several sets of bank details for one business partner.

When you define payment details you can enter the Payment Type (customer accounts and/or G/L account posting) and the payment method.

You can also define the Payment Method Supplement, which is a characteristic for grouping payments.

In addition, you can enter the House Bank ID and Account ID for the account at the relevant house bank. You use the house bank ID to define your own bank details, which are generally to be used for payments to and from your business partner. The system checks the currency of the house bank account against the currency entered for the payment details.

See also:

Creating Standing Instructions for Payment Details

Repetitive Code

###### Creating Standing Instructions for Payment Details

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Company-Code-Dependent Data in Business Partner > Standing Instructions > Payment Details > Creating Standing Instructions for Payment Details | L7 | trm01 p.122 | loio `a8ec29198137469db73dc1c87c8ed47d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a8ec29198137469db73dc1c87c8ed47d.html?locale=en-US)

**Procedure**

On the SAP Easy Access screen, choose Treasury and Risk Management Business Partner Special Functions Standing Instructions Payment Details .

Enter the business partner and the company code.

You are on the SI: Payment Details tab page in the company code-dependent data for the business partner.

You can define several payment details for each currency for a business partner. The system uniquely identifies valid payment details using a payment details ID that you can assign yourself together with a currency.

The fields House Bank and Account ID define the bank data of your own house bank.

By setting the Payment Transaction and Payment Request indicators, you can determine whether a payment involves a payment transaction (active initiation of a payment with a payment program) and the way in which the payment is to be posted. The choice of payment program determines the posting logic.

The system transfers the payment methods to be used to the payment program using the fields Payment Method and Payment Method Supplement.

If payment involves a payment transaction, then you must enter an alternative payer/payee, so that corresponding payments can be generated with the help of the payment program.

You must specify partner bank details if you want to choose a particular payer/payee bank account. Otherwise, the bank details are taken from the business partner data. You can also enter the payment details for payers/payees other than the business partner.

For payments with payment requests, it is also possible to decide whether, and how, payments can be combined (netting).

You will find which entry fields are required, optional, or obsolete in the input help for the payment details.

Open the Payment Details Assignment screen using with the quick info text Assign. Here, you determine for which financial transactions the payment details you have selected are valid.

The assignment takes place at the following levels:

- Contract type (1 loans, 2 securities, 4 foreign exchange, 5 money market, 6 derivatives)


Product category

Product type

The availability of transaction types depends upon their Customizing settings.

Transaction type

The availability of transaction types depends upon their Customizing settings.

There are several ways you can carry out the assignment:

Select the contract types / product categories / product types / transaction types.


If you have selected a superior node, you cannot deselect the nodes that are automatically selected below it.

You select nodes by choosing with the quick info text Select/Deselect Incoming Line or Select/Deselect Outgoing Line. You can enter your assignments here directly. Crosses are entered in the list against your selections. You can use this function to assign incoming and outgoing payments.


By choosing with the quick info text Select All Outgoing or Select All Incoming, you can assign the payment details to all contract types. By choosing with the quick info text Deselect All Outgoing or Deselect All Incoming, you can remove all selections. You can use these functions to assign incoming and outgoing payments.

Unless you have carried out these allocations, the payment details will not appear as the proposed standing instructions when you enter a transaction.

By choosing with the quick info text Import of Partner, you can copy the Standing Instructions Payment Details belonging to another business partner.


Save the changed data.

###### Input Help: Payment Details

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Company-Code-Dependent Data in Business Partner > Standing Instructions > Payment Details > Input Help: Payment Details | L7 | trm01 p.124 | loio `9821285bd9f442669d3868555e654732` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9821285bd9f442669d3868555e654732.html?locale=en-US)

By setting or not setting the Payment Transaction and Payment Request indicators in the standing instructionsfor correspondence you choose whether a payment program is to be used for the payment and if so which one. Depending on whether you set the indicators or not, the posting logic is different.

|Posting Logic|Payment Transaction|Payment Request|
|---|---|---|
|1|Not set|Not set|
|2|Not set|Set|
|3|Set|Not set|
|4|Set|Set|


The way in which you have set the indicators determines how you enter the payment details. The following table shows which entries are required or optional and which ones are not included:

|Entry Field|Posting Logic 1|Posting Logic 2|Posting Logic 3|Posting Logic 4|
|---|---|---|---|---|
|Currency|X|X|X|X|
|Payment details ID|X|X|X|X|
|House bank|O|O|O|O|
|Account ID|O|O|O|O|
|Payment transaction| | |X|X|
|Payer/payee| |O|O|O|
|Partner bank| |X|O|X|
|Payment method| | |O| |
|Payment method supplement| |O|O|O|
|Payment request| |XC| |XC|
|Individual payment| |OC| |OC|
|Same direction| |O| |O|
|Payment method| |X| |X|
|Determine grouping definition (text)| |0| |0|


X = Input required

O =Optional input

C = Input only included if it does not contradict Customizing of flow types.

/ = Input not included

###### Repetitive Code

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Company-Code-Dependent Data in Business Partner > Standing Instructions > Payment Details > Repetitive Code | L7 | trm01 p.125 | loio `65756ccfd54c43f5b0521c66e36fd60f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/65756ccfd54c43f5b0521c66e36fd60f.html?locale=en-US)

**Use**

The Repetitive Code column appears in the payment details for a transaction and in the standing instructions. This feature is used primarily in the USA to simplify payment processing for payments that recur on a regular basis.

**Definition**

A repetitive code is an agreement that you make with your bank to automate your payment processes.

**Structure**

The agreement that you make with your house bank to transfer money electronically between two bank accounts includes the following information:

Sender bank data

Recipient bank data

Intermediary bank data (multi-level bank chains)

**Integration**

You can define a repetitive code in the standing instructions, which is then transferred automatically to the payment details of the transaction.

The following fields are always preset by repetitive codes:

House Bank

Account ID

Payer/Payee

Bank Account of Payer/Payee

Reference Text

Depending on the repetitive code you define, you cannot change some of these fields. This is because the agreement with your bank means that the repetitive code has a higher priority than the standing instructions.

The graphic below illustrates the interrelationships of the elements described above.

[figure TRM01-F027]

###### Transaction Authorization

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Company-Code-Dependent Data in Business Partner > Standing Instructions > Transaction Authorization | L6 | trm01 p.126 | loio `522cab2cf97a4fc09375eb7db5385faf` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/522cab2cf97a4fc09375eb7db5385faf.html?locale=en-US)

**Use**

In the Transaction Manager, a business partner must be authorized for a product type/transaction type before transactions with this partner can be entered in the system. You can assign transaction authorizations in the standing instructions under company code-dependent data in business partner maintenance.

**Prerequisite**

The business partner is not flagged for archiving.

**Scope of Functions**

You can assign a transaction authorization at all levels. Any authorizations that you assign at a higher lever automatically include the levels below. If a business partner is authorized for the contract type Money Market, for example, then transactions may be concluded with the partner in each product category, product type, and transaction type allocated to this contract type.

**Activities**

On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Business Partner Special Functions Standing Instructions Transaction Authorization .


The system displays the business partner that was most recently processed. Enter the company code for the business partner that you have selected and choose Continue.

The system displays the company code-dependent data from business partner maintenance. You can make settings for correspondence on various hierarchy levels on the SI: Authorizations tab page.

When you assign authorizations at a higher level, these authorizations automatically apply to all the levels that appear below.

You can assign authorizations at the following hierarchy levels:

- Contract type (2 securities, 4 foreign exchange, 5 money market, 6 derivatives)


Product category

Product type

The availability of transaction types depends upon their Customizing settings.

Transaction type

The availability of transaction types depends upon their Customizing settings.

Input help

You can either make the settings directly in the list, or use the following functions in the input help. If you make entries directly in the list and select a higher-level node, the setting will then apply to all the lower levels too.


If you have selected a superior node, you cannot deselect the nodes that are automatically selected below it.

By choosing with the quick info text Import from Other Partner you can copy the Standing Instructions belonging to another business partner.

###### Derived Flows

> **Path:** Treasury and Risk Management > Master Data > Business Partner > Company-Code-Dependent Data in Business Partner > Standing Instructions > Derived Flows | L6 | trm01 p.127 | loio `3558c91f3bf34cea8966d13275d07da3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3558c91f3bf34cea8966d13275d07da3.html?locale=en-US)

**Use**

You can use the derivation procedure in conjunction with the business partner to automatically generate flows when you create a financial transaction. For example, you can make settings to automatically generate tax flows from incoming accrued interest flows when you enter the purchase of a security.

The derivation procedure can be assigned to the business partner at the following hierarchy levels:

Contract type (for example, money market, foreign exchange)

Product categories for the respective contract type, (for example, fixed-term deposit for money market)

Product types for the corresponding contract type/product category (for example, time deposit for the product category fixedterm deposit)

Transaction types for a product type (for example, time deposit investments or borrowings)

**Prerequisites**

The business partner must exist in the system, not be marked for deletion, and be released.

You must create the derivation procedure in Customizing for the application areas Money Market, Foreign Exchange, Securities, and Derivatives under Define Derivation Procedures and Rules.

**Activities**

On the SAP Easy Access screen for the business partner, choose Special Functions Standing Instructions Derived Flows .

Enter the company code for you business partner and choose Enter.

The system displays the Maintain Business Partner screen. Choose Company Code.

You are in the processing screen for company code-dependent data. Choose the Derived Flows tab page.

You can assign the derived flows at the following levels: Contract type, product category, product type, and transaction type.

The following options are available for carrying out the assignment:

When you choose the level to which you wish to assign a certain procedure, a dialog screen appears, in which you can select the derivation procedure you require. This derivation procedure is then assigned at the level you have chosen, and at all of the lower levels.


You cannot automatically reset the selection for a node that appears below the level that you have chosen.

Make selections using the key, which also provides you with an input help.

Choose the (Import from other Partner) key to copy the standing instructions from another business partner.

Save your entries.

#### Defining Banks, House Banks, Bank Accounts, House Bank Accounts

> **Path:** Treasury and Risk Management > Master Data > Defining Banks, House Banks, Bank Accounts, House Bank Accounts | L3 | trm01 p.128 | loio `bf4975f65e394e8788d409669a52e148` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bf4975f65e394e8788d409669a52e148.html?locale=en-US)

With Bank Relationship Management, you can define the following master data:

Defining banks and house banks using the Manage Banks (Deprecated) app.

Alternatively, you can use SAP GUI transaction FI01 to define banks and FI12_HBANK to define house banks.

Defining house bank accounts and bank accounts using the Manage Bank Accounts app.

Alternatively, you can use SAP NetWeaver Business Client (NWBC) as the user interface to define bank accounts and house bank accounts.

