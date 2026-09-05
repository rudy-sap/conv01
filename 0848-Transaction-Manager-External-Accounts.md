# Transaction Manager > External Accounts - SAP TRM Knowledge Base (branch split)

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

#### External Accounts

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts | L3 | trm06 p.223 | loio `83df5dc9b5454b18a1611199cfb93076` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/83df5dc9b5454b18a1611199cfb93076.html?locale=en-US)

**Use**

External accounts represent accounts that you have with business partners. An example of an external account is the clearing account that you have with your central counterparty. The functions for the external accounts allow you to portray central counterparty clearing.

**Implementation Considerations**

To be able to use these functions, you need to make the following settings:

Customizing

In Customizing for external accounts under Transaction Manager General Settings Define Product Type for External Account Positions , you first have to create a product type (for product category 690 External Accounts) for the positions on the external accounts.

In the activity External Accounts Define Account Assignment Reference Determination (External Accounts) , you can define rules for automatically determining account assignment references for your external account positions in the parallel valuation areas. To be able to make postings to a clearing position, you need to assign an account assignment reference to each clearing account position. The system assigns the account assignment references automatically when you post a flow to the clearing account for the first time using the Post Flows (TREA) [transaction TREA_POST_FLOWS] function. The assignment is made on the basis of the rules that you define in this Customizing activity.

**Note:**

You need to have previously created the account assignment references in the activity Transaction Manager

General Settings Accounting Link to Other Accounting Components Define Account Assignment References .

In the activity External Accounts Central Counterparty Clearing Activate Central Counterparty Clearing , you have to activate clearing for your relevant financial transactions specifically for the company code, product type, and transaction type. You can choose between the following clearing options:

Central Clearing Mandatory

Central Clearing Optional

Central Clearing Already Occurred

Not relevant

Under External Accounts Central Counterparty Clearing Update Types , you first need to call the Define Update Types and Assign Usages Customizing activity, create all update types that are required for central counterparty clearing, and assign them to the External Account: Central Counterparty Clearing usage.

In the Specify Update Types for Central Counterparty Clearing activity, you need to assign the flow category to these update types. You also need to select the Aggregation-Relevant checkbox. With this checkbox, you can decide for each update type of the external account whether the flows of that update type are relevant for aggregation.

If you select the Aggregation-Relevant checkbox for an update type, all flows of this update type within an external account statement are summarized into one flow on the clearing account position.

All summarized flows are cleared with a net payment (transaction TREA_PAY).

If you do not select the Aggregation-Relevant checkbox, the flows are not summarized and do not form part of the net payment. Instead, individual payments are made for these flows.

In the activity Assign Update Types for Clearing Account Positions, you have to assign update types for the transaction-dependent variation margins and fees. This is because the transaction-dependent flows need to be visible on the assignment position as well as on the clearing account position.

In the activity Assign Update Types for Net Payment, you assign an update type for an outgoing net payment and an update type for an incoming net payment.

**Example:**

You need to create one update type for each flow category and four update types for the transaction-dependent flows on the clearing account position:

|Update Type|Name|Flow Category|Comment|
|---|---|---|---|
|EA_FEE+|CCC: Fee Refund|Fee Refund|Is relevant for posting Is relevant for payment when the AggregationRelevant is not set|
|EA_FEE-|CCC: Fees|Fees|Is relevant for posting Is relevant for payment when the AggregationRelevant is not set|
|EA_FEED+|CCC: Fee Refund (DealRelated)|Fee Refund (Deal-Related)|Is relevant for posting Is relevant for payment when the AggregationRelevant is not set|


|Update Type|Name|Flow Category|Comment|
|---|---|---|---|
|EA_FEED-|CCC: Fee (Deal-Related)|Fee (Deal-Related)|Is relevant for posting Is relevant for payment when the AggregationRelevant is not set|
|EA_INI+|CCC: Initial Margin Refund|Initial Margin Refund|Is relevant for posting Is relevant for payment when the AggregationRelevant is not set|
|EA_INI-|CCC: Initial Margin Outgoing|Initial Margin Outgoing|Is relevant for posting Is relevant for payment when the AggregationRelevant is not set|
|EA_MTI+|CCC: Positive Variation Margin (Deal-Independent)|Positive Variation Margin (Deal-Independent)|Is relevant for posting Is relevant for payment when the AggregationRelevant is not set.|
|EA_MTI-|CCC: Negative Variation Margin (Deal-Independent)|Negative Variation Margin (Deal-Independent)|Is relevant for posting Is relevant for payment when the AggregationRelevant is not set|
|EA_MTM+|CCC: Positive Variation Margin|Positive Variation Margin|Is relevant for posting Is relevant for payment when the AggregationRelevant is not set|
|EA_MTM-|CCC: Negative Variation Margin|Negative Variation Margin|Is relevant for posting|


|Update Type|Name|Flow Category|Comment|
|---|---|---|---|
| | | |Is relevant for payment when the AggregationRelevant is not set|
|EA_INT-|CCC: Interest Outgoing|Fees|Not relevant for posting Must be marked as relevant for aggregation|
|EA_INT+|CCC: Interest Incoming|Fee Refund|Not relevant for posting Must be marked as relevant for aggregation|
|EA_NET-|Outgoing Net Payment| |Is relevant for posting Is relevant for payment|
|EA_NET+|Incoming Net Payment| |Is relevant for posting Is relevant for payment|
|EA_VM-|CLP: Negative Variation Margin|Does not need to be specified|Update Type for Flow on Clearing Account Position Is not relevant for posting or payment|
|EA_VM+|CLP: Positive Variation Margin|Does not need to be specified|Update Type for Flow on Clearing Account Position Is not relevant for posting or payment|
|EA_FEED-|CLP: Fee|Does not need to be specified|Update Type for Flow on Clearing Account Position Is not relevant for posting or payment|


|Update Type|Name|Flow Category|Comment|
|---|---|---|---|
|EA_FEED+|CLP: Fee Refund|Does not need to be specified|Update Type for Flow on Clearing Account Position Is not relevant for posting or payment|


In the activity Transaction Manager General Settings Accounting Link to Other Accounting Components Define Account Determination , you have to define how accounts are determined for the update types that are relevant for posting. For posting flows, you need to create a new account symbol (such as 9.9 CCC Technical Clearing) and assign to it the Central Clearing Posting in Payment Currency posting type. Furthermore, you create new posting specifications for the postings made with these accounts. You then assign these posting specifications to the update types. In the activity Assignment of G/L Accounts to Account Symbols, you then assign G/L accounts (which, technically, are clearing accounts) to the new account symbol, possibly on the basis of your account assignment references. You need to have created the G/L accounts beforehand in Financial Accounting.

See also:Posting Logic for Flows on Clearing Accounts

Authorization Objects

You can use the following authorization objects to assign authorizations for processing the new functions:

|Authorization Object|Permitted Activities|Description|
|---|---|---|
|T_TREA_STA|01 Create or Generate 02 Change 03 Display 06 Delete 43 Release|You use this authorization object to specify the activities for which users have authorization for an external account statement. The authorization object is checked by the following functions: Process External Account Statement (transaction TREA_STA_MNT) Upload External Account Statement (transaction TREA_STA_UPL) Release Positions (transaction TREA_RELEASE)|
|T_TREA_CA|01 Create or Generate 02 Change 03 Display 06 Delete NP Net Payment|You use this authorization object to specify the activities for which users have authorization for an external account. The authorization object is checked by the following functions: Process External Account (transaction TREA_ACC_MNT) Generate Net Payment (transaction TREA_PAY)|


**Integration**

The functions for the external accounts are integrated in transaction and position management in Transaction Manager.

**Key Features**

You can use the following functions for external accounts to manage clearing accounts in the Transaction Manager.

Enter Master Data

Create External Account

Defining Default Values for Clearing

Enter Clearing-Relevant Financial Transactions

When you enter a financial transaction, you assign a clearing account on the Administration tab page.

When the central counterparty has accepted or rejected clearing, you perform the function Accept/Reject Clearing (transaction TREA_CLEAR). You use the Reverse Clearing/Rejection function (transaction TREA_CLEAR_REV) to reverse clearing or a rejection.

To perform clearing, you can also use the Central Clearing Monitor (transaction TPMCCP).

Once you have entered the master data for an external account, you can also create the account statements for this account and release the account statement items.

See also:

Process External Account Statement (transaction TREA_STA_MNT)

Upload External Account Statement (transaction TREA STA_UPL)

Release Items (transaction TREA_RELEASE)

You can use the following functions to post flows to an external account and to make a payment for them:

Generate Net Payment (transaction TREA_PAY)

Post External Account Flows (transaction TREA_POST_FLOWS)

Reverse External Account Flows (transaction TREA_REVERSE)

Information System

You use the Clearing History (transaction TREA_CLEAR_HIST) to obtain an overview of all financial transactions that are relevant for clearing.

Assignment positions and clearing account positions are managed for clearing accounts. On the assignment positions, you find all flows of a clearing account that relate to a specific financial transaction. The clearing account position provides information about all flows on a clearing account. The clearing account position is integrated with Position Management. For an overview of existing positions, you can use the Display External Account Positions program (transaction TREA_SHOW_POSITIONS). The following values are displayed for the selected clearing account positions:

Variation Margin in Position Currency

Variation Margin in Local Currency

Initial Margin in Position Currency

Initial Margin in Local Currency

A clearing-relevant financial transaction is managed as an operative position on which you see the flows of the financial transaction. If you would like to see all flows for a clearing account as well as the flows of the related financial transactions, you can use the External Account : Position Flows program (transaction TREA_SHOW_FLOWS). Select the clearing account position, the operative position, and the relevant clearing account. However, you could also display just the flows on the assignment positions or on the clearing account positions.

**Restrictions**

You can use central counterparty clearing for foreign exchange transactions (product type 600) and for swaps (product type 620).

The clearing account positions are not integrated with the Risk Analyzer in SAP Treasury and Risk Management.

**See Also**

See also the documentation in Customizing for external accounts under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings External Accounts .

##### Positions for Clearing Accounts

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Positions for Clearing Accounts | L4 | trm06 p.229 | loio `2c54f49eb4a64e57aa53cc3e755039b3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2c54f49eb4a64e57aa53cc3e755039b3.html?locale=en-US)

Clearing Account Position

For clearing accounts, the clearing account position is used as a position in the sense of position management in the Transaction Manager. The clearing account positions are split up using the differentiation criteria Company Code, Valuation Area, Product Type, and External Account.

The clearing account position uses the following position components:

- 1001 Initial Margin

- 1002 Variation Margin


- 2001 Initial Margin Open

- 2002 Variation Margin Open

- 2003 Other (such as Fees) Open


8000 Clearing Payment

- 9000 Total Open

- 9001 Total Margin Open


All flows of an external account are entered into a clearing account position.

**Note:**

The transaction-dependent variation margin flows (in a position currency other than the valuation currency) can be valuated during the valuation of the corresponding FX transaction. For more information, see also Foreign Currency Valuation.

Assignment Position

The assignment position is not a position in the sense of position management in the Transaction Manager. It exists within external accounts. On the assignment position, you see all flows of a clearing account that relate to a specific financial transaction.

Operative Position

The operative position is not a position in the sense of position management in the Transaction Manager. It exists within external accounts. On the operative position, you see the transaction flows of a financial transaction that is relevant for clearing.

##### External Account Statement

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > External Account Statement | L4 | trm06 p.230 | loio `2c13cdc26aa84284bee863fb44c30944` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2c13cdc26aa84284bee863fb44c30944.html?locale=en-US)

**Use**

You can either enter an external account statement manually or upload it from an Excel file:

Processing External Account Statements

Uploading External Account Statements

If you have activated Margin Limit Management in Customizing for External Accounts under Central Counterparty Clearing and selected the functions for margin balances and margin limits in the master data of an external account, additional tabs are displayed for these.

Margin Balances and Margin Limits

After you have entered and checked the data of an account statement, you use the release line items function.

**More Information**

Margin Management

###### Processing External Account Statements

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > External Account Statement > Processing External Account Statements | L5 | trm06 p.230 | loio `078a32ea754d4215930dd872b31e8897` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/078a32ea754d4215930dd872b31e8897.html?locale=en-US)

**Use**

To process an external account statement, call the Process External Account Statement function (transaction TREA_STA_MNT) from the application menu for the Transaction Manager under External Accounts External Account Statement Process External Account Statement .

**Procedure**

|Function|Procedure|Comments|
|---|---|---|
|Create|1. Choose Create. 2. Enter the company code, the external account, and the date, and then choose Create. 3. Enter the following data for the first line item: |After saving, the account statement is created. It has the status Not Processed. All line items have the payment release status Not Released and the posting release status Not Released. You release the line items using the Release Line Items (TREA_RELEASE) function. |


|Function|Procedure|Comments|
|---|---|---|
| |Update Type Payment Amount Payment Currency Transaction Previous Net Present Value Current Net Present Value Previous Net Present Value: Clean Current Net Present Value: Clean External Reference 4. Choose Insert Line and enter additional line items. 5. When you have entered all line items of the external account statement, choose Save. |When the line items of the account statement are released, the flows are generated and posted to the clearing account position and assignment position. You use the following functions to post the flows and make the payments: Create Net Payments Post External Account Flows Reverse External Account Flows|
|Display|1. Choose an account statement from the hierarchy on the left-hand side of the screen. **Note:** All external account statements with the statuses Not Processed or Partially Processed are displayed in the hierarchy. If you also want to see processed account statements, choose Change Selection. In the dialog box that appears, you can restrict the display using the following criteria: Company Code External Account Date You can also restrict the display using the checkboxes Not Processed, Partially Processed, and Processed. By saving the settings that you make as a variant, you can set the variant as the default selection by choosing Set Default Selection.|In the case of positions that relate to a specific financial transaction, you can display the transaction data with the Display Transaction function. When a line item has been released, you can use the Display Cash Flow function to display the relevant flows on the clearing account position or on the assignment position. By choosing Environment Change Documents , you can display the change documents for an account statement.|


|Function|Procedure|Comments|
|---|---|---|
| |2. The account statement appears on the right-hand side of the screen.| |
|Change|1. Choose an account statement from the hierarchy on the left-hand side of the screen. 2. Choose Change. 3. Make the necessary changes. 4. Save your entries. |You can make changes only to line items that have not yet been released. In the case of line items that are released for payment but not yet for posting, you can change the transaction number.|
|Delete|1. Choose an account statement from the hierarchy on the left-hand side of the screen. 2. Choose Delete. |You can delete an external account statement only when none of its line items have been released.|


**More Information**

Margin Management

###### Uploading External Account Statements

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > External Account Statement > Uploading External Account Statements | L5 | trm06 p.232 | loio `52e8f8dc2de8424a98f66f4c7ec31031` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/52e8f8dc2de8424a98f66f4c7ec31031.html?locale=en-US)

**Prerequisites**

If you would like to import account statements from an Excel file, the file needs to meet certain format requirements.

The file format must be .xls or .xlsx.

The file must have the following columns:

|A|B|C|D|E|F|G|H|I|J|K|L|
|---|---|---|---|---|---|---|---|---|---|---|---|
|Date|Company Code|External Account|External Transaction Number|Transaction Number|Update Type|Payment Amount|Payment Currency|Local Currency Amount|Local Currency|Previous Net Present Value|Previous Net Present Value: Clean|


The external account needs to have been created in the system.

The Excel file to be uploaded must not be open during the upload.

**Context**

You can import an external account statement from an Excel file.

**Procedure**

- 1. Call the function Upload External Account Statement (transaction TREA_STA_UPL).
- 2. In the File Selection area, enter your Excel file in the File Name field. If you set the Background Processing checkbox, the file is uploaded directly.

If you do not set the Background Processing checkbox, you can check the data again before you upload it.

- 3. You can perform the upload as a test run first. For this, set the Test Run checkbox.
- 4. Choose Execute.
- 5. If you have not set the Background Processing checkbox, the Check Data Before Upload screen now appears.

The data from the Excel file is displayed in an SAP List Viewer list. You can now check whether the data is correct. If the data is correct, choose Save. If the data is not correct, choose Back. Correct the data in your Excel file and restart the upload.

- 6. The system checks the data and issues a message log. If an error occurs, the upload is terminated. In this case, you correct the data in the Excel file.


If no errors occur, the system creates the account statement and issues a success message.

###### Calculate Net Present Values of Financial Transactions for External Accounts

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > External Account Statement > Calculate Net Present Values of Financial Transactions for External Accounts | L5 | trm06 p.233 | loio `da8078d1bf7147c28eb60dc41cb9b439` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/da8078d1bf7147c28eb60dc41cb9b439.html?locale=en-US)

**Use**

You use this transaction for selected external accounts to calculate and display the discounted and nondiscounted net present values of the relevant financial transactions. You find this transaction in the area menu under Transaction Manager External Accounts External Account Statements .

**Prerequisites**

To be able to use this function, you need to have made the following settings:

You have made the Customizing settings for Central Counterparty Clearing. You find these settings under Transaction Manager General Settings External Accounts .

You have made the settings in Customizing for the Market Risk Analyzer. You find these settings under Treasury and Risk Management Market Risk Analyzer. .

Ensure that the evaluation type that is required for the calculation of the net present values is available. You find the settings for this under Treasury and Risk Management Valuation Define and Set Up Evaluation Type .

**Features**

- 1. Run the transaction (TREA_EVAL). Select one or more external accounts.

If you do not select any accounts, the system performs the calculation for all external accounts.

- 2. Enter the calculation date and, optionally, the payment currency. The system only uses this payment currency if no currency is stored for the external account AND if the local currency must not be used.
- 3. Set the Test Run indicator if necessary.


**Note:**

We recommend that you always perform a test run first before any updated values are actually transferred to the database.

- 4. Specify whether you want the application log to be displayed after a run has been performed.
- 5. You use the Adjustment Run indicator to specify that this run does not select all financial transactions again but only those that need to be adjusted.
- 6. Execute the run and check the values displayed.


To display any system error messages, navigate to the relevant error log.

###### Releasing Line Items

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > External Account Statement > Releasing Line Items | L5 | trm06 p.234 | loio `265c33c6b0c94a1380e373275e91a7ad` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/265c33c6b0c94a1380e373275e91a7ad.html?locale=en-US)

**Context**

Once you have entered an external account statement or uploaded it from an Excel file, you can release the account statement positions.

You specify the type of margin statement that you want to create in the master data for external accounts (transaction TREA_ACC_MNT). If you opt for a margin statement in the form of a margin balance overview, you can only ever reverse the last margin statement. You need to delete any existing account statements that have not been processed yet (status Not Processed) before you can reverse the preceding margin statement. This rule is necessary because the margin flows of a margin statement are calculated on the basis of the preceding margin statement.

If you opt for a margin statement that is not a margin balance overview, you can reverse margin positions in any sequence.

When the line items are released, the system generates flows for them that update the position components of the clearing account position.

The following flows are generated:

- Case A: Net payment for flows on the clearing account position


In this instance, the flows are generated as follows:

A flow is generated for each position for initial margins and transaction-independent fees.

For variation margins and transaction-dependent fees, a flow for each position is generated for the respective assigned position, and, for the clearing account position, an aggregated flow is generated for both variation margins and for transaction-dependent fees.

Example

Customizing setting under Specify Update Types for Central Counterparty Clearing:

|Update Type|Flow Category|Relevant for Aggregation|
|---|---|---|
|EA_INI-|Initial Margin Outgoing|X|
|EA_MTI-|Negative Variation (TransactionIndependent)|X|
|EA_MTM-|Negative Variation Margin|X|


Line items of an external account statement:

|Update Type|Transaction|Amount|Posting Release Status|Payment Release Status|
|---|---|---|---|---|
|EA_INI-| |1000|Not released|Not released|
|EA_MTI-| |100|Not released|Not released|
|EA_MTM-|Transaction 1|50|Not released|Not released|
|EA_MTM-|Transaction 2|50|Not released|Not released|


Flows generated after releasing the line items:

|Position Context|Transaction|Update Type|Amount|Relevant for Posting|
|---|---|---|---|---|
|CLP| |EA_INI-|1000|X|
|CLP| |EA_MTI-|100|X|
|CLP| |EA_VM-|100| |
|ASP|Transaction 1|EA_MTM-|50|X|
|ASP|Transaction 2|EA_MTM-|50|X|


Position components of the clearing account position:

|Component|Description|Amount|
|---|---|---|
|1001|Initial Margin|1000|
|1002|Variation Margin|200|
|2001|Initial Margin Open|1000|
|2002|Variation Margin Open|200|
|2003|Other (such as Fees) Open|0|
|8000|Clearing Payment|0|
|9000|Total Open|1200|
|9001|Total Margin Open|1200|


- Case B: No Aggregation of Flows on the Clearing Account Position


For the transaction-independent positions, the system generates a posting-relevant flow that is entered in the clearing account position.

For positions that can be assigned to one financial transaction, two flows have to be generated. First, a postingrelevant flow that is entered in the assignment position, and second, a payment-relevant flow that is entered in the clearing account position.

Customizing setting under Specify Update Types for Central Counterparty Clearing

|Update Type|Flow Category|Relevant for Aggregation (Indicator)|
|---|---|---|
|EA_INI-|Initial Margin Outgoing|Yes/No|
|EA_MTI-|Negative Variation (TransactionIndependent)|Yes/No|
|EA_MTM-|Negative Variation Margin|Yes/No|


Line items of an external account statement:

|Update Type|Transaction|Amount|Posting Release Status|Payment Release Status|
|---|---|---|---|---|
|EA_INI-| |1000|Not released|Not released|
|EA_MTI-| |100|Not released|Not released|
|EA_MTM-|Transaction 1|50|Not released|Not released|
|EA_MTM-|Transaction 2|50|Not released|Not released|


Flows generated after releasing the line items:

|Position Context|Transaction|Update Type|Amount|Relevant for Posting|
|---|---|---|---|---|
|CLP| |EA_INI-|1000|X|
|CLP| |EA_MTI-|100|X|
|CLP|Transaction 1|EA_VM-|50| |
|CLP|Transaction 2|EA_VM-|50| |
|ASP|Transaction 1|EA_MTM-|50|X|
|ASP|Transaction 2|EA_MTM-|50|X|


Position components of the clearing account position:

|Component|Description|Amount|
|---|---|---|
|1001|Initial Margin|1000|
|1002|Variation Margin|150|
|2001|Initial Margin Open|0|
|2002|Variation Margin Open|0|
|2003|Other (such as Fees) Open|0|
|8000|Clearing Payment|0|


|Component|Description|Amount|
|---|---|---|
|9000|Total Open|0|
|9001|Total Margin Open|0|


Following their release, you can post the posting-relevant flows using the Post External Account Flows function.

The payment of flows is made as follows:

- Case A

You generate a net payment. See also: Creating Net Payments

- Case B


When you post the flows using the Post External Account Flows function, the payment requests for the payment-relevant flows are also generated. Now you only need to start the payment run.

**Procedure**

- 1. Under External Accounts External Account Statements , call function Release Line Items (transaction TREA_RELEASE).
- 2. You can select the flows to be released based on the following criteria:

Company Code

External Account

Date

- 3. Set the Only Releasable Line Items checkbox, so that you select only the flows that have not yet been released.
- 4. You can perform the function as a test run first.
- 5. Choose Execute. The Release Statement Line Items screen appears.
- 6. To display the margin values calculated for individual position components in the position currency and local currency, choose Detail. The position components are as follows:

Initial Margin / Variation Margin: Margin positions without considering margin limit calculation (note: Fees are always cleared automatically)

Open margin positions after performing margin limit calculation; the position is cleared when the payment is initialized

Open total: Total of all open positions

Open total per margin: Total open positions for initial margin and variation margin

- 7. Release Statement Items (Test Run) Select the position to be released and choose Execute.
- 8. The flows are generated. The flows in the external account statement receive the posting and payment release status Released.

###### Margin Management (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > External Account Statement > Margin Management | L5 | trm06 p.237 | loio `d3085a46763c45c09664e61d07780d4a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d3085a46763c45c09664e61d07780d4a.html?locale=en-US)

Use

A margin is a deposit that needs to be placed on an external account belonging to a broker before the trader can participate in trading on an exchange or over the counter. If the broker has enlisted the services of a central clearing provider, financial transactions that are relevant for clearing are concluded with that central clearing provider.

A distinction is made between the margin categories initial margin and variation margin:

The initial margin is specified by the clearing provider and is used as a security to cover future variation margins.

The variation margin is also specified by the clearing provider and is used to hedge against price risks. If the variation margin exceeds the agreed margin limit, the clearing provider asks for a remargining payment (margin call).

**Prerequisites**

To be able to portray margins, you need to have made the settings for external accounts and entered an external account in the transaction Specify External Accounts (TREA_ACC_MNT).

**Features**

The following functions are available:

You can enter the margin balances of the external account statements prepared daily and compare them against the amounts calculated automatically for comparison and monitoring purposes.

If you have activated Margin Management, you can use the margin limits to determine the margin payments automatically.

Manually Changing Payment Amounts:

After you have made the settings in the Customizing activity Assign Update Types to Manual Payment Changes (TREAV_UPTYP_PADJ) and enable changing determined payment amounts in transaction Maintain External Accounts (TREA_ACC_MNT), you can retroactively make manual changes to the payment amounts in the external account

statement. A posting-relevant flow is triggered for each difference between a calculated payment amount and a payment amount that has been changed manually. You can find these in the external account statement on the Positions tab. If an additional account statement is entered, the position created earlier is cleared by an offsetting line item.

Once you have released margin positions (transaction Release Positions - TREA_RELEASE), you can create the corresponding payment flows (transaction Create Net Payment - TREA_PAY).

You can also use reports for analyzing margin positions by key date and period (Display Margin Limit Positions of a Period - TREA_MLM_POS_PERIOD and Display Margin Limit Positions of a Key Date - TREA_MLM_POS_KEYDAT). You find these reports in the SAP area menu under Treasury and Risk Management Transaction Manager External Accounts

Information Systems .

**Note:**

You enter margin positions manually; they cannot be transferred automatically from uploaded external account statements.

If the margin balances functions or margin limits functions are activated, an account statement cannot be saved until all positions of the previous account statement have been released and posted.

If the margin balances functions are not activated, you enter the margin positions on the Positions tab.

Margin Management Using Margin Balances and Margin Limits

[figure TRM06-F094 - See also:]

See also:

External Account Statement

###### Margin Balances

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > External Account Statement > Margin Management > Margin Balances | L6 | trm06 p.239 | loio `d0b303710d174899b1db828f8cf37e42` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d0b303710d174899b1db828f8cf37e42.html?locale=en-US)

**Use**

You use the transaction Process External Account Statements to enter account balances for the initial margins and variation margins provided daily by the clearing provider in the margin account statement.

The system proposes the currency stored in the master data of the external account. You can replace the proposed currency with another currency. If the currencies differ, you can also enter an exchange rate.

The system uses the difference between the current and previous balance to determine the margin flows for each margin category.

Margin Amounts

In the Margin Amounts screen area, the values for each margin category are shown in the position currency. From the master data of the external account, the system determines the current margin limit amount. The payment amount is calculated using the limit

utilization determined. If you manually change a payment amount that the system has calculated, you need to select a reason for this adjustment.

Comparison of Variation Margins

You can compare the variation margin shown in the account statement against the variation margin calculated by the system. The prerequisite for performing this comparison is that the relevant external account is assigned to the financial transactions. Depending on the setting that you have made in the master data of the external account, the system selects either discounted or non-discounted values. If the manually entered variation margin differs from the variation margin calculated in the system, the system shows the difference as a percentage.

When you run the threshold check, the system compares the difference amount of the initial margin and of the variation margin against the threshold values defined. If the threshold value is exceeded, the system issues a warning or error message. You find the setting for this in Customizing under Central Clearing Margin Balances Specify Thresholds for Margin Deviations .

###### Margin Limits

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > External Account Statement > Margin Management > Margin Limits | L6 | trm06 p.241 | loio `0e1ac3a4d15e440b92231eda8bad3c8c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0e1ac3a4d15e440b92231eda8bad3c8c.html?locale=en-US)

**Use**

The system uses the margin limits of an external account to determine automatically the margin payments for the external account statements entered daily.

When the external account statement is entered, the system performs a margin limit check for each margin categories (initial margin and variation margin). With this check, the system compares in each case the margin amount of the account statement against the margin limit stored in the master data of the external account. If a margin limit is exceeded, the margin payment is achieved from the difference amount.

On the Margin Limits tab, you obtain the position values of the relevant position components for each margin category and for each process step. The values are displayed with the +/- sign of the payment amount (negative position value = minus sign; positive position value = positive sign):

- 1. Calculated payment amount: Position values after margin limit calculation
- 2. Adjusted payment amount: Position values after manual adjustment


The update types for the calculated payment amounts are displayed on the Positions tab page. If the margin limit of a margin category is exceeded as a result of entering the payment amount, additional positions are updated for measurement of the limit

utilization. The positions of these update types can be released in the next step in the transaction TREA_RELEASE. These specific update types are defined in Customizing. It is also possible to create update types manually for fees.

If a change is made manually to a calculated payment amount, an additional update type is created with a position that contains the difference between the calculated payment amount and the manually changed payment amount. The update type with the relevant position is displayed on the Positions tab. Since a manual change to the payment amount represents a margin balance change that is reflected in the account statement of the following day, this position is created with the opposite direction. In the master data of the external account, you activate the function for making manual changes to calculated payment amounts.

**Prerequisites**

For margin limits to be considered in the calculation of margin payments, you need to have made the following settings:

You have made the settings in Customizing under External Accounts Central Clearing Margin Limit Management .

You have activated Margin Limit Management in the master data of the external account (transaction TREA_ACC_MNT) and have entered margin limits on the Margin Limit Data tab.

**Activities**

- 1. Once you have entered the margin balances, go to the Positions tab. Check the values on the Positions tab. The positions of the update types EA_IMLU and EA_VMLU for limit utilization are for statistical or information purposes only.
- 2. Choose the Margin Limit tab. Check the amounts by comparing those determined against those entered.
- 3. You can change the calculated payment amount subsequently on the Margin Balances tab. For this, you need to select the adjustment reason. Each time that the payment amount is changed, an additional update type with a posting-relevant position is created and displayed on the Positions tab.
- 4. Then release the positions (transaction Release Positions — TREA_RELEASE) and generate the payment flows in the relevant valuation areas (transaction Create Net Payment — TREA_PAY).


**Example**

Determining Payment Amounts with Limit Check:

|Agreed Margin Limit for Initial Margin|10000|
|---|---|
|Last Initial Margin|5000|
|Current Initial Margin|6000|
|Initial Margin Difference Amount|1000|
|Initial Margin Payment Amount|0|


|Agreed Margin Limit for Variation Margin|10000|
|---|---|
|Last Variation Margin|10000|
|Current Variation Margin|12000|
|Variation Margin Difference Amount|2000|
|Variation Margin Payment Amount|2000|


**More Information**

Margin Management

Margin Balances

##### Clearing

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Clearing | L4 | trm06 p.243 | loio `b2b400b094d84661a399bf9676c4c2c3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b2b400b094d84661a399bf9676c4c2c3.html?locale=en-US)

###### Central Clearing Monitor

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Clearing > Central Clearing Monitor | L5 | trm06 p.243 | loio `2716bd518ab94328961101baf841cff7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2716bd518ab94328961101baf841cff7.html?locale=en-US)

Use

The central clearing monitor allows you to display all financial transactions that are relevant for clearing and to process them from this central location.

You can process all clearing-relevant financial transactions collectively when you accept or reject clearing, replace the clearing partner, or use the reversal functions.

The central clearing monitor displays the clearing details and the flows as well as the clearing history for a financial transaction.

You can process financial transactions either individually or collectively. In this way, you can select, for example, all financial transactions with the clearing status Clearing Requested (Planned) and for which clearing has been accepted by the clearing partner, and then accept clearing collectively in the system for all these selected financial transactions.

See also:External Accounts

**Features**

The Clearing Monitor is divided into the following three screen areas:

Selection

In this area, you specify which clearing-relevant financial transactions are returned by the search.

In the Search field, you specify whether you want to find all clearing-relevant financial transactions or just those with the clearing status Clearing Rejected, Clearing Accepted, or Clearing Requested (Planned).

You can use the following parameters to restrict the search further for financial transactions:

Company Code

Financial Transaction (Financial Transaction Number)

Product Type

Transaction Type

External Account

Clearing Provider

(This information comes from the master data of the external account contained in the Counterparty field)

Up to Planned Clearing Date

Choose the Start pushbutton to search for the financial transactions.

You can choose the pushbutton to delete your selection criteria.

Results List

When the search has been successful, the system displays the results list beneath the Selection area.

The first financial transaction in the list is highlighted, and the related business details appear on the right-hand side of the screen (third area of the Central Clearing Monitor; see below).

When you are in the Central Clearing Monitor in change mode, you can select individual or multiple financial transactions, choose the Execute Directly pushbutton, and opt for one of the following:

Accept Clearing Directly

When you perform this function, you need to enter the Clearing Date on the dialog screen that appears. You can specify whether the payment details are taken from the clearing provider or from the external account.

Reject Clearing Directly

Reverse Acceptance of Clearing

Reverse Rejection of Clearing

**Note:**

It is not possible to perform these functions in test mode from here.

Business Details

In this area, you can see the details for the financial transaction on the following three tab pages:

Clearing Details

First, the counterparty is displayed. In the Clearing Details area, you see the clearing data of the financial transaction:

Clearing Status of the Financial Transaction

Clearing Account

Clearing Provider

Clearing Date

Planned Clearing Date

In the lower section of the tab, you see the payment details from the clearing account.

Flow Details

On this tab, you see the flows of the financial transaction.

History

On this tab, you see the clearing history of the financial transaction.

You can choose the pushbutton next to the financial transaction number to navigate to the financial transaction data.

When you are in change mode, you can use the Execute (Clearing Business Transactions) pushbutton to perform the following clearing business transactions for the financial transaction currently displayed:

Accept Clearing

Reject Clearing

Reverse Acceptance

Reverse Rejection

Reverse Change of Clearing Partner

**Note:**

To change the clearing partner, choose Extras Change Clearing Partner .

**Activities**

Choose Transaction Manager External Accounts Clearing Central Clearing Monitor (transaction TPMCCP).

**More Information**

Accepting/Rejecting a Clearing

Reversing a Clearing/Rejection

Clearing History

###### Accepting/Rejecting a Clearing

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Clearing > Accepting/Rejecting a Clearing | L5 | trm06 p.245 | loio `c2b2e08d52504f62a6d8f70288a88a5a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c2b2e08d52504f62a6d8f70288a88a5a.html?locale=en-US)

**Context**

When you have received confirmation that the clearing of your financial transaction has been accepted or rejected, perform the Accept/Reject Clearing function (transaction TREA_CLEAR).

The central counterparty has rejected the clearing.

When you execute this function, the business partner in the financial transaction (role Counterparty) is replaced by the new business partner (= the business partner assigned to the external account) and the payment details are updated.

The financial transaction acquires the clearing status Clearing Accepted.

The flows of the transaction acquire the Cleared indicator. The transaction flows are no longer relevant for payment. All other payments are made using the clearing account. Although the transaction flows are still relevant for posting, they are now no longer posted using bank clearing but instead using the new account symbol 9.9 (technical clearing: Clearing).

See also:Posting Logic for Flows on Clearing Accounts

If you use Trade Repository Reporting (TRR), the system creates a trade repository object (TARO) with the action type 45Notice and a TARO with the action type 10New. Within the function, you specify in the Trade Repository Reporting area the external transaction ID used by the financial transaction after novation.

If, when novation is performed, the financial transaction has not yet been reported to the trade repository (and consequently there is no TARO with the status Sent for this financial transaction), only the existing TARO is updated.

The central counterparty has accepted the clearing.

The financial transaction is presented to another central counterparty for clearing.

Another clearing account is assigned and a new planned clearing date is specified.

The clearing status of the financial transaction remains unchanged (status "Clearing").

Notice is given for the financial transaction.

Perform the Reject Clearing function. The financial transaction acquires the clearing status Clearing Rejected.

In a second step, you give notice for the financial transaction using the transaction management functions (transaction FTR_EDIT).

**Procedure**

- 1. Call the function under External Accounts Clearing Accept/Reject Clearing (transaction TREA_CLEAR).
- 2. In the General Selections area, use the following criteria to select the relevant financial transactions:

Company Code

Transaction

Product Type

Transaction Type

Clearing Account

Counterparty

Up to Planned Clearing Date

In the Control area, you specify whether the selected transactions are accepted or rejected for clearing or whether the clearing partner needs to be replaced. If you want to replace the clearing partner, you have to enter the new clearing account and the planned clearing date.

In the Payment Details area, you specify whether the payment details are taken from the clearing provider or from the external account.

In the Trade Repository Reporting area, you can choose between the following options:

New external trade ID

If you already know the new external trade ID of the financial transaction, you can enter it directly for the specific trade repository.

Delete External Trade ID

Select this option if the financial transaction needs to acquire a new external trade ID after novation but you do not yet know the new external trade ID. The system then deletes the assignment of the existing external trade ID for the financial transaction. If you have set up the use of an interim trade ID in Customizing for Trade Repository Reporting, the system generates an interim trade ID and assigns it to the financial transaction.

Keep External Trade ID

Select this option if the financial transaction needs to retain the existing external trade ID.

- 3. You can perform a test run.
- 4. Choose Execute.
- 5. The system issues a message log and a list of the financial transactions that were successfully processed.
- 6. When the test run has returned the desired result, repeat the function in the update mode.

###### Reversing Clearing/Rejection

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Clearing > Reversing Clearing/Rejection | L5 | trm06 p.246 | loio `4c7408a0dba84aad953b66406afcf218` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4c7408a0dba84aad953b66406afcf218.html?locale=en-US)

**Context**

You use this function to reset a clearing or the rejection or the replacement of the counterparty.

If you use Trade Repository Reporting (TRR), the system creates a trade repository object (TARO) with the action type 40Error and a TARO with the action type 10New.

**Procedure**

- 1. Call the function under External Accounts Clearing Reverse Clearing/Rejection (transaction TREA_CLEAR_REV).
- 2. Use the General Selections (Company Code, Transaction, Product Type, Transaction Type, Clearing Account, Counterparty, From Planned Clearing Date) to select the financial transactions that you want to reverse.
- 3. You can perform the function as a test run first.
- 4. The system reverses the clearing or rejection of the selected financial transactions.
- 5. The system issues an error log and a list of the financial transactions that were reversed.


The reversed financial transactions acquire the status Clearing Requested (Planned) again. In the case of financial transactions for which the clearing had been accepted, the system undoes the novation with this reversal, and the original counterparty is entered into the financial transaction again. The payment details and the flows are as they were before clearing was performed.

If the counterparty had been replaced, the system undoes this replacement, and the original counterparty and the original planned clearing date are entered into the financial transaction again.

If the clearing had been rejected, the system resets the change in status.

###### Clearing History

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Clearing > Clearing History | L5 | trm06 p.247 | loio `b202b4545e134e02af67f2a04ccdcc6b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b202b4545e134e02af67f2a04ccdcc6b.html?locale=en-US)

**Use**

The clearing history allows you to obtain an overview of all financial transactions that are relevant for clearing.

From this overview, you can reverse clearing for a financial transaction.

**Features**

Selection

Financial transactions are selected using the following criteria:

Company Code

Financial Transaction Number

Product Type

Transaction Type

Clearing Account

Counterparty

Up to Planned Clearing Date

You can influence the selection further using the following checkboxes:

Including Reversed Clearings

If you set this checkbox, the system displays all selected financial transactions for which clearing has been reversed.

Including Planned Clearings

If you set this checkbox, the system displays all selected financial transactions for which clearing has previously only been planned.

Output List

The list shows the selected financial transactions.

The system displays the list using the SAP List Viewer for SAP GUI (Classic). You can use the standard functions of the SAP List Viewer to edit the list.

From this list, you can also reverse clearing (acceptance/rejection) for a financial transaction. Select the financial transaction to be reversed and choose Reverse. The system reverses clearing for that financial transaction and issues any error, warning, or success messages.

See also:Reversing Clearing/Rejection

**Activities**

- 1. Call the function under External Accounts Clearing Clearing History (transaction TREA_CLEAR_HIST).
- 2. Enter the selection criteria.
- 3. Choose Execute.
- 4. The system outputs the list.
- 5. If you want to reverse clearing, select the line and choose Reverse.


Accounting

**Central Clearing: Posting Logic for Flows**

Use

When a central counterparty has accepted the clearing of a financial transaction, all flows for that financial transaction and the external account flows (such as margin payments and fees) pass via the clearing account.

The flows from the financial transaction (such as interest flows) are then no longer relevant for payment and are posted using the clearing account as opposed to the bank clearing account.

Payment is made by means of a net payment.

**Prerequisites**

The documentation on External Accounts describes the settings that you need to make in Customizing so that you can use the functions for central clearing. The same section contains a table of the necessary update types.

In the activity Define Account Determination, you need to create the following posting specifications and assign the postingrelevant update types:

- 30001 Central Clearing: CCC: Technical Clearing / Bank Clearing

- 30002 Central Clearing: Bank Clearing / CCC: Technical Clearing

- 30003 Central Clearing: Position / CCC: Technical Clearing

- 30004 Central Clearing: CCC: Technical Clearing / Position

- 30005 Central Clearing: Margin Expense / CCC: Technical Clearing

- 30006 Central Clearing: CCC: Technical Clearing / Margin Refund

- 30007 Central Clearing: Fees / CCC: Technical Clearing

- 30008 Central Clearing: CCC: Technical Clearing / Fees


Assignment to Update Types:

|Update Type|Name|Posting Specifications|
|---|---|---|
|EA_NET-|Outgoing Net Payment|30001|
|EA_NET+|Incoming Net Payment|30002|
|EA_FEE+|CCC: Fee Refund|30008|
|EA_FEE-|CCC: Fees|30007|
|EA_FEED+|CCC: Fee Refund (Deal-Related)|30008|
|EA_FEED-|CCC: Fee (Deal-Related)|30007|
|EA_INI+|CCC: Initial Margin Refund|30006|
|EA_INI-|CCC: Initial Margin Outgoing|30005|
|EA_MTI+|CCC: Positive Variation Margin (DealIndependent)|30006|
|EA_MTI-|CCC: Negative Variation Margin (DealIndependent)|300005|
|EA_MTM+|CCC: Positive Variation Margin|30006|
|EA_MTM-|CCC: Negative Variation Margin|30005|


**Example**

Example of a Posting for an External Account Statement

The external account statement from May 2, XXXX contains the following positions:

|Update Type|Transaction|Amount|Posting Release Status|Payment Release Status|
|---|---|---|---|---|
|EA_INI-| |1,000|Not released|Not released|
|EA_MTI-| |100|Not released|Not released|
|EA_MTM-|Transaction 1|50|Not released|Not released|
|EA_MTM-|Transaction 2|50|Not released|Not released|
|EA_INT-|Transaction 1|10,000|Not released|Not released|
|EA_INT+|Transaction 1|9,000|Not released|Not released|


Flows generated after releasing the positions

|Position Context|Transaction|Update Type|Amount|Posting-relevant|
|---|---|---|---|---|
|CLP| |EA_INI-|1,000|X|
|CLP| |EA_MTI-|100|X|
|CLP| |EA_VM-|100| |
|CLP|Transaction 1|EA_INT-|10,000|The interest payments are posted by means of the interest flow from the financial transaction.|
|CLP|Transaction 1|EA_INT-|9,000|The interest payments are posted by means of the interest flow from the financial transaction.|
|ASP|Transaction 1|EA_MTM-|50|X|
|ASP|Transaction 2|EA_MTM-|50|X|


Position Components on the Clearing Account Position

|Component|Description|Amount|
|---|---|---|
|1001|Initial Margin|1,000|
|1002|Variation Margin|200|
|2001|Initial Margin Open|1,000|
|2002|Variation Margin Open|200|
|2003|Other (such as Fees) Open|1,000|
|8000|Clearing Payment|0|
|9000|Total Open|2,200|
|9001|Total Margin Open|1,200|


Posting Flows

You use the "Post External Account Flows" function to post the flows.

Creating Net Payments

When you perform the Create Net Payment function, the system creates and posts the following flow:

|Update Type|Amount|Relevant for Posting|
|---|---|---|
|EA_NET-|2,200|X|


The system also sets to zero the open position components on the clearing account position.

The following postings were generated from the posting-relevant flows:

- 1. Interest 10,000 / CCC: Technical Clearing 10,000
- 2. CCC: Technical Clearing 9,000 / Interest 9,000
- 3. Margin Expense 1,000 / CCC: Technical Clearing 1,000
- 4. Margin Expense 100 / CCC: Technical Clearing 100
- 5. Margin Expense 50 / CCC: Technical Clearing 50
- 6. Margin Expense 50 / CCC: Technical Clearing 50
- 7. CCC: Technical Clearing 2,200 / Bank Clearing 2,200


[figure TRM06-F095]

##### Accounting (1 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Accounting | L4 | trm07 p.2 | loio `d15e5f8b9d5c4267badf7d3603cb4621` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d15e5f8b9d5c4267badf7d3603cb4621.html?locale=en-US)

**Use**

Transaction Manager and Loans Management are FI subledgers used to store information on the various financial transactions and finance positions.

With the parallel position management of the Transaction Manager, it is possible to manage these positions according to other accounting principles parallel in different valuation areas.

The valuation area-independent operational business transactions forward their flows to the parallel valuation areas, where they are managed on the basis of the settings specific to each valuation area.

**Note:**

Since the parallel position management is based on update types and not on flow types, the corresponding update types must be assigned to the flow types.

In Loans, the position-changing flows are transferred to the parallel valuation areas on a debit position basis. This means, for example, that the incoming payment function in the Loans area is not connected to the parallel valuation areas.

[figure TRM07-F001 - Prerequisites]

Prerequisites

|Customizing Activity| |Comments|
|---|---|---|
|To set up the parallel valuation areas, you have to make settings in the following activities in Customizing under Transaction Manager General Settings Accounting .| | |
|Organization Define Valuation Areas Define Accounting Codes Assign Accounting Codes and Valuation Areas|Here you specify the valuation areas that you want to use. **Note:** Valuation area 0001 is always the operational valuation area. Here, you use the functions of the parallel valuation areas to| |


|Customizing Activity| |Comments|
|---|---|---|
|Product Categories to Be Excluded - Parallel Valuation Areas|You create accounting codes and assign them to the valuation areas. For the update of the parallel valuation areas into Accounting, you can extend your chart of accounts and post directly to the general ledger or you can use the special purpose ledger in FI. If you want to use the special purpose ledgers, see the application documentation in SAP Library under Accounting Financial Accounting Special Purpose Ledgers . The documentation on the Customizing activity Assign Accounting Codes and Valuation Areas describes how you create a special purpose ledger and link it to the parallel valuation areas. manage listed derivatives, forwards, and repos only.| |
|Update Types Define Update Types Assign Update Types to Usages Assign Update Types for Valuation Assign Update Types for Derived Business Transactions Alternative Assignment of Update Types for Position Outflows Assign Update Types for FAS 133 Distribution Assign Update Types for Account Assignment Reference Transfer Assign Update Types for Valuation Class Transfers Update Types for Initializing Positions Assign Update Types for Local Currency Determination Assign Update Types to Usages in the Securities Area Under Transaction Manager Securities Position Management   Securities Account Transfer Update Types Assign Update Types for Securities Account Transfers  Securities Account Management Update Types Specify Update Types for Securities Account Management   Securities Account Management Update Types Assign Update Types for Functions of Security Account Management  Corporate Actions Update Types Assign Update Types to the Corporate Action Categories  Rights Update Types Assign Update Types to Rights Categories Specify and Assign Update Types for Futures Account Management|Update types carry the information for a flow in the parallel valuation areas. They roughly correspond to the flow types in the operational valuation areas. Once you have defined and assigned the update types to the various usages, you then need to perform the usage-specific Customizing activities for each usage. You can find the relevant Customizing activities, Define Update Types and Assign Update Types to Usages in all those parts of Customizing where settings are made for the different usages. To enable the transfer of valuation area-dependent operational business transactions into the parallel valuation areas, you have to assign some update types to the corresponding flow types. This assignment is necessary in the Securities and Listed Derivatives areas even if you do not have any parallel valuation areas. If an update type needs to be posted, you define the posting rules for the update type in Customizing under Transaction Manager  General Settings Accounting Parallel Valuation Areas Link to Other Accounting Components Define Account Determination .| |


|Customizing Activity| |Comments|
|---|---|---|
|In Customizing for the Listed Derivatives area under Position Management Futures Account Management Update Types Specify Update Types for Futures Account Management Assign Update Types for Margin Management per Product Type Assign Update Types for Transaction Management - Foreign Exchange/OTC Derivatives In Customizing for the Foreign Exchange/OTC Derivatives area under Transaction Management Update Types Assign Update Types for Position Update Assign Update Types to Flow Types In Customizing for Loans Management under Transaction Management Update Types Assign Loan Flow Types to Update Types In Customizing for the Money Market/Foreign Exchange/Securities/Listed Derivatives/OTC Derivatives/Trade Financearea under Transaction Management Update Types Assign Transaction Flow Types to Update Types In Customizing for the Securities area under Accounting Operational Valuation Area Flow Types Assign Update Types to Flow Types| | |
|Derived Business Transactions Control of Processing of Derived Business Transactions|Here you determine whether the derived business transactions are generated online or offline. **Note:** If your data volume is large, it can be useful to opt for offline processing and schedule the update run for derived business transactions (RTPM_TRL_DERIVE_TRANSACTIONS) as a batch job, for example, every evening.| |
|Link to Other Accounting Components Define Account Assignment References Define Account Assignment Reference Determination (Transactions) Define Account Assignment Reference Determination (Securities/Listed Derivatives) Define Account Assignment Reference Determination (Loans) Define Account Determination|Here you define account assignment references and establish rules for determining the account assignment references automatically You also specify for the update types the account determination in General Ledger Accounting. **Note:** The flow types of the operational valuation area have the Relevant to Posting indicator. The Customizing check report allows you to check whether an account determination has been defined for all flow types that are designated as relevant to posting. Update types do not have this indicator. As soon as account determination is defined for an update type, the update type then becomes relevant to posting. Conversely, as long as no account determination has been defined for an update type, the update type is not relevant to posting.| |
|In Customizing for Loans Management under Basic Settings Parallel Valuation Areas| | |


|Customizing Activity| |Comments|
|---|---|---|
|Initialization Date per Company Code|You do not make any manual settings here. Instead, you can see here whether (and if so, since when) loan positions have been managed in the parallel valuation areas. The indicator is set automatically by the system when the parallel valuation areas are initialized for the loans positions.| |


**Note:**

You can use the delivered Customizing settings as a guide.

See also: See the documentation on the individual Customizing activities.

**Features**

Parallel valuation areas can be used for all product types of the areas Money Market, Foreign Exchange, Derivatives, Securities, Loans, and Trade Finance.

Using the parallel valuation areas, it is possible to manage positions in parallel according to different valuation guidelines. This means that you can perform quarterly and year-end closing according to different accounting principles, for example, HGB (German Commercial Code) and US GAAP.

The position management in the parallel valuation areas contains functions for valuation, account assignment reference transfers, and valuation class transfers. For each valuation area, the values of the positions are stated depending on how the position components are managed.

To use the parallel valuation areas, you have to make the corresponding Customizing settings for position management. These settings are cross-application and they control the management of the positions in the application functions described below.

Example

In Customizing, you specify the criteria to be used to create the positions, you define the position management procedures, and you also specify the rules for assigning the position management procedures to the positions. The application function Valuation then performs key date valuation for each valuation area at the level of the positions, applying the steps defined in the position management procedures.

###### Central Clearing: Posting Logic for Flows

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Accounting > Central Clearing: Posting Logic for Flows | L5 | trm06 p.239 | loio `3a7504e7e2ec472385e363f8b84b05b5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3a7504e7e2ec472385e363f8b84b05b5.html?locale=en-US)

Post External Account Flows

###### Creating Net Payments

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Accounting > Creating Net Payments | L5 | trm06 p.252 | loio `a3060c3730634addbfaeb9ab9291eab6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a3060c3730634addbfaeb9ab9291eab6.html?locale=en-US)

**Context**

If you have intended to make a net payment to your external accounts for your flows, you need to use this function - after releasing the positions of an account statement - to create the flow for the net payment.

**Procedure**

- 1. Selection General Selections

Company Code

External Account

Position Value Date

Posting Control

Enter the following posting data:

FI posting date

FI posting period

Document date

Set the Test Run checkbox if you want to perform the function in a test run first.

- 2. Choose Execute.
- 3. List Output The following list shows you the selected clearing accounts with the open total amount.
- 4. Select one or more clearing accounts and choose Pay.
- 5. For each clearing account selected, the system creates a payment-relevant flow for the open total amount. The system posts the flows and creates the payment requests. The system also sets to zero the open amounts on the position components of the clearing account positions.
- 6. As a final step, you simply start the payment run so that the payment requests are paid.

###### Posting External Account Flows

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Accounting > Posting External Account Flows | L5 | trm06 p.252 | loio `67abda90f1bc4ca799bd477c7675d40f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/67abda90f1bc4ca799bd477c7675d40f.html?locale=en-US)

**Context**

You use this function to post the posting-relevant flows to your external accounts.

**Procedure**

- 1. Call the function under External Accounts Accounting Post External Account Flows (transaction TREA_POST_FLOWS).
- 2. Use the following criteria to select the flows that you want to post:


Position Context

Select the clearing account position and/or the assignment position. If you only select the clearing account position, you can use the criteria Company Code and External Account to select the flows that you want to post. If you also select the assignment position, you can restrict the flows to those relating to specific financial transactions.

Enter the selection criteria.

Specify the date until which you want to select flows. The current date appears by default.

In the Posting Control area, specify the FI posting date, the FI posting period, and the document date.

You can execute the program first in a test run.

- 3. Choose Execute.
- 4. The system selects the flows to be posted and performs the posting.
- 5. The system issues a posting log and an error log.
- 6. When the test run has returned the desired result, repeat the program in the update mode.


**Results**

The amounts of the flows were posted to the accounts in Financial Accounting.

The flows receive the status Posted.

Payment requests are created for the flows that are relevant for payment.

###### External Account: Reverse Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Accounting > External Account: Reverse Transactions | L5 | trm06 p.253 | loio `ae90b684ff944fe293204d623258f4fb` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ae90b684ff944fe293204d623258f4fb.html?locale=en-US)

**Context**

You use this function to reverse the following business transactions:

Net payments

Posting of transactions in an external account

Releasing positions of an external account

**Procedure**

- 1. Call the function under External Accounts Accounting Reverse External Account Flows (transaction TREA_REVERSE).
- 2. Use the following criteria to select the flows that you want to reverse:


Position Context

Select the clearing account position and/or the assignment position. If you only select the clearing account position, you can use the criteria Company Code and External Account to select the flows that you want to post. If you also select the assignment position, you can restrict the flows to those relating to specific financial transactions.

Enter the selection criteria.

In the Flow Selection area, specify the date until which you would like to select flows. The current date appears by default. Additionally, select whether you want to reverse the net payment, the posting, or the release of flows in the external account.

In the Posting Control area, specify the reason for the reversal, the FI posting date, the FI posting period, and the document date.

You can execute the program first in a test run.

- 3. Choose Execute.
- 4. The system selects the flows to be reversed and performs the reversal. For this, the system also selects and reverses any dependent flows. For example, if you want to reverse the release of the flows but a net payment has already been made after the release, the net payment also needs to be reversed.
- 5. The system issues a reversal log.
- 6. When the test run has returned the desired result, repeat the program in the update mode.


**Results**

The posting of the flows is undone and the flows acquire the posting status Reversed.

If you reverse the release of the flows, the system only sets the status of the associated flows to Reversed, whereas the related items acquire the posting and payment release status Not Released.

Master Data

**Processing External Accounts**

Use

An external account represents an account that you have with a business partner, such as your clearing partner. An external account is identified uniquely by the company code and its short description.

The master data of an external account comprises the following data:

General Data

In the Clearing Account Data, you enter the following data:

Counterparty

Here you enter the business partner with whom you have the clearing account. The business partner could be, for example, the clearing house or the member performing the clearing.

The business partner that you enter here must have the role Counterparty.

External Account ID

The external account ID is the number with which the account is managed with your counterparty.

Product Type

Assign a product type (with product category 690) to the clearing account.

General Valuation Class

Payment Data

Here you enter the payment data for the flows that appear on this account.

You can enter data for a specific currency, time, and update type.

You enter the following data:

House bank

Account

Payment activity

Payer/Payee

Partner Bank

Payment method

Payment method supplement

Payment Request checkbox

Same Direction checkbox

Individual Payment checkbox

Determination of Grouping Definition

Repetitive Code

User Data

In the user data, you see when the master data of the external account was created and by whom, as well as when the last changes were made and by whom.

After you have created master data for an external account, you can manually enter the account statements for an external account or upload them from an Excel file. You do this in the activity Transaction Manager External Accounts External Account Statement Process External Account Statement .

**Prerequisites**

You need to have made the Customizing settings for the external accounts.

You need to create your counterparty (with whom you have your clearing account) as a business partner and assign the role Counterparty to this business partner.

**Procedure**

Choose External Accounts Master Data Process External Account and perform one of the following functions:

|Function|Procedure|Comments|
|---|---|---|
|Create|1. Choose Create. 2. Enter the company code. In the External Account field, enter a short description not exceeding 10 characters. The system automatically assigns the account type 001Clearing Account to the external account.| |


|Function|Procedure|Comments|
|---|---|---|
| |Now choose Create or enter an existing external account as a template and choose Copy. 3. The Create External Account screen appears. 4. Save the data. 5. Save your entries. | |
|Change|1. Choose an external account from the hierarchy on the left-hand side of the screen. 2. The data of the account is displayed on the right-hand side of the screen. 3. Choose "Change". 4. Make any necessary changes and save your entries. | |
|Display|1. Choose an external account from the hierarchy on the left-hand side of the screen. 2. The data of the account is displayed on the right-hand side of the screen. | |
|Delete|1. Choose an external account from the hierarchy on the left-hand side of the screen. 2. The data of the account is displayed on the right-hand side of the screen. 3. Choose Delete. |You can only delete an external account if no external account statement has yet been entered for that account.|


**Result**

The external account has now been created, and you can enter account statements for it and assign the clearing account to a financial transaction that is relevant for clearing.

**More Information**

Processing External Account Statements

The documentation on the Administration tab page within a financial transaction

Defining Default Values for Clearing

##### Master Data (2 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Master Data | L4 | trm10 p.208 | loio `f3d2138d35f046949d2ae6c5df61b812` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f3d2138d35f046949d2ae6c5df61b812.html?locale=en-US)

In the Information System under Master Data, you find the following report for analyzing your business partner data:

Changes to Business Partners

In the Securities area, you also find the reports Class Information and Securities Account List .

###### Processing External Accounts

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Master Data > Processing External Accounts | L5 | trm06 p.239 | loio `7ae206bef71842a499d9c3e0996c91ad` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7ae206bef71842a499d9c3e0996c91ad.html?locale=en-US)

###### Defining Default Values for Clearing

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Master Data > Defining Default Values for Clearing | L5 | trm06 p.256 | loio `35d79d9aca614db99a5d6edb8b469040` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/35d79d9aca614db99a5d6edb8b469040.html?locale=en-US)

**Context**

For clearing-relevant financial transactions (for which you have set the Central Clearing Optional clearing option in Customizing for external accounts in the activity Activate Central Clearing), you can change or add to the central clearing option (on the basis of company code, product type, transaction type, counterparty, and transaction currency) and define an external account as the default value. When a clearing-relevant financial transaction is created, the settings that you make are entered automatically as the clearing account in the Administration tab page in the Clearing area.

The default value can be overwritten in the financial transaction.

**Procedure**

- 1. Change the data displayed or choose New Entries.
- 2. Choose the company code, the product type, the transaction type, the counterparty, and/or the transaction currency and assign the desired clearing option and/or clearing account.
- 3. Save your entries.


**Example**

In Customizing for external accounts in the activity Activate Central Clearing, you have set the central clearing option Central Clearing Optional in company code 0001 for product type SWAP.

In the activity Define Default Values for Clearing, make the following settings:

|Company Code|Product Type|Transaction Type|Counterparty|Currency|Central Clearing Option|External Account|
|---|---|---|---|---|---|---|
|0001|SWAP| | | |Central Clearing Optional| |
|0001|SWAP| |Counter Party A| |Central Clearing Mandatory|Clearing 1|
|0001|SWAP| |Counterparty B| |Central Clearing Mandatory|Clearing 2|
|0001|SWAP| |Counterparty C| |Not relevant| |


Information System

##### Information System (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Information System | L4 | trm10 p.2 | loio `88ac9a3ffd2c4dbba01b1d6b7d2d699e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/88ac9a3ffd2c4dbba01b1d6b7d2d699e.html?locale=en-US)

**Purpose**

You can use the Information System in the Transaction Manager to execute the reports defined by SAP or to create your own reports.

When defining reports, you can use SAP Query or load data into the Business Information Warehouse (BW) for analysis.

**Integration**

To access the Information System, choose Accounting Financial Supply Chain Management Transaction Manager Information System .

**Features**

Logical Databases for the Transaction Manager

Logical databases (LDBs) have been created to provide easier access to data in the Transaction Manager.

These databases provide a structured, integrated view of the system database tables. They provide a pool of table fields for a particular business function. In doing so, they encapsulate access to up to 100 database tables and integrate certain calculation procedures (for example, the NPV calculator).

|Logical Database|Use|
|---|---|
|FTI_TR_POSITIONS Treasury Positions FTI_TR_POSITIONS_1 Treasury Positions Projection FTI_TR_POSITIONS_2 Treasury : Positions Eval + addtnl position attrs |You can use this LDB to evaluate positions in the Transaction Manager for a given key date. This enables you to analyze all the key figures and characteristics that are relevant for accounting for the specified key date.|
|FTI_TR_PERIODS Period Evaluations FTI_TR_PERIODS_1 Treasury: Period Analysis Projection FTI_TR_PERIODS_2 Treasury: Period-Based Eval + addtnl postn attrs |You can use these LDBs to evaluate flows in the Transaction Manager for a given period. This enables you to analyze position trends and revenues within the selected period, including positions at the start and end of the period, on a flexible basis.|
|FTI_TR_PL_CF Treasury: Revenue and Cash Flow Reporting FTI_TR_PL_CF_1 Treasury: Revenue and Cash Flow Reporting|You can use this LDB to evaluate revenues/flows incurred within a given period. This enables you to analyze all the revenues for the respective due date or period.|
|FTI_TR_CASH_FLOWS Treasury Payment Information FTI_TR_CASH_FLOWS_2 Treasury Payment Info + addtnl position attrs|You can use this LDB to evaluate payments in the Transaction Manager for a given period. You can flexibly analyze payment flows from transaction management within the selected period.|


|Logical Database|Use|
|---|---|
|FTI_TR_DEALS Transaction Reporting|This LDB evaluates information from transaction management. You can use the logical database for front office-based reporting. These functions enable cross-application reporting over the various financial products. In addition to cash flowbased evaluations, you can also create transaction data reports.|
|FTLM_DB01 Limit Management| |
|FTI_SWAP_POSITION Swap Positions| |
|FTI_TR_EXP_POS Exposure Positions| |
|FTI_TR_HEDGE Treasury E-Hedge Accounting Reporting| |
|FTI_TR_THX_HEDGE Treasury P-Hedge Accounting Reporting| |
|FTI_BW_CFM_VALUES Market Values and Simulated Values in Pos. Mgmt| |


To improve system performance, all LDBs are accessed by a field list that includes only the fields and their nodes that are required by the calling program for the period.

Using SAP Query for the application areas in the Transaction Manager:

SAP Query is used to generate lists that are not yet contained in the standard system. It offers the advantage that the user can create comprehensive reports without having to carry out manual programming.

SAP Query comprises the components Queries and InfoSet Query for defining reports, the InfoSets component to maintain InfoSets, the User Groups component to manage user groups, and the Translation/Query component that can be used to translate texts created in SAP Query.

See also:

For more information about the SAP Query features and its use, see the SAP Query documentation.

To evaluate data in the Transaction Manager using SAP Query, you use the logical databases for the Transaction Manager. The logical databases have been designed in a way so that you can use them according to their evaluation purposes.

You can use InfoSets for the Transaction Manager to define reports and various report forms, such as basic lists, statistics, and ranked lists.

Some standard queries for the Transaction Manager have also been defined so that you can execute them or use them as a copy template.

To use the functions for maintaining queries, InfoSets, and user groups, choose Information System Tools SAP Query Information System .

Link to the Business Information Warehouse (BW):

The Transaction Manager is linked to the Business Information Warehouse (BW). In doing so, the logical databases in the Transaction Manager are used as the basis for the BW extractors.

All the standard reports for the Transaction Manager are located in the report structure delivered with the system. Choose Information System Reports .

###### External Account: Position Flows

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Information System > External Account: Position Flows | L5 | trm06 p.257 | loio `fea51d964478466cb7584ed99f0b5ab0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fea51d964478466cb7584ed99f0b5ab0.html?locale=en-US)

Context

You use this program to display all flows for a clearing account position, for an assignment position, and/or for an operative position.

If you would like to display, for example, all flows for a clearing account position as well as the flows of the related financial transactions, select the clearing account position and the operative position as well as the relevant clearing account.

However, you could also display just the flows on the assignment positions or on the clearing account positions.

**Note:**

The position flows cannot be aggregated.

**Procedure**

- 1. Call the program under External Accounts Information System External Account: Position Flows (transaction TREA_SHOW_FLOWS).
- 2. Depending on what you want to include, set the Clearing Account Position, Assignment Position, and Operative Position checkboxes accordingly.
- 3. You can restrict the display based on the following criteria:

Company Code

External Account

Transaction

(The criterion "Transaction" only appears when you have selected the assignment position and/or the operative position.)

Specify the type of flows that you would like to see:

Position Value Date

Enter a period or a To date.

Planned Flows

Fixed Flows

Reversed Flows

Select the desired flows.

- 4. The list is issued using the SAP List Viewer.

If you set the Amounts with +/- Sign indicator, the system outputs the amounts with their respective signs. If you do not set this indicator, the system outputs the amounts without their sign.

If you have already defined a layout for the output list, you can select that layout.

- 5. Choose Execute.
- 6. The system outputs the list, sorted by the following:


Company Code

External Account

Transaction

For each flow, the system specifies the position to which it belongs (the list uses colors to highlight this distinction). Reversed flows are highlighted in red.

You can display the following information about the flows:

Position Value Date

Update Type

Update Type Name

Payment Currency

Payment Amount

Status

Local Currency

Local Currency Amount

Nominal Amount

Nominal Currency

Position Currency

Amount in Position Currency

Translation Date

Local Currency Translation

Direction

Due Date

Payment Date

To show additional information for the flows, choose Change Layout.

- 7. To process the list, you can use the standard functions of the SAP List Viewer.
- 8. If you want to display details for a flow, select the flow and choose Details.

###### Displaying External Account Positions

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Information System > Displaying External Account Positions | L5 | trm06 p.259 | loio `32913c36e68149848375ae3d8bb1162f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/32913c36e68149848375ae3d8bb1162f.html?locale=en-US)

**Prerequisites**

Clearing account positions exist.

Define the currency exchange rate in the market data so that the system can, if necessary, translate the amounts from the position currency to your local currency.

**Context**

This program provides you with information about the amounts of the variation margin and the initial margin on your clearing account positions on a given key date.

The following values are displayed for the selected clearing account positions:

Variation Margin in Position Currency

Variation Margin in Local Currency

Initial Margin in Position Currency

Initial Margin in Local Currency

**Procedure**

- 1. Call the function under External Accounts Information System Display External Account Positions (transaction TREA_SHOW_POSITIONS).


- 2. Select the clearing account position. In addition, you can select the assignment position. In this way, in addition to listing the total margin amounts on the clearing account positions, the system also returns how the margin is divided - what amounts to which financial transactions.
- 3. Enter the selection criteria.

Company Code

External Account

Financial Transaction

(if you have selected the assignment position)

- 4. Enter the key date.
- 5. The list is issued using the SAP List Viewer. If you have defined layouts, you can select one of them here. You can display the list as a tree or a matrix.
- 6. Execute the function.
- 7. The list is output on the basis of your selections. The list display uses the following key:

Company Code

External Account

Position Currency

Financial Transaction Level

- 8. From the list, you can navigate to the flows related to a position.


**Note:**

You can also switch between the display variants from within the list.

###### Display Net Present Values of Financial Transactions for External Accounts

> **Path:** Treasury and Risk Management > Transaction Manager > External Accounts > Information System > Display Net Present Values of Financial Transactions for External Accounts | L5 | trm06 p.260 | loio `43dd4707a6d9433d882f22d339e23484` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/43dd4707a6d9433d882f22d339e23484.html?locale=en-US)

**Use**

You use this transaction for selected external accounts to display the discounted and nondiscounted net present values of the relevant financial transactions. You find this transaction under Transaction Manager External Accounts Information System

.


**Prerequisites**

To be able to execute this function, you need to have made the following settings:

You have made the settings specified in the section Calculate Net Present Values of Financial Transactions for External Accounts (transaction TREA_EVAL).

You have already used transaction TREA_EVAL to calculate net present values and to save them in the database. You find this transaction in the area menu under Transaction Manager External Accounts .

**Features**

- 1. Run the transaction (TREA_EVAL_SHOW). Select one or more external accounts.


If you do not select any accounts, the system displays the values for all external accounts.

- 2. Specify whether you want to display discounted or nondiscounted net present values.
- 3. Choose Execute (F8). You receive an overview of the selected financial transactions with the net present values calculated for them.


To display any system error messages, navigate to the relevant error log.

