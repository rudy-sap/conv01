# Risk Management > Basics > Editing Generic Transactions - SAP TRM Knowledge Base (branch split)

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

##### Editing Generic Transactions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions | L4 | trm02 p.42 | loio `e69dc85357281d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e69dc85357281d4be10000000a174cb4.html?locale=en-US)

**Use**

You use this transaction to create, display, or change generic transactions, or to create a new transaction as a copy of an existing generic transaction.

You can use generic transactions to depict structured and non-structured financial products and to make them available to Risk Analysis. Generic transactions are structured in a way that enables them to be valuated by the price calculator. They are therefore based on cash flows.

You can create generic transactions using various elementary transactions, each of which describe a simple transaction. You can arrange the elementary transactions in a freely definable hierarchical structure. For example you can depict a loan with a right of notice as a call option on a loan.

The generic transaction is used in the Risk Analysis, Profitability Analysis (only calculation of NPVs is possible) and Default Risk and Limit System components. You can use generic transactions to:

Depict transactions that cannot be depicted in any other way.

Store transactions that are transferred from non-SAP systems in a standard way.

Functions are available that allow you to:

Integrate existing transactions in the generic transaction. You do this using a pointer, which references the transaction in question.

Store templates for generic transactions to enable you to create generic transactions more quickly.

Manage versions of the generic transactions.

Structure of a Generic Transaction

The elementary transactions of a generic transaction are identified by a transaction form. This controls the valuation of the elementary transaction in the Risk Analysis component.

[figure TRM02-F040 - The elementary transactions of a generic transaction are identified by a transaction form. This controls the valuation of the elementary transaction in the Risk Analysis component.]

**Prerequisites**

You have made the appropriate settings for the generic transaction in the Business Data Tool (BDT). In particular, you have used the field selection control to define for every elementary transaction which fields are offered for you to maintain. You can determine the BDT settings for the generic transaction by choosing Treasury and Risk Management Market Risk Analyzer

Tools Development BDT Generic Transaction in the area menu.

**Procedure**

- 1. Choose Treasury and Risk Management Market Risk Analyzer Tools Development BDT Generic Transaction Application Generic Transaction .


The system displays a selection screen Data Selection.

You can enter an external number or an internal number, and a version date. The external number identifies generic transaction uniquely. The system assigns the internal numbers. You can use the version date to save more than one version of a generic transaction. You can use the version date in the case of transactions with variable interest payments for example, in order to examine the transaction before and after interest rate fixing.

**Note:**

The sole purpose of version management for generic transactions is to enable you to record changes to the generic transaction as a result of corporate actions (for example a change to the nominal values). When you save a generic transaction, you can choose whether or not the system creates a version. In general, you do not need to use a version date, as changes are documented in the change documents.

Ensure that the version date is always before the start of the term of the first elementary transaction of the generic transaction If this is not the case, the system does not select the generic transaction when you carry out evaluations with an evaluation date that is before the creation date.

If you leave the Version Date field empty, the system uses today’s date as the version date.

You can create one version per day only.

- 2. To edit a generic transaction, proceed as follows:

Create without template

- a. Enter an external number to identify the generic transaction.
- b. You can also enter a version date from which the generic transaction is valid. If you do not enter a version date, the system uses today’s date.
- c. Choose Create .


Create with template

- a. Select a generic transaction that you want to use as a template.
- b. Enter an internal or an external number and a version date, or use input help.
- c. Choose Copy Generic Transaction .
- d. The system opens a dialog box.

Enter a new external number for the generic transaction.

You can also enter a version date from which the generic transaction is valid. If you do not enter a version date, the system uses today’s date as the version date.

- e. Choose Copy Generic Transaction.


Change

- a. Select a generic transaction that you want to change.
- b. Enter an internal or an external number, or use input help.
- c. Choose Change .


Display

- a. Select a generic transaction that you want to display.
- b. Enter an internal or an external number and a version date, or use input help.
- c. Choose Display.


- 3. The system displays a screen that contains all information relating to the generic transaction, or in which you can enter this information. The dialog structure on the left contains the hierarchy of the elementary transactions of the generic


**Note:**

You can use category 8 for generic transactions that you want to use as a template only.

**Note:**

Note that you can change the current version only. You do not therefore need to enter a version date for the generic transaction.

transaction. The tab pages on the right contain the master data and the analysis parameters.

- 4. Action


To change or create a generic transaction, proceed as follows:

- a. Enter master data for the generic transaction


Enter the following information:

Short name

Enter an appropriate name for your generic transaction.

Category

Generic transactions can have the following categories:

Real Generic Transaction (Category 0)

Transaction that exists in the SAP system and is to be valuated. You can process this transaction online and offline and it is suitable for external data transfer (EDT).

Sample Hierarchy for a Generic Transaction (category 8)

Sample that contains the hierarchy of the subtransactions of a generic transaction. You can process this transaction online only and it is not suitable for external data transfer (EDT).

Class Supplement as a Generic Transaction (category 9)

Class for a Treasury transaction that is to be expanded to form a generic transaction.

**Note:**

Note that you can create financial objects for generic transactions of category 0 (real generic transaction) only.

Securities Identification Number

Enter the security ID number of the generic transaction.

**Note:**

You do not need make entries for the transaction environment and the security ID number for all transactions. Cash flow transactions for example do not require a security ID number.

Transaction environment

Enter a company code, securities account, portfolio, trader, currency, and business partner for the generic transaction.

Create hierarchy for the elementary transactions

The dialog structure shows which elementary transactions make up the generic transaction, and how the hierarchy of the elementary transactions is arranged. You can use the following interactions in order to create new elementary transactions or change the hierarchy:

|Action|Function|
|---|---|
| Create Trans. on Next Level|The system creates an elementary transaction directly below the selected node on the next level down in the hierarchy.|


| Create Trans. on Same Level|The system creates an elementary transaction directly behind the selected node on the same hierarchy level. This interaction is not possible for the top hierarchy node of the generic transaction.|
|---|---|
| Change Trans. Form|You change the transaction form of the selected elementary transaction.  This interaction enables you to change the transaction form of an elementary transaction at a later point in time. This overwrites the data in the old transaction form. Note that for purposes of consistency, these changes can only be made to root nodes in the hierarchy, and only then, if there are no subordinate elementary transactions assigned to the root node.|
| Delete Elementary Transaction|The system deletes the selected elementary transaction.|


**Note:**

For notes on creating structured transactions, see Examples of Generic Transactions .

- b. Elementary transaction data


- i. Select the elementary transaction in the dialog structure.

The system opens a dialog box.

- ii. Select the transaction form of the elementary transaction.


**Note:**

The transaction form controls the valuation in Risk Management, as it tells the price calculator what kind of transaction is involved. If a node has an elementary transaction form, the corresponding sub-tree also has to describe this transaction. If this is not the case, inconsistency errors occur.

For more information, see Transaction Form of an Elementary Transaction.

The system creates the tab pages for the header information and the cash flow of the transaction. The entries that the system requires depends on the transaction form of the elementary transaction.

- i. Choose the Header Information tab page .
- ii. You must make the following entries for all transaction forms:


Valuation rule

You can define a valuation rule for each of the elementary transactions that belong to the generic transaction.

Note that the valuation rules defined in the elementary transactions are overridden by any valuation rule that is defined in the financial object of the generic transaction.

Default Risk and Limit System

Set the Selected Transaction indicator as required. The following restrictions apply:

The indicator must be set in exactly one elementary transaction.

You cannot change the indicator in elementary transactions with the transaction form 200 (complex financial transaction).

You cannot change this indicator for generic transactions of category 9 (complex class).

Start of Term

You must make an entry in this field for the top node in the hierarchy of the elementary transactions. For all other nodes, this field is optional.

You must enter additional information on the generated tab page, depending on the transaction form you chose. For more information, see the examples of generic transactions.

- c. Choose the Cash Flow tab page and enter the cash flows for the transaction.


Choose Back and then Save .



You have the following additional options when editing generic transactions:

|Action|Function|
|---|---|
| Check Entries|The system checks whether the entries in the tab page that is currently displayed are consistent.|
| Other Generic Transaction|The system returns to the selection screen in which you can select a new generic transaction for editing.|


**Result**

You have edited the generic transaction.

When you make changes, the system generates change documents. These are flagged as “change document relevant” in the ABAP Dictionary. You can display the change documents from the Edit Generic Transaction screen by choosing Extras Change Documents .

**Note:**

You have to create a financial object for the generic transaction so that the generic transaction is taken into account in the evaluations. If the generic transaction refers to a transaction that already has a financial object in the SAP system, you have to make sure that this existing financial object is deactivated. Otherwise, these transactions will be included in evaluations twice.

###### Transaction Form of an Elementary Transaction

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Transaction Form of an Elementary Transaction | L5 | trm02 p.47 | loio `dc10da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dc10da531198434de10000000a174cb4.html?locale=en-US)

Every elementary transaction of a generic transaction is defined by means of a transaction form (TFORM). The following provides an overview of the transaction forms provided by SAP:

|Transaction Form|Name|Comment|Elementary Transactions Appropriate to this Transaction Form|
|---|---|---|---|
|001|Mortgage/Interest Rate Instrument| | |
|002|Loans| | |


|Transaction Form|Name|Comment|Elementary Transactions Appropriate to this Transaction Form|
|---|---|---|---|
|010|Stock|If you use the transaction form Stock as an underlying for an OTC option, the purchase/sale indicator is irrelevant. You make the system aware of this by specifying whether the option is a call or a put.| |
|013|Index| | |
|021|Bond| | |
|030|Warrant| | |
|041|Foreign Exchange| | |
|042|Fixed-Term Deposit| | |
|043|Deposit at Notice| | |
|044|Commercial Paper| | |
|049|Caplet/Floorlet as Underlying|If the Convexity adjustment is active for a risk analysis evaluation, the Number of days field in the Calculation methods field group for the caplet/floorlet cash flow has to be filled.| |
|050|Cap/Floor/Collar| |061 OTC Option|
|051|Swap| | |
|052|FRA| | |
|055|Future| | |
|060|Listed Option| | |
|061|OTC Option|The strike of the option must be entered directly.|Transaction form of the underlying For caps, floors, and collars this is 049.|
|062|Complex OTC Option|You can use this option to depict a right of notice (for example, for bonds or loans). You do not need to enter the strike of the option. The system determines this automatically.|Only the following transaction forms are permitted as underlyings: 021 (Bond) 001 (Mortgage) 002 (Loans) |
|063|Exercise Opportunity for a Bermuda Option.| |Underlying, for example, transaction form 042 (fixed-|


|Transaction Form|Name|Comment|Elementary Transactions Appropriate to this Transaction Form|
|---|---|---|---|
| | | |term deposit) and further Bermuda options (transaction form 063).|
|065|Forward Volatility Agreement| | |
|070|Accounts| | |
|100|Fixed Cash Flow| | |
|120|Non-Interest-Bearing Position| | |
|200|Complex Financial Transaction|With this transaction form you can group together several transactions and allow them access to Risk Analysis as one single transaction.|Subtransaction|
|300|Complex Class|This transaction form is used to combine security positions with other elementary transactions. It only makes sense to use this with category 9 generic transactions (class supplement as generic transaction).|For example, transaction forms 010 (Stock), 021 (Bond) or 062 (OTC Option).|
|401|Reference to an Original Transaction|Transaction in the SAP system: The Start of term field is only interpreted if this elementary transaction is used in the highest hierarchy node.| |
|402|Reference to ID Number|It only makes sense to use this sort of reference as an elementary transaction with transaction form 300 if you are creating a category 9 generic transaction (Class Addition as Generic Transaction).| |
|403|Reference to an external transaction| | |


**Note:**

For more information on references, see References to Other Transactions.

###### References to Other Transactions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Transaction Form of an Elementary Transaction > References to Other Transactions | L6 | trm02 p.49 | loio `ba10da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ba10da531198434de10000000a174cb4.html?locale=en-US)

Referencing another transaction is the easiest way to set up an elementary transaction for a generic transaction. In this case, the elementary transaction is merely a reference to an existing transaction, and otherwise contains no information. We make the following distinctions between transactions referenced by an elementary transaction:

External transactions outside of Risk Analysis, referenced by an object number (TFORM 401)

For transactions that have already been created in the SAP system, you can simply enter the object number of the transaction in the Original Trans. field in the References to Original Transaction data group .

**Note:**

Before searching for an original transaction in the system, you have specified which type of elementary transaction you require by entering the transaction form (TFORM). The search for suitable original transactions in the system does not take into account your preselection. You must ensure that an elementary transaction with a particular TFORM also contains a reference to an appropriate transaction. In the input help for the Original Trans. field, you can distinguish between the following transaction categories: Loans , Financial Transactions ( Money Market/Forex/Derivatives ), Positions ( sec./DTB ), ForwardTransactions , Accounts , and Non-Interest-Bearing Positions . However, it is the transaction form of the elementary transaction that is most important for the price calculator.

In Risk Analysis, references of this type are removed directly and consequently the transactions replace the corresponding elementary transaction in the generic transaction. If, for example, you reference a cap in Treasury (TR), then at the time of valuation in Risk Analysis a fully structured sequence of caplets will be available under the elementary transaction that references the cap.

External transactions outside of the SAP system, referenced by an external number (TFORM 403)

For transactions outside of the SAP system enter an external transaction identification number of up to 20 digits. This number is used as an anchor point in the data pool.

References of this type are never removed, as the SAP system cannot use the external data storage structure. Using external transaction numbers for valuations only makes sense if you are using an interface for an external price calculator.

Complex Additions to TR Classes (TFORM 402)

This form of generic transaction is intended to combine security positions with other elementary categories, to integrate them with the flexibility of the generic transaction. Complex class additions are defined within a generic transaction, but are not complete generic transactions yet, as they contain no position information. Only after position selection in the course of a risk evaluation do they become complete generic transactions that relate to the position in the relevant class.

When you create generic transactions with the transaction form 402 you must enter the value 9 (class supplement as generic transaction) in the Cat. field in the generic transaction master data. In the same screen, the security ID number of the class has to be entered in the Extended class data group .

In the hierarchical depiction of the generic transaction, you have to create a central elementary transaction with the transaction form 300 (Complex Class). No other information is necessary. Underneath that, in the next level, you must create another elementary transaction with the transaction form 010 (Stock) or 021 (Bond). In the header of the stock or bond, enter the security ID number of the class in the Security ID number field. You have now created a link to the Risk Analysis position selection.

Now you can assign as many transaction additions in the form of additional elementary transactions to the security position as you like.

###### Interest Rate Fixing for Generic Transactions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Interest Rate Fixing for Generic Transactions | L5 | trm02 p.50 | loio `8810da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8810da531198434de10000000a174cb4.html?locale=en-US)

**Use**

In this function, the system fixes the interest rates for the variable-rate cash flows of generic transactions. The system calls the function during the analysis of generic transactions. The interest rate is fixed when the fixing date is before or on the horizon date.

**Integration**

The system calls the function for fixing interest rates during the calculation of NPV key figures (such as the net present value, and the clean price) and in the analyses of the cash flows for the following components of Treasury and Risk Management:

Market Risk Analyze

Credit Risk Analyzer

Portfolio Analyzer

**Prerequisites**

You have created generic transactions and stored variable interest rate cash flows for single transactions on the Cash Flow tab page. On the same tab page, you have left the Reference Rate and Fixing Date fields empty, and you have not set the Fictitious Cash flow indicator.

You have stored the market data needed to fix interest rates in the system.

**Features**

The system fixes interest rates only for variable-rate interest cash flows whose interest rate fixing date is before or on the horizon date, and that mature or are paid after the horizon.

The system takes into account variable-rate interest cash flows from derivative elementary transactions such as caps, floors, and swaps. It also solves the reference rates that you created as a formula.

**Note:**

The system does not fix the interest rates for referenced transactions (transaction forms 401, 402, and 403).

The system takes the needed market data to fix interest rates from the database. If there is no market data for interest rate fixing date, the system uses historical market data. If it cannot find any historical market data, it sets the reference rate to 0 percent. If data is missing, the system writes a warning message to the application log.

###### Examples of Generic Transactions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions | L5 | trm02 p.51 | loio `1411da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1411da531198434de10000000a174cb4.html?locale=en-US)

The following documentation contains examples of generic transactions:

Cash Flow Transactions (for example loan with fixed or variable interest calculation or swaps)

Loan with Rights of Notice

Convertible Bonds

Reverse Convertible Bonds

Hit-At-The-End-Options

One-Touch Binary Options

Bermuda Options

Basket Options

Caps, Floors, Collars

Forex Options

FIONA Swaps

You can also create fictitious transactions , which cannot be generated in the ALM simulation. This enables you to test hedging strategies.

###### Cash Flow Transactions (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Cash Flow Transactions | L6 | trm02 p.52 | loio `bd10da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bd10da531198434de10000000a174cb4.html?locale=en-US)

Cash flow transactions include all transactions valued according to their cash flows in Risk Analysis. Examples of cash flow transactions include stocks with dividend payments, bonds, loans, swaps, or forward rate agreements.

When creating cash flow transactions as generic transactions you must describe the transactions’ cash flows precisely. The following contains examples of cash flow transactions. Characteristic Cash Flows of Cash Flow Transactions is a summary of essential data on typical cash flow types in table format (see below).

**Examples of Cash Flow Transactions**

Stocks

Stocks are only considered cash flow transactions when they include dividend payments. When creating such a stock position as a generic transaction, as well as the header information, you must also enter data for the cash flows. You can do this as follows:

Choose transaction form 10 (Stock) as the transaction form for the elementary transaction.

Enter the following information on the Header Information tab page:

Start of term for the relevant business transaction as well as specifying whether it involves a spot or a forward and a purchase or sale transaction.

Identification number of security, the exchange, and the quantity of stock positions. Enter Direct quotation for the quotation type (value 2).

Choose the Cash Flow tab page and enter the dividend payments as cash flows with the characteristic Fixed Interest , Fixed Currency (see table below)

Select Back and then save.



Bonds

When you create bonds as a generic transaction you can define cash flows as with stocks. The system uses these cash flows to calculate the accrued interest on the bond. Furthermore, cash flows are relevant if the price of the bond is not available in the market data or in the valuation rule for the bond and the corresponding evaluation type a valuation for the interest curve is provided. In such a case the system uses the cash flows to value the bond. You can do this as follows:

Choose transaction form 21 (Bond) as the transaction form for the elementary transaction.

Choose the Header Information tab page .

Enter the start and end of term for the bond in the Business Transaction area of the screen and set the spot/forward indicator as well as the purchase/sale indicator.

Enter the identification number of security, the exchange, and the quotation type. Then enter either the quantity or the nominal amount, and the currency of the bond.

Choose the Cash Flow tab page and enter the cash flows for the bond. Use the characteristic cash flows appropriate to the bond, for example, Fixed Interest, Fixed Currency or Variable Interest (see table below).


If bonds are valued using a rate, you must heed the cash flow characteristic “interest deferral”.

Select Back and then save.

Forward Rate Agreement (FRA)

Typically, for a forward rate agreement you create just one cash flow. You can do this as follows:

Choose transaction form 52 (FRA) as the transaction form for the elementary transaction.

Choose the tab page Header Information.

Enter the start and end of term for the bond under Business Transaction and set the spot/forward indicator as well as the purchase/sale indicator.

Enter the nominal amount and the currency under Position Definition.

Choose the Cash Flow tab page and enter the cash flows for the FRA. To do this, use the characteristic cash flows for the forward rate agreement (see below).

Select Back and then Save

Assigning Cash Flow Transactions to Characteristic Cash Flows

The following table explains which cash flows can be used with which cash flow transactions.

|Transaction|Characteristic Cash Flow|
|---|---|
|Fixed loan, fixed-interest securities, zero bonds, fixed-term deposits, deposits at notice, commercial papers, etc.|Fixed interest, fixed currency (for interest and repayment)|
|Variable loan, floater/reverse floater, etc.|Variable interest (for the interest payments) Fixed interest, fixed currency (for the repayment)|
|Swaps|Fixed interest, fixed currency (for the fixed side) Variable interest (for the variable side) Use the Side field to specify the fixed and/or variable side of the transaction.|
|Fixed interest multiple currency bonds|Variable currency (for the interest payments) Fixed interest, fixed currency|


|Transaction|Characteristic Cash Flow|
|---|---|
| |(for the repayment)|
|Variable interest-bearing multiple currency bonds|Variable interest (for the interest payments) Variable currency (for the interest payments)|


**Characteristic Cash Flows from Cash Flow Transactions**

To enter cash flows for a generic transaction carry out the following:

Select the required elementary transaction in the dialog structure (double click).

The system displays the header information for the generic transaction.

Choose the Cash Flow tab page .

Choose Create Cash Flow .


Enter the cash flow type and due date. Then select the row with the cash flow and choose Choose Cash Flow.

The system displays a template in which you can enter all the relevant information regarding the cash flow.


Depending on the transaction form of the elementary transaction the system displays several fields. The elementary transaction Cash Flow (transaction form 100) does not allow any reference interest rate for example.

Enter the required information for the cash flow.

You can use the characteristic cash flows listed below as an example.

Choose Back and then save .



The following tables show the characteristic cash flows of cash flow transactions:

|Field|Meaning|
|---|---|
|Due date|Date from which the cash flow is discounted|
|Cash flow amount|Amount to be discounted (with +/- sign)|
|Cash flow currency|Currency of amount|


|Field|Meaning|
|---|---|
|Due date|Date from which the cash flow is discounted|
|Nominal amount|Nominal amount to which interest rate relates|
|Currency|Currency of nominal amount|


|Field|Meaning|
|---|---|
|Reference interest rate|Reference interest rate|
|+/- sign|Sign for the reference interest rate|
|Formula|You have the option of defining the reference interest rate using a formula.|
|Interest rate determination|Interest rate determination date|
|Direction|Inflow and outflow|
|Calculation from|Beginning of the interest calculation period|
|Calculation to|End of the interest calculation period|



**If the Convexity adjustment is active for a risk analysis evaluation, the field Number of days in the Calculation methods field group for the cash flow characteristic “Variable interest” has to be filled.**

|Field|Meaning|
|---|---|
|Due date|Due date for FRA|
|Nominal amount|Nominal amount of FRA (from the position data in the tab page Header Information )|
|Currency|Currency of nominal amount|
|Percentage|Agreed interest rate|


|Field|Meaning|
|---|---|
|Due date|Date from which the cash flow is discounted|
|Nominal amount|Nominal amount in original currency|
|Currency|Currency of nominal amount|
|Interest rate|Interest rate used to generate cash flow in original currency|
|Cash flow currency|Currency into which the cash flow has to be translated|
|Fixed rate|Indicator showing whether a fixed rate is available for the currency translation|
|Exchange rate|Fixed exchange rate|


|Field|Meaning|
|---|---|
|Number of days|Number of days for interest deferral (accrued interest calculation)|
|Number of base days|Number of days in year|
|Calculation method|Interest calculation method for accrued interest|

###### Loans with Rights of Notice

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Loans with Rights of Notice | L6 | trm02 p.56 | loio `0b11da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0b11da531198434de10000000a174cb4.html?locale=en-US)

In order to valuate loans with rights of notice, you must create them as generic transactions.

An example could be a loan with an original term of 15 years on which notice can be given after 10 years with a notice period of 6 months.In order to valuate the loan, you must split it into two transactions: A long loan and a European short call on the loan with the term end date 10.5 years in the future.The term start date is 01/01/2002, the currency is EUR.The Prerequisite and Example sections demonstrate how to create the generic transaction.


This division is not completely correct from a business perspective, as it assumes that no right of notice exists after 10.5 years, although legally the right could still exist.The option price determined from this division is therefore only the lower limit of the actual price of the right of notice.The upper limit for the right of notice could be determined by moving the exercise date for the option to the final due date of the loan.


You use the Complex OTC Option elementary transaction in order to depict the loan with a right of notice as a generic transaction.The system currently supports only European-style exercise for this option.It is not currently possible to accurately calculate the price of this kind of option with American-style exercise.

Note: You have the option of modeling notice options as exercise opportunities (Bermuda option) within a generic transaction.

**Prerequisite**

In order to create the generic transaction, you must have created the disbursed loan in Loans Management and the corresponding financial object must exist.For more information, see also Editing Financial Objects .

**Procedure**

The following hierarchy of elementary transactions is required in order to depict the loan with a right of notice as a generic transaction.

[figure TRM02-F060 - The following hierarchy of elementary transactions is required in order to depict the loan with a right of notice as a generic transaction.]

Create the hierarchy as follows:

- 1. Create a new generic transaction. See Editing Generic Transactions for the procedure.

In the dialog structure, select the first elementary transaction and assign to it transaction form 200 (complex financial transaction).

- 2. Select the elementary transaction again.The system displays a tab page.
- 3. Enter the start of the term of the underlying loan in the Start of term field.
- 4. Create a transaction with transaction form 401 (reference to ID number) under the Complex Financial Transaction elementary transaction.To do this, select the Complex Financial Transaction elementary transaction in the dialog structure and choose Create Elementary Trans. on Next Level . Select the new elementary transaction and assign to it transaction form 401.

The system displays a tab page.

- 5. Enter the object number of the underlying loan in the Original Trans . field.You can use input help to select the loan.
- 6. Create a transaction with transaction form 62 (OTC option) under the Complex Financial Transaction elementary transaction.(Proceed as for step 3).

The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Start date of term of loan.

Notification By/End Date of Term field

Earliest possible date for giving notice on the loan.

Purchase/Sale field

Set the indicator to sale (option is a short call).

On the Options Information tab page, flag the option as a standard option with European exercise and, in particular, as a call option.Enter the following information:

Strike Currency field

Currency of loan.

Delivery of Underlying field

Earliest possible date for giving notice on the loan.

Quotation of Underlying field

Percentage quoted.

You do not need to make any entries on the Cash Flow tab page.

- 7. Create a transaction with transaction form 401 (reference to ID number) under the Complex OTC Option elementary transaction.(Proceed as for step 3).

The system displays a tab page.

- 8. Enter the object number of the underlying loan in the Original Trans . field.You can use input help to select the loan.
- 9. Choose Back and then Save.





Note that, once you have created the generic transaction, two financial objects may exist for the loan: One for the original transaction and one for the loan with the right of notice as a generic transaction.You must deactivate either the analysis parameters (RM) in the financial object for the original transaction, or the analysis parameters (RM) in the financial object for the generic transaction.

**Result**

You have created the loan with a right of notice as a generic transaction.

**Example**

You would enter the following data for the generic transaction for the loan in the example.The tables below show what entries need to be made in the individual fields for each elementary transaction.

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|01/01/2002|The term start of the underlying loan|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|01/01/2002|The term start of the underlying loan|
|Header Information|Notification By/End Date of Term|07/01/2010|Notice can be given on the loan after ten years and six months (notice period) at the earliest.|
|Header Information|Purchase/Sale|200|Sale|
|Options Information|Option Category|001|Standard option|
|Options Information|Exercise Type|1|European exercise|
|Options Information|Put/Call Indicator|2|Call|
|Options Information|Strike Currency|EUR|Currency of loan|
|Options Information|Delivery of Underlying|07/01/2010|In our model, the underlying is delivered on the exercise date. This is the earliest possible date on which notice can be given – after ten years and 6 months.|
|Options Information|Quotation of Underlying|1|Percentage-quoted|



The tab pages may also contain other fields.You do not need to make entries in fields that are not included in this table as they are not relevant for valuating the generic transaction.

###### Convertible Bonds (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Convertible Bonds | L6 | trm02 p.58 | loio `7d0fda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7d0fda531198434de10000000a174cb4.html?locale=en-US)

Convertible bonds are issued by stock corporations. The investor has the right to swap the bond for a fixed quantity of the stock of the issuing corporation within a particular time limit.

The investor swaps the bond for stock if the value of the stock is greater than the nominal value of the bond. Convertible bonds can therefore be split into a bond and a call option on the underlying stock.

In order to valuate convertible bonds, you must create them as generic transactions.

**Prerequisite**

You have created the security classes for the bond and the stock in Treasury. A financial object exists for the bond.

**Note:**

Ensure that you make an entry in the Nomin. per TU field in the basic data of the bond class. By doing so, you specify the amount of the nominal volume for which the option in the generic transaction is valid.

**Procedure**

To depict a convertible bond as a generic transaction, create the following elementary transaction hierarchy:

[figure TRM02-F065 - Create the hierarchy as follows: (The following depicts the transaction from the perspective of the investor.)]

Create the hierarchy as follows: (The following depicts the transaction from the perspective of the investor.)

- 1. Create a new generic transaction with category 9 (class supplement). In the master data, enter the ID of the bond created in Treasury. See Editing Generic Transactions for the procedure.

a. .

- 2. In the dialog structure, select the first elementary transaction and assign to it transaction form 300 (complex class) .


The system displays a tab page.

Enter the issue date of the bond in the Start of term field.

- 3. Create a transaction with transaction form 402 (reference to ID number) under the Complex Class elementary transaction. To do this, select the Complex Class elementary transaction in the dialog structure and choose Create Elementary Trans.: Next Level . Select the new elementary transaction and assign to it transaction form 402.


The system displays a tab page.

Enter the object number of the bond in the ID Number field. You can use input help to select the transaction.

- 4. Create a transaction with transaction form 61 (OTC option) under the Complex Class elementary transaction. (Proceed as for step 3).

The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Issue date of the bond

Notification By field

Due date of bond

Purchase/Sale field

Set the indicator to Purchase/Investment Made .

On the Options Information tab page, flag the option as a standard option with European exercise and, in particular, as a call option. Enter the following information:

Strike Currency field

Currency of the bond

Delivery of Underlying field

Due date of bond

Quotation of Underlying field

Direct quotation

You do not need to make any entries on the Cash Flow tab page.

- 5. Create a transaction with transaction form 10 (stock) under the OTC Option elementary transaction. (Proceed as for step 3).

The system displays the tab page for the header information.

Enter the security ID number, the exchange, enter Direct quotation quotation type, and enter the number of units. Flag the transaction as a spot transaction and a purchase.

- 6. Choose Back and then Save.




**Result**

You have created the convertible bond as a generic transaction.

The system does not generate a financial object when you save even if automatic financial object integration is active. You have already created a financial object for the bond.

**Example**

Interest is calculated on a convertible bond for EUR 1,000 with 2%, which runs from 01/01/2002 to 01/01/2007. The bond class gives the owner of the bond the right to convert EUR 1,000 of the class into 20 units of company A’s stock at the end of the term. Company A’s stock has the security ID number 803200. The convertible bond has the security ID number 803260.

From the investor’s perspective, this class can be split into a bond with the corresponding interest and repayment structure, and the purchase of a call option. The call option is of the European exercise type, its term end is 01/01/2007, and its strike is EUR 1,000 for 20 units of stock.

The following tables contain the entries that you would have to make for the generic transaction and the elementary transactions for this example. As the generic transaction just references the bond, you do not need to enter the interest rate of 2% when you create the generic transaction.

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Master Data|ID Number|803260|Security ID number of bond|
|Master Data|Short Name|Convertible bond A. EUR 1000|Appropriate name for convertible bond|
|Master Data|Cat|9|Generic transaction is class supplement. The system updates the position automatically using the underlying bond. The system accesses the extended class for evaluations.|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|07/17/2002|Issue date of the bond|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|ID number|803260|Security ID number of bond|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of term|01/01/2002|Issue date of the bond|
|Header Information|Notification By|01/01/2007|Due date of bond|
|Header Information|Purchase/Sale|100|Purchase/Investment Made|
|Options information|Option Category|1|Standard option|
|Options Information|Exercise Type|1|European exercise type|
|Options Information|Put/Call Indicator|2|Call, as the investor has the option of converting the bond to stock|
|Options Information|Strike Amount|1,000|Nominal amount of bond|
|Options Information|Strike Currency|EUR|Currency of the bond|
|Options Information|Delivery of Underlying|01/01/2007|Due date of bond|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Options Information|Quotation of Underlying|2|Direct quotation, as stock is quoted directly|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Spot/forward|1|Spot transaction|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Header Information|Security ID Number|803200|Security ID number of stock|
|Header Information|Exchange|FFM|Frankfurt am Main|
|Header Information|Quotation type|2|Direct quotation|
|Header Information|Number of units|20|Number of units of stock|


**Note:**

The tab pages may also contain other fields. You do not need to make entries in fields that are not included in this table as they are not relevant for valuating the generic transaction.

###### Reverse Convertible Bond

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Reverse Convertible Bond | L6 | trm02 p.62 | loio `9a10da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9a10da531198434de10000000a174cb4.html?locale=en-US)

In the case of reverse convertible bonds, the issuer has the right to deliver a certain quantity of stock on the due date instead of repaying the nominal amount. Which stock the issuer delivers is determined in advance.

The issuer delivers stock if the value of the stock is lower than the value of the nominal amount of the bond. Reverse convertible bonds can therefore be split into a bond and a put option on the underlying stock.

In order to valuate reverse convertible bonds, you must create them as generic transactions.

**Prerequisite**

You have created the security classes for the bond and the stock in Treasury. A financial object exists for the bond.

**Procedure**

To depict a reverse convertible bond as a generic transaction, create the following elementary transaction hierarchy:

[figure TRM02-F069 - Create the hierarchy as follows:]

Create the hierarchy as follows:

- 1. Create a new generic transaction. Assign the generic transaction status 9 (class supplement). Enter the security ID number in the master data of the generic transaction. See Edit Generic Transaction for the procedure.

a. .

- 2. In the dialog structure, select the first elementary transaction and assign to it transaction form 300 (complex class) .

Select the elementary transaction in the dialog structure again.

The system displays the tab page for the corresponding header information.

Enter the issue date of the bond in the Start of term field.

- 3. Create a transaction with transaction form 402 (reference to ID number) under the Complex Class elementary transaction. To do this, select the Complex Class elementary transaction in the dialog structure and choose Create Elementary Trans.: Next Level . Select the new elementary transaction and assign to it transaction form 402.

Select the required elementary transaction in the dialog structure again.

The system displays the tab page for the corresponding header information.

Enter the object number of the bond in the ID Number field. You can use input help to select the transaction.

- 4. Create a transaction with transaction form 61 (OTC option) under the Complex Class elementary transaction. (Proceed as for step 3).


The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Issue date of the bond

Notification By field

Due date of bond

Purchase/Sale field

Set the indicator to Sale.

On the Options Information tab page, flag the option as a standard option with European exercise and, in particular, as a put option. Enter the following information:

Strike Currency field

Currency of the bond

Delivery of Underlying field

Due date of bond

Quotation of Underlying field

Direct quotation

You do not need to make any entries on the Cash Flow tab page.

- 5. Create a transaction with transaction form 10 (stock) under the OTC Option elementary transaction. (Proceed as for step 3).

Select the required elementary transaction in the dialog structure again.

The system displays the tab page for the corresponding header information.

Enter the security ID number, the exchange, enter the Direct quotation quotation type, and enter the number of units. Flag the transaction as a spot transaction and a purchase/investment.

- 6. Choose Back and then Save .




**Result**

You have created a reverse convertible bond as a generic transaction.

The system does not generate a financial object when you save even if automatic financial object integration is active. You have already created a financial object for the bond.

**Example**

A bank is the issuer of a reverse convertible bond. The bond is issued on 07/17/2002. The bond class with security ID number329706 gives the issuer the right to repay the class with 18 units of company A’s stock instead of EUR 10,000 on 08/17/2004. Company A’s stock has the security ID number 840400. The issuer pays an interest rate of 8.75%, (which is higher than the market interest rate) for this right.

From the investor’s perspective, this class can be split into a bond with the corresponding interest and repayment structure, and the sale of a put option. The put option is of the European exercise type, its term end is 08/17/04, and its strike is EUR 10,000 for 18 units of stock.

The following tables contain the entries that you would have to make for the generic transaction and the elementary transactions for this example.

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Master Data|Security ID Number|329706|Security ID number of bond|
|Master Data|Short Name|8.75%|Appropriate name for reverse convertible bond|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Master Data|Status|9|Generic transaction is class supplement|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|07/17/2002|Issue date of the bond|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Security ID Number|329706|Security ID number of bond|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|07/17/2002|Issue date of the bond|
|Header Information|End of Term|08/17/2004|Due date of bond|
|Header Information|Purchase/Sale|200|Sale|
|Options Information|Option Category|1|Standard option|
|Options Information|Exercise Type|1|European exercise type|
|Options Information|Put/Call Indicator|1|Put, as the issuer has the option of selling stock to repay the bond|
|Options Information|Strike amount|10,000|Nominal amount of bond|
|Options Information|Strike Currency|EUR|Currency of the bond|
|Options Information|Delivery of Underlying|08/17/2004|Due date of bond|
|Options Information|Quotation of Underlying|Direct quotation| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Spot/Forward|1|Spot transaction|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Header Information|Security ID Number|840400|Security ID number of stock|
|Header Information|Exchange|FFM|Frankfurt am Main|
|Header Information|Quotation Type|2|Direct quotation|
|Header Information|Number of Units|18|Number of units of stock|

###### Hit-at-the-end Option

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Hit-at-the-end Option | L6 | trm02 p.65 | loio `eb10da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/eb10da531198434de10000000a174cb4.html?locale=en-US)

A digital option is a bet on a result that is characterized by the strike, and by “up” (call) or “down” (put).If the option is exercised, a fixed amount (the rebate) is paid.A digital up 0.93 on the US dollar is an example of a bet that the EUR/USD exchange rate will be

greater than 0.93 when the option is exercised.Whether the exchange rate before or after the exercise date is higher, does not matter.

In order to valuate a hit-at-the-end option, you must create it as a generic transaction.

**Procedure**

Create the following hierarchy of elementary transactions in order to depict digital options, such as hit-at-the-end options:

[figure TRM02-F072 - Create the hierarchy as follows:(The following depicts the transaction from the perspective of the owner of the option).]

Create the hierarchy as follows:(The following depicts the transaction from the perspective of the owner of the option).

Create a new generic transaction.See Edit Generic Transaction for the procedure.

In the dialog structure, select the first elementary transaction and assign to it transaction form 61 (OTC option).

The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Issue date of the option

Notification By field

Due date of the option

Purchase/Sale field

Purchase/investment

Enter any commission, charges, or premium payments on the Cash Flow tab page.


Note that, in the case of fixed cash flows, such as commission, the plus/minus sign must be taken into account, but the Direction field can be empty.The Direction field is only of significance for variable cash flows.

Flag the option as a hit-at-the-end option (in the example, up/call) with European-style exercise on the Options Information tab page. Enter the following information:

Rebate Amount and Rebate Currency fields

Amount that is to be paid for the underlying if the option is in-the-money when it becomes due.This amount does not include any accumulated interest (clean strike).

You do not need to enter the strike amount for options on foreign exchange transactions, as the amount is determined from the underlying of the specified cash flow.

Direction field

Inflow, as the example option is held.

Due Date field

Due date of rebate.

Create a transaction with transaction form 41 (foreign exchange) under the OTC Option elementary transaction.To do this, select the OTC Option elementary transaction in the dialog structure and choose Create Elementary Trans.: Next Level Select the new elementary transaction and assign to it transaction form 41.

The system displays two tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Start of term of option

Spot/forward field

Spot transaction

Purchase/Sale field

Set the indicator to Purchase/Investment Made .

Nominal Amount and Currency fields

Nominal volume and currency of spot exchange transaction.


The nominal volume does not affect the NPV calculation of the option.For technical reasons you must however make an entry in this field.

Create two cash flows on the Cash Flow tab page:One outgoing purchase cash flow and one incoming purchase cash flow.Enter the following information for both cash flows:

Cash Flow Type field

Purchase cash flow


Note that “cash flow type” is a Customizing term and can therefore be changed.The value that you select here must be assigned to the Purchase Payment Cash Flow indicator.

Due Date field

Due date of the option

CF Amount field

Amount and currency of the cash flow in question

Direction field

Flag the cash flows as outflows or inflows.

Choose Back and then Save .



**Result**

You have created the hit-at-the-end option as a generic transaction.

**Example**

A digital up of 0.93 is issued on the US dollar.The term start date is 03/01/2004 and the term end date is 11/30/2004. A rebate of 300,000 USD is agreed.

For this hit-at-the-end call option, the rebate is paid if the EUR/USD exchange rate is more than 0.93 on the exercise date.

Before you can create the option as a generic transaction, you must depict the strike as a spot exchange transaction: The rate EUR

- 0.93 per USD is equivalent to the quotient 93,000,000 EUR divided by 100,000,000 USD.


The following tables contain the entries that you would have to make for the generic transaction and the elementary transactions for this example.

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Master Data|Short Name|Digital up of 0.93 on USD|Appropriate name for convertible bond|
|Master Data|Category|0|Real generic transaction|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|03/01/2004|Start of Term|
|Header Information|End of Term|11/30/2004|Due date of option|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Options Information|Option Category|31|Hit-at-the-end call option|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Options Information|Exercise Type|1|European|
|Options Information|Put/Call Indicator|2|Call, as option is agreed as digital up|
|Options Information|Rebate currency|USD|Rebate currency|
|Options Information|Rebate amount|300,000|Rebate amount|
|Options Information|Direction|+|Inflow|
|Options Information|Due Date|11/30/2004|Due date of option|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|11/30/2004|Due date of option|
|Header Information|Spot/Forward|1|Spot transaction|
|Header Information|Nominal amount|93,000,000|Nominal volume of incoming cash flow|
|Header Information|Currency|EUR|Currency of incoming cash flow|
|Cash Flow (incoming cash flow)|Cash Flow Type|CA|Cash flow active|
|Cash Flow (incoming cash flow)|Cash Flow Amount|93,000,000|Incoming cash flow calculated from the strike|
|Cash Flow (incoming cash flow)|Currency|EUR|Currency of cash flow|
|Cash Flow (incoming cash flow)|Direction|+|Inflow|
|Cash Flow (outgoing cash flow)|Cash Flow Type|CA|Cash flow active|
|Cash Flow (outgoing cash flow)|Cash Flow Amount|100,000,000|Outgoing cash flow calculated from the strike|
|Cash Flow (outgoing cash flow)|Currency|USD|Currency of cash flow|
|Cash Flow (outgoing cash flow)|Direction|-|Outflow|



The tab pages may also contain other fields.You do not need to make entries in fields that are not included in this table as they are not relevant for valuating the generic transaction.

###### One-Touch Binary Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > One-Touch Binary Options | L6 | trm02 p.69 | loio `6e0fda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6e0fda531198434de10000000a174cb4.html?locale=en-US)

A digital one-touch binary option pays out a fixed amount (the rebate) as soon as the agreed price limit (barrier) is reached.This can happen at any time within the term of the option.

This option category is always European as it is not possible to exercise the option early (the option pays out automatically the first time it is in-the-money).

In order to valuate a one-touch binary option, you must create it as a generic transaction.

**Procedure**

Create the following hierarchy of elementary transactions in order to depict digital options, such as one-touch binary options:

[figure TRM02-F079 - Create the hierarchy as follows:]

Create the hierarchy as follows:

Create a new generic transaction.See Edit Generic Transaction for the procedure.

In the dialog structure, select the first elementary transaction and assign to it transaction form 61 (OTC option).

The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Issue date of the option

Notification By field

Due date of the option

Purchase/Sale field

Purchase transaction

Enter any commission, charges, or premium payments on the Cash Flow tab page.


Note that, in the case of fixed cash flows, such as commission, the plus/minus sign must be taken into account, but the Direction field can be empty.The Direction field is only of significance for variable cash flows.

Flag the option as a one-touch barrier option (call or put) with European-style exercise on the Options Information tab page. Enter the following information:

Put/Call Indicator field

Specify whether the option is a put or a call.

Strike Currency field


By entering the strike currency, you determine the currency of the option.You do not need to specify a strike.Instead, enter a barrier.

Barrier Rate 1 field

Enter the rate at which the option is exercised.

- Create a transaction with transaction form 41 (foreign exchange) under the OTC Option elementary transaction.To do this, select the OTC Option elementary transaction in the dialog structure and choose Create Elementary Trans.: Next Level Select the new elementary transaction and assign to it transaction form 41.


The system displays two tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Start of term of option

Spot/forward field

Spot transaction

Purchase/Sale field

Purchase/investment

Nominal Amount and Currency fields

Nominal volume and currency of spot exchange transaction.


The nominal volume does not affect the NPV calculation of the option.For technical reasons you must however make an entry in this field.

Create two cash flows on the Cash Flow tab page:One outgoing purchase cash flow and one incoming purchase cash flow.Enter the following information for both cash flows:

Cash Flow Type field

Purchase cash flow


Note that “cash flow type” is a Customizing term and can therefore be changed.The value that you select here must be assigned to the Purchase Payment Cash Flow indicator.

Due Date field

Due date of the option

CF Amount field

Amount and currency of the cash flow in question

Direction field

Flag one cash flow as an outflow, and the other as an inflow.

Choose Back and then Save



**Result**

You have created a one-touch barrier option as a generic transaction.

**Example**

The start of the term of a one-touch barrier option is 03/01/2004 and the end of the term is 11/30/2004. A rate of 0.95 EUR/USD and a strike of 0.93 EUR/USD have been agreed.

Before you can create the option as a generic transaction, you must depict the barrier as a spot exchange transaction: The rate EUR 0.93 per USD is equivalent to the quotient 93,000,000 EUR divided by 100,000,000 USD.

The following tables contain the entries that you would have to make for the generic transaction and the elementary transactions for this example.

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Master Data|Short Name|Barrier option|Appropriate name for convertible bond|
|Master Data|Status|0|Real generic transaction|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|03/01/2004|Start of term|
|Header Information|End of Term|11/30/2004|Due date of option|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Options Information|Option Category|61|Hit-at-the-end option|
|Options Information|Exercise Type|1|European|
|Options Information|Put/Call Indicator|2|Call, as option is agreed as digital up|
|Options Information|Strike Currency|EUR|Rebate currency|
|Options Information|Barrier Rate 1|0.95|Rate at which the option is exercised|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|11/30/2004|Due date of option|
|Header Information|Spot/Forward|1|Spot transaction|
|Header Information|Nominal Amount|93,000,000|Nominal volume of incoming cash flow|
|Header Information|Currency|EUR|Currency of incoming cash flow|
|Cash Flow (incoming cash flow)|Cash Flow Type|06|Cash flow active|
|Cash Flow (incoming cash flow)|Cash Flow Amount|93,000,000|Outgoing cash flow calculated from the strike|
|Cash Flow (incoming cash flow)|Currency|EUR|Currency of cash flow|
|Cash Flow (incoming cash flow)|Direction|-|Outflow|
|Cash Flow (outgoing cash flow)|Cash Flow Type|06|Cash flow active|
|Cash Flow (outgoing cash flow)|Cash Flow Amount|100,000,000|Incoming cash flow calculated from the strike|
|Cash Flow (outgoing cash flow)|Currency|USD|Currency of cash flow|
|Cash Flow (outgoing cash flow)|Direction|+|Inflow|

###### Bermuda Options (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Bermuda Options | L6 | trm02 p.73 | loio `f710da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f710da531198434de10000000a174cb4.html?locale=en-US)

A Bermuda option consists of a number of predetermined exercise opportunities. The holder of the option must submit an exercise notice before actually exercising the option.Each exercise opportunity has an exercise notice deadline, which is fixed and binding.In the case of European-style options, the exercise notice is issued on the notice period end date only (that is, on the exercise notice deadline). With American-style options on the other hand, notice can be issued at any time up to and including the notice period end date. The lead time (the period between notice being given and the option being exercised) is fixed and is binding.

In order to valuate Bermuda options, you must create them as generic transactions.


An option is provided in the internal processing structure for each of the possible exercise opportunities.Each suboption is defined by its notice period end date and the lead time.

**Procedure**

Create the following hierarchy to depict a Bermuda option as a generic transaction:In this example, the Bermuda option has two exercise opportunities and a fixed-term deposit as the underlying.

In general, the following applies:

You create an elementary transaction with the Exercise Opportunity transaction form.You then create each individual elementary transaction under the previous elementary transaction, and always one layer deeper.The exercise opportunity with the earliest notification deadline is the first exercise opportunity in the hierarchy, and the exercise opportunity with the latest notification

deadline is penultimate exercise opportunity in the hierarchy. The last elementary transaction is the elementary transaction for the underlying.

You can currently use the following transaction forms for the underlying: Mortgage/interest rate instrument, loan, bond, zero bond, fixed-interest-rate bond, participation certificate, fixed-term deposit, commercial paper, swap, forward rate agreement, cash flow, reference to an original transaction or to an external transaction.

[figure TRM02-F087 - Create the hierarchy as follows:]

Create the hierarchy as follows:

Create a new generic transaction.See Editing Generic Transactions for the procedure.

In the dialog structure, select the first elementary transaction and assign to it transaction form 63 (exercise opportunity).

The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Start of first notice period for the Bermuda option.

Notification By field

End date of notice period for the first exercise opportunity.

Purchase/Sale field

Enter whether the Bermuda option is a purchase or a sale.


The system interprets the Bermuda option as a purchase or a sale depending on the entries you make for the elementary transaction on the highest level of the hierarchy.

On the Options Information tab page, enter the exercise type of the option, and enter the following information:

Exercise Type field

Specify whether American-style or European-style exercise applies to the Bermuda option.

Lead Time field

Time between notice and exercise of the option.

Put/Call Indicator

Flag the Bermuda option as a put option or a call option.

Strike Amount and Strike Currency fields

Clean strike amount of exercise opportunity (price of underlying without accrued interest).


You do not need to enter a strike amount if the underlying is a swap.The system uses the variable side of the swap to determine the strike amount.

Enter the option premium on the Cash Flow tab page.This is cash flow type 9 (charges, commission).


You must enter a term start date for the option, although it is not used by the price calculator for evaluation purposes.

Create a transaction with transaction form 63 (exercise opportunity) for the second exercise option below the Exercise Opportunity elementary transaction.To do this, select the Exercise Opportunity elementary transaction in the dialog structure and choose Create Elementary Trans.: Next Level Select the new elementary transaction and assign to it transaction form 63.

The system displays three tab pages. Make the necessary entries as for step 2.


Note that you need to set the Purchase/Sale indicator for the first exercise opportunity only.The system ignores the Purchase/Sale indicator if it is set in elementary transactions with the Exercise Opportunity transaction form in lower levels of the hierarchy.

In contrast, the entries in the following fields do not have to be the same for all the individual elementary transactions: Start of Term, Notification By, Lead Period .

Note the following restrictions: The start dates of the terms of the individual exercise opportunities must be in chronological order.The start of the notice period for one exercise opportunity must be before the start of the term of the next exercise opportunity.

- Create a transaction with transaction form 42 (fixed-term deposit) under the second Exercise Opportunity elementary transaction.Proceed as for step 3.


The system displays two tab pages.

Enter the following information on the Header Information tab page:

Spot/Forward field

Spot transaction

Purchase/Sale field

The underlying must always be flagged as a purchase transaction.

Nominal Amount and Currency

Nominal amount of fixed-term deposit

Choose Back and then Save.



**Result**

You have created a Bermuda option as a generic transaction.

**Example**

A bank issues a Bermuda option that gives the purchaser the right to enter into a contract for a fixed-term deposit.The fixed-term deposit would have a nominal volume of 1 million euros and an interest rate of 5%.The fixed-term deposit has a term of two years and starts on 01/01/2006. Repayments and interest payments are made on 12/31/ of each year. The purchaser can exercise the option either on 01/01/2005 at a strike of 980,000 euros, or on 01/01/2006 at a strike of 1,000,000 euros.The lead time for both exercise opportunities is one month. The purchaser must issue notice on the exercise of the option on 12/01/2004 or 12/01/2005.The exercise type is therefore European.

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|01/01/2003|First exercise opportunity for Bermuda option.Field is not relevant for the valuation as exercise opportunity is European|
|Header Information|Notification By|12/01/2004|End of the period of notice for the first exercise date|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Options Information|Exercise Type|1|European|
|Options Information|Lead Time|31|Lead Time in Days|
|Options Information|Put/Call Indicator|2|Call|
|Options Information|Strike Amount|980,000|The strike is zero, as the underlying is a forward transaction from the perspective of the first exercise opportunity|
|Options Information|Strike Currency|EUR| |
|Cash Flow|Cash Flow Type|6|Purchase Cash Flow|
|Cash Flow|Cash Flow Amount|2,200|Charges and commission|
|Cash Flow|Currency|EUR| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow|Side|0|Incoming and outgoing|
|Cash Flow|Direction|-|Outflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|11/30/2004|Start of term of Bermuda option|
|Header Information|Notification By|12/01/2005|End of the period of notice for the first exercise date|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Options Information|Exercise Type|1|European|
|Options Information|Lead Time|31|Lead Time in Days|
|Options Information|Put/Call Indicator|1|Put|
|Options Information|Strike Amount|1,000,000| |
|Options Information|Strike Currency|EUR| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Spot/Forward|1|Spot transaction|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Header Information|Nominal amount|1,000,000| |
|Header Information|Currency|EUR| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow|Cash Flow Type|Purchase Cash Flow|“Cash flow type” is a customizing term.The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Cash Flow Amount|1,000,000|Nominal volume of fixed-term deposit|
|Cash Flow|Due Date|01/01/2006| |
|Cash Flow|Currency|EUR| |
|Cash Flow|Percentage|0| |
|Cash Flow|Direction|-|Outflow|
|Cash Flow|Exchange rate|0| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow|Cash Flow Type|Interest cash flow|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Due Date|12/31/2006| |
|Cash Flow|Cash Flow Amount|50,000|Interest amount|
|Cash Flow|Currency|EUR| |
|Cash Flow|Percentage|0| |
|Cash Flow|Direction|+|Inflow|
|Cash Flow|Exchange rate|0| |
|Cash Flow|Calculation from|01/01/2006| |
|Cash Flow|Calculation to|12/31/2006| |
|Cash Flow|Interest Calculation Method|3|act/365|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow|Cash Flow Type|2|Interest cash flow|
|Cash Flow|Due Date|12/31/2007| |
|Cash Flow|Cash Flow Amount|50,000|Interest amount|
|Cash Flow|Currency|EUR| |
|Cash Flow|Percentage|0| |
|Cash Flow|Direction|+|Inflow|
|Cash Flow|Exchange Rate|0| |
|Cash Flow|Calculation from|01/01/2007| |
|Cash Flow|Calculation to|12/31/2007| |
|Cash Flow|Interest Calculation Method|3|act/365|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow|Cash Flow Type|Sale cash flow|“Cash flow type” is a customizing term.The value of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Due Date|12/31/2007| |
|Cash Flow|Cash Flow Amount|1,000,000|Nominal volumes of fixed-term deposit|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow|Currency|EUR| |
|Cash Flow|Percentage|0| |
|Cash Flow|Direction|+|Inflow|
|Cash Flow|Exchange Rate|0| |

###### Basket Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Basket Options | L6 | trm02 p.79 | loio `d010da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d010da531198434de10000000a174cb4.html?locale=en-US)

Basket options are options with more than one underlying. The value of a basket option, therefore, is equal to the total value of the individual underlyings.

**Integration**

The system is currently only able to valuate basket options with the following properties:

European exercise type

Foreign exchange transactions as underlyings


The system can also valuate average spot basket options. The value of these options is not calculated on the basis of a spot at any one particular point in time, but rather by calculating average values over a time series. To create an average spot basket option, follow the procedure as defined below, but use the average spot basket option category of option. For more information about setting up a time series, see the Creating Average Spot Options document.

For more information about valuating basket options, see the Basket Options and Average Spot Options document in the Price Calculator documentation.

**Procedure**

Create the following hierarchy to display a basket option as a generic transaction: In the figure below you can see a basket option with three foreign exchange transactions used as underlyings.

[figure TRM02-F095 - Create the hierarchy as follows:]

Create the hierarchy as follows:

Create a new generic transaction. See Edit Generic Transaction for the procedure.

In the dialog structure, select the first elementary transaction and assign to it transaction form 061 (OTC option).

The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Enter the start date for the term of the option.

End of term field.

Enter the due date for the option.

Purchase/Sale field

Enter whether the OTC option is a purchase or a sale.


The system interprets the OTC option as a purchase or a sale depending on the entries you make for the elementary transaction on the highest level of the hierarchy.

Enter the following information on the Cash Flow tab page:

Cash Flow Type field

Specify the type of the cash flow (for example, sale or purchase cash flow).

Due Date field

Specify when the premium payment for the option is due.

CF Amount field

Currency field

Currency of cash flow

Plus/Minus Sign field

Specify if the cash flow represents an in- or an outflow.

Enter the following information on the Option Information tab page:

Option Category field

Assign the option to the basket option category.

Exercise Type field

The system can currently only process basket options with a European exercise type.

Put/Call Indicator field

Select the Bermuda option as either a put option or a call option.


You must enter a term start date for the option, although it is not used by the price calculator for evaluation purposes.

Create a transaction with the transaction form 41 (foreign exchange) under the OTC option elementary transaction for the first elementary transaction at the second level. To do this, select the OTC Option elementary transaction in the dialog structure and choose Create Elementary Trans.: Next Level . Select the new elementary transaction and assign to it transaction form 41.


The system displays three tab pages. Specify two cash flows on the Cash Flow tab page that have different plus/minus signs. The ratio of the first cash flow to the second is equal to the strike rate.

Create another transaction with transaction form 41 (foreign exchange) under the second Foreign Exchange elementary transaction. Proceed as for step 3.

Create another transaction with transaction form 41 (foreign exchange) under the second Foreign Exchange elementary transaction. Proceed as for step 3.

Select Back and then Save



**Result**

You have created a basket option with an OTC option as an elementary transaction on the first level of the hierarchy, and three elementary transactions of the Foreign Exchange transaction form on the second level.

**Example**

A French firm carries out business in America, Australia, and Switzerland and wants to protect itself from a possible decline in foreign currencies. The amounts to be hedged are 24,600,000 USD, 12,300,000 AUD and 23,400,000 CHF. The company buys an basket put option at 50 billion euro that runs for over a year, and is due on 23.03.2005. The exchange rates in force at the time the option was concluded are agreed upon as the option’s strike price.

- 1.23 euro per US dollar


1.64 euro per Australian dollar

1.56 euro per Swiss Franc

Note that when creating a basket option as a generic transaction, the strike prices must be represented by two cash flows (one in euro, and one in the other respective foreign currency).

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|23.03.2004|You must enter the start of the term of the option. This is, however, not relevant to the price calculator valuations.|
|Header Information|End of Term|23.03.2005|Due date of option|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Cash Flow|Cash Flow Type|05|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Due Date|26.03.2004|Date on which the premium is paid.|
|Cash Flow|Cash flow amount|1.698.000-|You must specify the plus/minus sign for the premium payment for the amount as well as for the Direction field.|
|Cash Flow|Currency|EUR| |
|Cash Flow|Direction|-|Outflow|
|Option Information|Option Category|50|Basket Option|
|Option Information|Exercise Type|European| |
|Option Information|Strike Currency|EUR| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow 1|Due Date|23.03.2005|The due date is the same as the date on which the term ends.|
|Cash Flow 1|Cash flow amount|20.000.000-|You must specify the plus/minus sign for the premium payment for the amount as well as for the Direction field.|
|Cash Flow 1|Currency|EUR| |
|Cash Flow 1|Direction|-|Outflow|
|Cash Flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow 2|Due Date|23.03.2005|The due date is the same as the date on which the term ends.|
|Cash Flow 2|Cash flow amount|24.600.000| |
|Cash Flow 2|Currency|USD| |
|Cash Flow 2|Direction|+|Inflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow 1|Due Date|23.03.2005|Option due date|
|Cash Flow 1|Cash flow amount|7.500.000-|You must specify the plus/minus sign for the premium payment for the amount as well as for the Direction field.|
|Cash Flow 1|Currency|EUR| |
|Cash Flow 1|Direction|-|Outflow|
|Cash Flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
| | | |depending on the Customizing settings|
|Cash Flow 2|Due Date|23.03.2005|The due date is the same as the date on which the term ends.|
|Cash Flow 2|Cash flow amount|12.300.000| |
|Cash Flow 2|Currency|AUD| |
|Cash Flow 2|Direction|+|Inflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow 1|Due Date|23.03.2005|Option due date|
|Cash Flow 1|Cash flow amount|15.000.000-|You must specify the plus/minus sign for the premium payment for the amount as well as for the Direction field.|
|Cash Flow 1|Currency|EUR| |
|Cash Flow 1|Direction|-|Outflow|
|Cash Flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow 2|Due Date|23.03.2005|Option due date|
|Cash Flow 2|Cash flow amount|23.400.000| |
|Cash Flow 2|Currency|CHF| |
|Cash Flow 2|Direction|+|Inflow|

###### Average Spot Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Average Spot Options | L6 | trm02 p.84 | loio `e210da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e210da531198434de10000000a174cb4.html?locale=en-US)

Average spot options are options with exactly one underlying. Their value is not calculated on the basis of the current underlying spot, but using the average value. The average value is based on a time series with specific dates/times on which the spot of the underlying is fixed.

**Integration**

The following restrictions presently apply to the valuation of average spot options:

The system can currently only valuate average spot options with a European exercise type (European options).

The averages are only gathered at specific, predefined times that are equally distanced.

The system uses the arithmetic average with identical weightings to calculate the averages.


For more information on valuating the average spot options, see the Basket Options and Average Spot Options document in the Price Calculator documentation.

**Procedure**

Create the following hierarchy to display an average spot option as a generic transaction:

[figure TRM02-F102 - Create the following hierarchy to display an average spot option as a generic transaction:]

Create the hierarchy as follows:

Create a new generic transaction. See Edit Generic Transaction for the procedure.

.

In the dialog structure, select the first elementary transaction and assign to it transaction form 061 (OTC option).

The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Enter the start date for the term of the option.

End of term field.

Enter the end date for the term of the option.

Purchase/Sale field

Enter whether the OTC option is a purchase or a sale.


The system interprets the OTC option as a purchase or a sale depending on the entries you make for the elementary transaction on the highest level of the hierarchy.

Enter the following information on the Cash Flow tab page:

Cash Flow Type field

Specify the type of the cash flow (for example, sale or purchase cash flow).

Due Date field

Specify when the premium of the option is due.

CF Amount field

Currency field

Currency of the individual cash flows

Plus/Minus Sign field

Specify if the cash flow represents an in- or an outflow.

Enter the following information on the Option Information tab page:

Exercise Type field

Specify whether American-style or European-style exercise applies to the OTC option.


The price calculator is only able to valuate European-style exercise types.

Put/Call Indicator

Flag the OTC option as a put option or a call option.

Strike Amount and Strike Currency fields

Clean strike amount of option (price of underlying without accrued interest).

Number of Averaging Time Points field

Specify the number of planned fixing dates.

Number of Fixed Points field

Specify how many spots have already been fixed.

Next Averaging Date field

Specify when the next spot is to be fixed.

Mean Value of Exercise Price field

Specify the mean value of the spots that have already been fixed.


You must manually update the Number of Fixed Points, Next Averaging Date and Mean Value of Exercise Price fields. The system is unable to automatically correct or update the data.


You must enter a term start date for the option, although it is not used by the price calculator for evaluation purposes.

Create a transaction with the transaction form 41 (foreign exchange) under the OTC option elementary transaction for the first elementary transaction on the second level of the hierarchy. To do this, select the OTC Option elementary transaction in the dialog structure and choose Create Elementary Trans.: Next Level . Select the new elementary transaction and assign to it transaction form 41.

The system displays three tab pages. Specify two cash flows on the Cash Flow tab page that have different plus/minus signs. The ratio of the first cash flow to the second is equal to the strike rate.

Select Back and then Save

**Result**

You have created an average spot option with an elementary transaction of transaction form 61 (OTC option) on the first (highest) level of the hierarchy, and with a elementary transaction of the transaction form 41 (foreign exchange) on the lower, second level.

**Example**

A US company with a yearly revenue of 1.3 billion euro wants to protect itself from falling US dollar rates. The company buys an

average rate put option at 1,3 billion euro that runs for a year and is due on 3.19.2005. In the month before the option is due, the euro/US dollar exchange rate is measured on every working day, and the readings are used to calculate the averages. The strike price for the option is the exchange rate at the time the option is concluded, 1.22 euro for each US dollar. The option premium is 460 million euro.

To valuate this option, create a corresponding generic transaction with the value Average Spot Transaction. To do this you need to make the following preparations and simplifications:

The strike price is shown in the system as a foreign exchange transaction with two cash flows in US dollars and euro. The euro-cash flow has an amount of 1.3 billion euro and represents an inflow (as a put-option was agreed). The US dollar cash flow amount is calculated using the strike rate.

The spot averaging is defined using the first averaging date and the number of grid points. Because the system only uses equidistant grid points, it can only enter the 2.19.2005 as the start date, and 20 as the number of grid points, without the days used necessarily being working days.

These simplifications usually only have, however, limited influence on the calculated NPVs of the option.

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|19.3.2004|You must enter the start of the term of the option. This is, however, not relevant to the price calculator valuations.|
|Header Information|End of Term|19.3.2005|The end of the term is the same date as the date of the last fixing point.|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Cash Flow|Cash Flow Type|05|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Due Date|22.3.2004|Date option premium payment is due.|
|Cash Flow|Cash flow amount|460.000.000-|Premium cash flow For payments, you must enter the ʻ-ʻ sign after the cash flow amount and in the Direction field.|
|Cash Flow|Currency|EUR| |
|Cash Flow|Direction|-|Outflow|
|Option Information|Option Category|2|Average rate option|
|Option Information|Type of Exercise|1|European|
|Option Information|Put/Call Indicator|1|Put|
|Option Information|Strike Amount|1.300.000.000|You do not have to enter the strike price amount. If you do, the system automatically overwrites the cash flow amount with the same currency.|
|Option Information|Strike Currency|EUR| |
|Option Information|Number of Averaging Times/Dates|20|Number of grid points for the calculation of averages.|
|Option Information|Number of Fixed Points|0|You have to update the spots that have already been fixed|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
| | | |manually. The system does not do this automatically.|
|Option Information|Next Averaging Date|20.2.2005|You have to update the next averaging date manually. The system does not do this automatically.|
|Option Information|Mean Value of Exercise Price|0|You have to update the mean value of the spots that have already been fixed manually. The system does not do this automatically.|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow 1|Due Date|19.3.2005|End of term of option|
|Cash Flow 1|Cash flow amount|1.300.000.000|Strike price amount in local currency|
|Cash Flow 1|Currency|EUR|Local currency|
|Cash Flow 1|Direction|+|Inflow|
|Cash Flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow 2|Due Date|19.3.2005|End of term of option|
|Cash Flow 2|Cash flow amount|1.066.000.000-|Strike price amount in foreign currency. For payments, you must enter the ʻ-ʻ sign after the cash flow amount and in the Direction field.|
|Cash Flow 2|Currency|USD|Foreign currency|
|Cash Flow 2|Direction|-|Outflow|

###### Correlation Options (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Correlation Options | L6 | trm02 p.89 | loio `c310da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c310da531198434de10000000a174cb4.html?locale=en-US)

**Use**

A correlation option consists of a basket option and a plain vanilla option for every individual underlying contained in the basket option. The long position of a correlation option consists of the short position of a basket option and the long position of the plain

vanilla options with an underlying.


Alternatively, a correlation option can also consist of an average spot basket option and the corresponding average spot options. For more information on creating these options, see the Create Average Spot Options document.


For more information about valuating correlation options, see the Correlation Options document in the Price Calculator documentation.

**Integration**

For more information on the restrictions that apply to the basket options contained in the correlation options, see the Create Basket Options document. The average spot option restrictions are explained in the Create Average Spot Options document.

**Procedure**

Create the following hierarchy to display a correlation option as a generic transaction: In the figure below you can see a correlation option with three foreign exchange transactions as underlyings.

[figure TRM02-F109 - Create the hierarchy as follows:]

Create the hierarchy as follows:

Create a new generic transaction. See Edit Generic Transaction for the procedure.

In the dialog structure, select the first elementary transaction and assign to it transaction form 200 (complex financial transaction).

The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Enter the start date for the term of the complex financial transaction.

End of term field.

Specify the end of the term of the financial transaction.

Purchase/Sale field

Specify whether the financial transaction is a purchase or a sale.


The system interprets the financial transaction as a purchase or a sale depending on the entries you make for the elementary transaction at the highest level of the hierarchy.

Creating the Basket Option:

Create a transaction with the transaction form 61 (OTC Option) under the Complex Financial Transaction elementary transaction for the first elementary transaction at the second level. To do this, select the Complex Financial Transaction elementary transaction in the dialog structure and choose Create Elementary Trans.: Next Level . Select the new elementary transaction and assign to it transaction form 61.

The system displays three tab pages. See the Create Basket-Option document for a description on how to fill the fields and create more elementary transactions.

Creating Individual Options:

Create three further transactions of the transaction form 61 (OTC Option) at the same level as the first elementary transaction ( OTC Option ). Then add an elementary transaction of the transaction form 41 (foreign currency) at the second, lower level of the hierarchy.


The three elementary transactions of the transaction form 41 (foreign currency) of the basket option are identical to the three elementary transactions of the same transaction form from the average rate option.

Select Back and then Save



**Result**

You have created a correlation option consisting of a basket option and three individual options.

**Example**

**The correlation option is made up of the basket option as described in the Create Basket Option documentation, and the corresponding individual options.**

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|23.3.2004| |
|Header Information|End of Term|23.3.2005| |
|Header Information|Purchase/Sale|100| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|23.3.2004| |
|Header Information|End of Term|23.3.2005| |
|Header Information|Purchase/Sale|200|Sale|
|Option information|Option Category|50|Basket Option|
|Option information|Type of exercise|1|European|
|Option information|Put/Call Indicator|1|Put|
|Option information|Strike Currency|EUR| |
|Cash Flow|Cash Flow Type|05|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Due date|26.3.2004| |
|Cash Flow|Cash flow amount|1,698,000-| |
|Cash Flow|Currency|EUR| |
|Cash Flow|Direction|-|Outflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 1|Due Date|23.3.2005| |
|Cash flow 1|Cash flow amount|20,000,000-| |
|Cash flow 1|Currency|EUR| |
|Cash flow 1|Direction|-|Outflow|
|Cash flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
| | | |depending on the Customizing settings|
|Cash flow 2|Due Date|23.3.2005| |
|Cash flow 2|Cash flow amount|24,600,000| |
|Cash flow 2|Currency|USD| |
|Cash flow 2|Direction|+|Inflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 1|Due Date|23.3.2005| |
|Cash flow 1|Cash flow amount|7,500,000-| |
|Cash flow 1|Currency|EUR| |
|Cash flow 1|Direction|-|Outflow|
|Cash flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 2|Due Date|23.3.2005| |
|Cash flow 2|Cash flow amount|12,300,000| |
|Cash flow 2|Currency|AUD| |
|Cash flow 2|Direction|+|Inflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 1|Due Date|23.3.2005| |
|Cash flow 1|Cash flow amount|15,000,000-| |
|Cash flow 1|Currency|EUR| |
|Cash flow 1|Direction|-|Outflow|
|Cash flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
| | | |the cash flow type can vary depending on the Customizing settings|
|Cash flow 2|Due Date|23.3.2005| |
|Cash flow 2|Cash flow amount|23,400,000| |
|Cash flow 2|Currency|CHF| |
|Cash flow 2|Direction|+|Inflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|23.3.2004| |
|Header Information|End of Term|23.3.2005| |
|Header Information|Purchase/Sale|100|Purchase/investment|
|Cash Flow|Cash Flow Type|05|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Due Date|26.3.2004|Specifies the date on which the premium of the option is paid.|
|Cash Flow|Cash flow amount|?| |
|Cash Flow|Currency|EUR| |
|Cash Flow|Direction|-|Outflow|
|Option information|Option Category|01|Standard|
|Option information|Type of exercise|1|European|
|Option information|Put/Call Indicator|1|Put|
|Option information|Strike Currency|EUR| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 1|Due Date|23.3.2005| |
|Cash flow 1|Cash flow amount|20,000,000-| |
|Cash flow 1|Currency|EUR| |
|Cash flow 1|Direction|-|Outflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 2|Due Date|23.3.2005| |
|Cash flow 2|Cash flow amount|24,600,000| |
|Cash flow 2|Currency|USD| |
|Cash flow 2|Direction|+|Inflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|23.3.2004| |
|Header Information|End of Term|23.3.2005| |
|Header Information|Purchase/Sale|100|Purchase/investment|
|Cash Flow|Cash Flow Type|05|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Due Date|26.3.2004|Specifies the date on which the premium of the option is paid.|
|Cash Flow|Cash flow amount|?| |
|Cash Flow|Currency|EUR| |
|Cash Flow|Direction|-|Outflow|
|Option information|Option Category|01|Standard|
|Option information|Type of exercise|1|European|
|Option information|Put/Call Indicator|1|Put|
|Option information|Strike Currency|EUR| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 1|Due Date|23.3.2005| |
|Cash flow 1|Cash flow amount|7,500,000-| |
|Cash flow 1|Currency|EUR| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash flow 1|Direction|-|Outflow|
|Cash flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 2|Due Date|23.3.2005| |
|Cash flow 2|Cash flow amount|12,300,000| |
|Cash flow 2|Currency|AUD| |
|Cash flow 2|Direction|+|Inflow|


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|23.3.2004| |
|Header Information|End of Term|23.3.2005| |
|Header Information|Purchase/Sale|100|Purchase/investment|
|Cash Flow|Cash Flow Type|05|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Due Date|26.3.2004|Specifies the date on which the premium of the option is paid.|
|Cash Flow|Cash flow amount|?| |
|Cash Flow|Currency|EUR| |
|Cash Flow|Direction|-|Outflow|
|Option information|Option Category|01|Standard|
|Option information|Type of exercise|1|European|
|Option information|Put/Call Indicator|1|Put|
|Option information|Strike Currency|EUR| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash flow 1|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 1|Due Date|23.3.2005| |
|Cash flow 1|Cash flow amount|15,000,000-| |


|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash flow 1|Currency|EUR| |
|Cash flow 1|Direction|-|Outflow|
|Cash flow 2|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash flow 2|Due Date|23.3.2005| |
|Cash flow 2|Cash flow amount|23,400,000| |
|Cash flow 2|Currency|CHF| |
|Cash flow 2|Direction|+|Inflow|

###### Forward Volatility Agreement

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Forward Volatility Agreement | L6 | trm02 p.98 | loio `0e11da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0e11da531198434de10000000a174cb4.html?locale=en-US)

A forward volatility agreement is an agreement to sell or buy a straddle sometime in the future. A straddle is a combination of a call option and a put option with the same underlying, expiration date, and strike price.

The contracting parties determine the strike price of the straddle on the day the term of the option begins. This is also the forward date. The strike price is set as equal to the forward spot for the expiration date of the straddle. Similarly, the premium of the forward volatility agreement is defined and paid on the forward date. This is based on the forward volatility that is agreed upon at the start of the contract.


For more information about valuating forward volatility agreements, see the Forward Volatility Agreement document in the Price Calculator documentation.

**Procedure**

Create the following hierarchy to display a forward volatility agreement as a generic transaction: The options included in the forward volatility agreement are not explicitly specified. You can find information about options in the top node, which has the transaction form 65 (forward volatility agreement). The node at the next level down in the hierarchy has the transaction form 41 (foreign exchange transaction), and contains the foreign currency cash flow, specifying the underlying of the option.

[figure TRM02-F115 - Create the hierarchy as follows:]

Create the hierarchy as follows:

Create a new generic transaction. See Edit Generic Transaction for the procedure.

In the dialog structure, select the first elementary transaction and assign to it transaction form 065 (forward volatility agreement).

The system displays three tab pages.

Enter the following information on the Header Information tab page:

Start of term field.

Option start date (this is the same as the end date of the forward transaction)


The system uses the date you created the forward volatility agreement on as the start date for the forward transaction.

End of term field.

End date of option

Purchase/Sale field

Specify whether the forward volatility agreement is a purchase or a sale.


The system interprets the forward volatility agreement as a purchase or a sale depending on the entries you make for the elementary transaction at the top of the hierarchy.

The Cash Flow tab page is not relevant to valuating the forward volatility agreement.

Only the following fields on the Option Information tab page are relevant:

Strike Currency field

Transaction currency

Forward Volatility field

Specify the agreed forward volatility. You specify this for the year, even if the volatility relates to the term of the option.


The Exercise Type field is not relevant here because the price calculator is presently only able to valuate forward volatility agreements with a European type of exercise. The Put/Call indicator remains empty (in a forward volatility agreement, the put and call options are the same.)

Create a transaction with the transaction form 41 (foreign exchange) under the Forward Volatility Agreement elementary transaction for the first elementary transaction at the second, lower level in the hierarchy. To do this, select the Forward Volatility Agreement elementary transaction in the dialog structure and choose Create Elementary Trans.: Next Level .

Select the new elementary transaction and assign to it transaction form 41.

The system then displays three tab pages. Only the Cash Flow tab page is relevant. Enter the following information:

Due Date field

Date on which the payment is made.

Cash Flow Amount and Currency fields

Nominal value of the forward volatility agreements

Choose Back and then Save .



**Result**

You have created the forward volatility agreement as a generic transaction.

**Example**

A bank negotiates a forward volatility agreement to hedge against changes to the volatility of the euro/US dollar exchange rate. The underlying straddle is to be exchanged on January 12 2004. The due date for the option has been agreed on as February 12 2004. The underlying for the options is a cash flow of 1.2 million US dollars that is to be paid on the option due date.

To create the forward volatility agreement, you need the yearly forward volatility σforward of the euro/US dollar exchange rate for the straddle period. For example, if we take a transaction that was concluded on 12.12.2003, at that time, for the period t1 of a

month, we would have the volatility σ1 11.64, and for the period t2 of two months, the volatility σ2 10.90.

The following formulas apply to forward volatilities for volatility values that have already been annualized:

[figure TRM02-F121 - The following formulas apply to forward volatilities for volatility values that have already been annualized:]

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Header Information|Start of Term|12.01.2004|The start of term date specifies the date the life of the option begins. It is also the date the forward ends.|
|Header Information|End of Term|12.02.2004|Specifies the end of the option’s life.|
|Header Information|Purchase/Sale|100|Purchase/investment|
|Option Information|Strike Currency|EUR|Transaction currency|
|Option Information|Forward Volatility|10,11|Annualized forward volatility of the exchange rate for the term of the option.|



Because the price calculator does not evaluate them, the Option Category , Exercise Type , and Put/Call Indicator fields on the Option Information tab page can remain empty.

|Tab Page|Field|Example of Contents|Comment|
|---|---|---|---|
|Cash Flow|Cash Flow Type|06|“Cash flow type” is a customizing term. The values of the cash flow type can vary depending on the Customizing settings|
|Cash Flow|Due Date|12.02.2004|Date of payment|
|Cash Flow|Cash flow amount|1.200.000,00|Nominal value of the forward volatility agreements|
|Cash Flow|Currency|USD| |



The Direction field on the Cash Flow tab page can stay empty because the price calculator does not evaluate this area.

###### Caps, Floors, Collars

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Caps, Floors, Collars | L6 | trm02 p.101 | loio `d910da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d910da531198434de10000000a174cb4.html?locale=en-US)

Caps, floors, and collars are constructed as options on three levels.

In level 1 you define an elementary transaction with TFORM 050 (cap/floor/collar). At the level below that, the actual caplets and/or floorlets are set up. These are OTC options on interest rate references according to the classical definition of an option on an underlying transaction. On this level you need to create the relevant number of OTC options (TFORM 061).

**Note:**

You can only distinguish between caplets and floorlets based on the put/call indicator.

On level 3, an elementary transaction is defined as an underlying for each corresponding option on level 2 (TFORM 049 caplet/floor as underlying).

###### Forex Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > Forex Options | L6 | trm02 p.102 | loio `d610da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d610da531198434de10000000a174cb4.html?locale=en-US)

Forex options are defined on a two-level basis, as with options on underlyings. This means there is one elementary option transaction, and a subordinate elementary forex transaction. You first have to create the option transaction with transaction form 061 and the underlying with transaction 041.

Determine in advance what the forex transaction will look like (buy and sell flows). Specify in which of these two currencies the strike price currency will be. In the following documentation this will be referred to as the strike currency, and the other currency as the reference currency.

**Example:**

If the strike of a USD/EUR option were x EUR, then the strike currency would be EUR, and USD would be the reference currency.

Define two cash flows for the forex transaction, one each for the incoming and outgoing sides.

###### FIONA Swap

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Examples of Generic Transactions > FIONA Swap | L6 | trm02 p.102 | loio `f410da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f410da531198434de10000000a174cb4.html?locale=en-US)

**Note:**

You must define a cash flow type that is assigned to the cash flow indicator retained cashflow .

In the generic transaction hierarchy, you define only one elementary transaction with TFORM 51 (swap). You enter the data for the Swap elementary transaction in two detail screens:

|Tab Page|Fields Requiring Entries|
|---|---|
|Header Information|Term start and end|
|Cash Flow|Fixed cash flow: the cash flow type must correspond to an interest cash flow, cash flow amount, side and direction under cash flow addition, calculation interval and interest calculation method. Variable cash flow: the cash flow type defined above, nominal amount, reference interest rate and +/- sign, side and direction under cash flow addition, calculation interval (corresponds to interest fixing period) and interest calculation method.|

###### Internal Risk Objects

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Internal Risk Objects | L5 | trm02 p.102 | loio `b510da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b510da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

To allow all transactions access to Risk Analysis the system stores them internally in a standard data structure. This data structure is called an internal risk object (technical name SDTFT). If you want to implement external price calculators, or transfer the risk object using external data transfer, you must already know the technical structure of the risk object. For further information, see Interface to External Price Calculators.

**Note:**

With the transaction Edit Generic Transaction you can fill the structure of the risk object directly. Generic transactions can be used in this way to depict structured products and other financial derivatives.

**Use**

In Risk Analysis, the internal risk object can store complex or simple transactions using a structure and a hierarchy. It forms the basis for price calculators and evaluations, regardless of where the original data lies (external, or in TR-TM for example).

**Structure**

Description of SDTFTs

The SDTFT consists of the following parts:

ABEST for describing characteristics for display purposes only (for example, in drilldown reporting). This information is not relevant for price calculators.

DTFT is the basis for analysis. The DTFT itself consists of (possibly) more than one FTEC (financial transaction elementary category) that forms the DTFT by means of a hierarchy. The highest FTEC is also called the MASTER-FTEC and contains the information for the transaction that was originally to be depicted. (A cap consists of several caplets, for example. These are all FTECs that are situated under the MASTER-FTEC CAP.)

The GID (global identifier) elements, when combined with the degree of branching, define the structure of the risk object. The degree of branching is 0 for end-nodes in the tree and a simple integer value, in contrast to the GID, which is a table of integers. The length of these integers precisely describes the level of the tree in which the indicated node is situated.

Saving an SDTFT on the Database

It is not possible to save one or more than one SFGDT on the database (and hence also in a Unix file, or similar) without further processing. The reason for this is that complex data structures cannot be stored on the database at present. Instead, the SDTFT must be broken down and then saved in flat structures. When doing so, make sure that the original hierarchy structure can be reconstructed.

First the depiction of a possible SDTFT:

[figure TRM02-F124 - In Risk Analysis, the hierarchy of elementary transactions is implemented by what are known as “GIDs” (global identifiers) in combination with the degree of branching. A GID is an n-data set (ʻn’ being the current level of an FTEC in the hierarchy) of natural numbers (integers). For example, let GID (1/2/1) be a node in a tree with a degree of branching of 3. That is to say 3 direct successors exist. The GIDs of these immediate “successor FTECs” in the hierarchy are therefore: (1/2/1/1), (1/2/1/2), and (1/2/1/3). They result by simply adding a further integer from the value range (1.... degree of branching) to the GID of the predecessor. In this way, a double-linked relationship exists between the previous node and the subsequent node in the hierarchy: by adding an integer to one GID you reach the successor, by deleting the last entry of the GID of a node you reach, correspondingly, the GID of the predecessor (the root always having the GID (1)).]

In Risk Analysis, the hierarchy of elementary transactions is implemented by what are known as “GIDs” (global identifiers) in combination with the degree of branching. A GID is an n-data set (ʻn’ being the current level of an FTEC in the hierarchy) of natural numbers (integers). For example, let GID (1/2/1) be a node in a tree with a degree of branching of 3. That is to say 3 direct successors exist. The GIDs of these immediate “successor FTECs” in the hierarchy are therefore: (1/2/1/1), (1/2/1/2), and (1/2/1/3). They result by simply adding a further integer from the value range (1.... degree of branching) to the GID of the predecessor. In this way, a double-linked relationship exists between the previous node and the subsequent node in the hierarchy: by adding an integer to one GID you reach the successor, by deleting the last entry of the GID of a node you reach, correspondingly, the GID of the predecessor (the root always having the GID (1)).

This information is stored in structure JBIHIER08.

Recreating the Hierarchy

Recreating the hierarchy can occur recursively by taking advantage of the fact that the GIDs are ranked in lexicographic order. For the example above, structure JBIHIER08 is filled as follows:

|Ranking|Degree of branching|
|---|---|
|1|3|
|2|2|
|3|0|
|4|1|
|5|1|
|6|0|
|7|1|
|8|0|
|9|0|


You can use the following algorithm:

Initialization by ((1), 1, X)

Sequential number 1 is part of GID (1).

Last_Nr_used = 1 (last used sequential number)

Sequential number 1 has three successors. In accordance with the structure and Last_Nr_used being 1, these must be: exactly the sequential numbers 2 to 4, meaning that no. 2 = (1/1), 3 = (1/2), 4 = (1/3).

Last_Nr_used = 4 (last used sequential number)

Delete processing flag for (1).

The processing flag is set if the degree of branching is > 0, which means that there are still successors. This is the case for 2 and 4.

These are to be processed as above, thus for 2:

2 has 2 successors, Last_Nr_used = 4, thus the successors are 5 and 6 with the GIDs (1/1/1) and (1/1/2).

If there is no longer an entry in the processing structure for which the processing flag is set, then the hierarchy has been created.

###### Additional Information on Enhancement of the Generic Transaction

> **Path:** Treasury and Risk Management > Risk Management > Basics > Editing Generic Transactions > Additional Information on Enhancement of the Generic Transaction | L5 | trm02 p.105 | loio `c10bc5536a51204be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c10bc5536a51204be10000000a174cb4.html?locale=en-US)

The transaction for editing generic transactions was developed using the Business Data Toolset (BDT). The enhancement concept implemented in the BDT therefore also applies to the generic transaction. The following contains information about which special features you must take into account when enhancing the input masks of fields. This document assumes that you are familiar with the BDT enhancement concept.

You edit generic transactions in three screen sequences:

Main screen sequence DAP01 with header data and the hierarchy

- Secondary screen sequence DAP02 belonging to the NODE screen sequence category for maintaining an elementary transaction

Screen sequence DAP02 is called from the hierarchy in the main screen sequence for each elementary transaction that is to be processed.

- Secondary screen sequence DAP03 belonging to the CASH screen sequence type for entering cash flow details.


The system calls screen sequence DAP03 from the table control of the secondary screen sequence DAP02 for each cash flow entry.

Note the following special features that apply when you enhance fields. The features depend on the screen sequence in which the application in question carries out enhancements:

- 1. Enhancements in the main screen sequence


The screens that can be enhanced in this screen sequence maintain the tables JBRDBKO and JBRDBABEST – that is, the header information of a generic transaction. There are no special features that differ from the general BDT enhancement rules. This means that the participating application reads the contents of the two tables at business transaction event ISDST using the tables’ GET modules. At business transaction event DSAVB, the system can transfer the additional data back to the owner application DAP, using the corresponding COLLECT modules and the DDIC name and APPEND enhancement details.

- 2. Enhancements in the secondary screen sequence DAP02 – maintaining the elementary transaction

Enhancement fields must be executed in the DDIC structure VTVFGKO0X for each APPEND. This structure is included indirectly in the relevant database table JBRDBKOET. (It is important that you use the structure named above so that the system also provides data for the additional fields when you select the generic transactions in SEM evaluations).

For each generic transaction you need the secondary screen sequence DAP02 for each elementary transaction, so there may be several screen sequences for each generic transaction. If field enhancements are made on this level, the participating application must know which elementary transaction it has been called up for in DAP02 processing. To determine this, the system can call up the module DAP_FGDT_GET_FGET on the PBO/PBC module level of the participating application. This module delivers the GID, that is, the internal ID of the elementary transaction that is currently being processed. The module also provides the field contents that have so far been determined for the structure JBRDBKOET. This structure includes, for example, the TFORM (transaction form).

The participating application must note the additional information relating to the relevant elementary transaction, in particular the GID key that was read with the module mentioned above, in an internal table (ideally with line category JBRDBKOET).

This information (for all elementary transactions) is returned to the owner application DAP using the module DAP_FGDT_JBRDBKOET_COLLECT at business transaction event DSAVB, together with the name of the enhancement APPENDS of the owner application. The owner application updates the data in DSAVE.

Special features when deleting

If you deleted an elementary transaction online (you do this in the hierarchy display of the elementary transactions in the main screen sequence), this does not affect the participating application. If the participating application transfers the enhanced data for an elementary transaction at business transaction event DSAVB, and the transaction has already been deleted, the owner application ignores it.

The internal GIDs of the elementary transactions in online maintenance do not include any hierarchy information as is the

case with external generic transactions. They only include a temporary key. A GID can be reassigned after an elementary transaction has been deleted. The participating application can ignore this because it checks for each GID whether it has already processed the GID or whether the GID is new ('read – modify – insert’ – logic).

Enhancing the option fields

Enhancements for elementary transactions that display option categories (for example TFORM 61 and 62) work in the same way: the option information is located on the same level as the elementary transaction header information in screen sequence DAP02. The affected database table here is JBRDBOPTI, and the corresponding module

DAP_FGDT_JBRDBOPTI_COLLECT for saving the enhancement is affected in DSAVB. The GID of the relevant elementary transaction calls the participating application with the module DAP_FGDT_GET_FGET. On the DDIC level, you execute the enhancement in the structure VTVFGOP01 as APPEND.

- 3. Enhancements in the secondary screen sequence DAP03 – Entry of cash flow details


The database table JBRDBBEWEG is maintained with the entry of cash flow details. You include field enhancements in the structure VTVFGCF02 using APPEND. The enhanced fields cannot be included in the table control for the cash flow entry. You can maintain them only on the cash flow detail screen. This detail screen is the central element of the secondary screen

sequence DAP03.

As the cash flow entry is executed for each elementary transaction, the participating application must get the GID of the elementary transaction currently being processed from the owner application, using DAP_FGDT_GET_FGET (as described above). In addition, the current cash flow number (NCFNR) must be requested from the owner application for each cash flow being processed. To do this, the system must call up the module DAP_FGDT_GET_FGCF. This can take place either at a PBO/PBC business transaction event of the participating views of the cash flow enhancement or (better) at business transaction event FCODE. At FCODE the owner application determines the cash flow selected in table control or generates this cash flow. This then provides the cash flow number. The participating application must note the enhancement data per elementary transaction (GID) and per cash flow number (NCFNR) (preferably in an internal table with line category

JBRDBBEWEG). At business transaction event DSAVB all field enhancement data for all cash flows and all elementary transactions are returned to the owner application, together with the APPEND name, using DAP_FGDT_JBRDBBEWEG_COLLECT. The owner application updates the data in DSAVE.

If cash flows are deleted using table control in maintenance, the same applies as in elementary transaction maintenance: because cash flow numbers can be re-assigned, the participating application must ensure that current data is available for every cash flow number.

Other Effects:

**External Price Calculator Interface**

The main purpose of the generic transaction field enhancement is to connect Risk Analyzer to external price calculators that request outgoing information via the generic transaction data layout delivered by SAP. If the participating applications apply the APPENDS to the structure mentioned above, the price calculator interface provides the enhanced fields, even in runtime.

**Change Documents**

Change documents are written for field enhancements if the data elements of the participating applications are intended for creating change documents.

**Authorization Check**

The authorization check provided by the BDT as a central service, checks the authorizations using its own authorization object, depending on the field value of any data field within the generic transaction. You can define authorization types for this by choosing Market Risk Analyzer Tools Development BDT Generic Transaction . For each authorization type, you can define which field the system uses to check the authorization. You can specify a maximum of two fields per authorization type. All fields that are ready for input in the Edit Generic Object transaction are available to you. (You can specify only fields from tables for which a service function module was created in transaction RCCOG for reading data).

The authorization object T_FGDT_ART in the object class TRTM, which was created specially for the generic transaction, contains (in addition to the activity and the authorization type) two field values (field names AUVAL1 and AUVAL2) for the user-defined fields of the authorization type for the generic transaction. You can create the instances 01 – create, 02 – change and 03 – display in the field activity. The system can then check the authorization for a particular user, using the authorizations to be created with the assignment of a pre-defined authorization type, field value instances and the activity.

The system carries out the authorization check when processing the generic transaction, between the initial screen and the first data screen, and also before saving (business transaction event AUTH1). During direct input, the system carries out the check once, after constructing the generic transaction. The check is only carried out if at least one authorization type is active.

**Example:**

The customer wants user A to be able to display only generic transactions with the company code 0001, and user B to be able to display only generic transactions with the company code 0002. User C needs to be able to create, change and display generic transactions for any company code.

The authorization type RT_BUKRS is created in Customizing for the generic transaction with the field JBRDBKO-BUKRS as screen field 1, using transaction RCC20.

The system creates three authorizations for the authorization object T_FGDT_ART with the following instances:

|Authorization|Authorization type|Activity|Field value 1|Field value 2|
|---|---|---|---|---|
|T_RT_SHW0001|RT_BUKRS|03|0001|*|
|T_RT_SHW0002|RT_BUKRS|03|0002|*|
|T_RT_ALL|RT_BUKRS|01-03|*|*|


**Note:**

The system assigns the individual authorization to the corresponding user, using an appropriate profile or role.

All three users can process generic transactions with a blank company code in the master data. The generic transaction can be saved if the company code field remains blank, or if the user has the appropriate authorization.

