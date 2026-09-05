# Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting - SAP TRM Knowledge Base (branch split)

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

##### Terms in Position Management and Treasury Accounting

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting | L4 | trm07 p.5 | loio `0c0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0c0dda531198434de10000000a174cb4.html?locale=en-US)

Here you get more details about terms used in Position Management and Treasury Accounting.

|Term|Definition|
|---|---|
|Valuation Area|In Treasury and Risk Management, you can set up different valuation areas so as to value your financial transactions in accordance with different accounting regulations. A valuation area represents exact one accounting principle (1:1), and is used to manage and valuate the Treasury positions according to this accounting principle. For more information, see also Parallel Accounting in Treasury and Risk Management. |


|Term|Definition|
|---|---|
|Treasury Position|The treasury position (or subledger position) is the most detailed level into which you can break down the balance sheet accounts of the Treasury and Risk Management subledger (TRL). The key date valuations are carried out at position level and the position components are managed at position level. This means that a position is created for each valuation area for a financial transaction. For example, if you have two valuation areas (one for your local accounting principle and one for IFRS), the system creates two positions for each financial transaction. The differentiation terms of the different product groups delimit the positions. You must assign an account assignment reference to each position. You can use this account assignment reference to control how the subledger positions are posted in the general ledger.|
|Differentiation Term|A position represents the smallest unit in the treasury subledger. The position is the basis for system valuations and for generating derived flows. Differentiation terms are used to determine how the positions are created. Some differentiation terms are defined by the system for each product group, and others can be selected additionally. For more information, see also Differentiation Terms. |
|Position Component|The values of a position are split into position components. We distinguish between original and derived position components. Derived position components are based on original position components and are in some cases determined by adding or subtracting original position components. For more information, see also Position Components. |
|Position Indicator|The position indicator of a subledger position contains the Position Management Procedure and the Account Assignment Reference, along with the balance sheet indicator. In the securities account position indicator you specify information, such as the custody type, at the level of the company code, security ID number, and securities account. The system can generate the position indicator automatically. As long as there are no posted flows for a position, you can change the assignment of the position management procedure and account assignment reference in the position indicator using the app Manage Position Indicator. However, as soon as there is a posted flow, it is no longer possible to change the position management procedure or the account assignment reference there. To change the position management procedure in that case, you must execute a valuation class transfer. To change the account assignment reference, you must execute an account assignment reference transfer.|


|Term|Definition|
|---|---|
| |To create, change, or display the position indicator, you need authorization for authorization object FW_BES_BUK of object class IS.|
|Position Management Procedure|The position management procedure determines which steps are used in the valuation or in generating the derived business transactions and also the sequence in which the steps are performed. The Transfer Category defines how, in the case of a position transfer the position components in the target position are to be filled where the target position components do not match the source position components.|
|Transfer Category|In a position transfer (for example, a valuation class transfer or securities account transfer), the transfer category controls how the position components are filled when the target position components do not match the source position components. This can be the case if the source and target positions have different position management procedures. For more information, see also Transfer Category. **Example:** When a bond position is being transferred, it may be the case that the 'old' position management procedure calls for amortization whereas the 'new' position management procedure does not.|
|General Valuation Class and Special Valuation Class|General valuation classes are used to classify transactions by asset type, and apply across all valuation areas. By contrast, special valuation classes are defined at valuation area level. The general valuation classes are assigned to the special valuation classes for the valuation areas. For each transaction, the system can therefore determine the special valuation classes for the different valuation areas on the basis of the general valuation class. You assign the general valuation class to a position when you create the financial transaction.|
|Account Assignment Reference|Account assignment references (AAR) are assigned to each treasury position in the position indicator. You use the account assignment reference to determine the G/L account in which the position is managed. You make the assignments of the G/L accounts dependent on the account assignment reference for the relevant account symbols (position and interest revenue) for posting the positions, dividend payments, interest payments, accruals and deferrals, incoming payments, and repayments in the general ledger. For more information, see also Account Assignment References. |
|Operational Business Transaction|Operational business transactions are business transactions that are not derived business transactions. Operational business transactions can trigger derived business transactions that are dependent on the valuation area. |


|Term|Definition|
|---|---|
| |The system differentiates between operational business transactions that are independent of the valuation area, and operational business transactions that are dependent on the valuation area. Operational business transactions independent of the valuation area General Functions Local Currency Changeover Securities Purchase and sale of securities Repayments Exercise of security rights Corporate actions (also includes the issue currency changeover) Securities account transfers Generation of debit positions (automatic and manual) Manual postings Interest accruals/deferrals Loans Disbursements Scheduled repayments (full repayment at the end of the term / installment repayment / annuity repayment) Unscheduled repayments Capitalized interest Capital transfers (inflow/outflow) Purchase/sale of borrower's note loans Changeover to the euro / reset of currency changeover Money Market, Foreign Exchange, Derivatives Payments/borrowings (liabilities) Payments / investments (assets) Repayments to be made (liabilities) Repayments to be received (assets) Capitalized interest Interest Open OTC transactions|


|Term|Definition|
|---|---|
| |Close OTC transactions OTC transaction purchases OTC transaction sales Exercise/expiration/termination of OTC transactions Open listed derivatives Close listed derivatives Close margin for listed derivatives Key date margin for listed derivatives Exercise/expiration/termination of OTC transactions Operational business transactions dependent on the valuation area Key date valuation Account assignment reference transfer Valuation class transfer|
|Derived Business Transactions|Derived business transactions supplement Operative Business Transactions. They are generated on the basis of the operative business transactions and are dependent on the valuation area. This means that the derived business transactions can be differ according to valuation area even if they stem from the same operative business transactions. For more information, see also Derived Business Transactions. |

###### Valuation Area

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Valuation Area | L5 | trm07 p.5 | loio `9e0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9e0eda531198434de10000000a174cb4.html?locale=en-US)

A valuation area represents exactly one accounting principle (1:1) and is used to manage and valuate the treasury positions according to this accounting principle.

In Treasury and Risk Management, you can set up different valuation areas so as to value your financial transactions in accordance with different accounting regulations.

**Example:**

- Valuation area 001 HGB (German Commercial Code)

- Valuation area 002 US GAAP

###### Account Assignment Reference

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Account Assignment Reference | L5 | trm07 p.9 | loio `1208da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1208da531198434de10000000a174cb4.html?locale=en-US)

Definition

Account assignment references are required for each Treasury Position.

You use the account assignment reference to determine the G/L account in which the position is to be managed.

You make the assignments of the G/L accounts in FI dependent on the account assignment reference for the relevant account symbols (position and interest revenue) for posting the positions, dividend payments, interest payments, accruals and deferrals, incoming payments, and repayments in the general ledger.

You create the account assignment references independent of the valuation areas. You can have the account assignment references assigned to positions based on the valuation area and/or you control the account determination based on valuation area and account assignment reference.

**Related Information**

Account Assignment References Assign Account Assignment Reference Transfer Account Assignment Reference

###### Accounting Code

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Accounting Code | L5 | trm07 p.10 | loio `a00ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a00ada531198434de10000000a174cb4.html?locale=en-US)

Definition

An accounting code in the parallel valuation areas corresponds to an FI company code. You create the accounting codes and assign them to company codes in Customizing under Transaction Manager General Settings Accounting Parallel Valuation Areas Organization Define Accounting Codes .

###### Operational Business Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Operational Business Transactions | L5 | trm07 p.10 | loio `b60eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b60eda531198434de10000000a174cb4.html?locale=en-US)

Operational business transactions are business transactions that are not derived business transactions. Operational business transactions can trigger derived business transactions that are dependent on the valuation area.

[figure TRM07-F010 - The system differentiates between operational business transactions that are independent of the valuation area, and operational business transactions that are dependent on the valuation area.]

The system differentiates between operational business transactions that are independent of the valuation area, and operational business transactions that are dependent on the valuation area.

Operational business transactions independent of the valuation area

General Functions

Local Currency Changeover

Securities

Purchase and sale of securities

Repayments

Exercise of security rights

Corporate actions (also includes the issue currency changeover)

Securities account transfers

Generation of debit positions (automatic and manual)

Manual postings

Interest accruals/deferrals

**Loans**

Disbursements

Scheduled repayments (full repayment at the end of the term / installment repayment / annuity repayment)

Unscheduled repayments

Capitalized interest

Capital transfers (inflow/outflow)

Purchase/sale of borrower's note loans

Changeover to the euro / reset of currency changeover

Money Market, Foreign Exchange, Derivatives

Payments/borrowings (liabilities)

Payments / investments (assets)

Repayments to be made (liabilities)

Repayments to be received (assets)

Capitalized interest

Interest

Open OTC transactions

Close OTC transactions

OTC transaction purchases

OTC transaction sales

Exercise/expiration/termination of OTC transactions

Open listed derivatives

Close listed derivatives

Close margin for listed derivatives

Key date margin for listed derivatives

Exercise/expiration/termination of OTC transactions

Operational business transactions dependent on the valuation area

Key date valuation

Account assignment reference transfer

Valuation class transfer

###### Derived Business Transactions (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Derived Business Transactions | L5 | trm07 p.12 | loio `ec28e76eed924159899a6284bab1c6a6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ec28e76eed924159899a6284bab1c6a6.html?locale=en-US)

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

If you have chosen to have the derived business transactions generated online in the Customizing activity Control of Processing of Derived Business Transactions, the system recalculates the derived business transactions every time you process an operative business transaction, which means that they are always up-to-date.

Post and Fix Derived Business Transactions [transaction TPM18]

This function changes the status of derived business transaction flows from planned to fixed. At the same time, the system posts the flows that are relevant for posting (= the flows relating to update types that have account determination settings).

###### Premium/Discount

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Premium/Discount | L5 | trm07 p.14 | loio `a40eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a40eda531198434de10000000a174cb4.html?locale=en-US)

The premium is the difference between the acquisition value and the repayment amount if the acquisition value is greater than the repayment amount.

The discount is the difference between the acquisition value and the repayment amount if the acquisition value is less than the repayment amount.

###### General Valuation Class

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > General Valuation Class | L5 | trm07 p.14 | loio `cd0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cd0dda531198434de10000000a174cb4.html?locale=en-US)

Definition

General valuation classes are used to classify transactions by asset type, and apply across all valuation areas.

By contrast, special valuation classes are defined at valuation area level. The general valuation classes are assigned to the special valuation classes for the valuation areas. For each transaction, the system can therefore determine the special valuation classes for the different valuation areas on the basis of the general valuation class.

You assign the general valuation class to a position when you create the financial transaction.

###### Special Valuation Class

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Special Valuation Class | L5 | trm07 p.14 | loio `aac2c7531dc61d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/aac2c7531dc61d4be10000000a174cb4.html?locale=en-US)

Definition

The special valuation classes are used to classify the financial investments in a specific valuation area by asset type.

Examples of valuation classes are current assets and fixed assets for a German HGB valuation area, or trading, available for sale (AfS), and held to maturity (HTM) for an IAS valuation area.

The (special) valuation class is a differentiation term in the parallel valuation areas. Each subledger position is assigned to a (special) valuation class.

**Note:**

This characteristic is only displayed for the parallel valuation areas.

###### Securities Account Group

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Securities Account Group | L5 | trm07 p.15 | loio `a3bc07ceb9e34cb4ae5802c0bf8c97e5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a3bc07ceb9e34cb4ae5802c0bf8c97e5.html?locale=en-US)

You can assign securities accounts to securities account groups.

The securities account group is relevant in the parallel valuation areas only if you've defined the securities account group as a differentiation term for the respective valuation area. You can define securities account groups in the Define Securities Account Groups Customizing activity.

###### Differentiation Terms

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Differentiation Terms | L5 | trm07 p.15 | loio `180dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/180dda531198434de10000000a174cb4.html?locale=en-US)

**Definition**

A position represents the smallest unit in the treasury subledger. The position is the basis for valuations and for generating derived flows. The differentiation terms are used to determine how the positions are created for financial instruments. Some differentiation terms are defined by the system for each product group, whereas you can select others to be applied additionally. If you want to use additional differentiation terms for your positions, you must define a differentiation in your configuration environment and assign it to the valuation areas and company codes for which they are relevant.

To ensure your treasury positions are created correctly, you must enter the values for the additional account assignments (if they are used as differentiation terms for your treasury positions) when you create the financial transaction, for example on the Administration tab.

If you use the securities account group or portfolio as a differentiation term, you must assign the securities accounts to a securities account group/portfolio in the master data of the securities account.

The differentiation terms are transferred to the journal entry when flows are posted to Financial Accounting. Since the WBS element is only relevant for postings to P&L accounts, this value is not transferred for postings to balance sheet accounts.

Overview of Available Differentiation Terms

|Kind of Differentiation Terms|Differentiation Terms Available for OTC Transactions (MM, FX, OTC Derivatives, Trade Finance)|Differentiation Terms Available for Securities|Differentiation Terms Available for Listed Derivatives/Futures|Differentiation Terms Available for Loans|
|---|---|---|---|---|


|Kind of Differentiation Terms|Differentiation Terms Available for OTC Transactions (MM, FX, OTC Derivatives, Trade Finance)|Differentiation Terms Available for Securities|Differentiation Terms Available for Listed Derivatives/Futures|Differentiation Terms Available for Loans|
|---|---|---|---|---|
|System-defined differentiation terms **Note:** These differentiation terms are always relevant and can't be changed.|Valuation Area Valuation Class For more information, see also General and Special Valuation Classes. Accounting Code Transaction Number|Valuation Area Special Valuation Class Accounting Code Security Class ID Number|Valuation Area Special Valuation Class Accounting Code ID Number Futures Account|Valuation Area Special Valuation Class Accounting Code Loan Contract|
|Additional differentiation terms **Note:** You can define differentiations to assign the additional differentiation terms to treasury positions.|WBS Element Cost Center Profit Center Functional Area Up to five custom differentiation terms are available if you defined them in the Define Custom Differentiation Terms Customizing activity. If Public Sector Management is used, the following two additional differentiation terms are also available: Fund Grant|Securities Account Securities Account Group Portfolio WBS Element Cost Center Profit Center Functional Area Lot (single position management) You can also handle security positions on single position level by making an entry on the Single Position Management tab. In this case, every security purchase is handled as a position. Up to five custom differentiation terms are available if you defined them in|Lot (single position management) For futures, you can make an entry on the Single Position Management tab. In this case, every future is handled as a position. Up to five custom differentiation terms are available if you defined them in the Define Custom Differentiation Terms Customizing activity.| |


|Kind of Differentiation Terms|Differentiation Terms Available for OTC Transactions (MM, FX, OTC Derivatives, Trade Finance)|Differentiation Terms Available for Securities|Differentiation Terms Available for Listed Derivatives/Futures|Differentiation Terms Available for Loans|
|---|---|---|---|---|
| | |the Define Custom Differentiation Terms Customizing activity. If Public Sector Management is used, the following two additional differentiation terms are also available: Fund Grant| | |


**Configuration**

You must define the differentiation and its assignment for treasury positions in the Define and Assign Differentiations Customizing activity before you post your first position in the relevant company codes and valuation areas.

The selected differentiation terms are relevant for all positions of the product groups supporting the specific differentiation terms. For example, if you add the differentiation term "securities account" to a differentiation, this differentiation term is only relevant for securities positions.

If you do not define and assign a differentiation, the treasury positions are delimited by the system-defined differentiation terms of the product groups.

If you want to use the securities account group as a differentiation term, you must define securities account groups in the Define Securities Account Groups Customizing activity. In the master data of the securities account, you must assign the securities accounts to a securities account group.

If you want to use the portfolio as a differentiation term, you must define portfolios in the Define Portfolios Customizing activity.

If you want to use custom differentiation terms, you must define the differentiation terms in the Define Custom Differentiation Terms Customizing activity.

**Caution:**

Defining and assigning differentiations for the positions of your company codes is an important basic setting that you must make before you post the first position in a company code.

###### Lot

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Lot | L5 | trm07 p.17 | loio `060dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/060dda531198434de10000000a174cb4.html?locale=en-US)

Definition

Smallest possible position management unit in the parallel valuation areas. A lot is generated by an operative business transaction that involves a change in the number of units. This is usually a securities purchase or an open transaction.

In the securities area, you can manage your positions at lot level. This is referred to as single position management.

###### Treasury Position

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Treasury Position | L5 | trm07 p.18 | loio `9d5dc753b1081d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9d5dc753b1081d4be10000000a174cb4.html?locale=en-US)

**Definition**

The treasury position (or subledger position) is the most detailed level into which you can break down the balance sheet accounts of the Treasury and Risk Management subledger (TRL). The key date valuations are carried out at position level and the position components are managed at position level. This means that a position is created for each valuation area for a financial transaction. For example, if you have two valuation areas (one for your local accounting principle and one for IFRS), the system creates two positions for each financial transaction.

The differentiation terms of the different product groups delimit the positions.

You must assign an account assignment reference to each position. You can use this account assignment reference to control how the subledger positions are posted in the general ledger.

**Integration**

The treasury positions of the different valuation areas for a financial transaction are generated automatically when the financial transaction is saved as a contract. At this point, the position indicator including the account assignment references is also generated for the treasury positions if you have not already created the position indicator manually.

**Note:**

In the securities area, the positions in the valuation areas are created in accordance with the respective differentiation as soon as a security is purchased in a securities account. Later purchases of the same security with the same differentiation values increase the existing positions. If you buy the same security with different differentiation values, such as a different securities account or valuation class, new positions are created. The general rule for securities positions is that all security purchases with the same differentiation values are managed as one position in the valuation areas.

If you use the integration with Public Sector Management, you can distribute the nominal amount/units of a money market or security transaction to different account assignments, you can do so in the Account Assignment table on the Cash Flow tab.

As long as there are no posted flows for a position, you can make the following changes for the positions:

You can correct the position relevant data on the Administration tab in the financial transaction data.

You change the assignment of the position management procedure and account assignment reference in the position indicator using the app Manage Position Indicator.

However, as soon as there is a posted flow for a position, it is no longer possible to change the position management procedure or the account assignment reference using the app Manage Position Indicator.

To change the position management procedure of a position in that case, you must execute a valuation class transfer. For more information, see also Execute Valuation Class Transfer.

To change the account assignment reference of a position, you must execute an account assignment reference transfer. For more information, see also Transfer Account Assignment Reference.

In addition, you can use the Account Assignment Transfer app, to transfer the units/nominals of a treasury position to another position with different account assignments (such as cost center, WBS element, functional area, profit center, or custom differentiation terms).

The values of the position components of a position are adjusted using derived business transactions triggered by the operational business transactions.

**Related Information**

Valuation Area Differentiation Terms Account Assignment References Position Indicator Operational Business Transactions Derived Business Transactions Position Components

###### Subledger Position

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Subledger Position | L5 | trm07 p.19 | loio `d30cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d30cda531198434de10000000a174cb4.html?locale=en-US)

Definition

See also: Position

###### Subposition (P-HA)

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Subposition (P-HA) | L5 | trm07 p.19 | loio `4e7a39e3361648cab0d1026b7faaf528` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4e7a39e3361648cab0d1026b7faaf528.html?locale=en-US)

**Definition**

The positions that are assigned to a hedging relationship (as hedged items or as a hedging instrument) in Hedge Accounting for Positions (P-HA) are managed in subpositions in position management, whereby a distinction is made between the free-standing subpositions and the designated subpositions.

A free-standing subposition is generated for the positions by assigning a hedged item and a hedging instrument to a hedging relationship.

If designation then occurs later on, the free-standing subpositions are reduced by the designated part and a subposition is generated for the designated part.

You can see whether and which subpositions can exist for positions in the position list (transaction TPM12). This contains a Subpositions column in which each position that has one or more subpositions has an icon. You can choose the icon to display the subpositions. In the Free column of this list, you can see whether the respective subposition is a free-standing or a designated subposition.

The position components are managed for a subposition, and they are also adjusted here using the derived business transactions.

**Integration**

Positions and subpositions are integrated as financial objects in Risk Management. You can use the Accounting Analyzer functions to analyze the position components.

###### Portfolio

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Portfolio | L5 | trm07 p.20 | loio `d19ad4811bc94190b6fe7818f46000ab` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d19ad4811bc94190b6fe7818f46000ab.html?locale=en-US)

You use portfolios as an organizational element to group various financial transactions for reporting purposes. You can define portfolios in the Define Portfolios configuration activity.

###### WBS Element

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > WBS Element | L5 | trm07 p.20 | loio `7cbfd5eee2974964a444d25d029f11e7` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7cbfd5eee2974964a444d25d029f11e7.html?locale=en-US)

A structural element in a work breakdown structure representing the hierarchical organization of a project.

A WBS element describes a task or a partial task that can be divided.

**Use as Differentiation Term for Treasury Positions**

You can use this field as differentiation term for your treasury positions. For more information, see also Differentiation Terms.

The WBS element is only relevant for postings to P&L accounts. This value isn't transferred in the case of postings to balance sheet accounts.

###### Cost Center

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Cost Center | L5 | trm07 p.20 | loio `94fbc66c14fc4a7c92da6410bda0e1a4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/94fbc66c14fc4a7c92da6410bda0e1a4.html?locale=en-US)

An organizational unit within a controlling area that represents a defined location of cost incurrence.

The definition can be based on:

Functional requirements

Allocation criteria

Physical location

Responsibility for costs

**Use as Differentiation Term for Treasury Positions**

You can use this field as differentiation term for your treasury positions. For more information, see also Differentiation Terms.

The cost center is only relevant for postings to P&L accounts. This value isn’t transferred in the case of postings to balance sheet accounts. You can use this field as differentiation term for your treasury positions. For more information, see also

###### Profit Center

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Profit Center | L5 | trm07 p.20 | loio `101cb6c8485845dfb5806c7ad8156d07` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/101cb6c8485845dfb5806c7ad8156d07.html?locale=en-US)

An organizational unit in Accounting that reflects a management-oriented structure of the organization for the purpose of internal control.

Operating results for a profit center can be analyzed using either the cost of sales approach or the period accounting approach.

By analyzing fixed capital as well, you can expand your profit center for use as an investment center.

**Use as Differentiation Term for Treasury Positions**

You can use this field as differentiation term for your treasury positions. For more information, see also Differentiation Terms.

###### Functional Area

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Functional Area | L5 | trm07 p.21 | loio `6551ef8f9a6f4b0dbfc8b28e036991d3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6551ef8f9a6f4b0dbfc8b28e036991d3.html?locale=en-US)

Structure criterion for an enterprise or government based on functional aspects

**Use as Differentiation Term for Treasury Positions**

You can use this field as differentiation term for your treasury positions. For more information, see also Differentiation Terms.

###### Fund

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Fund | L5 | trm07 p.21 | loio `e7e1633618414fe6a62b0d35a05b34db` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e7e1633618414fe6a62b0d35a05b34db.html?locale=en-US)

A capital investment made collectively by individuals or organizations in order to allow a wider range of investment access than feasible for separate investors, and in order to share the costs of the investment.

**Use as Differentiation Term for Treasury Positions**

You can use this field as differentiation term for your treasury positions. For more information, see also Differentiation Terms.

###### Grant

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Grant | L5 | trm07 p.21 | loio `9167f8b0e787408887d077619a7392b0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9167f8b0e787408887d077619a7392b0.html?locale=en-US)

Legal instrument used to establish a funding relationship between a sponsor (grantor) and grantee, in order to carry out a public purpose of support or stimulation in which the sponsor doesn't expect to be substantially involved.

A grant may be for any purpose and cover all or only part of the costs of the project in question. You must enter a grant type for each grant you create in Grants Management (GM).

**Use as Differentiation Term for Treasury Positions**

You can use this field as differentiation term for your treasury positions. For more information, see also Differentiation Terms.

###### Position Indicator

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Position Indicator | L5 | trm07 p.21 | loio `2b1ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2b1ada531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The position indicator of a subledger position contains the Position Management Procedure and the Account Assignment Reference, along with the balance sheet indicator.

In the securities account position indicator you specify information, such as the custody type, at the level of the company code, security ID number, and securities account.

**Integration**

The system can generate the position indicator automatically.

As long as there are no posted flows for a position, you can change the assignment of the position management procedure and account assignment reference in the position indicator using the app Manage Position Indicator. However, as soon as

there is a posted flow, it is no longer possible to change the position management procedure or the account assignment reference there.

To change the position management procedure in that case, you must execute a valuation class transfer.

To change the account assignment reference, you must execute an account assignment reference transfer.

To create, change, or display the position indicator, you need authorization for authorization object FW_BES_BUK of object class IS.

**Note:**

If you want to change the position indicator, even if the above requirements are not met, you can proceed as follows:

- 1. Create a new securities account. Maintain the valuation parameters in the position indicator according to your requirements and perform a securities account transfer. The change you make to the valuation parameters is effective for the position of the securities account transfer as of the key date of the transfer.

- 2. You cannot change the valuation parameters for positions that already exist.


**Customizing**

You can make settings for the position indicator for securities in Customizing for the Transaction Manager. Choose Securities Master Data Position Indicator Define Generation of Securities Account Position Indicator and Define Generation of Subledger Position Indicator. These settings include whether the securities account position indicator and

subledger position indicator are created manually or automatically. Another setting determines whether, as soon as it becomes necessary to create a new position indicator, a dialog box appears where you can choose manual creation of the securities account position indicator or have the system generate the securities account position indicator automatically.

If you want the system to determine the position indicator automatically, you have to define the following default values in Customizing:

- 1. Default values for determining the account assignment reference automatically

You enter these values in Customizing for the Transaction Manager. Choose General Settings Accounting Link to Other Accounting Components Define Account Assignment Reference Determination .

- 2. Assign the position management procedure.


In Customizing for the Transaction Manager, choose General Settings Accounting Settings for Position Management Assign Position Management Procedure . Here you define the rules based on which position management procedures are assigned to the positions.

Custody types are defined in Customizing for the Transaction Manager. Choose Securities Master Data Specific Class Data Define Custody Types .

Asset groupings are defined in Customizing for the Transaction Manager. Choose Securities Position Management Asset Groups Define Indicators for Balance Sheet Grouping .

**Note:**

There is a relationship between holding and shareholding that you can set up in Customizing. There you can specify for each holding whether it is a shareholding. If the shareholding indicator is set, a check is run whenever you create or change a securities account position indicator. The system performs this check to make sure an appropriate holding was also selected.

###### Position Change Category

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Position Change Category | L5 | trm07 p.23 | loio `d00cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d00cda531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The position change category tells you which position components are changed by an update type and how they are changed.

**Examples of Position Change Categories**

1000 No position change

1002 Incoming payment

1020 Outgoing payment

- 1010 Post negative purchase value

- 1011 Post purchase value

- 1012 Post variation margin

- 1013 Clear variation margin

- 1014 Post costs to cost component (assign the update type for capitalized costs if the capitalized costs are to be held separately (exclusive))

- 1015 Post costs to purchase value component (assign the update type for capitalized costs if the capitalized costs are to be held inclusively)


...

###### Position Management Category

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Position Management Category | L5 | trm07 p.23 | loio `4f0e5b9b49dd01b1e10000000a421bc1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4f0e5b9b49dd01b1e10000000a421bc1.html?locale=en-US)

Positions belonging to different product categories place different demands on position management (valuation). Therefore, different position management categories have been defined, and these categories use different procedures for key date valuation.

The system uses the following eight position management categories:

- 1. Securities/Loans/Money Market Transactions/Listed Options, Normal Style (Without Index-Linked Bonds)
- 2. Index-Linked Bonds
- 3. OTC Derivatives (Profit-Related Postings) (used for OTC options, interest rate swaps, FRAs, and caps/floors)
- 4. Listed Options (Future Style) and Futures
- 5. Foreign Exchange Transactions
- 6. Forwards/Repos
- 7. OTC Derivatives (Transfer Posting to Underlying)
- 8. Securities/Loans with Installment Repayment (Without Index-Linked Bonds)


A position management procedure relates to one position management category.

###### Position Management Procedure

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Position Management Procedure | L5 | trm07 p.23 | loio `1417d7537c98424de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1417d7537c98424de10000000a174cb4.html?locale=en-US)

**Definition**

The position management procedure determines which steps are used in the valuation or in generating the Derived Business Transactions and also the sequence in which the steps are performed.

**Features**

You use a Transfer Category to define how, in the case of a position transfer (for example, a position class transfer or a securities account transfer) the Position Components in the target position are to be filled where the target position components do not match the source position components.

Setting options are also available for the following areas:

Impairment procedure ( see Impairments )

Interest calculation for derived business transactions

Managing the position as a liability position and/or asset position

For more information, in Customizing for Treasury and Risk Management choose Transaction Manager General Settings Accounting Settings for Position Management Define Position Management Procedure.


**Activities**

You determine how the various steps are to be carried out in Customizing by choosing Transaction Manager General Settings Accounting Settings for Position Management Key Date Valuation .


Define Amortization Procedure

Define One-Step Price Valuation Procedure

Define Security Valuation Procedure

Define Foreign Currency Valuation Procedure

Define Price Valuation Procedure for Forward Exchange Transactions

You create the position management procedure using the IMG activity Define Position Management Procedure .

Using Assign Position Management Procedure , you determine the rules for assigning the position management procedures to the positions.

See also:

Valuation

###### Position Components

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Position Components | L5 | trm07 p.24 | loio `3f27275305552c3ee10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3f27275305552c3ee10000000a423f68.html?locale=en-US)

Position components hold the values of a treasury position. We distinguish between original and derived position components. Derived position components are based on original position components and are determined by adding or subtracting original position components.

Each position is assigned to a position management procedure. The position management procedure defines how the position is managed and valuated. A position management procedure commonly consists of a position management category and valuation

steps.

For more information, see Position Management Procedure.

The position management category sets the relevant position components for the position and the possible valuation steps that can be assigned. The valuation steps define how and in which order the position is valuated.

For more information, see Position Management Category.

The following position management categories are available, which have their specific position components:

**1. Securities/Loans/Money Market Transactions/Listed Options, Normal Style (Without Index-Linked Bonds)**

Available for the following product categories: 010, 020, 030, 040, 041, 042, 060, 070, 111, 112, 113, 114, 160, 510, 520, 530, 540, 550, 560, 570, 580, 690, 750, 850, 860, 991

Original components:

Units/Nominal (0001)

Designated Units/Nominal (0002)

Intercompany Billing (1000)

Purchase Value (1001)

Security Valuation (1002)

Foreign Currency Valuation (1003)

Capitalized Costs (1004)

Valuation of Capitalized Costs, Security (1005)

Valuation of Capitalized Costs, Foreign Currency (1006)

Amortization (1007) [when differentiating between issue/negotiation spread: amortization with issue spread]

Premium/Discount (1008) [Cleared Premium/Discount Deferral/Tax Compensation]

Deferral Item, Purchase Value (1010) [not included in the book value; when differentiating between issue/negotiation spread: negotiation spread to be amortized]

FX Valuation of Amortized Acquisition Value (1011)

Variation Margin (1012)

If, in the definition of the security valuation procedure and/or the foreign exchange valuation procedure, the Do Not Realize Gains/Losses setting was made, the following components are used:

Security Valuation, Not Affecting P/L (1013) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Foreign Currency Valuation, Not Affecting P/L (1014) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Costs: Security Valuation, Not Affecting P/L (1016) [not included in the book value; for transfers (valuation class

Costs: Foreign Currency Valuation, Not Affecting P/L (1017) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Accrued Interest (1018) [netting; not included in the book value]

Amortization Negotiation Spread (1019)

Consolidated Security Gains (1021) (from intragroup transactions)

Consolidated Security Losses (1022) (from intragroup transactions)

Consolidated FX Gains (1023) (from intragroup transactions)

Consolidated FX Losses (1024) (from intragroup transactions)

Fair Value Adjustment Gains (1025)

Fair Value Adjustment Losses (1026)

Original Fair Value Adjustment (1027)

For Internal Calculation: Hedge Amortization (1029)

This position component is required for a one-time increase of the acquisition value in the context of a designation of a hedging relationship (P-HA). This is because, in this case, the actual amortized acquisition value of the securities position is not the basis for the amortization; instead, the market value of the securities position at the time of the designation is used as the basis. Consequently, the system creates a flow for the difference between the current amortized acquisition value and the market value at the time of the designation and updates it to this component. The component then flows into position component Amortized Acquisition Value (9004).

FX Valuation of Acquisition Value (1030)

Capitalization Reserve France (1099)

Impairment (1201)

FX Impairment (1202)

Classification Amount (1300)

Hedge Adjustment (1301)

Effective/Hedging Reserve (1302)

Ineffective (1303)

CFH, NIH: Effective, Dormant (1304)

CFH, NIH: Ineffective, Dormant (1305)

Derived components:

Book Value (9001) = Purchase Value (1001) + Security Valuation (1002) + Foreign Curency Valuation (1003) + Capitalized Costs (1004) + Valuation of Capitalized Costs, Security (1005) + Valuation of Capitalized Costs, Foreign Currency (1006) + Amortization (1007) + Cleared P/D Deferral/Tax Compensation (1008) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Book Value without Capitalized Costs (9002) = Purchase Value (1001) + Security Valuation (1002) + Foreign Curency Valuation (1003) + Amortization (1007) + Cleared P/D Deferral/Tax Compensation (1008) + FX Valuation of Amort.

Acquisition Value (1011) + Amortization Negotiation Spread (1019) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Acquisition Value (9003) = Purchase Value (1001) + Capitalized Costs (1004) + FX Valuation of Acquisition Value

(1030)

Amortized Acquisition Value (9004) = Acquisition Value (9003) + Amortization (1007) + FX Valuation of Amortized Acquisition Value (1011) + Amortization Negotiation Spread (1019) [1019 depending on amortization procedure] + For Internal Calculation: Hedge Amortization (1029) + Impairment (1201) + FX Impairment (1202) +

Amortized Cost (9005) = Purchase Value (1001) + Capitalized Costs (1004) + Amortization (1007) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + For Internal Calculation: Hedge Amortization (1029) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202)

**2. Index-Linked Bonds**

Available for the following product categories: 040, 060, 070

Original components:

Intercompany Billing (1000)

Units/Nominal (0001)

Designated Units/Nominal (0002)

Intercompany Billing (1000)

Purchase Value (1001)

Security Valuation (1002)

Foreign Currency Valuation (1003)

Capitalized Costs (1004)

Valuation of Capitalized Costs, Security (1005)

Valuation of Capitalized Costs, Foreign Currency (1006)

Amortization (1007) [when differentiating between issue/negotiation spread: amortization with issue spread]

Premium/Discount (1008) [Cleared Premium/Discount Deferral/Tax Compensation]

Index Valuation (1009)

Deferral Item, Purchase Value (1010) [not included in the book value; when differentiating between issue/negotiation spread: negotiation spread to be amortized]

FX Valuation of Amortized Acquisition Value (1011)

If, in the definition of the security valuation procedure and/or the foreign exchange valuation procedure, the Do Not Realize Gains/Losses setting was made, then the following components are used:

Security Valuation, Not Affecting P/L (1013) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Foreign Currency Valuation, Not Affecting P/L (1014) [not included in the book value; for transfers (valuation class

Index Valuation, Not Affecting P/L (1015) [not included in the book value]

Costs: Security Valuation, Not Affecting P/L (1016) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Costs: Foreign Currency Valuation, Not Affecting P/L (1017) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Accrued Interest (1018) [netting; not included in the book value]

Amortization Negotiation Spread (1019)

Consolidated Security Gains (1021) (from intragroup transactions)

Consolidated Security Losses (1022) (from intragroup transactions)

Consolidated FX Gains (1023) (from intragroup transactions)

Consolidated FX Losses (1024) (from intragroup transactions)

For Internal Calculations: Hedge Amortization (1029)

Needed for a one-time increase of the acquisition value in the context of a designation of a hedging relationship (P-HA) since, in this case, the actual amortized acquisition value of the securities position is not the basis for the amortization; instead, the market value of the securities position at the time of the designation is used as the basis. Therefore, the system creates a flow for the difference between the current amortized acquisition value and the market value at the time of the designation and updates it to this component. The component then flows into position component Amortized Acquisition Value (9004).

FX Valuation of Acquisition Value (1030)

Capitalization Reserve France (1099)

Impairment (1201)

FX Impairment (1202)

Classification Amount (1300)

Hedge Adjustment (1301)

Effective/Hedging Reserve (1302)

Ineffective (1303)

CFH, NIH: Effective, Dormant (1304)

CFH, NIH: Ineffective, Dormant (1305)

Derived components:

Book Value (9001) = Purchase Value (1001) + Security Valuation (1002) + Foreign Curency Valuation (1003) + Capitalized Costs (1004) + Valuation of Capitalized Costs, Security (1005) + Valuation of Capitalized Costs, Foreign Currency (1006) + Amortization(1007) + Cleared P/D Deferral/Tax Compensation (1008) + Index Valuation (1009) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Book Value without Capitalized Costs (9002) = Purchase Value (1001) + Security Valuation (1002) + Foreign Curency Valuation (1003) + Amortization(1007) + Cleared P/D Deferral/Tax Compensation (1008) + Index Valuation (1009) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Acquisition Value (9003) = Purchase Value (1001) + Capitalized Costs (1004) + FX Valuation of Acquisition Value

(1030)

Amortized Acquisition Value (9004) = Acquisition Value (9003) + Amortization (1007) + FX Valuation of Amortized Acquisition Value (1011) + Amortization Negotiation Spread (1019) [1019 depending on amortization procedure] + For Internal Calculation: Hedge Amortization (1029) + Impairment (1201) + FX Impairment (1202) +

Amortized Cost (9005) = Purchase Value (1001) + Capitalized Costs (1004) + Amortization (1007) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + For Internal Calculation: Hedge Amortization (1029) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202)

**3. OTC Derivatives (Profit-Related Postings) for OTC Options, Interest Rate Swaps, FRAs, and Caps/Floors**

Available for the following product categories: 600, 610, 620, 630, 640, 710, 712, 740, 760, 770, 780, 800, 810

Original components:

Units/Nominal (0001)

Designated Units/Nominal (0002)

Intercompany Billing (1000)

Purchase Value (1001)

Security Valuation (1002)

Foreign Currency Valuation (1003)

Variation Margin (1012)

Security Valuation, Not Affecting P/L (1013)

Foreign Currency Valuation, Not Affecting P/L (1014)

Impairment (1201)

FX Impairment (1202)

Classification Amount (1300)

Hedge Adjustment (1301)

Effective/Hedging Reserve (1302)

Ineffective (1303)

CFH, NIH: Effective, Dormant (1304)

CFH, NIH: Ineffective, Dormant (1305)

Derived components:

Book Value (9001) = Purchase Value (1001) + valuations (1002 + 1003) + Impairment(1201) + FX Impairment(1202) + Hedge Adjustment (1301)

Book Value Without Capitalized Costs (9002) = Book Value (9001)

**4. Listed Options (Future Style) and Futures**

Available for the following product categories: 700, 750, 890.

Original components:

Units/Nominal (0001)

Designated Units/Nominal (0002)

Intercompany Billing (1000)

Purchase Value (1001)

Security Valuation (1002) [not used]

Foreign Currency Valuation (1003) [not used]

Capitalized Costs (1004)

Variation Margin (1012) [not included in the book value]

Classification Amount (1300)

Hedge Adjustment (1301)

Effective/Hedging Reserve (1302)

Ineffective (1303)

CFH, NIH: Effective, Dormant (1304)

CFH, NIH: Ineffective, Dormant (1305)

Derived components:

Book Value (9001) = Purchase Value (1001) + Valuations (1002 + 1003) + Capitalized Costs (1004) + Hedge Adjustment (1301)

Book Value Without Capitalized Costs (9002) = Purchase Value (1001) + Valuations (1002 + 1003) + Hedge Adjustment

(1301) = Book Value (9001) - Capitalized Costs (1004)

Acquisition Value (9003) = Purchase Value (1001) + Capitalized Costs (1004)

**5. Foreign Exchange Transactions**

Available for the following product categories: 600

Original components:

Units/Nominal (0001)

Designated Units/Nominal (0002)

Intercompany Billing (1000)

Purchase Value (1001)

Security Valuation (1002)

Security Valuation, Not Affecting P/L (1013)

Spot Valuation in Purchase Currency (1105) [only in valuation currency]

Spot Valuation in Sale Currency (1106) [only in valuation currency]

Margin/Swap Accrual/Deferral (1107) [only in valuation currency]

Swap Valuation (1108) [only in valuation currency]

Impairment (1201)

FX Impairment (1202)

Classification Amount (1300)

Hedge Adjustment (1301)

Effective/Hedging Reserve (1302)

Ineffective (1303)

CFH, NIH: Effective, Dormant (1304)

CFH, NIH: Ineffective, Dormant (1305)

Derived components:

Book Value (9001) [only in valuation currency] = Purchase Value (1001) + Valuations (1002 + 1105 + 1106 + 1108) + Margin/Swap Accrual/Deferral (1107) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

**6. Forwards/Repos**

Available for the following product categories: 730, 740

Original components:

Units/Nominal (0001)

Designated Units/Nominal (0002)

Intercompany Billing (1000)

Purchase Value (1001)

Security Valuation (1002)

Foreign Currency Valuation (1003)

Margin/Swap Accrual/Deferral (1107) [distribution of the difference between the forward price and the spot price over the term]

Classification Amount (1300)

Hedge Adjustment (1301)

Effective/Hedging Reserve (1302)

Ineffective (1303)

CFH, NIH: Effective, Dormant (1304)

CFH, NIH: Ineffective, Dormant (1305)

Derived components:

Book Value (9001) = Purchase Value (1001) + Valuations (1002 + 1003) + Margin/Swap Accrual/Deferral (1107) + Hedge Adjustment (1301)

**7. OTC Derivatives (Transfer Posting to Underlying)**

Available for the following product categories: 600, 610, 620, 630, 640, 710, 712, 740, 760, 790

Original components:

Units/Nominal (0001)

Designated Units/Nominal (0002)

Intercompany Billing (1000)

Purchase Value (1001)

Security Valuation (1002)

Foreign Currency Valuation (1003)

Variation Margin (1012)

Security Valuation, Not Affecting P/L (1013)

Foreign Currency Valuation, Not Affecting P/L (1014)

Impairment (1201)

FX Impairment (1202)

Classification Amount (1300)

Hedge Adjustment (1301)

Effective/Hedging Reserve (1302)

Ineffective (1303)

CFH, NIH: Effective, Dormant (1304)

CFH, NIH: Ineffective, Dormant (1305)

Derived components:

Book Value (9001) = Purchase Value (1001) + valuations (1002 + 1003) + Impairment(1201) + FX Impairment(1202) + Hedge Adjustment (1301)

Book Value Without Capitalized Costs (9002) = Book Value (9001)

**8. Securities/Loans/Money Market with Installment Repayment (Without IndexLinked Bonds)**

Available for the following product categories: 042, 550, 570

Original components:

Units /Nominal (0001)

Designated Units /Nominal (0002)

Intercompany Billing (1000)

Purchase Value (1001)

Security Valuation (1002)

Foreign Currency Valuation (1003)

Capitalized Costs (1004)

Valuation of Capitalized Costs, Security (1005)

Valuation of Capitalized Costs, Foreign Currency (1006)

Amortization (1007) [when differentiating between issue/negotiation spread: amortization with issue spread]

Premium/Discount (1008) [Cleared Premium/Discount Deferral/Tax Compensation]

Deferral Item, Purchase Value (1010) [not included in the book value; when differentiating between issue/negotiation spread: negotiation spread to be amortized]

FX Valuation of Amortized Acquisition Value (1011)

If, in the definition of the security valuation procedure and/or the foreign exchange valuation procedure, the Do Not Realize Gains/Losses setting was made, the following components are used:

Security Valuation, Not Affecting P/L (1013) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Foreign Currency Valuation, Not Affecting P/L (1014) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Costs: Security Valuation, Not Affecting P/L (1016) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Costs: Foreign Currency Valuation, Not Affecting P/L (1017) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Accrued Interest (1018) [netting; not included in the book value]

Amortization Negotiation Spread (1019)

Repayment (1020)

Consolidated Security Gains (1021) (from intragroup transactions)

Consolidated Security Losses (1022) (from intragroup transactions)

Consolidated FX Gains (1023) (from intragroup transactions)

Consolidated FX Losses (1024) (from intragroup transactions)

Fair Value Adjustment Gains (1025)

Fair Value Adjustment Losses (1026)

Original Fair Value Adjustment (1027)

Interest Income (1028)

For Internal Calculations: Hedge Amortization (1029)

Needed for a one-time increase of the acquisition value in the context of a designation of a hedging relationship (P-HA) since, in this case, the actual amortized acquisition value of the securities position is not the basis for the amortization; instead, the market value of the securities position at the time of the designation is used as the basis. Therefore, the system creates a flow for the difference between the current amortized acquisition value and the market value at the time of the designation and updates it to this component. The component then flows into position component Amortized Acquisition Value (9004).

FX Valuation of Acquisition Value (1030)

Capitalization Reserve France (1099)

Impairment (1201)

FX Impairment (1202)

Classification Amount (1300)

Hedge Adjustment (1301)

Effective/Hedging Reserve (1302)

Ineffective (1303)

CFH, NIH: Effective, Dormant (1304)

CFH, NIH: Ineffective, Dormant (1305)

Derived components:

Book Value (9001) = Purchase Value (1001) + Security Valuation (1002) + Foreign Curency Valuation (1003) + Capitalized Costs (1004) + Valuation of Capitalized Costs, Security (1005) + Valuation of Capitalized Costs, Foreign Currency (1006) + Amortization(1007) + Cleared P/D Deferral/Tax Compensation (1008) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + Repayment (1020) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Book Value without Capitalized Costs (9002) = Purchase Value (1001) + Security Valuation (1002) + Foreign Curency Valuation (1003) + Amortization(1007) + Cleared P/D Deferral/Tax Compensation (1008) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + Repayment (1020) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Acquisition Value (9003) = Purchase Value (1001) + Capitalized Costs (1004) + Repayment (1020) + FX Valuation of Acquisition Value (1030)

Amortized Acquisition Value (9004) = Acquisition Value (9003) + Amortization (1007) + FX Valuation of Amortized Acquisition Value (1011) + Amortization Negotiation Spread (1019) [1019 depending on amortization procedure] + Repayment (1020) + For Internal Calculation: Hedge Amortization (1029) + Impairment (1201) + FX Impairment

(1202) +

Amortized Cost (9005) = Purchase Value (1001) + Capitalized Costs (1004) + Amortization (1007) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + Repayment (1020) + For Internal Calculation: Hedge Amortization (1029) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202)

**9. Exposures**

This position management category is used for the exposure subitems created during the automated designation process of the Hedge Accounting for Exposure Items process. The exposure subitem represents a valuation-area-specific hedged portion of the exposure item and it is used as a carrier for the hedging reserve and cost of hedging reserve for the hedging instrument according

to the relevant hedge accounting rule.

Units/Nominal (0001)

Designated Units/Nominal Amounts (0002)

Amount Components Exposures (1008)

Classification Amount (1300)

Effective / Hedging Reserve (1302)

Ineffective (1303)

Effective / Cost of Hedging Reserve (1322)

Ineffective / Hedging Reserve TPL (1323)

Effective / Hedging Reserve TPL (1324)

Ineffective / Cost of Hedging Reserve TPL (1333)

Effective / Cost of Hedging Reserve TPL (1334)

P/L Effective / Designated Components (1343)

P/L Effective / Non-Designated Components (1344)

Amortization / Non-Designated Components (1345)

**10. Index-Linked Bonds with Installment Repayment**

Available for the product category: 040

Original components:

Intercompany Billing (1000)

Units/Nominal (0001)

Designated Units/Nominal (0002)

Intercompany Billing (1000)

Purchase Value (1001)

Security Valuation (1002)

Foreign Currency Valuation (1003)

Capitalized Costs (1004)

Valuation of Capitalized Costs, Security (1005)

Valuation of Capitalized Costs, Foreign Currency (1006)

Amortization (1007) [when differentiating between issue/negotiation spread: amortization with issue spread]

Premium/Discount (1008) [Cleared Premium/Discount Deferral/Tax Compensation]

Index Valuation (1009)

Deferral Item, Purchase Value (1010) [not included in the book value; when differentiating between issue/negotiation spread: negotiation spread to be amortized]

FX Valuation of Amortized Acquisition Value (1011)

If, in the definition of the security valuation procedure and/or the foreign exchange valuation procedure, the Do Not Realize Gains/Losses setting was made, then the following components are used:

Security Valuation, Not Affecting P/L (1013) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Foreign Currency Valuation, Not Affecting P/L (1014) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Index Valuation, Not Affecting P/L (1015) [not included in the book value]

Costs: Security Valuation, Not Affecting P/L (1016) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Costs: Foreign Currency Valuation, Not Affecting P/L (1017) [not included in the book value; for transfers (valuation class transfer, securities account transfer)]

Accrued Interest (1018) [netting; not included in the book value]

Amortization Negotiation Spread (1019)

Repayment (1020)

Consolidated Security Gains (1021) (from intragroup transactions)

Consolidated Security Losses (1022) (from intragroup transactions)

Consolidated FX Gains (1023) (from intragroup transactions)

Consolidated FX Losses (1024) (from intragroup transactions)

For Internal Calculations: Hedge Amortization (1029)

Needed for a one-time increase of the acquisition value in the context of a designation of a hedging relationship (P-HA) since, in this case, the actual amortized acquisition value of the securities position is not the basis for the amortization; instead, the market value of the securities position at the time of the designation is used as the basis. Therefore, the system creates a flow for the difference between the current amortized acquisition value and the market value at the time of the designation and updates it to this component. The component then flows into position component Amortized Acquisition Value (9004).

FX Valuation of Acquisition Value(1030)

Capitalization Reserve France (1099)

Impairment (1201)

FX Impairment (1202)

Classification Amount (1300)

Hedge Adjustment (1301)

Effective/Hedging Reserve (1302)

Ineffective (1303)

CFH, NIH: Effective, Dormant (1304)

CFH, NIH: Ineffective, Dormant (1305)

Derived component:

Book Value (9001) = Purchase Value (1001) + Security Valuation (1002) + Foreign Currency Valuation (1003) + Capitalized Costs (1004) + Valuation of Capitalized Costs, Security (1005) + Valuation of Capitalized Costs, Foreign Currency (1006) + Amortization (1007) + Cleared P/D Deferral/Tax Compensation (1008) + Index Valuation (1009) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + Repayment (1020) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Book Value without Capitalized Costs (9002) = Purchase Value (1001) + Security Valuation (1002) + Foreign Currency Valuation (1003) + Amortization (1007) + Cleared P/D Deferral/Tax Compensation (1008) + Index Valuation (1009) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + Repayment (1020) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Acquisition Value (9003) = Purchase Value (1001) + Capitalized Costs (1004) + Repayment (1020) + FX Valuation of Acquisition Value(1030)

Amortized Acquisition Value (9004) = Acquisition Value (9003) + Amortization (1007) + FX Valuation of Amortized Acquisition Value (1011) + Amortization Negotiation Spread (1019) [1019 depending on amortization procedure] + Repayment (1020) + For Internal Calculation: Hedge Amortization (1029) + Impairment (1201) + FX Impairment

(1202)

Amortized Cost (9005) = Purchase Value (1001) + Capitalized Costs (1004) + Amortization (1007) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + Repayment (1020) + For Internal Calculation: Hedge Amortization (1029) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202)

Book Value (9001) = Purchase Value (1001) + Security Valuation (1002) + Foreign Currency Valuation (1003) + Capitalized Costs (1004) + Valuation of Capitalized Costs, Security (1005) + Valuation of Capitalized Costs, Foreign Currency (1006) + Amortization(1007) + Cleared P/D Deferral/Tax Compensation (1008) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + Repayment (1020) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Book Value without Capitalized Costs (9002) = Purchase Value (1001) + Security Valuation (1002) + Foreign Currency Valuation (1003) + Amortization(1007) + Cleared P/D Deferral/Tax Compensation (1008) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + Repayment (1020) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202) + Hedge Adjustment (1301)

Acquisition Value (9003) = Purchase Value (1001) + Capitalized Costs (1004) + Repayment (1020) + FX Valuation of Acquisition Value (1030)

Amortized Acquisition Value (9004) = Acquisition Value (9003) + Amortization (1007) + FX Valuation of Amortized Acquisition Value (1011) + Amortization Negotiation Spread (1019) [1019 depending on amortization procedure] + Repayment (1020) + For Internal Calculation: Hedge Amortization (1029) + Impairment (1201) + FX Impairment

(1202) +

Amortized Cost (9005) = Purchase Value (1001) + Capitalized Costs (1004) + Amortization (1007) + FX Valuation of Amort. Acquisition Value (1011) + Amortization Negotiation Spread (1019) + Repayment (1020) + For Internal Calculation: Hedge Amortization (1029) + FX Valuation of Acquisition Value (1030) + Impairment (1201) + FX Impairment (1202)

**Clearing Account Positions**

For clearing accounts, the clearing account position is used as a position in the sense of position management in the Transaction Manager. The clearing account positions are split up using the differentiation criteria Company Code, Valuation Area, Product Type, and External Account.

The clearing account position uses the following position components:

- 1001 (Initial Margin)

- 1002 (Variation Margin)


- 2001 (Initial Margin Open)

- 2002 (Variation Margin Open)

- 2003 (Other (such as Fees) Open)


8000 (Clearing Payment)

- 9000 (Total Open)

- 9001 (Total Margin Open)


All flows of an external account are entered into a clearing account position.

The clearing account position is not valuated.

###### Transfer Category

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Transfer Category | L5 | trm07 p.38 | loio `eb0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/eb0cda531198434de10000000a174cb4.html?locale=en-US)

**Definition**

In a position transfer (for example, a valuation class transfer or securities account transfer), the transfer category controls how the position components are filled when the target position components do not match the source position components. This can be the case if the source and target positions have different position management procedures.

**Example:**

When a bond position is being transferred, it may be the case that the 'old' position management procedure calls for amortization whereas the 'new' position management procedure does not.

**Structure**

The position components are filled by the derived business transactions for the position transfer. When the system generates the derived business transactions for the operative business transaction (valuation class transfer or securities account transfer), it reads the transfer category of the target position and generates corresponding flows.

We distinguish between the following transfer categories:

- 01 Post to Same Components

The system transfers all position components unchanged. This applies even if one of the components is not used in the target position, for example.

- 02 Post to Components Used Only


The system makes a transfer posting only to those components that are also planned in the target position. The following rules apply:

Amortization occurs in the source position but is not determined for the target position. However, the security valuation is executed in both cases. The system posts the amount in the Amortization component (source position) to the Security Valuation component (target position).

Security valuations occur in the source position but are not determined for the target position. However, there is amortization in both cases. The system posts the amount in the Security Valuation component of the source position to the Amortization component of the target position.

Index valuations occur in the source position but are not determined in the target position. However, security valuation takes place in both cases. The system posts the amount in the Index Valuation component of the source position to the Security Valuation component of the target position.

There are index valuations in the source position. Neither index valuations nor security valuations are determined for the target position, but both the target and source positions are amortized. The system posts the amount in the Index Valuation component of the source position to the Amortization component of the target position.

Foreign currency valuations were executed in the source position but are not determined for the target position. However, security valuations take place in both cases. The system posts the amount in the Foreign Currency Valuation component of the source position to the Security Valuation component of the target position.

There are foreign currency valuations in the source position. Neither foreign currency valuations nor security valuations are determined for the target position, but amortization occurs in both the target and source positions. The system posts the amount in the Foreign Currency Valuation component of the source position to the Amortization component of the target position.

Gain/loss handling for the source position is set to Do Not Realize Gains/Losses (Security/Foreign Currency/Index). For the target position, however, the system posts security, foreign currency, or index valuations

to P/L, or executes amortization. The valuation components that do not affect profit and loss are cleared from the source position. The system posts the amounts from the valuation components not affecting the P&L to the appropriate P&L accounts. You define the update types for these flows on the Transfer Postings tab in the Clearing to Profit/Loss area.

Since the gross procedure is defined for amortization, there are premium/discount flows in the source position. Amortization is not determined for the target position, however, because the net procedure is defined. (Transfer postings between gross and net methods are possible for valuation class transfers. The system checks whether this prerequisite is fulfilled.)

When you make a transfer posting, the system replaces the flow Post Discount (Accrued/Deferred Items) (D038) with the flow Post Premium (D036). This means that a flow from the position with the gross procedure defined for amortization is replaced by a flow from the position with the net procedure defined for amortization. The system replaces the flow Post Premium (Accrued/Deferred Items) (D040) with the flow Post Discount (D034). In this way, the discount or premium is cleared from the target position.

- 03 Reverse Security and FX Valuations

The system does not generate transfer flows for:

Equity accounts that do not affect P/L

Adjustment flows

- 04 Reverse Security Valuations, Transfer FX Valuations


To avoid the need for account extensions for equity accounts, the system generates adjustment flows for the valuation of the foreign exchange. However, it does not generate posting flows or adjustment flows for the Security valuation components.

- 05 Transfer Security Valuations, Reverse FX Valuations

To avoid the need for account extensions for equity accounts, the system generates adjustment flows for the valuation of the security. However, it does not generate posting flows or adjustment flows for the Foreign Currency valuation components.

- 06 Transfer Unrealized Valuations (otherwise same as 02)

- 07 Post Book Value to Purchase Value Component


You use this transfer category if you want to process the inflow in the target position as a purchase during a position transfer.

The (proportional) book value of the source position is transferred as the purchase value of the target position. In the target position, posting flows are not generated for any other position component. If the N Automatic Accrual/Deferral with Income Transfer setting is used for derived business transactions for interest in the position management procedure, the (proportional) interest received from the source position is also transferred to the target position (with an additional transfer posting flow in the target position).

###### Update Type

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Terms in Position Management and Treasury Accounting > Update Type | L5 | trm07 p.41 | loio `150dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/150dda531198434de10000000a174cb4.html?locale=en-US)

Definition

Update types carry the information for a flow in the parallel valuation areas.

Once the update types have been defined and assigned to the various usages, each update type is configured for the respective usages.

If an update type should be posted, then you must set the relevant for posting indicator in Customizing and define the posting rules in account determination.

