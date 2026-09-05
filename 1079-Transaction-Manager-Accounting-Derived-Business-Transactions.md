# Transaction Manager > Accounting > Derived Business Transactions - SAP TRM Knowledge Base (branch split)

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

##### Derived Business Transactions (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions | L4 | trm07 p.129 | loio `5419c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5419c55368511d4be10000000a174cb4.html?locale=en-US)

**Definition**

Derived business transactions supplement Operative Business Transactions. They are generated on the basis of the operative business transactions and are dependent on the valuation area. This means that the derived business transactions can be differ according to valuation area even if they stem from the same operative business transactions.

**Use**

Derived business transactions are generated in the following cases (examples):

When you enter a security purchase or loan disbursement involving a discount or premium and manage the position using the gross procedure. The derived business transaction is used to generate the discount or premium flow.

When you enter position outflows [sale, repayment, exercise, stock swap with payment and any other position outflows that are not transfer postings], the price gains and losses are generated as derived business transactions.

If amortization is required by the Position Management Procedure for the position, and the operative business transaction changes the amortized acquisition value of the position (= purchase value + capitalized costs + amortizations), the system generates amortization flows for the total position.

If you make internal transfer postings [securities account transfers, valuation class transfers, corporate actions, exercising rights, exercising OTC options], the system generates derived business transactions that transfer the positions per position component.

When you enter position outflows that are not transfer postings, the system generates translations that update the position components (proportionate reduction). Translations are not usually relevant for posting.

When you change the currency (local currency, issue currency or contract currency) over to the euro, the system generates reconciliation flows. These flows ensure that the positions are consistent for a certain date.

Examples:

If, after the changeover, the position currency is the same as the valuation currency, then the position values in these currencies should also match.

If the position is a zero position, the value of all the position components should also be zero.

When you change over the issue currency or the contract currency, currency swap flows are generated to clear the old currency amounts in the general ledger and post the corresponding amounts in the new currency.

**Structure**

Derived business transactions can have the following status:

Plan

If a flow has plan status, it has not yet been posted.

To be fixed

Fixed

If a flow has fixed status, it has been posted (if it was relevant for posting).

To be reversed

Reversed

In the Customizing activity Control of Processing of Derived Business Transactions, you define the status the derived business transactions have when they are generated:

Same status: The derived business transactions always have the same status as the corresponding operative business transaction.


In the case of OTC transactions, this means that you must fix the derived transactions using the function Fix and Post Derived Business Transactions , since the related original business transactions are never fixed.

Plan status: The derived business transaction are always generated with plan status. To fix the derived business transactions, you use the Fix and Post Derived Business Transactions function.

Derived business transactions can be generated online or offline.

If you choose the online option, the system automatically generates or updates the derived business transaction for the respective valuation area immediately after the operative business transaction is processed (created, changed, or posted).

If the system finds existing derived business transactions that have already been fixed but are no longer up-to-date, it generates these in the To be reversed status and the current derived business transactions in the To be fixed status. Posting and fixing these derived business transactions takes place using the function Fix, Post, Reverse Business Transactions (TPM10).

**Note:**

If you have a large amount of data, generating the derived business transactions online can impair performance (especially if they are fixed immediately). In such cases you can process the derived business transactions offline.

If you choose offline processing, the derived business transactions are not generated directly when you create, change, or post an operative business transaction. Instead, you generate them using the Update Derived Business Transactions function (transaction TPM27). You can also post and fix flows using the Fix and Post Derived Business Transactions function (transaction TPM18).

**Integration**

Customizing

In Customizing for Treasury and Risk Management, carry out the activities by choosing Transaction Manager General Settings Accounting Derived Business Transactions .

For more information, see also: Assigning Update Types for Derived Business Transactions.

Application

The application menus for the various areas contain the following functions, which you access by choosing Accounting Derived Business Transactions :

Update Derived Business Transactions [transaction TPM27].

You only need to use this function if you have specified that the derived business transactions should be generated offline in the IMG activity Control of Processing of Derived Business Transactions. In this case, the system does not generate the derived business transactions for the valuation areas automatically when you create, change or post an operative business transaction.

**Note:**

If you have chosen offline processing, the position components (such as the book values) are not always up-to-date.

If you have a large amount of data, it can be useful to opt for offline processing and schedule the update run for derived business transactions [RTPM_TRL_DERIVE_TRANSACTIONS] as a batch job, for example, every evening.

If you have chosen to have the derived business transactions generated online in the Customizing activity Control of Processing of Derived Business Transactions, the system recalculates the derived business

transactions every time you process an operative business transaction, which means that they are always up-to-date.

Post and Fix Derived Business Transactions [transaction TPM18]

This function changes the status of derived business transaction flows from planned to fixed. At the same time, the system posts the flows that are relevant for posting (= the flows relating to update types that have account determination settings).

###### Update Derived Business Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Update Derived Business Transactions | L5 | trm07 p.132 | loio `8911e45200160575e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8911e45200160575e10000000a44538d.html?locale=en-US)

**Use**

You use this function only if, in theControl of Processing of Derived Business Transactions Customizing activity, you specified that derived business transactions for positions are created offline. In such case, the system does not create any derived business transactions specific to valuation areas when operational business transactions are performed.

**Note:**

If you have opted for offline processing, the position components (such as the book values) are not always up-to-date.

If your data volume is large, it can be useful to opt for offline processing and schedule the update run for derived business transactions [RTPM_TRL_DERIVE_TRANSACTIONS] as a batch job, for example, every evening.

For more inforamtion, see also: Derived Business Transactions.

**Activities**

- 1. In the application menus for the areas Money Market, Foreign Exchange, Securities, Derivatives, and Loans, choose the following path: Accounting Derived Business Transactions Update (transaction TPM27).
- 2. If you only want to run the update for certain accounting codes and valuation areas, specify these in the selection screen.
- 3. You can select the financial transactions for which the derived business transactions are to be updated according to the following criteria:


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

- 4. Posting Control area

Ignore Update Period Rule indicator

Reason for Reversal

If you entered a TRM reversal reason when you reversed the financial transaction, you do not need to enter one here.

Posting Date (If intended posting/reversal date is before)

FI Posting Period

Enter a date here if you do not want the current date to be applied as the document date.

Document Date

Test Run indicator

You can perform a test run first. In this case, the system outputs the accrual/deferral list and simulates the posting.

- 5. Control Parameters area

Here you can use the Log Display indicator.

- 6. You can first simulate the update of the derived business transactions by selecting the Test Run indicator. If you do not set this indicator, the system generates the derived business transactions according to your Customizing settings.
- 7. Multitasking Settings area

This area appears on the screen when you have set the Allow User to Control Parallelization Parameters in GUI indicator for the application in Customizing for Parallel Processing under Transaction Manager General Settings Parallel Processing Control .

If you have activated parallel processing for the function in Customizing, the Use Multitasking is set. If you want to execute the function without parallel processing in spite of the setting made to the contrary in Customizing, deselect the Use Multitasking indicator.

If you have deactivated parallel processing in Customizing, the indicator is not set. If you want to execute the function with parallel processing in spite of the setting made to the contrary in Customizing, set the Use Multitasking indicator.

In the following fields, you see the parallelization parameters defined in Customizing: Server Name, Logon/Server Group, Max. No. of Tasks, and Package Size. In the function Generate Derived Flows (transaction TPM27), only the package size is displayed.

You can change the parallelization parameters, provided that you observe the following restriction:

The maximum number of tasks defined in Customizing is an upper limit. You can only enter a lower number of tasks.

- 8. Execute the function.

###### Post Derived Business Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Post Derived Business Transactions | L5 | trm07 p.134 | loio `5719c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5719c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

This function changes the status of derived business transaction flows from Scheduled and To Be Fixed to Fixed. At the same time, the system posts the flows that are relevant for posting (= the flows relating to update types that have account determination settings).

**Integration**

Derived Business Transactions

**Activities**

- 1. In the application menus for the Money Market, Foreign Exchange, Securities, Derivatives and Loans areas, choose Accounting Derived Business Transactions Post and Fix .
- 2. Selection


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

- 3. Execute the report.


**Note:**

**Output**

The system generates a posting log.

###### Assign Update Types for Derived Business Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions | L5 | trm07 p.137 | loio `9e0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9e0bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

In this IMG activity, you assign the required update types for derived business transactions . You make the assignment for each position management procedure. In Customizing for Treasury and Risk Management , choose Transaction Manager General

Settings Accounting Derived Business Transactions Update Types Assign Update Types for Derived Business Transactions.

**Note:**

The selected position management procedure determines which update types are required.

It is possible that a tab is empty or only needs a few fields with entries.

Example: For a position management procedure where amortization is not planned, you do not have to fill the Amortizations tab.

**Prerequisites**

You have created position management procedures in Customizing for Treasury and Risk Management by choosing Transaction Manager General Settings Accounting Settings for Position Management Define Position Management Procedure .

You have selected and assigned the Derived Business Transactions usage type in Customizing for Treasury and Risk Management by choosing Transaction Manager General Settings Accounting Derived Business Transactions

Update Types Define Update Types and Assign Usages .

**Procedure**

You assign the update types on the following tab pages:

Inflows

Price/Rate Gains or Losses

Amortizations

The system executes amortization for the entire position, regarding all business transactions that affect the position. For more information, see Amortization and Swap/Margin Accrual/Deferral .

Transfer Postings

Position Outflows

In the case of position outflows that are not transfer postings, the system proportionally clears the position components (such as purchase value, security valuation, amortization). You then define corresponding update types for these clearing flows (translation flows). For more information, see Position Outflows .

Reconciliation Flows

If you change the local currency, issue currency, or contract currency, the system uses reconciliation flows so that the position is correctly valuated on a key date.

Examples:

After you have changed the position currency and valuation currency, the amounts should match.

If a position is zero, the position component values must also be zero.

Currency Swap

This tab page only applies to issue currency changeovers for securities or contract currency changeovers for loans.

For each position component, you define update types for flows so that the system posts the entire position value in the new currency and clears the position value in the old currency. The system generates two flows for all components, except for clearing components and foreign exchange valuation components. These flows do not change the position. They are only used for posting to the general ledger To determine the position amounts in the old currency, the system uses the function module TPM_GET_CURRENCY_SWAP_AMOUNTS (backup table BCKTRLT_FLOW).

If the position valuation does not affect profit and loss, but involves a write-up in position valuation and a write-down in valuation currency (or vice versa), the system generates additional adjustment flows for the posting and reversal (posting to a prior period). For this reason, the transfer postings tab page provides the update types in fields 81, 82, 87, and 88. For more information, see Transfer Postings .

Interest

On this tab page, you define update types for the derived business transactions that the system generated from interest flows.

Netting

Instead of posting the accrued interest relating to a bond purchase directly to the profit and loss account, the system initially posts the interest to a netting account . The netting account balance is cleared completely to the profit and loss account when the next interest payment is made, or cleared proportionally in the case of a previously sold bond. In the case of an interest payment, you can define an update type relevant for posting so that the system can clear the accrued interest for this flow. To do this, you need to select the option Netting Accrued Interest in the Derived Business Transactions for

Interest field for the selected position in the position management procedure. In Customizing for Treasury and Risk Management , choose Transaction Manager General Settings Accounting Settings for Position Management

Define Position Management Procedure.

This function is only available for interest payments at the end of the period. In other words, the system only takes into account accrued interest that has been paid. Ignore the field Accrued Interest Received.

**Note:**

The update types used for price/rate gains or losses and amortizations are relevant for posting. You also make account determination settings for the update types in Customizing for the Transaction Manager by choosing General Settings Accounting Link to Other Accounting Components Define Account Determination .

We provide you with predefined position management procedures and update types already assigned to derived business transactions.

Valuation

Intragroup

Classification

Value Adjustment .

Hedging-Related Transfer Postings

###### Inflows

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions > Inflows | L6 | trm07 p.139 | loio `ac0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ac0cda531198434de10000000a174cb4.html?locale=en-US)

On this tab, you assign the update types for flows that are generated with an inflow (a security purchase, for example) for a given position management procedure.

**Deferred Premium/Discount**

You make this assignment only if the gross procedure has been selected in the position management procedure. The net and gross procedures distinguish the amortization procedures.

With the net procedure, the amortization amount is written up to or written down from the position and displayed as a gain or loss in the profit and loss statement.

With the gross procedure, the total amortization amount for a purchase is posted directly as an accrual/deferral and then cleared over time in the amortization process.

Deferred premium/discount items are managed for the following position management categories: Securities/Loans/Money Market (Without Index-Linked Bonds). To generate deferred premium/discount items, the gross procedure must be specified in the amortization procedure.

For more information, see Amortization.

**Separate Balance Sheet Accounts: Derivatives**

You can manage derivative transactions (swaps, foreign exchange transactions) in different balance sheet accounts and define a settlement payment affecting the position as an additional flow when the transaction is closed or terminated. In this case, the system creates the settlement payment as a business transaction in the category Charges/Tax. The system credits the assets account and debits the clearing account for the settlement payment to be made. If a settlement payment is to be received, the system credits the clearing account and debits the liabilities account. You may have to transfer the settlement payment,

depending on the previous transaction balance. To avoid extending the balance sheet account, the system generates an adjustment flow for the corresponding amount and credits the liability account and debits the assets account.

To ensure the system can generate this flow, you must select the option Manage Assets and Liabilities Accounts in the Liabilities/Assets field in the position management procedure.

Example

You intend to amortize a bond according to the gross procedure. You purchase a bond below par that is included in the bond position. The system automatically generates a purchase flow using the difference amount (to be amortized) between the acquisition value and the repayment value. The update types entered in field 5 (Deferral/Clearing Items: Positive Amounts) on the Inflows tab are assigned to the automatically generated flow. You can therefore use this flow to post to the Deferral/Clearing Items account.

###### Realized Gains/Losses

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions > Realized Gains/Losses | L6 | trm07 p.140 | loio `af0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/af0cda531198434de10000000a174cb4.html?locale=en-US)

Price/rate gains or losses result from position outflows that are not transfer postings. These may include the following:

Sales or redemptions

Exercising forward exchange transactions or OTC options

Expiration of OTC options

**Securities, Foreign Exchange**

Gains or losses on the security and foreign exchange produce the same price/rate gain or loss, regardless of the sequence in which they are calculated. The system derives the sequence from the valuation procedure determined in the position management procedure. If you have not specified a valuation procedure, the system first calculates the gains/losses in security price and then in the exchange rate.

**Foreign Exchange Transactions**

You make your settings for foreign exchange transactions in the valuation procedure for both standard transactions and cross transactions. In the case of cross transactions, the system displays the gain or loss associated with the purchase currency and sale currency separately. In the case of standard transactions, however, the gain and loss are not separated.

###### Transfer Postings

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions > Transfer Postings | L6 | trm07 p.140 | loio `a40bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a40bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The system uses these update types for internal transfer postings, such as securities account transfer postings and OTC options. The update types are used to post individual position components from the old position to the new position.

In the case of transfer postings, the system generates a clearing (outgoing) flow and a posting (incoming) flow for each position component.

**Prerequisites**

You have defined update types for each position component used in the Define Update Types and Assign Usages configuration step under Manage Your SolutionConfigure Your SolutionFinanceTreasury and Risk ManagementSettings for Update Types.

**Key Features**

You must specify a transfer category in the position management procedure. If, for a transfer posting, the target position components don’t match the source position components, the transfer category determines which information the system provides for a position transfer (for example, a valuation class transfer or securities account transfer). The components vary if different position management procedures have been defined for the source and target positions.

The transfer posting category of the target position determines which transfer posting flows are generated.

Position component: Accruals/Deferrals Position

The system uses this component if you’ve specified the gross procedure for amortizations. In the case of a purchase, the system posts the amount to be amortized directly to an Accruals/Deferrals (a/d) account. This account is cleared on a continuous basis during amortization. If this position is transferred, the amount of the accrued or deferred items must be transferred from both the deferred premium/discount account and the accruals/deferrals account. You need to create two flows.

You have to define update types for accrual/deferral items (position) and accrual/deferral items (a/d) for the Accrual/Deferral Item component.

Clear to the Profit and Loss Account

In the position management procedure for the target position, the transfer category Post to Components Used Only is defined. The valuation procedure for the source position is set to Do Not Realize Gains/Losses (Security/Foreign Currency/Index). In the case of the target position, the system posts the valuation for a security, foreign currency, or index to P/L, and determines amortization.

**Note:**

Valuation components that don’t affect profit and loss are cleared from the source position. The system then posts the amounts to the corresponding P/L accounts. Update types are used when clearing to the profit and loss account. In this way, for example, the system can replace the Post Security Write-Up (Not Posted to P/L) (DBT_D046) update type with Clear Security Write-Up (Not Posted to P/L) (DBT_D069).

Valuation of Adjustment Flows Not Posted to Profit and Loss

Adjustment Flows in the Source Position of a Transfer Posting

If a valuation not posted to profit and loss has different +/- signs in position currency and valuation currency (write-up in position currency, write-down in valuation currency, for example), both amounts are shown in the same equity account. The amount in position currency determines whether the write-up account (OCI+) or depreciation account (OCI-) is used. If both amounts are cleared when a transfer is made, the system generates a flow for the valuation currency that affects the incorrect account. If a write-down occurs in the valuation currency, the system generates a flow that posts this amount from the depreciation account, even though the amount is on the debit side of the write-up account. In these cases, the system generates an adjustment flow that corrects the excess number of postings to the account.

Adjustment Flows in the Target Position of a Transfer Posting

In the case of a transfer posting in the target position, if both the depreciation account and the write-up account display a balance other than zero, the system generates adjustment flows. The system posts the amount on the account with the lower balance to the other account.

If the result in position currency in the target position is positive after the transfer posting, the following adjustment flows have to be generated for the components security valuation, foreign currency valuation, valuation of security costs, valuation of foreign currency costs (not affecting profit and loss):

If the existing position in position currency and valuation currency is negative, an adjustment flow is generated using this amount (positive).

If the existing position is negative in the position currency but positive in valuation currency, one adjustment flow is generated using the position currency amount (positive) and one using the valuation currency amount (negative).

In the case of the flow Post Negative Amount, an adjustment flow is generated using the same amount (Positive).

If the result in position currency in the target position is negative after the transfer posting, the following adjustment flows have to be generated:

If the existing position in position currency and valuation currency is positive, an adjustment flow is generated using this amount (negative).

If the existing position is positive in the position currency but negative in valuation currency, an adjustment flow is generated using the position currency amount (negative) or the valuation currency amount (positive).

In the case of the flow Post Positive Amount, an adjustment flow is generated using the same amount (negative).

Meaning of positive: From OCI+ to OCI-

Meaning of negative: From OCI- to OCI+

Adjustment flows do not affect the Treasury ledger (General Ledger Accounting).

Posting to Outgoing Positions (Exercise Rights)

Flows with these update types are generated if a right is exercised to transfer values to an outgoing position. For example, if you exercise a put option with the right to sell stocks. So that the values from the option (for example, the premium paid for the option) are considered in determining the price/rate gains or losses from the sale of the base value, the system posts the values of this right with these flows to the clearing component of the base value.

Separate Balance Sheet Accounts (Derivatives)

To use this function, for the posting flows in the position management procedure of the target position (underlying), you need to select the option Manage Assets and Liabilities Accounts in the Assets/Liabilities field. Separate balance sheet accounts can be managed for the underlying of an option, but only when the base value is a foreign exchange transaction. In this case, when exercising OTC currency options, the system transfers the option values as a base value for the foreign exchange transaction. Depending on whether the position value is positive or negative after the transfer posting, the system posts a positive option value to either the Assets account (DBT_D002) or Liabilities account (DBT_D202) of the foreign exchange transaction. A negative option value is likewise posted to the Liabilities account (DBT_D076) or Assets account (DBT_D276) of the foreign exchange transaction.

###### Position Outflows

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions > Position Outflows | L6 | trm07 p.142 | loio `a70bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a70bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

In the case of position outflows (such as sales or repayments) that are not transfer postings, the system proportionally clears the position components (such as purchase value, security valuation, amortization). You then define corresponding update types for these clearing flows (translation flows).

**Tip:**

If the position is reduced, the corresponding position component is also reduced proportionally and the loss is calculated. The system generates translation flows in this case.

**Prerequisites**

You have defined update types for each position component used in the Define Update Types and Assign Usages configuration step under Manage Your Solution Configure Your Solution Finance Treasury and Risk Management Settings for Update Types .

**Features**

We distinguish between the following flow categories:

Proportional Write-Off in the Case of Position Outflows

A position is reduced by a business transaction. This does not affect the transfer, however. These translation flows are not usually relevant for posting.

Flows Relevant for Posting

From these flows relevant for posting, the following positions are affected:

Positions that are amortized according to the gross method or with the additional component Deferral Item for Purchase Value.

Positions that do not affect profit/loss

Positions for which accrued interest is initially posted to a netting account, instead of being posted directly to the profit and loss account, based on a requirement from Spanish customers.

Special Features

The Diff. in Forex Valuation and Deferred Premium/Discount fields relate to the requirements in accordance with US GAAP (position management using the gross procedure), namely that the foreign exchange result must always correspond to that of IAS (position management using the net procedure). This means that the procedure for posting amortization amounts (gross or net) must not affect the foreign exchange result.

Accrued interest

When handling accrued interest (when purchasing a security), the intention may be to initially post the interest to a netting account and the netting account is cleared only when the first interest payment occurs.

If the (part) sale of the affected position occurs before the first interest payment date, the (proportional) accrued interest must be written off.

See also: Netting Accrued Interest (Reset Procedure)

Valuations not affecting profit/loss

The standard procedure for handling the valuation of position outflows not affecting profit/loss is intended as follows:

Valuation of Adjustment Flows Not Posted to Profit and Loss

In the case of valuation amounts that are not posted to profit and loss but instead to separate accounts depending on whether they are positive or negative (OCI+/OCI-), only one of these accounts may display a balance other than zero.

If a valuation not posted to profit and loss has different +/- signs in position currency and valuation currency (write-up in position currency, write-down in valuation currency, for example), both amounts are shown in the same equity account.

The amount in position currency determines whether the write-up account (OCI+) or depreciation account (OCI-) is used. If both amounts are written off with a position outflow, a flow is created for the valuation currency that does not affect the correct account. If a write-down occurs in the valuation currency, the system generates a flow that posts this amount from the depreciation account, even though the amount is on the debit side of the write-up account. In these cases, the system generates an adjustment flow that corrects the excess number of postings to the account. See Transfer Postings .

**Note:**

Posting logic for the update types:

Positive amounts: Debit OCI+, credit OCI-

Positive amounts: Debit OCI+, credit OCI-

Separate Balance Sheet Accounts (Derivatives)

To use the functions for separate balance sheet accounts, you need to have selected the option Manage Assets and Liabilities Balance Sheet Account in the Liabilities/Assets field in the position management procedure.

You can manage derivatives (foreign exchange, swaps, FRAs) in separate balance sheet accounts. You use an assets account to manage derivatives with a positive market value, and a liabilities account to manage derivatives with a negative market value. This also applies to futures. However, the update types defined for futures are not relevant in this case.

Only one of these accounts may have a balance other than zero. You therefore need to have defined additional update types for the clearing flows relevant for posting so that the system can post a positive amount to the liabilities account and a negative amount to the assets account. For example, forward exchange transactions have clearing flows for purchase value, purchase currency valuation, sale currency valuation, swap accrual/deferral, swap valuation, and security valuation.

**Note:**

Posting logic for update types in separate balance sheet accounts (comparison):

|Positive Amounts:|Positive Amounts (Separate Balance Sheet Accounts):|
|---|---|
|Debit Assets account|Debit Liabilities account|


|Negative Amounts:|Negative Amounts (Separate Balance Sheet Accounts):|
|---|---|
|Credit Liabilities account|Credit Assets account|

###### Valuation (2 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions > Valuation | L6 | trm07 p.144 | loio `b20cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b20cda531198434de10000000a174cb4.html?locale=en-US)

On this tab, you assign the update types for valuation flows that are created when a position is changed.

**Valuation of Amortized Acquisition Value (in the case of position changes)**

You can valuate monetary info account positions in a foreign currency in such a way that currency translation differences are posted from changes of amortized costs affecting profit/loss via the profit and loss statement.

You enter other book value changes via equity affecting profit/loss.

Affected position management categories:

- 001 Securities/Loans/Money Market Without Index-Linked Bonds

- 002 Index-Linked Bonds


008 Securities/Loans with Installment Repayment (Without Index-Linked Bonds)

**Prerequisites for Creating Flows:**

You must assign a position management procedure in which the valuation step Foreign Currency Valuation is planned for the position.

In the foreign currency valuation procedure, the value Amortized Acquisition Value is assigned in the Component to Be Valuated field.

In the predefined content, none of the procedures has this setting.

**Note:**

In the position management procedure, a second foreign currency valuation step must be planned in which foreign currency valuation is performed on the book value.

###### Intragroup

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions > Intragroup | L6 | trm07 p.145 | loio `a00cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a00cda531198434de10000000a174cb4.html?locale=en-US)

**Background**

A company comprises different subsidiaries. Subsidiaries also trade securities. These types of financial transactions are called intragroup transactions ( IGT ). Financial transactions that are made with external business partners are known as external

transactions. Some accounting principles stipulate that the gains and losses from intragroup transactions are to be excluded from the consolidated financial statements.

The buying company posts the seller's gains and losses to the consolidation accounts for this. These are represented by the following position components:

Consolidated security gains

Consolidated security losses

Consolidated FX gains

Consolidated FX losses

Gains/losses are not included on the consolidated balance sheet in consolidation. The seller's gain and loss accounts are cleared via the seller's consolidation accounts.

Affected position management categories:

- 001 Securities/loans/money market without index-linked bonds
- 002 Index-linked bonds


008 Securities/Loans with Installment Repayment (without Index-Linked Bonds)

The process of creating derived business transactions is triggered using function Process Intragroup Transactions (TRIG_ IGT ).

See also:

Intragroup Trading

**Resetting book value purchase before classifying intragroup**

When a purchase is classified as an intragroup transaction ( IGT ), the original purchase value (+ costs) of the position paid to the seller is reset. These update types are used for clearing the position value, they are not relevant to posting.

Transferring book value purchase after intragroup classification

General flows

These update types are used to post the position components with the values on the buyer side with which this position is managed on the seller side at time of purchase (or were defined with the values in function Process Intragroup Transactions (transaction TRIG_ IGT )).

These flows are not relevant to posting.

Posting-relevant general flows

These update types are used to post realized profits and losses (that have arisen with the seller), as with the consolidated gains and losses already posted that have occurred from previous intragroup transactions.

These update types are relevant to posting.

|Profits:|Consolidated gains from securities/forex|to|Position|
|---|---|---|---|
|Losses:|Position|to|Consolidated losses from securities/forex|


Posting-relevant flows in the case of postings against consolidated profits and losses

These update types are used for flows that unrealized profits and losses that were realized through a purchase by the seller to post against the consolidation accounts.

|Unrealized gains:|Consolidated profits|to|Unrealized gains|
|---|---|---|---|
|Unrealized losses:|Unrealized losses|to|Consolidated losses|


For example, if an unrealized gain is posted to the account Consolidated Gains , but a realized loss was already posted to the account Consolidated Losses , or vice versa, adjustment flows are generated that clear the consolidation account with the smaller amount so that the total gain/loss is only posted to one consolidation account.

These update types are assigned with Adjustment Flows: Consolidated Gains.

|Positive adjustment amounts|Consolidated losses|to|Consolidated gains|
|---|---|---|---|
|Negative adjustment amounts|Consolidated gains|to|Consolidated losses|


**Note:**

These update types are only relevant if the seller has not flagged the indicator Clear valuations not affecting profit/loss against position in the position management procedure under Handling Valuations not affecting profit/loss.

Posting-relevant flows in the case of posting against position

These update types are relevant for postings that post unrealized gains/losses to consolidation accounts if the seller has flagged indicator Clear valuations affecting profit/loss against the position in the position management procedure under Handling valuations not affecting profit/loss in the case of position outflows. (See also Position Outflows )

|Unrealized gains|Position|to|Unrealized gains|
|---|---|---|---|


|Unrealized losses|Unrealized losses|to|Position|
|---|---|---|---|


The advantage of this is that no adjustment flows are necessary for the consolidation accounts, as only the total gain/loss is posted via the consolidation accounts.

###### P-Hedge Accounting: Classification

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions > P-Hedge Accounting: Classification | L6 | trm07 p.147 | loio `a90cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a90cda531198434de10000000a174cb4.html?locale=en-US)

You use this configuration step to assign the update types needed for classification. These update types are required for flows that are created when valuation results for a position within a hedging relationship are classified. The update types are used to determine the effective and ineffective part of these valuation results.

On the Classification tab, you assign the update types (for positive as well as for negative amounts) for the Classification, Reset Classification, Reclassification, and Reset Reclassification for the different position components.

The following position components are affected by classification:

1324 Effective / Hedging Reserve

- 1322 Effective / Cost of Hedging Reserve

- 1323 Ineffect. / Hedging Reserve TPL


1333 Ineffect. / Cost of Hdg. Res. TPL

1303 Ineffective

- 1343 P&L Eff. / Designated Components

- 1344 P&L Eff. / Non-Designated Comp.

- 1345 Amortization / Non-Designated Comp.


Affected position management categories:

005 FX Transactions

007 OTC Derivatives (posting to underlying)

**Related Information**

Hedge Accounting for Exposure Items Run Classification Hedge Accounting for Positions (P-HA) Classification

###### Value Adjustment

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions > Value Adjustment | L6 | trm07 p.147 | loio `a30cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a30cda531198434de10000000a174cb4.html?locale=en-US)

This tab is available to you if you activate business function TRM, Hedge and Exposure Management, SWIFT (FIN_TRM_LR_FI_AN_2).

This is where you assign the update types necessary to map Purchase-GAAP Accounting. ( See also:P-GAAP )

**Transfer postings between profits and losses**

If the position components Non-Realized Profits and Non-Realized Losses of a P-GAAP-relevant position change due to a valuation or a realization, it may be necessary to adjust the value adjustment distribution to the components Profits Value Adjustment and Losses Value Adjustment .

This distribution occurs in accordance with the rule set that was implemented in the class method CL_VAD_RULES_ VAL => TRANSFER_RULES.

**Linear Amortization**

You use the indicator Amortization: Value Adjustment in Customizing for the amortization procedure to define that the position components Profits Value Adjustment and Losses Value Adjustment are written down linear with time (for monetary items ).

**Proportional Write-Off in the case of Position Outflows**

The update types match the update types of the tab Position Outflow .

**Transfer posting between positions**

The update types match the update types of the tab Transfer Postings .

**Transfer book value after intragroup classification**

The update types match the update types of the tab Intragroup .

**Transfer posting between subpositions (Hedge Accounting for Positions)**

The update types match the update types of the tab Hedging-Related Transfer Postings .

###### P-Hedge Acounting: Transfers Between Subpositions

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Assign Update Types for Derived Business Transactions > P-Hedge Acounting: Transfers Between Subpositions | L6 | trm07 p.148 | loio `a60cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a60cda531198434de10000000a174cb4.html?locale=en-US)

These update types are required if a position in a hedging relationship of the Hedge Accounting of Exposure Items process is designated or dedesignated.

The concept of subpositions has been introduced to distinguish the hedged and non-hedged parts of a position in a hedging relationship. Subpositions containing the values of the position components of the subpositions are assigned to the position. The position components of the subpositions are cumulative, that is, the sum of all subpositions corresponds to the value of the position.

If a position is partially designated, the values of the position components are transferred proportionally from the lowest subposition that represents the stand-alone part through to the subposition of the hedged part (vice versa in the case of dedesignation).

On the P-Hedge Accounting: Transfer Between Subpositions tab, you need to enter update types for the following derived business transactions:

Hedge Accounting for Positions: Transfers Between Subpositions

These update types are required so that values of the position components are transferred between subpositions.

Adjustment Flows for Valuation Not Affecting P/L

See also: Adjustment Flows Not Affecting Profit/Loss Valuation section under Transfer Postings

Hedge Accounting for Positions

Transfer Hedge Adjustment to Valuation Components

| |Post Positive Amounts|Post Negative Amounts|
|---|---|---|
|Spot Valuation in Purchase Currency|(946)|(948)|
|Spot Valuation in Sale Currency|(950)|(952)|
|Security Valuation|(958)|(960)|


To distinguish between the hedged and non-hedged parts of a position in a hedging relationship, the concept of subpositions was introduced. Values are assigned to a subposition as part of a position. It gets the values of the position components of the subposition. The position components of the subpositions are cumulative, in other words, the total of all subpositions corresponds to the value of the position.

If a position is partially designated, the values of the position components are transferred proportionally from the lowest subposition that represents the stand-alone part through to the subposition of the hedged part (vice versa in the case of dedesignation).

Transfer Outgoing Positions

Not relevant.

###### Alternative Update Types for Position Outflows

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Derived Business Transactions > Alternative Update Types for Position Outflows | L5 | trm07 p.149 | loio `fbfab9cbb57941e1bcbfdfb2b458bd58` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fbfab9cbb57941e1bcbfdfb2b458bd58.html?locale=en-US)

Customizing activity

Replace the update types for derived business transactions with alternative update types, based on certain conditions. The position change category of the old update type is automatically assigned to the new update type. This enables you to configure a different posting specification for the alternative update types according to the specific condition.

You make these settings for a given position management procedure.

Alternative update types can be used, for example, to avoid P&L inflation. The P/L account is inflated when the system generates income-related derived business transactions that offset each other (such as a realized price loss and a positive OCI translation). By using alternative update types, you can group these flows and post them to the same P/L account.

**Conditions**

The following conditions are supported:

Conditions for position outflows of security positions:

The following conditions describe the possible results at the maturity of a security position

- 01 Total Realized Gains/Losses, Security >= 0

- 02 Total Realized Gains/Losses, Security < 0

- 03 Total Realized Gains/Losses, FX >= 0


- 04 Total Realized Gains/Losses, FX < 0


Explanations:

Total amount realized for security = Security price gain - Security price loss + Translation of security write-up (not posted to P/L) - Translation of security write-down (not posted to P/L) + [Translation of discount - Translation of premium] + Translation of loss allowance (negative amounts) - Translation of loss allowance (positive amounts)

Total amount realized for foreign currency = Exchange rate gain - Exchange rate loss + Translation of FX write-up (not posted to P/L) - Translation of FX write-down (not posted to P/L) + Translation of exchange rate gain for loss allowance Translation of exchange rate loss for loss allowance

Example of Using Conditions for Position Outflows of Security Positions

During key date valuation, write-ups and write-downs are generated for a position, but not posted to P/L. These write-ups and write-downs are cleared by "translations" when positions are sold.

Position 01/01/XX:

Nominal value: 200,000 EUR

Amortized acquisition value: 200,000 EUR

Security write-up (not affecting P/L): 20,000 EUR

Book value: 220,000 EUR

Position outflow 01/02/XX: 100,000 EUR nominal at a price of 105%

The following derived business transactions would be generated:

DBT_B003 (security price loss): 5,000 EUR [Posting: Realized price losses to balance sheet position]

DBT_E025 (Translation of security write-up (not posted to P/L): 10,000 EUR [Posting: OCI to Realized price gains]

In this case, the position outflow results in inflated P/L figures if the price losses and price gains are not posted to the same account. You can avoid this by defining the following alternative update type:

Position management procedure: 4711

Old update type: DBT_B003 (security price loss)

Condition: Total amount realized for security >= 0

New update type: DBT_BA03 (security price loss -> security price gain)

The position outflow would then generate the following flows, as opposed to those above:

DBT_BA03 (security price loss - alternative): 5,000 EUR [Posting: Realized price gains to balance sheet position]

DBT_E025 (Translation of security price valuation not posted to P/L): 10,000 EUR [Posting: OCI to realized price gains]

If the total realization amount (DBT_B001) is positive and exceeds the translation for the security write-down not posted to P/L (DBT_E026), these flows could be grouped by the following entry:

Position management procedure: 4711

Old update type: DBT_E026 (translation of security write-down not posted to P/L)

Condition: Total amount realized for security >= 0

New update type: DBT_EA26 (Translation of security write-down not posted to P/L -> Gain)

You also can make corresponding settings for the other conditions.

Conditions for Hedge Accounting for Positions

05 P-Hedge Accounting

This condition allows you to replace any hedge accounting update types by another update type.

07 P-Hedge Accounting: Hedge Adjustment

The result of the key date valuation of a designated FX transaction is transferred to component Hedge Adjustment and is posted differently than the key date valuation result of a freestanding FX transaction: Update types of key date valuation of freestanding FX transactions are replaced by update types of key date valuation of designated FX transactions.

Conditions for Hedge Accounting for Exposure Items process, which is part of the Hedge Management and Accounting of Net Open Exposures (FX Risk) process

05 P-Hedge Accounting

This condition allows you to replace any hedge accounting update types by another update type.

- 07 P-Hedge Accounting: Hedge Adjustment

The result of the key date valuation of a designated FX transaction is transferred to component Hedge Adjustment and is posted differently than the key date valuation result of a freestanding FX transaction: Update types of key date valuation of freestanding FX transactions are replaced by update types of key date valuation of designated FX transactions.

- 08 Reclassification After Balance Sheet Recognition

You can replace the update types of reclassification flows (DBT_K031 - DBT_K038) that are created after the balance sheet recognition date by alternative update types (DBT_KA31 - DBT_KA38).

Example:

For DBT_K031 the posting specification 29603 Hedging Reserve to Realized Gain is assigned.

For DBT_KA31 the posting specification 29601 Hedging Reserve to Other Operative Revenue is assigned.

25 P/L Offset of Reclassification After Balance Sheet Recognition

Condition 25 is always applied together with condition 08. This rule can be used for changes from gain to loss or loss to gain after an already appliedReclassification after Balance Sheet Recognition. The system decides if the flow, where the update type was replaced by the rule before, has to get another update type and/or needs to be split into two flows to clear an existing effective amount and post the delta amount to the respective account.

Example: If there is already a reclassified positive amount after the balance sheet recognition date recorded on the ESI position, and

if the amount in question is negative, the positive amount gets reduced by the negative amount (one posting only).

if the negative amount exceeds the positive amount, there is a split (two postings): The positive amount gets completely reduced (clearing flow) and for the delta amount a flow is created where the update type remains.

- 09 Immediate Reclassification at Dedesignation


If a dedesignation request is triggered after the balance sheet recognition date, the calculated amounts that were already reclassified at the balance sheet recognition date must be reset and posted to the P/L account relevant for premature

dedesignation.

Overview Reclassification Update Types and Alternative Reclassification Update Types relevant for Premature Dedesignation after Balance Sheet Recognition Date

|Old Udate Type|Description|New Update Type|Description|
|---|---|---|---|
|DBT_K031|Reclassification Effective / Hedging Reserve (positive)|DBT_KB31|Im. Dedesignation Recl. Hedging Reserve (positive)|
|DBT_K032|Reclassification Effective / Hedging Reserve (negative)|DBT_KB32|Im. Dedesignation Recl. Hedging Reserve (negative)|
|DBT_K033|Reclassification Effective / Cost of Hedg. Res. (positive)|DBT_KB33|Im. Dedesignation Recl. Cost of Hedg. Res. (positive)|
|DBT_K034|Reclassification Effective / Cost of Hedg. Res. (negative)|DBT_KB34|Im. Dedesignation Recl. Cost of Hedg. Res. (negative)|
|DBT_K035|Reset Reclassification Eff. / Hedging Reserve (positive)|DBT_KB35|Im. Dedesignation Recl. Reset Hedging Reserve (positive)|
|DBT_K036|Reset Reclassification Eff. / Hedging Reserve (negative)|DBT_KB36|Im. Dedesignation Recl. Reset Hedging Reserve (negative)|
|DBT_K037|Reset Reclassification Eff. / Cost of Hedg. Res. (positive)|DBT_KB37|Im. Dedesignation Recl. Reset Cost of Hedg. Res. (positive)|
|DBT_K038|Reset Reclassification Eff. / Cost of Hedg. Res. (negative)|DBT_KB38|Im. Dedesignation Recl. Reset Cost of Hedg. Res. (negative)|


- 10 Reclassification of Dedesignated Portion at B/S Recognition


Update types of reclassification flows that are created due to a dedesignation triggered by a dedesignation request before the balance sheet recognition date are replaced and posted at balance sheet recognition date for hedging relationships if in the hedging area on Hedge Accounting I tab in the Consider Balance Sheet Recognition Date field the Immediate Reclassification at Balance Sheet Recognition Date value is set and you have chosen Planned Reclassification in the Reclassification Handling field in the dedesignation request.

Conditions relevant at the maturity of an FX transaction (product category 600) with a position management procedure that contains a valuation step 4 Security Valuation

During the maturity of an FX forward transaction, it can happen that translation postings of unrealized gains/losses lead to extensions of the P&L. Therefore, you can use alternative update types at maturity of FX forward transactions (with valuation step 'Security' in position management procedure) to avoid P/L extensions in case of a position outflow. The following conditions allow you to post previously unrealized FX result correctly at maturity.

- 11 Realized Gain >= Valuation Gain


The translation update type of valuation gain is posted against realized FX gain.

For this condition, you must make the following entry:

|Position Management Procedure|Old Update Type|New Update Type|
|---|---|---|
|An entry for each position management procedure used for FX transactions that contain a valuation step 4 Security Valuation|DBT_E003 Translation write-up (Price) (Asset) Not posting relevant|DBT_EAG3 with posting specification 12410 Realized Exchange Rate Gains to Position|


- 12 Realized Gain < Valuation Gain

The translation update type of valuation gain is posted against realized FX loss and the update type of realized FX gain is posted to realized FX loss.

For this condition, you must make the following entries:

- 13 Realized Gain >= Valuation Loss

The translation update type of valuation loss is posted against realized FX gain.

For this condition, you must make the following entry:

- 14 Realized Gain < Valuation Loss


|Position Management Procedure|Old Update Type|New Update Type|
|---|---|---|
|An entry for each position management procedure used for FX transactions that contain a valuation step 4 Security Valuation|DBT_B013 Forward Exchange Transaction Gain (Standard) with posting specification 12300 Position to Realized Exchange Rate Gains|DBT_BL13 FX realized result: Post realized gain to loss with posting specification 12310 Position to Realized Exchange Rate Losses|
|An entry for each position management procedure used for FX transactions that contain a valuation step 4 Security Valuation|DBT_E003 Translation write-up (Price) (Asset) Not posting relevant|DBT_EAL3 Security Valuation result: Post valuation gain to real. loss with posting specification 12400 Realized Exchange Rate Losses to Position|


|Position Management Procedure|Old Update Type|New Update Type|
|---|---|---|
|An entry for each position management procedure used for FX transactions that contain a valuation step 4 Security Valuation|DBT_E004 Translation write-down (Price) Not posting relevant|DBT_ELG4 Security Valuation result: Post valuation loss to real. gain with posting specification 12300 Position to Realized Exchange Rate Gains|


The translation update type of valuation loss is posted against realized FX gain.

For this condition, you must make the following entry:

|Position Management Procedure|Old Update Type|New Update Type|
|---|---|---|
|An entry for each position management procedure used for FX transactions that|DBT_E004 Translation write-down (Price)|DBT_ELG4 Security Valuation result: Post valuation loss to real. gain|


|Position Management Procedure|Old Update Type|New Update Type|
|---|---|---|
|contain a valuation step 4 Security Valuation|Not posting relevant|with posting specification 12300 Position to Realized Exchange Rate Gains|


- 15 Realized Loss >= Valuation Gain

The translation update type of valuation gain is posted against realized FX loss.

For this condition, you must make the following entry:

- 16 Realized Loss < Valuation Gain

The translation update type of valuation gain is posted against realized FX loss.

For this condition, you must make the following entry:

- 17 Realized Loss >= Valuation Loss

The translation update type of valuation loss is posted against realized FX loss.

For this condition, you must make the following entry:

- 18 Realized Loss < Valuation Loss


|Position Management Procedure|Old Update Type|New Update Type|
|---|---|---|
|An entry for each position management procedure used for FX transactions that contain a valuation step 4 Security Valuation|DBT_E003 Translation write-up (Price) (Asset) Not posting relevant|DBT_EAL3 Security Valuation result: Post valuation gain to real. loss with posting specification 12400 Realized Exchange Rate Losses to Position|


|Position Management Procedure|Old Update Type|New Update Type|
|---|---|---|
|An entry for each position management procedure used for FX transactions that contain a valuation step 4 Security Valuation|DBT_E003 Translation write-up (Price) (Asset) Not posting relevant|DBT_EAL3 Security Valuation result: Post valuation gain to real. loss with posting specification 12400 Realized Exchange Rate Losses to Position|


|Position Management Procedure|Old Update Type|New Update Type|
|---|---|---|
|An entry for each position management procedure used for FX transactions that contain a valuation step 4 Security Valuation|DBT_E004 Translation write-down (Price) Not posting relevant|DBT_ELL4 Security Valuation result: Post valuation loss to real. loss with posting specification 12310 Position to Realized Exchange Rate Losses|


The translation update type of valuation loss is posted against realized FX gain and the update type of realized FX loss is posted to realized FX gain.

For this condition, you must make the following entries:

|Position Management Procedure|Old Update Type|New Update Type|
|---|---|---|
|An entry for each position management procedure used for FX transactions that contain a valuation step 4 Security Valuation|DBT_B014 Forward Exchange Transaction Loss (Standard) with posting specification 12400 Realized Exchange Rate Losses to Position|DBT_BG14 FX realized result: Post realized loss to gain with posting specification 12410 Realized Exchange Rate Gains to Position|
|An entry for each position management procedure used for FX transactions that contain a valuation step 4 Security Valuation|DBT_E004 Translation write-down (Price) Not posting relevant|DBT_ELG4 Security Valuation result: Post valuation loss to real. gain with posting specification 12300 Position to Realized Exchange Rate Gains|

