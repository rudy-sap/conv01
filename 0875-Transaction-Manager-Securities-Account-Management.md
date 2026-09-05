# Transaction Manager > Securities Account Management - SAP TRM Knowledge Base (branch split)

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

#### Securities Account Management

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management | L3 | trm06 p.261 | loio `1619da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1619da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Various functions are available for managing your securities positions. You can use these to map the changes that securities positions undergo over time. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities Back Office Securities Account Management .

**Features**

Position Information

Here you can use the evaluation reports for securities account management. They provide you with a lot of information about the security positions.

Securities Account Transfer

The Securities account transfer function enables you to transfer a position from one securities account to another.

External Securities Account Statements

You can use these functions to import external securities account statements and compare them with internal information.

Payments

Here you can use the functions for the Automatic and Manual Debit Position and the function Manual Posting .

See also:Payments .

Updating Planned Records

The function Update Planned Records recalculates the cash flows for the selected securities positions and updates the database.

Restraints on Disposal

You can use this function to block and unblock securities positions.

See also:Editing Restraints on Disposal

**Prerequisites**

- 1. You made the necessary Customizing settings for update types. Choose Transaction Manager Securities Position Management Securities Account Transfer and Securities Account Management.


- 2. You entered the posting specifications for the update types in Customizing for Transaction Manager. Choose General Settings Accounting Link to Other Accounting Components Define Account Determination .

##### Position Overview (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Position Overview | L4 | trm10 p.56 | loio `b20bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b20bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This report provides an overview of the key position values. It includes base key figures (such as the acquisition value and book value) and a range of derived values (such as hidden reserves and pending losses).

**Integration**

This report is a query. The query is based on InfoSet CFM_POSITIONS, which, in turn, is based on logical database FTI_TR_POSITIONS.

- The technical name of this query is CFM_POS_1.


**Features**

Selection

Product Groups

Selections

Control Parameters

Output

The list is displayed using the SAP List Viewer .

See also:SAP List Viewer for SAP GUI (Classic)

##### Securities Account Position List

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Securities Account Position List | L4 | trm06 p.263 | loio `4418da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4418da531198434de10000000a174cb4.html?locale=en-US)

Use

This list shows, for each company code and securities account, a list of all the class positions in the account on any given date.

The list is displayed via the SAP List Viewer .

You can display the following columns:

Short name - ID number

ID number

Nominal

Nominal currency

Units

##### Class Position

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Class Position | L4 | trm06 p.263 | loio `c61ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c61ada531198434de10000000a174cb4.html?locale=en-US)

Use

The class position list shows for each company code and ID number, on a specific date, the positions of a class in the various securities accounts.

The list is displayed via the SAP List Viewer .

You can display the following columns:

Securities account

Securities account name

Nominal

Nominal currency

Units

##### Execute Securities Account Transfer

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Execute Securities Account Transfer | L4 | trm06 p.263 | loio `b336cd5341dd7314e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b336cd5341dd7314e10000000a174cb4.html?locale=en-US)

**Use**

Within a company code, you can transfer positions at their book values from one securities account to another.

The securities account transfer can affect the general ledger as well as the subledger since, by changing the securities account for a position (= change in the subledger accounting), you can change both the valuation class and the account assignment reference, if the target securities account has a different account assignment reference in the position indicator to that of the source securities account (= changes in the general ledger accounts).

**Prerequisites**

You made the settings in Customizing for Treasury and Risk Management under Transaction Manager Securities Position Management Securities Account Transfer .

There cannot be any fixed, condition-based transactions (such as, repayment) after the key date of the securities account transfer for the positions involved.

**Features**

The securities account transfer takes the transfer amount at book value from the source securities account and posts it to the target securities account. The system generates the associated flows depending on the position management procedure.

For more information, see Position Management Procedure. Also see the documentation in the Customizing of Treasury and Risk Management under Transaction Manager General Settings Accounting Settings for Position Management Define Position Management Procedure .

You can display the quantities of the security ID number in the source and target securities account before the securities account transfer.

You can display the source and target securities account cash flows including the securities account transfer.

**Activities**

- 1. You can call the app on SAP Fiori launchpad in the Securities Account Management business group or in the area menu of the back-end system under Accounting Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Securities Back Office Securities Account Management Securities Account Transfer Execute (transaction FWDU).

- 2. Enter the company code, the ID number, the source securities account, and the date of the position change (position value date). The calculation date defaults to the current date, but you can overwrite it. The Securities Account Transfer: Edit screen appears.
- 3. Choose the target securities account using the input help. You can change the default update type.
- 4. In the Values area, you enter either the number of units to be transferred or the nominal amount. For interest-bearing securities, the Coupon date field displays the next interest payment date. Using the Dates pushbutton, you can choose one of the following interest dates. The coupon dates determines the date from which the interest payments are made to the target securities account.
- 5. In the Additional Specifications area, you enter the following:

Position value date

Calculation date

General valuation class

Portfolio

- 6. The Posting Control area includes the following fields:


**Note:**

Using the pushbuttons Quantities (Source Securities Account) and Quantities (Target Securities Account), you can display the quantities of the security ID number in the source and target securities account before the securities account transfer.

Document Date

FI Posting Date and FI Period: In the standard system, this field contains the calculation date. If you choose a posting date that differs from the calculation date, make sure that the posting date is not before the calculation date.

Assignment: You can define a short text for this activity and the text is then passed on to the accounting department.

- 7. Choose Cash Flow (Source Securities Account) to display the source securities account cash flows including the securities account transfer.
- 8. Choose Cash Flow (Target Securities Account) to display the target securities account cash flows including the securities account transfer.


- 9. To execute the transfer, choose Save. The system generates the flows required for the transfer and updates the position in the relevant securities account.


The transfer is recorded in a posting log.

You can reverse the securities account transfer using the Reverse Securities Account Transfer app or call it in the area menu of the back-end system under Accounting Financial Supply Chain Management Treasury and Risk Management

Transaction Manager Securities Back Office Securities Account Management Securities Account Transfer Reverse (transaction FWDS).

##### Planned Record Update

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Planned Record Update | L4 | trm06 p.265 | loio `fa41f252ad7e0175e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fa41f252ad7e0175e10000000a44538d.html?locale=en-US)

**Use**

This program recalculates cash flows for selected securities positions and then updates the database.

This recalculation is particularly important for planned records that include reference interest rates and exchange rates because their values change continuously.

If changes are made in the conditions, the system automatically updates the planned records as soon as the changes to the conditions are saved.

The flows are updated in the database only for the cash management update period (CM period). We therefore recommend that you update the planned records for this period, even for securities positions that do not normally change.

Since postings are made on the basis of the planned records in the cash flow, you must always update the planned records before you execute the following functions:

Accrual/deferral

Automatic posting

Alternatively, you can update planned records using the Display Class Cash Flow for Securities Account function. Choose SAP Easy Access Accounting Treasury and Risk Management Securities Back Office Securities Account Management Position Information Securities Account Cash Flow (TPM40).

We recommend that you update the planned records regularly, or even daily if possible.

**Procedure**

- 1. From the SAP Easy Access menu, choose SAP Easy Access Accounting Treasury and Risk Management Securities Back Office Securities Account Management Securities Account Cash Flow (FWUP) .


- 2. Enter the individual value or range of values for the product type for the company code and the ID number.
- 3. Choose Program Execute . The new planned records are saved. The system displays a list of the individual securities account positions.


See also:

Cash Flow for a Class in a Securities Account

##### Payments

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Payments | L4 | trm06 p.266 | loio `9b19da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9b19da531198434de10000000a174cb4.html?locale=en-US)

Use

The following functions are available for payments for the securities account management area:

Automatic Debit Position (Automatic Posting)

Manual Debit Position (Incoming Payments)

Manual Postings

Reversing Manual Postings/Manual Debit Positions

###### Automatic Debit Position (Automatic Posting)

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Payments > Automatic Debit Position (Automatic Posting) | L5 | trm06 p.266 | loio `ad19da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ad19da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The Automatic Debit Position function allows you to automatically process flows that occur at regular predefined intervals for previously fixed amounts.

**Example:**

You can use this function for fixed-interest securities to post interest flows or repayments automatically, or flows generated from the conditions.

There are two procedures for processing these regularly occurring flows:

One-Step Procedure

When you use the one-step procedure, the selected flows that have Planned status are transferred to actual flows in the subledger by the automatic debit position function, and the amounts are posted directly to the bank clearing account in Financial Accounting. The items are cleared in the bank clearing account when the account statement is imported.

If you wish to post flows individually, you can do this using the Manual Debit Position (Incoming Payments) function.

Example: Automatic Debit Position Process

[figure TRM06-F099 - Two-Step Procedure]

Two-Step Procedure

You can also use the automatic posting function together with the Manual Debit Position function. (To do this, you have to make certain Customizing settings as described in the prerequisites). The automatic posting function not only posts the existing planned records as actual records, but at the same time generates new incoming payment flows as planned records (or actual records) in a receivables account.

When the ʻaccount statement’ has been imported, you can use the Manual Debit Position (Incoming Payments) function to post the incoming payment in the Treasury subledger.

Example: Process of Automatic Debit Position with Incoming Payment

[figure TRM06-F100 - Example: Process of Automatic Debit Position with Incoming Payment]

**Prerequisites**

You select the automatic posting option for all the flows you want to post automatically in the Posting Control field in Customizing for securities by choosing Define Flow Types.

By choosing Define Company Code-Dependent Data, you can define whether automatic posting is actually permitted for each product type.

You make the same settings under Securities Position Management Securities Account Management Update Types

Define Update Types and Specify Update Types for Securities Account Management. Before you can make the settings under Specify Update Types for Securities Account Management, you must use Assign Update Types to Usages to assign the update types to usage 0003 Securities Account Management.

If you want to use the two-step procedure, then you have to define this in the Securities area Customizing under Define Flow Types and under Specify Update Types for Securities Account Management. You do this for all flows for which incoming payment flows are to be generated by checking the Incoming Payments field. By choosing Maintain Company Code-Dependent Data, you can define whether incoming payment flows are actually generated for each product type.

You also have to create the incoming payment flows under Define Flow Types and under Define Update Types. Then you assign them as offsetting flows to the update types under Position Management Securities Account Management Update Types

Assign Update Types to the Functions of Security Account Management .

See also:

For more information, see the relevant section in the Implementation Guide.

In the Securities area Customizing under Accounting in Operative Valuation Area Flow Types Assign Flow Types to Update Types , you assign the securities flow types to the corresponding update types.

Tax flow types

If you defined tax rates for the flow types you want to process using the automatic posting function by choosing Define Tax Rates in Customizing, these tax flows are generated automatically in automatic posting and posted as actual records. The automatic posting function also includes taxes that have to be generated for automatically generated taxes.

You also have to set the Posting Control field to 01 for the tax flow types by choosing Define Flow Types and Specify Update Types for Securities Account Management in Customizing, and make the relevant entries in the Incoming Payments field if you want to process incoming payments.

To ensure the automatic debit position run works successfully, first post all the flows that affect the relevant ID numbers and securities accounts up to the due date for which the automatic debit position run is carried out.

Repayments are the only exception to this rule, because they can be posted by the automatic posting function itself.

The automatic debit position run does not take account of securities accounts containing flows that affect positions which still have Planned status. If this is the case, an error log appears listing the flows that have to be posted first.

See also:

The prerequisites section in Securities Account Management

Affected Flows

Manual Debit Position (Incoming Payments)

Taxes

**Features**

Selection

|General Selections| |
|---|---|
|Company code|Selection of securities flows to be processed|
|Product type| |
|ID number| |
|Securities account| |
|Up to and including due date| |
|Posting Control| |
|Posting date Document date|To control how postings to the general ledger in FI are made, you can enter a posting date and a document date. If you do not enter a posting date, the system posts all the flows for an ID number in a company code and a securities account with the earliest due date of these flows. The system uses the current date as the document date.|
|Simulation|When you set this indicator, the system performs a simulation run. This is similar to the update run, except that no flows are posted to the general ledger or the subledger.|


Output

Posting log

The posting log provides you with information about all the flows that are transferred to and posted in FI.

Log of actual flows posted and planned records generated

This log displays all the flows that were posted as actual flows as well as the new planned records.

Error logs

Error log for the planned records to be posted first

This log displays which position-changing flows in Planned status still have to be settled before they are posted automatically.

General error log

This error log shows you which ID numbers in each company code could not be processed. The reasons for this may be as follows:

You cannot process ID numbers you are currently working on using the automatic posting function (with the exception of the test run).

An error occurred in the posting interface when processing the relevant class in the company code. For this, see the error log for the posting interface.

Error log for the posting interface

This lists all the errors that occur when you post or simulate posting.

Selection parameters output

The selection parameters that were used to start the posting run are listed at the end of the log.

**Activities**

Choose Back Office Securities Account Management Payments Automatic Debit Position .

###### Manual Debit Position (Incoming Payments)

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Payments > Manual Debit Position (Incoming Payments) | L5 | trm06 p.270 | loio `c519da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c519da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use the Manual Debit Position (Incoming Payments) function to:

Edit and post flows generated by the conditions of a security (such as dividends, interest, or repayments).

Edit and post flows entered as planned flows using the manual posting function.

You can use the manual debit position function to edit an individual activity made up of one or several flows with Planned status. Use the automatic debit position function to edit or post several activities together.

**Integration**

The automatic debit position and manual debit position (incoming payments) functions are closely linked. Both functions are used to process flows generated by the conditions. You process many flows together when you use the automatic debit position function, whereas the manual debit position (incoming payments) function enables you to process each flow individually. Here you can also make changes to the flows.

By making the appropriate Customizing settings, you can set up the functions together so that you can use a two-step procedure to process regularly occurring flows that are generated by the conditions. To do this, see Automatic Debit Position (Automatic Posting). If you decided to use the two-step procedure, you can only use the manual debit position (incoming payments) function

to process those incoming payment flows that were generated by the automatic posting run. [You can, of course, still use the manual debit position (incoming payments) function to process flows that were generated as planned records by the manual posting function.]

**Prerequisites**

If you have chosen the two-step procedure to process flows generated by the conditions, you have to make certain settings in Customizing.

See Automatic Debit Position (Automatic Posting).

**Features**

You can check which flows you can edit individually when you use the Manual Debit Position function by consulting the list of Permitted Flow Categories.

You can process the flows in the incoming payments function.

You can decide whether or not you want to generate a tax rate for the relevant flow. Tax rates are generated automatically when you use the automatic debit position (provided that you have made the relevant settings in Customizing for Securities by choosing Define Tax Rates).

You can change the amount of the flow.

You can delete a flow.

You can add a new flow.

You have the option of capitalizing dividends and distributed profits.

See also: Editing and Posting an Activity

When you post the flows, the postings are made according to the account assignment reference you defined for the flow type in Define Account Assignment Reference in Customizing, and the flows then become actual records.

**Activities**

To enter, process, select, edit, and post an activity, read the following sections:

Using Manual Debit Positions

Selecting a Posting Activity

Editing and Posting an Activity

###### Using Manual Debit Positions

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Payments > Manual Debit Position (Incoming Payments) > Using Manual Debit Positions | L6 | trm06 p.271 | loio `cb19da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cb19da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Proceed as follows:

**Activities**

- 1. Choose Back Office Securities Account Management Payments Manual Debit Position .

This takes you to the Manual Debit Position: Initial Screen screen.

- 2. Enter the company code, the ID number, and the securities account.

In the Settlement currency field, you can enter the currency to be used for the posting activity. Unless you fill the field, the system takes the settlement currency from the flow you select in the next step.

- 3. The system then checks if flows with planned status exist for the company code, security ID, and securities account that you have specified. These can be edited using the Incoming payments function.
- 4. Press ENTER. The system displays a list of the cash flows. From here, you go on to Selecting a Posting Activity.


**Note:**

You can see exactly which flows can be edited using the Incoming Payments function by consulting the list of Permitted Flow Categories.

###### Selecting a Posting Activity

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Payments > Manual Debit Position (Incoming Payments) > Using Manual Debit Positions > Selecting a Posting Activity | L7 | trm06 p.271 | loio `ce19da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ce19da531198434de10000000a174cb4.html?locale=en-US)

Proceed as follows:

- 1. The screen Cash Flow in Position Currency displays all the flows you can process using the incoming payments function in the form of a cash flow.


- 2. To edit and post a flow, you can choose between the following alternatives:


Double-click on a flow.

Position the cursor on a flow and click on the Choose function.

**Note:**

If the cash flow contains several flows of the same flow type, and these flows have been derived from a condition, you must post the flows in chronological order, from the oldest to the most recent.

If you fail to do this, the system will delete any planned flows dated earlier than the flow to be posted which have the same flow type.

- 1. Once you have selected a flow, the system displays all the flows which belong to the same posting activity. You can then edit and subsequently post them.
- 2. The following section describes Editing and Posting an Activity .

###### Editing and Posting an Activity

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Payments > Manual Debit Position (Incoming Payments) > Using Manual Debit Positions > Editing and Posting an Activity | L7 | trm06 p.272 | loio `d119da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d119da531198434de10000000a174cb4.html?locale=en-US)

You can choose from the following processing options:

- 1. Date details
- 2. Here, you can change the value date of the posting activity. You cannot change the other data, since it has either been derived from a condition or defined during manual posting.
- 3. General details
- 4. Enter the paying bank, the counterparty and the internal bank account. The system fills the internal bank account field automatically, either with the internal bank account defined for the securities account, or with the account defined in the standing instructions for the counterparty. In order for this to happen, the counterparty standing instructions must have been indicated as active in the company code additional data in Customizing.
- 5. Posting data
- 6. Enter the posting date for the manual posting activity and your own allocation text, which appears in the FI document after the posting has been made.
- 7. Exchange rates
- 8. If the manual posting activity relates to several currencies, the system displays the exchange rates between the position currency and the settlement currency, between the settlement currency and the local currency and between the position currency and the local currency. Only the rates actually required for currency translation are visible.


If you change the exchange rates, the system immediately translates all flows in the manual posting activity on the basis of the new rates. The amounts are always translated in the following order:

Amount in position currency


Amount in settlement currency


Amount in local currency


The system defaults to the exchange rates on the value date. You can restore the default rate for each exchange rate at any time by deleting the corresponding entry.

- 9. Editing an Existing Flow
- 10. Adding a Flow
- 11. Deleting a Flow
- 12. In Process Flow details screen, you can manually change the value for the payment reason, which was automatically determined using Automatic Payment Reason Determination – Securities Account and Transaction Management app.

- 13. Capitalize (only for dividends and distributed profits).
- 14. Recalculating Taxes
- 15.


The lower part of the table always displays all the current flows for the activity. The last table entry is the net payment amount , which is made up of all the flows. (Net Payment Amount )

- 16. When you have finished editing, post the complete activity using the Post function. When this activity has been completed, the system displays a posting log.

###### Create Manual Posting

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Payments > Create Manual Posting | L5 | trm06 p.273 | loio `9e19da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9e19da531198434de10000000a174cb4.html?locale=en-US)

App ID: FWBS

With this app, you can enter individual costs that are not assigned to any other business transactions.

To do this, you can generate one or more new flows in manual posting. Then you can either save these as scheduled flows or post them directly as actual flows. You can post scheduled flows, which you have entered manually, at a later stage using the Manual Debit Position (Incoming Payments) app.

**Prerequisites**

Your key user made the relevant settings in the self-service configuration steps under Settings for Update Types.

**Activities**

- 1. Open the Create Manual Posting app on SAP Fiori launchpad.

The screen Manual Posting: Initial Screen appears.

- 2. Enter the Company Code, the Security ID Number, and the Securities Account.
- 3. In the Settlement Currency field, you can enter the currency to be used for the posting activity. If you leave the field blank, the system uses the security's position currency.

Choose ENTER. The screen Manual Posting appears.

- 4. Date Specifications area:


Enter the following data:

Interest Value Date

Due Date

Value Date

Position Value Date

- 5. Payment Details (Manual Entry) area:

Here you can enter which house bank and which house bank account is to be used. If you do not make any entries, the specifications from the securities account master data are used.

- 6. Posting Control area

Enter the posting date for the manual posting activity and your own assignment text that appears in the FI document after the posting has been made.

- 7. Exchange Rates area

If the manual posting activity relates to several currencies, the system displays the exchange rates between the position currency and the settlement currency, between the settlement currency and the local currency, and between the position currency and the local currency. Only the rates actually required for currency translation are visible.

If you change the exchange rates, the system immediately translates all flows in the manual posting activity on the basis of the new rates. The amounts are always translated in the following order:

- a. Amount in Position Currency
- b. Amount in Settlement Currency
- c. Amount in Local Currency


The system defaults to the exchange rates on the value date. You can restore the default rate for each exchange rate at any time by deleting the corresponding entry.

- 8. To add a new flow, choose (Insert Additional Flow), or from the menu choose Edit Insert Other Flow .

Select the update type for the flow.

Enter the amount in settlement currency. Choose Translate to calculate the corresponding amounts in position and local currency.

If the settlement and position currencies are different:

- a. You can change the settlement currency for the single flow.
- b. You can change the amount in position currency.


If you change the amount in position currency, the system recalculates the amounts in settlement and local currency on the basis of the new position currency amount.

The amounts are always translated in the following order:

- i. Amount in Position Currency
- ii. Amount in Settlement Currency
- iii. Amount in Local Currency


- 9. To process an existing flow, mark it and choose (Choose Flow), or from the menu choose Edit Choose .


Now you can also manually define payment reason for the purpose code.

- 10. To save changes to a single flow, select the Copy function.
- 11. If you want to undo the changes you have made, use the Cancel function or press ESC .
- 12. To delete flows from the activity, select the flows to be deleted and choose (Delete Other Flow), or from the menu choose Edit Delete Other Flow .


**Note:**

You can only delete flows you have added during the current editing session.

- 13. The last table entry is the net payment amount, which is made up of all the flows.
- 14. When you have finished editing, save the complete manual posting activity as a planned flow via Save without Posting or post it directly as an actual flow using the Post function.
- 15. When the posting activity is complete, the system displays a posting log for control purposes.


**Supported Device Types**

Desktop

Tablet

###### Reversing Manual Postings/Manual Debit Positions

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Payments > Reversing Manual Postings/Manual Debit Positions | L5 | trm06 p.275 | loio `b919da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b919da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to reverse the following flows that that were posted via the debit position functions (manual debit position, automatic debit position and manual posting:

Flows generated by the conditions of a security (interest, dividends, bullet repayment)

Price gains, price losses, adjustment flows resulting from a final repayment

Interest capitalization flows for zero bonds that result from a bullet repayment or a securities account transfer

If you reverse postings that were generated on the basis of conditions, the actual records are converted back into planned records. All other reversed actual records no longer appear in the cash flow.

**Integration**

You can use various different reversal functions in the securities area: Choose the relevant reversal function for the flows you want to reverse.

For more information, see Overview: Reversals in Securities.

**Prerequisites**

If the business transaction you want to reverse contains a position-changing flow, then no posted flow may exist in the business transaction's securities account where the position value date is later than the value date of the business transaction.

**Activities**

The reversal posting is carried out per securities account position.

- 1. Call up the function. The Reverse Manual Posting/Manual Debit Position: Initial Screen appears.
- 2. Enter the Company Code, the Security ID Number and the Securities Account.
- 3. Choose Enter. The system displays a list of the cash flows including all flows that can be reversed using this function.


- 4. In the date field in the bottom left-hand corner of the screen, you can define the date from which you wish to see the cash flow.
- 5. Double-click on an entry in the list or position the cursor on an entry and click on the Choose button to display detailed information on this position.
- 6. 4.Position the cursor on the entry to be reversed and select Edit Reverse .

This displays all the flows that are to be reversed with the selected flow.

- 7. Enter the CFM-specific reversal reason, the FI reversal reason, and the posting date of the reversal.

There is no default value for the posting date. If you leave the field empty, the system reverses the flow with the date of the original flow.

- 8. If you wish to carry out the reversal in the subledger only, press the right mouse key and select the function.
- 9. Choose the Reverse function.


**Note:**

We recommend that you only use this function if you are required to post a transaction in the securities subledger separately from the posting in the general ledger in Financial Accounting, for example, because the document in FI has already been reversed.

##### Editing Restraints on Disposal

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Editing Restraints on Disposal | L4 | trm06 p.276 | loio `7719da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7719da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to create restraints on disposal and lock positions or partial positions. In the case of a sale, the system checks whether a restraint on disposal exists for the affected position. If a restraint on disposal has been created, the system then checks whether it is affected by the sale. If the locked position is affected by the sale, an error message is displayed.

**Note:**

You block an entire securities account in the securities account master data.

See also: Manage Securities Accounts

**Example**

On 12/06, you have 1000 units of stock A in securities account XY. You plan to sell 300 of these stocks on 01/15. To ensure that 300 units are available for sale on this day, you define the following restraint on disposal in the system:

Company code: ABC

ID number: Stock A

Securities account: XY

Units: 300

Locked Until: 01/15/08

Reason for Lock: B

If a sale or another reduction in stock is entered, the system checks whether there are still at least 300 units of stock A remaining in securities account XY. Therefore, up until 01/15, the system only permits sales totaling 700 units.

Impact of the Restraint on Disposal

[figure TRM06-F106 - Impact of the Restraint on Disposal]

**Integration**

Forward Securities Transactions

Position locks can be generated automatically when forward securities are sold, and also deleted automatically when the security is delivered.

Position locks differ from restraints on disposal by their valid from date. Restraints on disposal are always valid to a specific date.

You can also use the Editing Restraints on Disposal function to display position locks.

See also: Position Locks due to Sale of Forward Securities

**Procedure**

- 1. Choose Back Office Securities Account Management Editing Restraints on Disposal .
- 2. Enter the company code. You can also specify the ID number or a securities account. Enter a date for which you wish to see the available positions and restraints on disposal.


- 3. The list contains all the selected positions including their nominal amounts or units. If a valid restraint on disposal or position lock already exists for a position key date, this is displayed in a second row.
- 4. You can use the list to do the following:


- a. Branch to the existing restraints on disposal and change them
- b. Delete the existing restraints on disposal
- c. Create new restraints on disposal

To create a restraint on disposal, select the relevant position. Choose Create. Define the number of units or the nominal amount to be locked as well as the date until which the lock should be valid. Save your entries.

- d. View existing positions locked using forward securities transactions.
- e. Select a position and the Position Trend pushbutton. You can use this function to branch to a list that displays chronological changes made to the position quantity (position increase/decrease) as well as restraints on disposal and positions locked after the key date.


- Initial Values of the total locks (restraints on disposal and position locks) on the key date (first list item); The key date is defined using the selected flow for which the position trend was called. The position date of the flow is the first day.
- Position Increase (due to a purchase, for example)
- Position Decrease (due to a sale or (scheduled) final repayment)
- Start of Lock (from a position lock by the sale of forward securities)

- End of Lock (from a restraint on disposal)


In the following columns you can see the position increase and decrease, the nominal value and currency or the units in the quantity change, as well as the total quantity (nominal amount, currency, or units) on the position date.

For the locks (restraints on disposal/position locks), the following columns contain the nominal amount or units for the lock as well as the total nominal amount, total number of units, and the remaining nominal amount and units.

##### External Securities Account Statements

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > External Securities Account Statements | L4 | trm06 p.278 | loio `4a8fd27cebe03897e10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4a8fd27cebe03897e10000000a42189c.html?locale=en-US)

**Use**

External securities account statements are sent by the depository bank managing the external securities account. An external securities account statement provides information about the positions managed in the external securities account by the depository bank. After you have received and checked an external securities account statement, you must reconcile the external data with your internal securities account class positions.

**Features**

You can receive the data for the external securities account statement by means of an MT535 message in the Treasury correspondence framework. For more information, see also Exchange Treasury Correspondence via SWIFT.

To import external securities account statements, you can use the method Create for BUS1062 External Securities Account Statement.

You can use the Manage Statements - External Securities Account app to create an external securities account statement manually.

You can use the Manage Statements - External Securities Account app to display and change the data of an external securities account statement manually.

Using the Reconcile Statement - External Securities Account app, you can reconcile your internal securities account positions with the data of the external securities account statement for selected key dates. The system displays any differences in the local currency.

**Note:**

The system establishes the connection between the external and the internal securities account positions using the external securities account ID. This is not necessarily the number under which the securities account is managed by the depository bank. However, the system uses the external securities account ID for automatic communications (such as SWIFT) with the depository bank.

Based on the date type in the external securities account statement, you can perform a comparison for the position date or the payment date.

Using the Delete Statement - External Securities Account app, you can remove the external securities account statements from the system (for example, after a securities account comparison).

**Data of the External Securities Account Statement**

Header Data

Company Code

Statement Number

External Sec.Acct ID

**Note:**

If you receive the external securities account statement via SWIFT, the external securities account ID is entered in field 97a Account: SafekeepingAccountin the SWIFT message.

In the securities account master data of your internal securities accounts, you must enter the external securities account ID that corresponds to the internal securities account using the Manage Securities Accounts app.

Key Date

Number of Positions

Date Category

Choose one of the following the data categories relevant for the reconciliation with the internal securities account:

Position Date

Calculation Date

Payment Date

Characteristics of the External Securities Account Statement

Status

The status is a characteristic that can be assigned to the securities account statement in the header data of an external securities account statement. The status of the external securities account statement can be changed. You must make this status change manually.

The following statuses for external securities account statements are predefined:

|SCLOS|Closed|
|---|---|
|SINIT|Initial|
|SOPEN|Open|
|SWORK|Work in Progress|


Example:

The securities account statement has the status SINIT when it has just been created. The status SWORK is used when the statement is still being edited. The status SOPEN indicates that the external securities account statement is ready for reconciliation. The status SCLOS indicates that reconciliation has already been performed.

Description

File

Group Ext. Sec. Acct Stats

- External Reference 1

- External Reference 2


Positions tab

On this tab, you can see one line item for each security class position managed in the external securities account. The following data can be entered:

Sec. Class ID Number

**Note:**

If you receive the external securities account statement via SWIFT, the security class ID number can be derived from the ISIN transferred with the SWIFT message in field 35b Identification of the financial instrument. Therefore, you must enter the ISIN as the secondary index in the security class data or use the ISIN as the security class ID number in the Manage Securities Classes app.

Short Name

Quotation

External Units

External Nominal Amount

Nominal Currency

External Nominal Amount Drawn

Nominal Currency

External Class Name

Ext. Position Classification

Long Name Ext. Pos. Classification

External Position Name

Note ID

Long Text for External Position Name

Note

Bank Data tab

Depository Bank

Sec.Acct Number

This is the number of the securities account at the depository bank. It must be the same as the securities account number entered in the internal securities account master data.

User Data tab

On this tab, you can see when and by whom the external securities account statement was created and last changed.

**Prerequisites**

You must fill the External Securities Account ID field in the securities account master data using the Manage Securities Accounts app.

To do so, you have changed the field selection control settings for the securities account master data and defined the External Securities Account ID field as a required entry field in the Customizing of the Transaction Manager under Securities Master Data Securities Account Management Maintain Field Selection for Security Account Master Data .

You must enter the ISIN for all your security classes. You can either enter the ISIN as the secondary index or use the ISIN as the security class ID number.

You can make settings in the following Customizing activities available for external securities account statements in the Customizing of the Transaction Manager:

Define Status for External Securities Account Statements

The status is a characteristic which can be assigned to the securities account statement in the header data of an external securities account statement. During editing of the external securities account statements, the status of the external securities account statement can change. You must make this status change manually using the Manage Statements - External Securities Accounts app.

Define Position Name for External Securities Account Statements

Define the external position name for the positions in an external securities account statement.

Define Position Classification for External Securities Account Statements

Define the external position classifications for the positions of the external securities account statements. The external classification are the classifications for the positions assigned by the financial institute managing the external securities account.

**Related Information**

Manage Statements - External Securities Account Reconcile Statement - External Securities Account Delete Statement - External Securities Account

###### Manage Statements - External Securities Account

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > External Securities Account Statements > Manage Statements - External Securities Account | L5 | trm06 p.282 | loio `3c1b5e0919054d81a5169c7c13fdc6a8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3c1b5e0919054d81a5169c7c13fdc6a8.html?locale=en-US)

- App ID: RECON4


With this app, you can create external securities account statements manually as well as display and change external securities account statements that have been generated electronically.

**Activities**

- 1. Open the Manage Statements - External Securities Account app on the SAP Fiori launchapd.
- 2. Select available external securities account statements using the following selection fields:

General Selections

Statement Number

Company Code

Securities Account ID

Key Date

Date Category

Status

External References

Group Ext. Sec. Acct Stats

- External Reference 1

- External Reference 2


User Data

Created On

Entered By

Last edited on

Last Changed By

- 3. Choose Execute.
- 4. The system shows all available external securities account statements according to your selection.
- 5. To display, change, or delete an external securities account statement, select the required external securities account statement in the tree on the left-hand side. The external securities account statements are sorted by company code, external securities account ID, and key date.
- 6. On the right-hand side, the data of the chosen external securities account statement is shown:


Header

Company Code

Statement Number

External Sec.Acct ID

**Note:**

If you receive the external securities account statement via SWIFT, the external securities account ID is entered in field 97a Account: SafekeepingAccountin the SWIFT message.

In the securities account master data of your internal securities accounts, you must enter the external securities account ID that corresponds to the internal securities account using the Manage Securities Accounts app.

Key Date

Number of Positions

Date Category

Choose one of the following the data categories relevant for the reconciliation with the internal securities account:

Position Date

Calculation Date

Payment Date

Characteristics of External Securities Account Statement

Status

The status is a characteristic that can be assigned to the securities account statement in the header data of an external securities account statement. The status of the external securities account statement can be changed. You must make this status change manually.

The following statuses for external securities account statements are predefined:

|SCLOS|Closed|
|---|---|
|SINIT|Initial|
|SOPEN|Open|
|SWORK|Work in Progress|


Example:

The securities account statement has the status SINIT when it has just been created. The status SWORK is used when the statement is still being edited. The status SOPEN indicates that the external securities account statement is ready for reconciliation. The status SCLOS indicates that reconciliation has already been performed.

Description

File

Group Ext. Sec. Acct Stats

- External Reference 1

- External Reference 2


Positions tab

Sec. Class ID Number

**Note:**

If you receive the external securities account statement via SWIFT, the security class ID number can be derived from the ISIN transferred with the SWIFT message in field 35b Identification of the financial instrument. Therefore, you must enter the ISIN as the secondary index in the security class data or use the ISIN as the security class ID number in the Manage Securities Classes app.

Short Name

Quotation

External Units

External Nominal Amount

Nominal Currency

External Nominal Amount Drawn

Nominal Currency

External Class Name

Ext. Position Classification

Long Name Ext. Pos. Classification

External Position Name

Note ID

Long Text for External Position Name

Note

Bank Data tab

Depository Bank

Sec.Acct Number

This is the number of the securities account at the depository bank. It must be the same as the securities account number entered in the internal securities account master data.

User Data tab

On this tab, you can see when and by whom the external securities account statement was created and last changed.

- 7. If you want to change the data of the external securities account statement, choose the Display <> Change button to switch to the change mode. Make the necessary changes, such as correcting data or changing the status of the external securities account statement.
- 8. If you want to delete the data of the external securities account statement, choose the Delete External Securities Account Statement button.


**Supported Device Types**

Desktop

Tablet

###### Reconcile Statement - External Securities Account

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > External Securities Account Statements > Reconcile Statement - External Securities Account | L5 | trm06 p.285 | loio `9ec44e20c49347bd97924be9b9407583` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9ec44e20c49347bd97924be9b9407583.html?locale=en-US)

- App ID: RECON5


With this app, you can reconcile your internal securities account class positions with the positions of an external securities account statement for selected key dates. The system displays the differences in the local currency.

**Activties**

- 1. Open the Reconcile Statement - External Securities Account app on the SAP Fiori launchpad.
- 2. Using the selection criteria, you can select the external securities account statements that you want to reconcile, for example, you could select all external securities account statement with the status SOPEN.
- 3. Perform the reconciliation.
- 4. The system reconciles the quantities of the positions in the external securities account statements with the quantities of the corresponding positions in the internal securities accounts for the selected date type.
- 5. The system displays logs.
- 6. From the result list, you can jump to the following:


**Note:**

The internal securities account is identified using the external securities account ID.

The security class is identified using the ISIN.

External securities account statement

Place the cursor on an external securities account statement and choose the External Securities Account Statement button. This displays the external securities account statement in the Manage Statements - External Securities Account app.

Cash flow of securities account class position

Place the cursor on a security class ID number and choose the Securities Account Cash Flow button. This leads you to the cash flow of the class in the securities account.

The cash flow provides a chronological quantity view of the positions. It shows incoming payment flows and any tax flows that may have to be generated. The cash flow is based on update types.

**Supported Device Types**

Desktop

Tablet

**Related Information**

Cash Flow for a Class in a Securities Account Manage Statements - External Securities Account

External Securities Account Statements

###### Delete Statement - External Securities Account

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > External Securities Account Statements > Delete Statement - External Securities Account | L5 | trm06 p.286 | loio `bd6222c735fd490aac345359b4ecc935` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bd6222c735fd490aac345359b4ecc935.html?locale=en-US)

- App ID: RECON6


With this app, you can delete external securities account statements, for example, after reconciliation with the internal securities account class positions.

**Activities**

- 1. Open the Delete Statement - External Securities Account app on the SAP Fiori launchpad.
- 2. Using the selection criteria, you can select the external securities account statements that you want to delete. For example, you could select all external securities account statements with the status SCLOS.

To calculate the market values in local currency, you can choose the securities stock exchange and the security price type that you want to use.

- 3. Choose Execute.


**Note:**

You can first delete external securities account statements as a test run.

**Supported Device Types**

Desktop

Tablet

**Related Information**

External Securities Account Statements

##### Issue

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Issue | L4 | trm06 p.286 | loio `a517da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a517da531198434de10000000a174cb4.html?locale=en-US)

Use

The following transactions are available to help you edit and manage issue transactions and issue positions of bonds.

Issue Volumes

Issue Charges

Issue Hedge

Issue Position

See also:

Bond Issue

###### Issue Volumes

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Issue > Issue Volumes | L5 | trm06 p.287 | loio `a430c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a430c753b1081d4be10000000a174cb4.html?locale=en-US)

**Use**

This report provides you with an overview of the individual nominal flows from issue transactions for a selected key date.

**Note:**

Redemptions are not displayed.

See also:

Bond Issue

Issue Charges

Issue Hedge

Issue Position

**Integration**

This report is a query. It is based on InfoSet /SAPQUERY/CFM_ISSUE, which, in turn, is based on logical database FTI_TR_DEALS .

- The technical name of this query is CFM_DEAL_02.


**Features**

Selection

Use the fields available to select the positions to be evaluated.

See also:

Refer also to the field help documentation and the documentation on the logical database underlying this report.

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

###### Issue Charges

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Issue > Issue Charges | L5 | trm06 p.287 | loio `a730c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a730c753b1081d4be10000000a174cb4.html?locale=en-US)

**Use**

This report gives you an overview of the other flows that exist for an issue transaction. You can specify a specific time period or key date for the selection.

**Note:**

You may have to make an additional selection using the flow types if you use other flow types that do not represent the issue charges.

See also:

Bond Issue

Issue Volumes

Issue Hedge

**Integration**

This report is a query. It is based on InfoSet /SAPQUERY/CFM_ISSUE, which, in turn, is based on logical database FTI_TR_DEALS .

The technical name of this query is CFM_DEAL_01.

**Features**

Selection

Use the fields available to select the positions to be evaluated.

See also:

Refer also to the field help documentation and the documentation on the logical database underlying this report.

Output

The list is displayed using the SAP List Viewer .

See also:

SAP List Viewer for SAP GUI (Classic)

###### Issue Hedge

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Issue > Issue Hedge | L5 | trm06 p.288 | loio `aa30c753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/aa30c753b1081d4be10000000a174cb4.html?locale=en-US)

**Use**

This report displays selected data from the issue class position in a securities account for existing hedging transactions of an issue position.

You use the ICH reference category to assign the hedging transactions and the selection.

See also:

Reference

Bond Issue

Issue Position

Issue Volumes

Issue Charges

**Integration**

This report is a query. It is based on InfoSet /SAPQUERY/CFM_ISSUE, which, in turn, is based on logical database FTI_TR_DEALS .

- The technical name of this query is CFM_DEAL_03.


**Features**

The only transactions and positions selected are those with a reference from the ICH category that are also active on the selected key date.

Information for a position is displayed in a line in each case. Hedging transactions (for example, OTC transactions) are, however, divided into two lines:

Fixed interest calculation

Variable interest calculation

This list is output with the SAP List Viewer . With the sort function and total function you can use the reference to display the net positions for both the fixed interest calculated (plain vanilla) and the variable interest calculated (floating rate).

See also:

SAP List Viewer for SAP GUI (Classic)

##### Execute Capital Increase

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Execute Capital Increase | L4 | trm06 p.289 | loio `ea18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ea18da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can map the process of an increase in capitalization in the system. Different steps in which different apps are involved need to be performed. You post the subscription rights and transfert the new stocks into old stocks as a corporate action. But you exercise the subscription rights using the Exercise Rights app. Before the individual steps can be executed, you must first create the subscription rights and also the new stock as classes and create the position indicators.

**Integration**

[figure TRM06-F107 - Overview: Capital Increase]

Overview: Capital Increase

You can use the following functions to perform the individual steps within this process:

|Function|Result|
|---|---|
|Enter class master data for the new stock and the subscription right. For more information, see also Manage Securities Classes app. |The new stock and the subscription right are created as security classes in the system. The subscription right appears in the Exercise Rights app under the right category Subscription Rights.|
|Create the position indicator for the new stock and the subscription right. For more information, see also Manage Position Indicator app. |The position indicators for the new stock and the subscription right are created.|
|Use the Manage Corporate Actions app to post the subscription rights. For more information, see also Corporate action. |The subscription rights that are issued from the old stocks are in the system available as position. The old stocks position is written down by an amount equal to the accounting value of the subscription rights, and the subscription rights position is posted.|
|Purchase/sell subscription rights, if required. For more information, see also Create Security Transaction. |The required number of subscription rights is in the position.|
|Exercise subscription rights For more information, see also Exercise Rights. |The subscription rights are exercised and the new stocks are obtained accordingly. The new stock is posted and the corresponding positions are available.|


|Function|Result|
|---|---|
|Transfer new stock If the new stocks are completely equal to the old stocks, you can transfer the new stocks to the old stocks. For more information, see also Corporate action. |During the transfer posting, the ID number of the old stock is determined automatically for the new stock. The position of new stocks is no longer available and the position of the old stocks is increased accordingly.|


**Note:**

The total value of a securities account position does not change as a result of the capital increase. The subscription rights that result from the capital increase simply shift the proportional share value.

The value of the subscription right for accounting purposes (account-based value) differs from the theoretical value if the book value of the old stock is lower than its current market value. In this case, you have to determine the accounting value of the subscription right by matching its theoretical value to the book value of the old stock.

The book value of the old stocks is, on the one hand, reduced by the amount of the accounting value of the subscription rights, and, on the other hand, the subscription right is posted to the position by the same amount. This means that the total value of the positions before and after the capital increase is the same.

The adjustment flows required for the book value markdown in the old stocks position are generated automatically.

Calculation of the Theoretical Value and the Account-Based Value of the Subscription Right

[figure TRM06-F108 - Calculation of the Theoretical Value and the Account-Based Value of the Subscription Right]

Example

|Case a) Book value of the old stock <= Market value of the old stock| |
|---|---|
|Book value of old stock|80 EUR|
|Market value - old stock|100 EUR|
|Purchase price - new stock|50 EUR|
|Dividend discrepancy - new stock|1 EUR|
|Subscription right ratio|1:1|
|Subscription ratio|1:1|
|Theoretical value of subscription right = (100 EUR - 50 EUR - 1 EUR) / (1 + 1) = 24.5 EUR| |
|Account-based value = 24.50 EUR * (80 / 100) = 19.60 EUR| |
|Case b) Book value of the old stock > Market value of the old stock| |
|Book value of old stock|80 EUR|
|Market value - old stock|70 EUR|
|Purchase price - new stock|50 EUR|
|Dividend discrepancy - new stock|1 EUR|
|Subscription right ratio|1:1|
|Subscription ratio|1:1|
|Theoretical value of subscription right = (70 EUR - 50 EUR - 1 EUR) / (1 + 1) = 9.50 EUR| |
|Account-based value = Theoretical value of subscription right = 9.50 EUR| |


**Related Information**

Manage Securities Classes Corporate Action Exercise Rights Exercising Subscription Rights

##### Exercise Rights

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Exercise Rights | L4 | trm06 p.292 | loio `7199d65378024308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7199d65378024308e10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to exercise security rights and option rights. The system supports the exercise of the following rights and rights categories:

Exercisable Security Rights

|Rights Category|Option Category| |Type of Exercise / Settlement| |
|---|---|---|---|---|
|Equity warrant|Put|Call|Delivery|Cash settlement|
|Bond warrant|Put|Call|Delivery|Cash settlement|
|Currency warrant|Put|Call|Cash settlement| |
|Index warrant|Put|Call|Cash settlement| |
|Subscription right|-|--|Exercise| |
|Warrant bond (percentage-quoted and unit-quoted)|-|-|Detach| |
|Convertible bond (percentage-quoted and unit-quoted)|-|-|Convert| |
|Right of notice for puttable bond (percentage-quoted and unit-quoted)|-|-|Give notice| |
|Right of notice for callable bond|-|--|Give notice| |
|Stock swap|-|-|Execute stock swap| |


Exercisable Option Rights

|Rights Category|Option Category| |Exercise Type| |
|---|---|---|---|---|
|Stock option|Put|Call|Delivery|Cash settlement|
|Bond option|Put|Call|Delivery|Cash settlement|
|Index option|Put|Call|Cash settlement| |


**Note:**

The system does not support the exercise of options on futures.

**Integration**

You create securities that grant executable rights as security classes. Once you have created these classes and the data for the respective executable right, they appear in the structure for executable rights when you call the Exercise Rights function.

The Exercise function generates flows based on update types that the system then passes on to the parallel valuation areas. The derived business transactions that depend on the valuation area are then generated automatically for exercising the rights.

Once you execute this function, the system sets a lock for the positions involved, preventing any changes being made to their business transactions with dates before the key date of the exercise.

The system performs the authorization check as follows:

The authorization object T_RIGHTS is used for securities and T_RIGHTS_D is used for listed options. When exercising a right, the system performs checks for the individual activities (exercise, display, simulate, and reverse) for each company code and securities account or futures account.

If the system finds classes with executable rights, it first loads all the positions in the specified company code. Each position is then checked to see whether you have display authorization. If you do not have sufficient authorization, the system cannot display the position.

If you have display authorization, the system then checks whether you are also authorized to exercise rights. If you do not have the required authorization, the system displays the position to be exercised as a zero position. It is not possible to make any entries.

**Prerequisites**

You have sufficient authorization to exercise rights.

In Customizing, under Treasury and Risk Management Transaction Manager Securities Position Management

Rights , you have defined the corresponding update types and assigned them to the usages Exercise Rights and Additional Flows (Exercise Rights). You have also assigned the update types to Rights Categories.

The following update types are delivered with the system:

- RHT0001 Rights: Position inflow units/nominal

- RHT0002 Rights: Position outflow units/nominal

- RHT0003 Rights: Position inflow amount

- RHT0004 Rights: Position outflow amount

- RHT0005 Rights: Incoming payments

- RHT0006 Rights: Outgoing payments

- RHT0007 Rights: Position inflow amount (liabilities)

- RHT0008 Rights: Position outflow amount (liabilities)


You have defined account determination for the update types relevant for posting. In Customizing for the Transaction Manager choose General Settings Accounting Link to Other Accounting Components Define Account Determination .

Positions exist for the security right.

You have not executed any valuations after the key date of the exercise.

**Features**

The system displays the positions for each company code for a particular key date and for selected securities or listed options. For each position, you can determine which part of the position is exercised.

If you save an exercise right, the system automatically generates business transactions that reflect position changes in the system.

You can use various rights depending on the product category selected from the exercisable class.

In the application menu for Treasury and Risk Management, choose Transaction Manager Derivatives/Securities Trading

Option Right/Security Right Exercise (transaction FWER).

**Activities**

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Securities Trading Security Right Exercise (transaction FWER).


- 2. Enter the company code.
- 3. Enter the key date.
- 4. Choose the ID Number.
- 5. Check your entries in the Header Data.
- 6. In the Position area, enter the nominal amount to be exercised or the number of units to be exercised for each securities account/futures account, general valuation class or long/short indicator.
- 7. Select the relevant line, choose Postprocess Flows and check the generated flows. Change these flows, if necessary, and/or enter other flows.
- 8. Check whether you have defined payment details for each payment flow.
- 9. Carry out a Test Run for the exercise. If errors occur, an error log appears.
- 10. Choose Exercise Right. If the posting run is completed successfully, the system displays a posting log with the flows concerned.


**Note:**

You can use the F4 help for finding ID numbers to do this.

**Note:**

The system checks the number entered during the exercise. A message appears if the minimum exercise is not reached, for example.

When exercising a right, the system generates a document for each exercised position. You can use this document to reverse the exercise, if necessary.

**Related Information**

Exercising Subscription Rights Execute Capital Increase Defining Global Payment Details Exercise the Expiration Right Flows Generated During the Exercise and Expiration of Rights

###### Exercising Subscription Rights

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Exercise Rights > Exercising Subscription Rights | L5 | trm06 p.295 | loio `de18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/de18da531198434de10000000a174cb4.html?locale=en-US)

**Activities**

- 1. Choose Trading Security Right Exercise . This takes you to the initial screen.
- 2. Make the entries in the following fields:


ID Number (of the subscription right)

Key Date

- 3. Confirm your entries by choosing Enter .

In the Header data area, you can now see the data for the subscription right (most importantly: the subscription data period and subscription ratio) and for the new stock.

The data shown is read from the class data of both securities.

In the Rights area, you can choose between different subscription periods if more than one exists.

In the Position area, you can see the existing positions for the subscription right for each securities account on the key date.

In the Unit. to ex. field, you enter the number of subscription rights you wish to exercise. The default value is always the total number of subscription rights.

You can enter other flows for the automatically-generated incoming and outgoing flows for each securities account, or you can change the flows generated. You also have the option of maintaining the payment details for the payment flows.

For more information, see also: Postprocessing Flows.

- 4. If all prerequisites are met and you have entered all the details for the exercise, you can carry out a test run. Choose Test Run.


- 5. Once the test run is successful, you can start the update run. Choose


- 6. The system generates a posting log.


See also: Flows Generated When Exercising Security Rights

If you have to reverse the exercise of the subscription rights, you can use the Reverse Rights function.

**Result**

When you exercise subscription rights, new stock is added to your position. You post new stocks at the value of the corresponding subscription rights and the subscription price paid.

###### Postprocessing Flows

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Exercise Rights > Exercising Subscription Rights > Postprocessing Flows | L6 | trm06 p.296 | loio `1e18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1e18da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can enter Other Flows for the incoming flows and outgoing flows for each securities account, or you can change the flows generated. You also have the option of maintaining the payment details for the payment flows.

The system saves all the flows that you change or enter if you interrupt processing, for example, to exercise another right. The flows you have entered stay as they are, and you can call them up again at any time.

**Features**

The Postprocess Flows screen is divided into the following areas:

General data

Securities Account

ID Number (reference)

Posting Control Data

Posting Date

Document Date

Assignment

You cannot change this data here.

To change the posting control data (for example, in order to define data in the Assignment area), go to the main screen for processing security rights. From there, you can choose (Posting control...) to branch to the screen for maintaining this data.

Payment Details

Here, you can see the payment details for the payment flows. The payment details data is either taken from the securities account master data or the global payment details (if you have have defined them).

You can change the data.

See also:Defining Payment Details per Securities Account

Generated flows

In this area you see the flows that were generated by the system for exercising the right.

See also:Flows Generated when Exercising Security Rights

You have the option of overriding the flow types for these flows. That means you can choose a different flow type, provided that is has the same flow category as the original flow type. Using the F4 Help for this field, you can choose one flow type from all the flow types displayed for this flow category.

Payment Flows

If payment flows arise when you exercise a security right, for example, for a warrant with cash settlement, the system generates a payment flow.

To change the data for a payment flow, select the flow and choose (Change Payment Flow) .

You can adjust a payment flow both in the settlement amount and in the settlement currency.

Other Flows

Here, you can enter the other flows for the incoming and outgoing flows.

For more information, see also: Entering Other Flows.

**Example:**

You exercise 30 equity warrants (Call with cash settlement ).

Base price : 100 EUR

Option ratio : 3:1

Current market price of the stock : 200 EUR

Additional payment : 1,000 EUR (= (30 * 1) / 3 * (200 EUR – 100 EUR)

If an incorrect market price for the stock was used to calculate the addition payment amount, you can change the amount calculated of 1,000 EUR.

It is often the case with payment flows that the settlement currency, the position currency and the local currency differ.

The position and local currency amounts are each calculated from the settlement amount using the exchange rates from the central exchange rate table. You can change these rates provided that the rate was not fixed.

You can also enter the amounts directly in the system. If you do this, the system no longer displays the exchange rates.

###### Entering Other Flows

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Exercise Rights > Exercising Subscription Rights > Postprocessing Flows > Entering Other Flows | L7 | trm06 p.298 | loio `2718da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2718da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can only enter other flows for the incoming and outgoing flows.

**Prerequisites**

The valid update types must have been assigned to the usage Exercise rights in Customizing. You do this under Assign Update Types to Usages .

**Procedure**

- 1. Select the incoming/outgoing flow for which you want to enter another flow.
- 2. Choose ( Insert line ) in the Other flows area. The Create Other Flow dialog box appears.
- 3. The exchange rates area displays the rate(s) which is/are used to translate the amounts to settlement currency, position currency and local currency. The rates are taken from exchange rate table. Here, you can define another rate manually provided that the rate was not fixed.

- a. Choose one of the existing flow types.
- b. Enter the amount and the currency of the flow by choosing Amount in settlement currency. You are free to choose the settlement currency, which can differ both from the position currency and the local currency.


- 4. Choose . The amounts are calculated in position currency and local currency.
- 5. Choose Copy to save the other flow.
- 6. If want to delete the other flow you have entered, select the other flow and choose ( Delete line ).



**Result**

The other flows are entered and stored according to your entries.

###### Defining Payment Details per Securities Account

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Exercise Rights > Exercising Subscription Rights > Postprocessing Flows > Defining Payment Details per Securities Account | L7 | trm06 p.298 | loio `2a18da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2a18da531198434de10000000a174cb4.html?locale=en-US)

Use

If payment flows are generated when you exercise a right, you must enter payment details (house bank and house bank account) for this payment.

You are recommended to use the house bank and the house bank account values taken from the securities account master data.

If you want to use a different form of payment processing to the one defined in the securities account master data, you can overwrite the default values from the master data for the securities account.

If no entries have been made for the house bank/house bank account in the securities account master data, you must enter the payment details manually.

In the Exercise security rights function, there are two ways of entering payment details:

- 1. You can define global payment details that apply for all securities accounts ( see also : Defining Global Payment Details ).

- 2. Alternatively, you can define the payment details at securities account level using the Postprocess flows function.


**Note:**

If you define the payment details globally, you can then overwrite these at securities account level. In other words, if you actually want other payment details to be valid for a securities account, you can create these entries using the Postprocess flows function.

The procedure below describes how to define payment details at securities account level.

**Prerequisites**

You must have defined the master data for the house bank in the Basic Functions area by choosing Master Data House Banks.


**Procedure**

- 1. Go to the initial screen for exercising security rights.
- 2. In the area headed Position , select the securities account for which you want to define other payment details.
- 3. Choose ( Postprocess flows). The screen for postprocessing flows appears.


- 4. Change the entries for the house bank and the house bank account in the Payment details area.
- 5. When you have entered your data, choose .



**Result**

The entries you changed for the house bank and the house bank account were saved.

###### Defining Global Payment Details

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Exercise Rights > Defining Global Payment Details | L5 | trm06 p.299 | loio `2418da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2418da531198434de10000000a174cb4.html?locale=en-US)

**Use**

If payment flows are generated when you exercise a right, you must enter payment details (house bank and house bank account) for this payment.

The system uses the default values from the house bank and the house bank account that you entered in the securities account or futures account master data. You can change or add to the standard values for payment processing at any time.

**Prerequisites**

You have defined the master data for the house bank. On the SAP Easy Access screen, choose Treasury and Risk Management Master Data House Banks Edit House Banks and Bank Accounts (FI12).

You have called up transaction Exercise Security Rights or Exercise Option Rights (FWER). On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Securities / Derivatives Trading Security Rights/ Option Rights Exercise .

**Procedure**

There are two ways of defining payment details:

You can define global payment details that apply to all securities accounts or futures accounts.

Alternatively, you can define the payment details at securities account level or futures account level using the Postprocess Flows function.

The procedure below describes how to define global payment details:

- 1. Go to the initial screen and choose the security right or option right for which you want to define global payment details.
- 2. Choose ( Payment details... ). Use the input help to choose the House bank and the House bank account .
- 3. Choose Copy.


**Result**

You have defined global payment details which are valid for all the securities accounts or futures accounts involved when you exercise the right, provided that you do not make any changes to individual securities accounts or futures accounts at a later date.

See also:Define Payment Details per Securities Account

###### Exercise the Expiration Right

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Exercise Rights > Exercise the Expiration Right | L5 | trm06 p.300 | loio `2e15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2e15da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can also exercise the expiration right for the following rights categories:

Equity Warrant

Bond Warrant

Index Warrant

Currency Warrant

Stock Option

Bond Option

Index Option

Subscription Right

**Prerequisites**

In Customizing for the Transaction Manager, you have defined the corresponding update types and assigned them to the Rights Exercise usage and the relevant Rights Categories. To do this, choose Transaction Manager Securities/Listed Derivatives

Position Management Rights .

**Note:**

We provide you with the standard update type Rights: Position outflow units/nominal (RHT0002).

**Procedure**

- 1. In the area menu, choose Treasury and Risk Management Transaction Manager Derivatives / Securities Trading Option Right/Security Right Exercise (transaction FWER).
- 2. In the dialog structure, choose the executable right and set the Expiration Right indicator under Specific Right.
- 3. In the Position screen area under Units to Be Exercised, enter the number of units that are to be expired for the relevant securities account or futures account.
- 4. Once the test run is successful, you can exercise the expiration right. The system displays a message informing you that the exercise was fixed.


**Result**

When you exercise the expiration right, the system posts the relevant securities or options from the position and automatically generates a derived business transaction containing the price loss flows associated with the expiration.

###### Flows Generated During the Exercise and Expiration of Rights

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Exercise Rights > Flows Generated During the Exercise and Expiration of Rights | L5 | trm06 p.301 | loio `dd16da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dd16da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Flows are divided into the following groups:

Write-off of exercised (partial) position:

The class position that contains the right is reduced by the exercised portion. The system generates this flow when exercising each right, regardless of the type. When an expiration right is exercised, the system only generates the write-off flow.

Post / Clear the Underlying:

This flow reflects the inflow or outflow of the underlying position. The system only generates this flow for rights with delivery, and not for rights with cash settlement. The type of warrant or option (call or put) determines whether the flow is an inflow or outflow.

Incoming/Outgoing Payment:

This flow is a payment that becomes due based on the right. The flow is generated when you exercise warrants or subscription rights. It may be an incoming or outgoing payment, depending on whether the position is a long position or short position of an option.

Position Inflow/Outflow Amount:

For each incoming payment flow, the system generates a flow from the category Position Inflow Amount. For each outgoing payment flow, a flow is generated from the category Position Outflow Amount. The system uses these flows to map the impact of the exercise on the value of the affected position.

In addition, the system generates a derived business transaction for each valuation area that includes flows for price gains as well as transfer postings of acquisition or book values. These flows are based mainly on your Customizing settings and are not taken into account in the following examples.

**Example**

Flows Generated When Exercising Call Warrants with Cash Settlement

There are 100 Call with cash settlement warrants for an A-stock in your position that you have purchased for 4 EUR each. The base price is EUR 400, the warrant ratio is 10:1, and the current market price is EUR 450. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Warrant position outflow (units)|100| |
|Warrant position outflow| |500|
|Incoming payment| |500|


Flows Generated When Exercising Call Warrants with Delivery

There are 100 Call with cash settlement warrants for an A-stock in your position that you have purchased for 4 EUR each. The base price is EUR 400, the warrant ratio is 10:1, and the current market price is EUR 450. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Warrant position outflow (units)|100| |
|Underlying position inflow (units)|100/10 =10| |
|Underlying position inflow| |4.000|
|Disbursement for underlying| |4.000|


Flows Generated When Exercising Put Warrants with Delivery

There are 100 Call with cash settlement warrants for an A-stock in your position that you have purchased for 4 EUR each. The base price is EUR 400, the warrant ratio is 10:1, and the current market price is EUR 350. There are 20 A-stocks in the position. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Warrant position outflow (units)|100| |
|Underlying position outflow (units)|100/10 =10| |
|Underlying position outflow| |4.000|


|Update Type|Units|Amount (EUR)|
|---|---|---|
|Incoming payment for underlying| |4.000|


Flows Generated when a Warrant Expires

There are 100 Call with cash settlement warrants for an A-stock in your position that you have purchased for 4 EUR each. The base price is 400 EUR. The warrant ratio is 10:1 and the current market price is 380 EUR. The market situation causes all warrants to expire. When you exercise the expiration right, the system generates the following flow:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Warrant position outflow (units)|100| |


Flows Generated when Exercising a Subscription Right

You purchased 400 subscription rights for new A-stocks with subscription ratio 4:1. The subscription price is EUR 300. You exercise all 400 of the subscription rights. The system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of subscription rights (units)|400| |
|Position inflow of new stocks (units)|400 / 4=100| |
|Position inflow of new stocks| |30.000|
|Disbursement for new stock| |30.000|


Flows Generated when Converting a Convertible Bond

There is a convertible bond with an acquisition value of 10,000 EUR (nominal 10,000 EUR) in the position with the right to convert this into 20 A-stocks. The conversion price is 10 EUR per stock. The system generates the following flows during the conversion:

|Update Type|Units/nominal|Amount (EUR)|
|---|---|---|
|Position outflow of convertible bond (units)|10.000| |
|Position inflow of A-stocks (units)|20| |
|Position inflow of A-stocks (amount)| |200|
|Disbursement for A-stocks| |200|


Flows Generated when Detaching a Warrant Bond

There is a warrant bond cum in your position with an acquisition value of 10,000 EUR (nominal 10,000 EUR) appended with 20 Astocks warrants. The current price of the cum warrant is 101% and the price of the ex-warrant is 99%. When detaching the warrants from the cum warrant, the system generates the following flows:

|Update Type|Units/nominal|Amount (EUR)|
|---|---|---|
|Position outflow of cum warrants (units)|10,000 EUR| |


|Update Type|Units/nominal|Amount (EUR)|
|---|---|---|
|Position inflow of ex-warrants (units)|10,000 EUR| |
|Position inflow of warrants (units)|20| |


Flows Generated when Swapping a Stock

You have 100 A-stocks in your position. You have the offer of swapping the A-stocks for B-stocks at a ratio of 1:50 and to pay a clearing amount of EUR 2 per B-stock. You exercise the stock swap for all of the A-stocks. The system generates the following flows:

|Update Type|Units/nominal|Amount (EUR)|
|---|---|---|
|Position outflow of A-stocks (units)|100| |
|Position inflow of B-stocks (units)|100 x 50 = 5,000| |
|Position inflow of B-stocks| |10.000|
|Disbursement for B-stocks| |10.000|


Flows generated when calling a bond

You have a bond in your position with an acquisition value of 10,000 EUR (nominal 10,000 EUR). The right of notice can be converted to a rate of 101%. When you terminate the bond, the system generates the following flows:

|Update Type|Nominal Amount|Amount (EUR)|
|---|---|---|
|Position outflow of bond (units)|10,000 EUR| |
|Position outflow of bond| |10.100|
|Incoming payment for bond| |10.100|


Flows Generated During the Expiration of a Stock Option

You have a long position with 10 options contracts (Call with Cash Settlement) in an A-stock. The base price is EUR 400, the warrant ratio is 10:1, and the current market price is EUR 380. Due to the market situation, all the options contracts expire.

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of option (units)|10| |


Flows Generated when Exercising a Call Option on Stock with Cash Settlement: Long

You have a long position with 10 options contracts (Call with Cash Settlement) in an A-stock. The base price is EUR 400, the warrant ratio is 1:10, and the current market price is EUR 450. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of option (units)|10| |
|Exercise date of the option| |5000|


|Update Type|Units|Amount (EUR)|
|---|---|---|
|Incoming payment| |5000|


Flows Generated when Exercising a Call Option on Stock with Cash Settlement: Short

You have a short position with 10 options contracts (Call with Cash Settlement) in an A-stock. The base price is EUR 400, the warrant ratio is 1:10, and the current market price is EUR 450. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of option (units)|10| |
|Position inflow of the option| |5000|
|Disbursement| |5000|


Flows Generated when Exercising a Call Option on Stock with Delivery: Long

You have a long position with 10 options contracts (Call with Cash Delivery) in an A-stock. The base price is EUR 400, the warrant ratio is 1:10, and the current market price is EUR 450. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of option (units)|10| |
|Position inflow of stock (units)|100| |
|Position inflow of stock| |40.000|
|Stock disbursement| |40.000|


Flows Generated when Exercising a Call Option on Stock with Delivery: Short

You have a short position with 10 options contracts (Call with Cash Delivery) in an A-stock. The base price is EUR 400, the warrant ratio is 1:10, and the current market price is EUR 450. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of option (units)|10| |
|Stock position outflow (units)|100| |
|Stock position outflow| |40.000|
|Incoming payment for stock| |40.000|


Flows Generated when Exercising a Put Option on Stock with Cash Settlement: Long

You have a long position with 10 options contracts (Put with Cash Settlement) in an A-stock. The base price is EUR 400, the warrant ratio is 1:10, and the current market price is EUR 450. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of option (units)|10| |
|Exercise date of the option| |5.000|
|Incoming payment| |5.000|


Flows Generated when Exercising a Put Option on Stock with Cash Settlement: Short

You have a short position with 10 options contracts (Put with Cash Settlement) in an A-stock. The base price is EUR 400, the warrant ratio is 1:10, and the current market price is EUR 350. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of option (units)|10| |
|Position inflow of the option| |5.000|
|Disbursement| |5.000|


Flows Generated when Exercising a Put Option on Stock with Delivery: Long

You have a long position with 10 options contracts (Put with Delivery) in an A-stock. The base price is EUR 400, the warrant ratio is 1:10, and the current market price is EUR 350. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of option (units)|10| |
|Stock position outflow (units)|100| |
|Stock position outflow| |40.000|
|Incoming payment for stock| |40.000|


Flows Generated when Exercising a Put Option on Stock with Delivery: Short

You have a short position with 10 options contracts (Put with Delivery) in an A-stock. The base price is EUR 400, the warrant ratio is 1:10, and the current market price is EUR 350. When you exercise the warrants, the system generates the following flows:

|Update Type|Units|Amount (EUR)|
|---|---|---|
|Position outflow of option (units)|10| |
|Position inflow of stock (units)|100| |
|Position inflow of stock| |40.000|
|Stock disbursement| |40.000|

##### Reverse Rights

> **Path:** Treasury and Risk Management > Transaction Manager > Securities Account Management > Reverse Rights | L4 | trm06 p.306 | loio `9818da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9818da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to reverse security rights and option rights you have already exercised. The system executes the reversal function for one or more securities accounts. You can also reverse individual flows in the exercise.

**Note:**

You can only reverse the last right exercised for each ID number in a securities account and company code.

**Procedure**

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Securities Trading Security Right Reverse (FWER_STORNO_NEU) .


- 2.

Reverse the exercising of a security right:

Specify the company code, the ID number of the exercised right, and the securities account. You can reverse the exercise of the right for one securities account or multiple securities accounts simultaneously. If you want to reverse the rights exercise for all securities accounts, enter the placeholder *.

Reverse the exercising of an option right:

Specify the company code, the ID number of the exercised right, and the futures account. You can reverse the exercise of the right for one or more positions simultaneously. If you want to reverse the rights exercise for all futures accounts, enter the placeholder *.

- 3. You can also specify the key date of the rights exercise to be reversed.
- 4. Select a reason for reversal.
- 5. Once the test run is successful, you can execute the reversal procedure. The system displays a reversal log with the relevant flows.


**Note:**

The system checks whether the key date specified for the last rights exercise is the same for this ID number in this securities account and company code. If this is not the case, the system enters the date of the last exercise in the key date field.

If you leave the key date field blank, the system determines the key date of the last rights exercise.

If you have selected several securities accounts, the system determines all the key dates of the last rights exercise for this ID number. If the key date is identical for each rights exercise, the system displays this key date.

