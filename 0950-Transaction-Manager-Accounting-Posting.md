# Transaction Manager > Accounting > Posting - SAP TRM Knowledge Base (branch split)

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

##### Posting

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting | L4 | trm07 p.41 | loio `5d15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5d15da531198434de10000000a174cb4.html?locale=en-US)

The posting function transfers the data to Financial Accounting.

Each financial transaction is based on certain transaction data (such as nominal amounts, interest rates). The flows relating to a financial transaction are generated from this transaction data. These flows are used to determine the data that is required for posting, such as document types, balance sheet accounts or income statement accounts and the posting keys. This data and the flows to be posted are transferred to the FI interface that generates the relevant postings and documents using the corresponding functions. The document principle is used throughout the entire system. In other words, postings are always saved as documents. The document is kept as a unit in the system until it is archived.

The account assignment rules for the posting types are fixed and monitored in Treasury and Risk Management.

Before you transfer the flows to FI, you determine the relevant posting specifications using the flexible account determination. The posting specifications identify the accounts used in the posting run. Account determination is based on a general concept with replacement rules and masking. You set up the account determination only once during implementation. This ensures a standard procedure and minimizes the number of input fields.

For more information, see also: Account Assignment Reference

**Related Information**

Fix, Pay and Post Flows Process Business Transactions Release Asynchronous Distribution Block Margin Management

###### Fix, Pay and Post Flows

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Fix, Pay and Post Flows | L5 | trm07 p.41 | loio `4219c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4219c55368511d4be10000000a174cb4.html?locale=en-US)

Post the flows from transaction management to Financial Accounting and also pay the payment-relevant flows.

App ID: TBB1

**Use**

With this app, you can fix the transaction management flows for the money market, foreign exchange, derivatives, trade finance, and securities applications, and update it to Financial Accounting.

You can only post transaction flows for which you have assigned a contract or settlement status.

Financial transactions that do not involve settlement and do not contain flows relevant for posting (such as open/close flows for futures) are assigned to be fixed status when the transaction is executed.

**Overview Payment Process**

Payment relevant flows of financial transaction can be paid using payment request. You maintain the settings for payment flows on Payment Detail tab within financial transaction data.

During the posting of the flows, the payment requests are generated.

You use the Automatic Payment Transactions for Payment Requests app to create the payments.

From the financial transaction data, you can navigate to the payment requests and the payment request status is shown, which gives following information:

Not Paid

Paid

Flagged for Reversal

Reversed

Within the financial transaction data, you can flag flows as flagged for reversal. For some flows, the entire activity must be reversed. The business transaction must then be reversed. The payment requests are updated according to these changes.

**Features**

Filter posting-relevant flows with parameters such as company code, transaction, product type, and so on

**Note:**

You enter Up to and Including Due Date up to which the flows will be posted.

Payment Control

This section contains two options to automate payment runs and send payments to SAP Bank Communication Management (BCM).

**Note:**

BCM can be activated by activating the scope item J78 (Advanced Cash Operations) in your system.

Schedule Auto Payment Run

Activate this option to automatically schedule payment runs for any payment requests that are generated for the selected flows. You can also schedule payment runs manually in the Automatic Payment Transactions for Payment Requests (App ID: F111) app.

**Note:**

Payments with the same values in the fields Country/Region Code, Local Currency, Withholding Tax Indicator, and Payment Date are assigned to the same payment run.

Send to Bank Communication Management

This option is available if you have activated auto payment runs and you are using SAP Bank Communication Management (BCM). If sent to BCM, the payment appears with a batch number in the Monitor Payments app (App ID: F2388).

When starting the automated payment run, you see a confirmation popup. Here, choose Log for Automatic Payment Run. In the Identification column of this log, you see the ID of the payment run. The combination of payment run and date serves to uniquely identify the payment run in other apps. You can use the Display Payment Run button in the menu bar to navigate directly to the payment run.

[figure TRM07-F014 - When starting the automated payment run, you see a confirmation popup. Here, choose Log for Automatic Payment Run. In the Identification column of this log, you see the ID of the payment run. The combination of payment run and date serves to uniquely identify the payment run in other apps. You can use the Display Payment Run button in the menu bar to navigate directly to the payment run.]

Post the flows that you select with the following options:

With the Pay Only option, you can start the payment process.

With the Post Operational Only option, you can fix and post flows for the paying valuation area and start the payment process, if necessary.

With the Post All Valuation Areas option, you can fix and post flows for all valuation area.

Generates a posting log for each posting.

To display the data for a flow, select the relevant posting line and choose Details. To see the accounting documents, select the reference key ID.

**Supported Device Types**

Desktop

Tablet

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

###### Process Business Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Process Business Transactions | L5 | trm07 p.43 | loio `4519c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4519c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

You use this function to post business transactions in transaction management to the parallel valuation areas. You can also fix or reverse corresponding derived business transactions as long as you've made the Same Status setting in Customizing.

**Note:**

The function Post Flows (transaction TBB1) can also be used to post transactions to the parallel valuation areas or the operative valuation area.

This function reverses the business transactions indicated as financial transactions to be reversed in all valuation areas.

Integration

[figure TRM07-F015 - Features]

Features

You use this function to perform the following postings:

Post or fix purchase and sale flows, other flows, and corresponding derived business transactions in the parallel valuation areas.

Reverse flows for the reversed financial transaction in all valuation areas (such as purchase flows or sale flows).

If you've opted for Online Processing by choosing Control of Processing of Derived Business Transactions in Customizing for position management, you can also perform the following postings:

Reverse the "old" posted derived business transactions for the affected positions.

Reverse the recalculated derived business transactions that are relevant for posting for the affected positions.

**Note:**

If you opt for offline processing in Customizing for parallel position management under Control of Processing of Derived Business Transactions, you recalculate and post the derived business transactions using the functions Update Derived Business Transactions and Fix and Post Derived Business Transactions.

See also:Derived Business Transactions

**Activities**

- 1. Call the app on the SAP Fiori launchpad in the Treasury Accounting group or in backend system under Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Money Market /

Foreign Exchange / Derivatives / Securities / Debt Management Accounting Posting Process Business Transactions (transaction TPM10).

- 2. Make the following selections:


|Product Groups|You can also select exposure item data and exposure subitem data because the product group Exposure Items was added. You can limit your results by searching for Exposure Item ID and Exposure Subitem ID.|
|---|---|
|General Selections|Company Code Valuation Areas|
|Limit by Transaction Number|You can use the indicator Limit by Transaction Number to select business transactions according to their number.|
|Limit by Subledger Positions|You can use the indicator Limit by Subledger Positions to select business transactions according to their product type and (special) valuation class. The following selection criteria applies to the product groups: Securities ID number Securities account Securities account group Portfolio Listed Derivatives ID number Futures account OTC Transaction Transaction Exposure Items Exposure Item ID|


| |Exposure Subitem ID Additional Selection Criteria Financial Transaction Hedging Relationship Number Select from OTC-Transaction If you mark this indicator the above field for entering financial transaction numbers isn't open for entries anymore. System now searches the exposure items by the financial transactions selected using the fields in OTC Transactions group. **Note:** For some reports, this area isn't available. **Note:** For some reports, this indicator isn't available.|
|---|---|
|Business Transaction Selections|FI Posting Date Indicator: Including Derived Business Transactions If you set this indicator, the corresponding derived business transactions are fixed. (for online processing and same status). Indicator: Business Transactions to Be Fixed/Posted. If you set this indicator only, then only the business transactions to be fixed or posted are selected. Indicator: Business Transactions to Be Reversed If you set this indicator only, then only the business transactions to be reversed are selected.|
|Posting Control| |
|TRM Reason for Reversal|If you entered a TRM reversal reason when you reversed the financial transaction, you don't need to enter one here.|
|Posting Date|Enter the posting date.|
|Posting Period|Enter the posting period.|
|Test Run indicator|If you set this indicator, the system simulates the run.|


**3. Execute the report.**

**Output**

If the indicator Display and Select Business Transactions was set in the output control, the system displays all the selected business transactions so that you can select which ones should be posted or reversed with this function. To do this, you can use the pushbuttons Choose Business Transactions to Be Posted and Business Transactions to Be Reversed. However, you can also select specifically which business transactions you want to post or reverse.

Once you've executed this function, the system displays a list of the posted or reversed business transactions. You can then use the Logs and Messages button to call the Posting log, Reversal log, and the Messages list.

###### Release

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Release | L5 | trm07 p.47 | loio `4cff6d895b605dc6e10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4cff6d895b605dc6e10000000a42189c.html?locale=en-US)

**Use**

If your company uses the release management function, you sometimes have to release flows before they can be posted or reversed.

For organizational reasons, a second user must release the posting manually.

**Note:**

You can also use the Release Workflow to release transactions.

See also:Release Workflow - Financial Transaction (TRM-TM)

**Prerequisites**

If you do not want to use the release function for transaction management, you need to set the Automatic Posting Release indicator in Customizing for Transaction Manager under Money Market/Foreign Exchange/Listed Derivatives/OTC Derivatives/Securities Transaction Management Transaction Types Define Transaction Types . In this case, the posting is released automatically - this means that the transaction does not have to be released by a second user.

**Procedure**

To release a posting:

- 1. Choose Accounting Posting Release .
- 2. Enter the company code and the transaction number.
- 3. By choosing Execute, you display a list of the flows that need to be released.
- 4. By choosing Edit Release up to the payment date, the system set a cross in the first column in the list.
- 5. Release the flows by choosing Save.


The following message appears: Posting releases for transaction XXX saved.

###### Asynchronous Distribution

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Asynchronous Distribution | L5 | trm07 p.47 | loio `3f82cd52bad99d36e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3f82cd52bad99d36e10000000a44538d.html?locale=en-US)

Use

You use this function to distribute operational business transactions in Transaction Management and Securities Account Management, independently of their valuation area and in two steps. In the first step, the operational business transaction is entered and then processed in Transaction Management and Securities Account Management. The business transaction is scheduled to be distributed to Position Management, dependent on the valuation area, but the distribution is not yet performed. In the second step, you perform the scheduled distribution using the function Distribute Business Transactions to Position Management (transaction TPM10A).

Performing the distribution in two steps is considerably quicker compared to importing a large number of financial transactions. Firstly, the financial transactions can be entered more quickly because the distribution to Position Management has not yet occured, and, secondly, you can speed up the subsequent distribution to Position Management considerably by creating appropriate bundles of transactions.

**Features**

Process for Asynchronous Distribution

- 1. Activate asynchronous distribution using Switch On/Off Asynchronous Distribution (transaction TPM10A_SWITCH).
- 2. Creating and Settling Transactions
- 3. Run the function Distribute Business Transactions to Position Management (transaction TPM10A) to distribute new transactions to Position Management (dependent on the valuation area).
- 4. Deactivate asynchronous distribution using Switch On/Off Asynchronous Distribution (transaction TPM10A_SWITCH).
- 5. As a precaution, run Distribute Business Transactions to Position Management (transaction TPM10A) again to distribute any business transactions that were entered between the last time when the function was run and the time when asynchronous distribution was deactivated.


Note:

When you run the function Distribute Business Transactions to Position Management (transaction TPM10A), the system sets a block on the affected positions to ensure that, while the function is running, no more operational business transactions can be entered for those positions. (While the block is in force, the system issues an error message upon any attempted transaction entry).

**More Information**

Activate/Deactivate Asynchronous Distribution

Distribute Business Transactions to Position Management

###### Activate/Deactivate Asynchronous Distribution

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Asynchronous Distribution > Activate/Deactivate Asynchronous Distribution | L6 | trm07 p.48 | loio `df7fcd52bad99d36e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/df7fcd52bad99d36e10000000a44538d.html?locale=en-US)

**Use**

In this table, you activate or deactivate the asynchronous distribution function.

You can restrict the activation of asynchronous distribution using the following attributes:

Product groups

Accounting code

Valuation area

**More Information**

Asynchronous Distribution of Operational Business Transactions

Distribute Business Transactions to Position Management

###### Distribute Business Transactions to Position Management

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Asynchronous Distribution > Distribute Business Transactions to Position Management | L6 | trm07 p.48 | loio `24fccd523b2ba91ae10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/24fccd523b2ba91ae10000000a44538d.html?locale=en-US)

**Use**

You use this function to asynchronously distribute business transactions to Position Management.

**Integration**

You execute this function only if you have activated asynchronous distribution and if business transactions have been entered asynchronously.

See also:

Asynchronous Distribution

Activate/Deactivate Asynchronous Distribution

**Activities**

- 1. Call the function in the application menu by choosing Transaction Manager Money Market/Foreign Exchange/Derivatives/Debt Management Accounting Posting Asynchronous Distribution Distribute Business Transactions to Position Management (transaction TPM10A).
- 2. Select the relevant product groups.
- 3. You can use the fields in the General Selections area to restrict the selection of business transactions further.
- 4. If you want to perform a test run first, set the Test Run indicator in the Posting Control field.
- 5. In the Output Control area, you can set the Display and Select Business Transactions indicator. When you set this indicator, the system first displays a list of all business transactions found, and you can select the ones that you want to distribute to Position Management.
- 6. Execute the function.
- 7. If you have set the Display and Select Business Transactions indicator, the system displays a list of the selected business transactions entered asynchronously. If you do not want to distribute one of the business transactions to Position Management, deactivate the Select/Deselect indicator.

Execute the function.

- 8. The system distributes the business transactions to Position Management, thereby updating the positions affected by those business transactions.

###### Block

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Block | L5 | trm07 p.49 | loio `5714da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5714da531198434de10000000a174cb4.html?locale=en-US)

**Use**

If you do not want the flows for a financial transaction to be posted for the time being, you can block them for posting.

**Procedure**

To block the flows, proceed as follows:

- 1. Choose Accounting Posting Block .
- 2. Enter the company code and the number of the transaction and confirm your entries. The system displays a list of all the flows for that transaction.
- 3. By choosing Edit Block from the payment date, the system sets an indicator in the first column in the list.
- 4. You block the flows by choosing Save. The system issues the following message: Posting blocks for transaction XXX saved.

###### Margin Management (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Margin Management | L5 | trm07 p.50 | loio `9915da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9915da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Margin management enables you to clear the profit and loss of any open market positions for futures or listed options.

The transactions for margin management are available on the SAP Easy Access screen. Choose Treasury and Risk Management Transaction Manager Derivatives Accounting Posting Margin Management .

**Prerequisites**

You have defined update types for margin management and assigned corresponding product types in Customizing for the Transaction Manager by choosing Listed Derivatives Position Management Futures Account Management Update Types

.


If you want to define a rate type for each product type to translate the position currency amounts into the local currency, in Customizing for the Transaction Manager choose Listed Derivatives Position Management Futures Account Management

Assign Rate Types to Convert Margin Flows .

**Note:**

To value variation and closed margin flows, the system uses the default rate type M - Standard Translation at Average Rate.

**Features**

The system generates a new position (single position) with each open transaction. For each key date, the system uses the rates to re-value the positions and determines the current values for receivables and payables which are then used to calculate the clearing amounts. The clearing amounts represent unrealized gains and losses.

You can close the single position again using one or more close transactions (or partial close transactions.) The system then automatically generates a corresponding closed margin with planned status.

[figure TRM07-F017 - Overview of Margin Management]

Overview of Margin Management

See also:

Open Transaction and Close Transaction

###### Variation Margin and Closed Margin

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Margin Management > Variation Margin and Closed Margin | L6 | trm07 p.51 | loio `2215da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2215da531198434de10000000a174cb4.html?locale=en-US)

**Variation Margin**

The variation margin (key date margin) represents the daily gains and losses of open futures positions and listed options (future style.) The settlement payment is derived by comparing the values of the open items from the previous day with the values from the current key date until market close.

The profit and loss is paid out or received on a daily basis. The variation margin ensures against an accumulation of losses over a long period of time. It also prevents a repayment of high loss to the creditor.

**Closed Margin**

The closed margin represents the profit and loss of closed positions compared to the previous day. If a closed transaction is used to either partially or completely close an open position, the system compares the value of the closed position from the previous day with that of the closed transaction and then determines the settlement payment (closed margin).

**Example**

Use the following initial data:

Number of contracts: 8

Tick value in 12

Tick size in points 0.5

The daily margin values are calculated as follows:

Value = (Number of contracts x Tick value / Tick size) x rate in points

Value = 8 x 12/ 0.5 x Price in points = 192 x Price in points

|Day/Rate|Price (Points)|Value (EUR)|Value Change (Variation Margin)|Outcome for Holder of the Long Position|Outcome for Holder of the Short Position|
|---|---|---|---|---|---|
|Opening price|4.850|931.200| | | |
|1. Day|5.100|979.200|+48.000|Profit|Loss|
|2. Day|5.050|969.600|-9.600|Loss|Profit|
|3. Day|5.000|960.000|-9.600|Loss|Profit|
|Closing price|5.150| | | | |


**Complete Position Closure**

On day 4, the position is closed completely using a closing transaction at a price of 5,150:

= 8 (5,150 x 12 / 0.5) 960,000

= 988.800 960.000

= + 28.800

The closing margin is EUR 28,800. The overall result is the sum of the variation margin and closed margin, or the difference resulting from the value of the position at the closed price and open price:

192 x (closed price in points purchase price in points) = 192 x 300 = 57,600

**Partial Position Closure**

On day 4, a closed transaction of 3 units is executed at a price of 5,150. The amount of the closed margin is calculated as follows:

Close Margin = Value of the closed position at the closed price value of the closed position on the previous day

= 3 (5150 x 12/ 0.5 ) (960,000 x 3/8)

= 370.800 360.000

=+ 10.800

The holder of the long position receives a closed margin of EUR 10,800 from the owner of the short position. The overall result is a profit of EUR 21,600 (This corresponds to 3/8 or 37.50 % of the total result when the position is closed completely.)

###### Posting the Variation Margin

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Margin Management > Variation Margin and Closed Margin > Posting the Variation Margin | L7 | trm07 p.52 | loio `ba15da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ba15da531198434de10000000a174cb4.html?locale=en-US)

You use this transaction to post the variation margin (key date margin) on each trading day. By doing this, the system can value all open positions with the variation margin at the settlement rate on a daily basis.

**Procedure**

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Derivatives Accounting Margin Management Post Variation Margin .
- 2. Enter the security ID number, company code, and the key date.
- 3. If you do not want the system to post close margin flows from the selected positions that have not yet been posted, set the Post Close Margin indicator. This ensures that only the flows on or before the key date are taken into account.
- 4. To carry out a test run, without changing the data in the database, set the Test Run indicator.
- 5. Choose Execute .

###### Posting the Close Margin

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Margin Management > Variation Margin and Closed Margin > Posting the Close Margin | L7 | trm07 p.53 | loio `e914da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e914da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this transaction to post close margin flows from close transactions.

**Note:**

When you create a close transaction, the system automatically generates a close margin business transaction with planned status. If you make any subsequent changes in the close transaction, the system updates the corresponding business transaction automatically.

**Prerequisites**

All the relevant open and close transactions have already been posted and fixed.

You have indicated the flow categories Purchase and Sale as relevant for posting . In Customizing for the Transaction Manager , choose Listed Derivatives Transaction Management Flow Types Define Flow Types. Then double-click on the relevant flow category line and set the indicator.

**Procedure**

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Derivatives Accounting Posting Margin Management Post Close Margin (TPM25).
- 2. Enter the futures ID number or the option ID number, the company code and the key date until all close margins are posted.
- 3. To execute a test run without making any changes to the database, set the Test Run indicator.
- 4. Choose Execute .

**Reversing Margin Flows**

You use this transaction to reverse postings for variation margins and close margins that are incorrect.

**Note:**

After you have reversed the variation margin, the corresponding flows are removed.

When reversing close margin flows, the system generates new flows with planned status.

**Procedure**

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Derivatives Accounting Posting Margin Management Reverse Margin Flows (PMSV).
- 2. Enter the company code, futures account, ID number, and the reversal reason.
- 3. Choose the key date from when all margin flows are to be reversed.
- 4. Set the Test Run indicator if you only want to simulate database changes.
- 5. Choose Execute .

###### Reversing Margin Flows

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Margin Management > Variation Margin and Closed Margin > Reversing Margin Flows | L7 | trm06 p.240 | loio `8715da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8715da531198434de10000000a174cb4.html?locale=en-US)

The type of margin account statement that you want to create is stored in the master data of each external account (transaction TREA_ACC_MNT). If the margin account statement is created as an overview of the margin balances, it is only ever possible to reverse the last margin account statement. You need to delete any existing account statements that have not been processed yet before you can reverse the preceding margin account statement. This rule is necessary because the margin flows of a margin account statement are calculated on the basis of the preceding margin account statement. If the margin account statement is not created as an overview of the margin balances, it is possible to reverse the margin positions in any sequence.

**Prerequisites**

You need to have made the settings in Customizing for External Accounts under Margin Balances.

Using transaction TREA_ACC_MNT, you need to set the Use Margin Balances indicator on the General Data tab in the master data of the external account. Once you have set this indicator, the Margin Balances tab appears in the transaction Process External Account Statement (TREA_STA_MNT).

To be able to make manual changes to payment amounts that have been calculated automatically, you have to set the Adjustment of Payment Amount Permitted indicator. The possible reasons for adjustments are stored in Customizing under Margin Limit Management.

**Activities**

- 1. Choose the Margin Balances tab.
- 2. Enter the margin amounts of the current account statement. If the initial margin is in a foreign currency, enter an exchange rate for converting the foreign currency to the account currency. Save your entries.
- 3. The system determines the difference between the previous balance and the new balance and calculates the payment amount.
- 4. Change the payment amount, if necessary, and choose a reason for the change.

Note: Change reasons are entered in Customizing for Central Counterparty Clearing under Margin Limit Management Specify Margin Limit Reasons .

- 5. On the Positions tab, check the flows created by the system.
- 6. Save the account statement. Then use transaction Release Positions (TREA_RELEASE) to release the positions.


Note: Changes cannot be made to an account statement once all of its positions have been released.

You can now use the transaction Create Net Payment (TREA_PAY) to trigger and post the relevant payments.

**Example**

Determining Payment Amounts Without the Margin Limit Check:

|Last Initial Margin|2000|
|---|---|
|Current Initial Margin|2000|
|Initial Margin Difference Amount|0|
|Initial Margin Payment Amount|0|


|Last Variation Margin|3000|
|---|---|
|Current Variation Margin|4000|
|Variation Margin Difference Amount|1000|
|Variation Margin Payment Amount|1000|


**More Information**

Margin Management

Margin Limits

###### Open Transaction and Close Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting > Margin Management > Open Transaction and Close Transaction | L6 | trm07 p.54 | loio `9816da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9816da531198434de10000000a174cb4.html?locale=en-US)

An open transaction is used to open a futures position or an options position on the market. The counter transaction used to clear or close the position is called a close transaction. This breaks any existing market commitments.

Open and close transactions are expressed as Purchases or Sales. A position may be opened by both a purchase (long position) and a sale (short position).

The following applies to clearing a position:

|Open purchase|Cleared by: Close sale|
|---|---|
|Open sale|Cleared by: Close purchase|


You should enter initial margins, charges, commissions, and taxes as additional flows.

The final gains/losses for forward exchange transactions are only determined when the item is cleared. You therefore have to correctly assign the close transactions to the open positions. The system checks whether the open positions available are sufficient. If the number of cleared units exceeds the open items, the system displays an error message.

