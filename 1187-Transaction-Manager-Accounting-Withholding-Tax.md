# Transaction Manager > Accounting > Withholding Tax - SAP TRM Knowledge Base (branch split)

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

##### Withholding Tax

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Withholding Tax | L4 | trm08 p.191 | loio `19aaf30ef2c04f90a55df0f0257fd1eb` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/19aaf30ef2c04f90a55df0f0257fd1eb.html?locale=en-US)

This topic describes calculation and withholding tax posting during the borrowings operations in Treasury and Risk Management (TRM).

You can use the standard Treasury and Risk Management functions to automatically calculate the withholding tax, generate the relevant flows and post them to Financial Accounting (FI) in accordance with the legal and business requirements. For more information, see SAP Treasury and Risk Management (TRM).

You can use this process to execute withholding tax calculation with the standard procedure and by posting the tax relevant flows to customer for the corresponding business partner.

The TRM withholding tax function is available for the following product types:

**Money Market**

Securities

Trade finance

In the case of a tax rate change, the new tax rate from the withholding tax code is considered for withholding tax calculation.

**Integration**

Prerequisite for the TRM withholding tax customizing is a complete extended withholding tax customizing in Financial Accounting.

The specific functions are integrated into the Financial Accounting process and calculate the withholding tax before posting the tax to the corresponding customer account.

**Features**

Customizing

To ensure that withholding tax is calculated and posted correctly, you must carry out Customizing settings for extended withholding tax. For more information, see Customizing for Withholding Tax.

Business Transactions

You record money market and securities transactions following the standard procedure.

The system automatically calculates withholding tax when you save the transaction.

If, for example, the interest rate has changed during settlement, the system recalculates withholding tax.

Reporting

You can prepare your report and print it: you use for this the Cash Flows.

**Constraints**

This component is not used for areas:

CML (Loans)

Micro-hedging for recording the underlyings for foreign exchange (forex) contracts

###### Customizing for Withholding Tax

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Withholding Tax > Customizing for Withholding Tax | L5 | trm08 p.192 | loio `cbc19f1af5ad483bbb2a2da6a35f2987` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cbc19f1af5ad483bbb2a2da6a35f2987.html?locale=en-US)

This topic describes Customizing activities that need to be set to maintain withholding tax.

To customize Treasury and Risk Management you carry out the generic Customizing activities for withholding tax using the information provided in the following.

For more information, see Overview.

**Settings**

Make the settings in Customizing for Financial Supply Chain Management, choose Treasury and Risk Management

Transaction Manager General Settings Taxes Specify Flow Attributes for Extended Withholding Tax (view TRXV_WT_ASSIGN)

You must maintain every update type in the Update Type Tax Base column of the activity, which should generate a withholding tax flow.

You create this withholding tax flow with a flow type maintained in the Update Type column.

For every item in this table the withholding tax type and the withholding tax code have to be defined.

Since it is very important to correctly maintain this table, we recommend that you read the F1 Help of the fields of this maintenance view.

###### Business Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Withholding Tax > Business Transactions | L5 | trm08 p.192 | loio `47b4d2b9baf6477a9a233143f1c588c4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/47b4d2b9baf6477a9a233143f1c588c4.html?locale=en-US)

Use

You record transactions following the standard procedure.

In addition, when you save this transaction, the system automatically calculates withholding tax.

During settlement, the system recalculates withholding tax.

###### Withholding Tax Calculation in Contracts

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Withholding Tax > Business Transactions > Withholding Tax Calculation in Contracts | L6 | trm08 p.192 | loio `637af6fb6a98473789fad033fe5c6e60` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/637af6fb6a98473789fad033fe5c6e60.html?locale=en-US)

**Use**

If you want to perform a withholding tax calculation and post it in Treasury and Risk Management you post tax-relevant flows.

The operator posts the tax-relevant flows involving the customer account for the corresponding business partner.

**Procedure**

In the contract you define the flow types for which withholding tax must be calculated and posted.

You assign a contract to a customer using the Control Data indicator on the Payment details tab page in the contract. Only then the system calculates and posts the withholding tax.

Maintain the fields “ Business Place ” and “ Section Code ” in a contract. In TRM, both fields can be maintained in the box “Position indicator” of a transaction. Run the transaction FTR_CREATE/FTR_EDIT and on the menu tab choose Environment → Position Indicator.

The integration to Financial Accounting guarantees that the values of these fields are also transferred to FI and are then part of the FI accounting document.

The mapping of registration data, reporting, payment and due dates are based on these fields.

**Result**

You have calculated the withholding tax and saved it in the database.

###### Calculating Withholding Tax on Interest Accruals

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Withholding Tax > Business Transactions > Calculating Withholding Tax on Interest Accruals | L6 | trm08 p.193 | loio `3e629469a53b49ff854024cf81cfaf48` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3e629469a53b49ff854024cf81cfaf48.html?locale=en-US)

**Use**

This function enables you to define the posting on accruals and deferrals of expenses and revenues in Treasury. To execute or reverse these postings, you use the corresponding transaction. On the SAP Easy Access screen, choose for Money Market → Accounting → Financial Supply Chain Management → Treasury and Risk Management → Transaction Manager → Money Market → Accounting → Execute Accrual/Deferral.

Choose for Securities, instead: Accounting → Financial Supply Chain Management → Treasury and Risk Management → Transaction Manager → Securities →Accounting → Execute Accrual/Deferral.

For more information about processing of interest accruals, see Accrual/Deferral .

For the TRM India withholding tax function only the difference procedure is possible as an accrual/deferral procedure.

**Prerequisites**

To generate a withholding tax flow for an accrual, it is necessary to maintain the accrual update type in the corresponding Customizing table.

**Features**

This program makes accruals or deferrals of expenses and revenues resulting from Treasury deals, and allocates revenue and expenditure items to the proper account periods.

This program performs the following functions:

Calculates the amount to be accrued or deferred for the flows concerned

Creates the corresponding accrual or deferral flows

Posts the items immediately in financial accounting, if required.

###### Calculating Withholding Tax Calculation for Brokerage Amounts

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Withholding Tax > Business Transactions > Calculating Withholding Tax Calculation for Brokerage Amounts | L6 | trm08 p.194 | loio `4b1022032b444849a6b520b273776c15` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4b1022032b444849a6b520b273776c15.html?locale=en-US)

**Use**

If withholding tax is raised on brokerage you can create brokerage flows on tab page Other flows of the transaction for brokerage amounts.

To generate withholding tax for a brokerage flow, you must maintain the brokerage update type, in the Update Type Tax Base column of the Customizing view..

**Example**

You can use the following update type:

SE3001: Brokerage capitalized

###### Posting and Transferring of Flows

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Withholding Tax > Posting and Transferring of Flows | L5 | trm08 p.194 | loio `978490055e87437f8a11bb9651d5cc64` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/978490055e87437f8a11bb9651d5cc64.html?locale=en-US)

**Use**

You use this function to generate documents to Financial Accounting in Treasury .

This is possible with program Treasury: Post Flows (transaction TBB1).

**Features**

The report performs following activities:

- 1. The program finds the corresponding posting details for each flow in account determination.
- 2. The document is prepared and transferred to Financial Accounting .
- 3. The calculated withholding tax amounts or flows are processed, transferred to Financial Accounting , and posted in a single FI document.
- 4. The list output displays the selected transactions with the withholding taxes calculated.


**Activities**

You can use the test run to check whether these steps can be carried out correctly, without Financial Accounting to be updated.

After a test run and during a productive run instead, the withholding tax information is stored in the contract, transferred to Financial Accounting, and posted in a single FI document.

