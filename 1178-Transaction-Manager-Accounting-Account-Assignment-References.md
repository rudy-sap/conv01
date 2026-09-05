# Transaction Manager > Accounting > Account Assignment References - SAP TRM Knowledge Base (branch split)

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

##### Account Assignment References

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Account Assignment References | L4 | trm08 p.169 | loio `fc0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fc0ada531198434de10000000a174cb4.html?locale=en-US)

Account assignment references (AAR) are assigned to each treasury position in the position indicator. You use the account assignment reference to determine the G/L account in which the position is managed. You make the assignments of the G/L accounts dependent on the account assignment reference for the relevant account symbols (position and interest revenue) for posting the positions, dividend payments, interest payments, accruals and deferrals, incoming payments, and repayments in the general ledger.

**Customizing**

You find Customizing activities relating to account assignment references in Customizing under Transaction Manager General Settings Accounting Link to Other Accounting Components :

You create the account assignment references based on valuation areas in the IMG activity Define Account Assignment References.

You can use the following Customizing activities for account assignment reference determination to define criteria according to which the account assignment references can be assigned automatically to the treasury positions.

Define Groupings

Define Account Assignment Reference Determination (OTC Financial Transactions)

Define Account Assignment Reference Determination (Securities/Listed Derivatives)

Define Account Assignment Reference Determination (Loans)

Define Account Assignment Reference Determination (External Accounts)

Define Account Assignment Reference Determination (Exposure Item)

You can assign the related business area and the related cost center depending on the company code and account assignment reference using the Customizing activity Allocate Additional Account Assignments to Account Assignment References.

You can assign the G/L accounts to the account assignment references in the Customizing activity Define Account Determination. You do this by making the determination of the G/L account for the position account symbols dependent on the account assignment reference.

**Derivation Process of Account Assignment References**

The derivation process of account assignment references starts when a treasury position is created.

The treasury positions for OTC transactions are created with the creation of the OTC transaction. The treasury positions of the different valuation areas for an OTC transaction are generated automatically when the financial transaction is saved as a contract. At this point, the position indicator including the account assignment references is also generated for the treasury positions.

In the securities area, the positions in the valuation areas are created in accordance with the respective differentiation as soon as a security is purchased in a securities account. Later purchases of the same security with the same differentiation values increase the existing positions. If you buy the same security with different differentiation values, such as a different securities account or valuation class, new positions are created. The general rule for securities positions is that all security purchases with the same differentiation values are managed as one position in the valuation areas.

The derivation of account assignment references for exposure subitems starts during the automated designation process (within the Hedge Management and Accounting of Net Open Exposures (FX Risk) process) when a exposure subitem is created.

The parallel positions for loans and their position indicators are generated with the disbursement of the loan.

**Note:**

If the derivation process failed and no account assignment reference could be derived by the system, you can manually enter the account assignment reference in the position indicator.

Using the Manage Position Indicator app, you can display, create manually, change, or delete the allocation of an account assignment reference to a treasury position. You can also reach the position indicator from the financial transaction data using the path in the menu More Environment Position Indicator .

You can change or delete the account assignment reference of a treasury position only if no posting has yet been made for that position. If a posting has already been made for a position, then the account assignment reference can be changed only by executing an account assignment reference transfer using the Transfer Account Assignment Reference app (App ID: TPM28).

###### Transfer Account Assignment Reference

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Account Assignment References > Transfer Account Assignment Reference | L5 | trm08 p.170 | loio `8e0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8e0dda531198434de10000000a174cb4.html?locale=en-US)

- App ID: TPM28


With the Transfer Account Assignment Reference app, you can post positions with their book value from one account assignment reference to another. This is similar to how financial positions can be transferred between G/L accounts.

You can also use the account assignment reference transfer to transfer the related profit and loss (P&L) postings of the current fiscal year up to the key date of the transfer. If an account assignment reference transfer has already taken place within the fiscal year, only the profit and loss postings since the last transfer date are relevant. The profit and loss items are read from the database and transfer posting flows are generated.

**Note:**

You can only perform the function once for each key date.

**Customizing**

Define Update Types and Assign Usages

Define update types for account assignment reference transfer and assign them to the usage Account Assignment Reference Transfer (9007).

Update Types for Account Assignment Reference Transfer

|Update Type|Description|
|---|---|
|AAREFDE1|Clear Asset Position from Old Account Assignment Ref.|
|AAREFDE2|Post Asset Position to New Account Assignment Ref.|
|AAREFDE3|Clear Liab. Position from Old Account Assignment Ref.|
|AAREFDE4|Post Liab. Position to New Account Assignment Ref.|
|AAREFTO1|Clear OCI Security (Positive) from Old Acct Assignment Ref.|
|AAREFTO2|Post OCI Security (Positive) to New Acct Assignment Ref.|
|AAREFTO3|Clear OCI Security (Negative) from Old Acct Assignment Ref.|
|AAREFTO4|Post OCI Security (Negative) to New Acct Assignment Ref.|
|AAREFTO5|Clear OCI FX (Positive) from Old Acct Assignment Ref.|
|AAREFTO6|Post OCI FX (Positive) to New Acct Assignment Ref.|
|AAREFTO7|Clear OCI FX (Negative) from Old Acct Assignment Ref.|
|AAREFTO8|Post OCI FX (Negative) to New Acct Assignment Ref.|
|AAREFTOD|Dummy Account Assignment Reference Transfer for OCI|
|AAREFTR1|Clear Book Value from old Account Assignment Reference|
|AAREFTR2|Post Book Value to new Account Assignment Reference|


Assign Update Types for Account Assignment Reference Transfer

Define the components to be included in the account assignment reference transfer and the corresponding update types for these components.

You restrict the components by selecting the account symbols. The system only considers account symbols with the following posting categories:

1 Position posting in position currency

- 4 Profit-related posting in position currency

- 5 Profit-related posting in payment currency

- 6 Other G/L account posting in position currency

- 7 Other G/L account posting in payment currency


Predefined settings of Assign Update Types for Account Assignment Reference Transfer configuration activity

|Account Symbol|Clear (D)|Post (D)|Clear (C)|Post (C)|
|---|---|---|---|---|
|1 Position (book value)|AAREFTR1|AAREFTR2|AAREFTR2|AAREFTR1|
|1.1 Asset Position (Derivatives)|AAREFTOD|AAREFTOD|AAREFDE1|AAREFDE2|
|1.2 Liability Position (Derivatives)|AAREFDE3|AAREFDE4|AAREFTOD|AAREFTOD|
|6.1.2.1 Revaluation reserves, security (positive)|AAREFTOD|AAREFTOD|AAREFTO1|AAREFTO2|
|6.1.2.2 Revaluation reserves, security (negative)|AAREFTO3|AAREFTO4|AAREFTOD|AAREFTOD|
|6.1.3.1 Revaluation reserves, foreign currency (positive)|AAREFTOD|AAREFTOD|AAREFTO5|AAREFTO6|
|6.1.3.2 Revaluation reserves, foreign currency (negative)|AAREFTO7|AAREFTO8|AAREFTOD|AAREFTOD|


Define Account Determination for Treasury and Risk Management

You define the account determination settings for the flows in the parallel valuation areas. The account determination settings define the accounts to be used when the flows are posted to Financial Accounting.

**Prerequisites**

The account assignment reference transfer must be the first posting-relevant business transaction for the position to be transferred as of the posting date of the account assignment reference transfer.

For the positions to be transferred, you need to ensure that no position-changing business transactions have status Scheduled before the posting date of the transfer.

**Activities**

- 1. Select the treasury positions for which you want to perform the account assignment transfer. To do this, you must choose the relevant product groups.


**Note:**

If you don’t choose a product group, no treasury positions are selected.

- 2. Enter the general selection criteria for the positions to be transferred:


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

If you use the integration with Public Sector Management, the system automatically derives the values for the fields fund, grant, functional area, and profit center from the master data records of the assigned cost center or WBS element, when you enter the cost center and the WBS element,

For more information, see also Integration with SAP Public Sector Management (PSM).

**Note:**

WBS element, cost center, profit center, and functional area are additional differentiation criteria available for OTC transactions and securities.

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

- 3. Special Selections

Account Assignment Reference

Enter the relevant account assignment references.

Terminated Deposit at Notice

No Zero Positions

If you set this indiator, zero positions are not selected.

Transfer of P&L Postings

If you set this indicator, the related P&L postings of the current fiscal year up to the key date are also transferred. If an account assignment reference transfer has already taken place within the fiscal year, the P&L postings since the last transfer date are relevant. The P&L items are read from the database and transfer posting flows are generated. Transfer of P&L Postings

- 4. Transfer Posting Parameter

- a. Enter the posting date (= key date on which transfer is to occur) and also the new account assignment reference.
- b. Enter the New Account Assignment Reference for all selected positions.


- 5. Output


**Note:**

If you set this indicator, and the system evaluates during the execution of the account assignment reference transfer, that you haven't assigned update types for an account symbol with posting category 4 Profit-related posting in position currency or 5 Profit-related posting in payment currency in the Assign Update Types for Account Assignment Reference Transfer configuration activity, you get the warning message 'No update type assigned to account symbol &1.' in the posting log.

**Recommendation:**

We recommend that you perform the transfer as a test run first. To do so, set the Test Run indicator.

After you have made the selection, the system displays a list of all positions to be transferred. After you have checked the positions to be transferred, choose Carry Out Transfer Posting. The general ledger transfer of the positions is performed and a posting log is output. You can branch from the posting log to the error log for the posting log.

Once you have performed the account assignment reference transfer, the system sets a posting block. This means that no postings with a key date earlier than the posting date of the account assignment reference transfer can be posted to the position.

**Related Information**

Account Assignment References Reverse Account Assignment Reference Transfer

###### Reverse Account Assignment Reference Transfer

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Account Assignment References > Reverse Account Assignment Reference Transfer | L5 | trm08 p.176 | loio `3a8d584576b747a095343163fd82aea2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3a8d584576b747a095343163fd82aea2.html?locale=en-US)

- App ID: TPM29


You can use this app to reverse an account asignment reference transfer.

If you need to reverse the account assignment reference transfer after the transfer has been updated, you can use this app.

**Activities**

- 1. Select the Treasury positions for which you wish to carry out the reversal of account assignment reference transfer. To do this, you must choose the relevant product groups.
- 2. Enter the general selection criteria for the positions to be transferred:


**Note:**

If you don’t choose a product group, no treasury positions are selected.

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

If you use the integration with Public Sector Management, the system automatically derives the values for the fields fund, grant, functional area, and profit center from the master data records of the assigned cost center or WBS element, when you enter the cost center and the WBS element,

For more information, see also Integration with SAP Public Sector Management (PSM).

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

- 3. In the Special Selections area you can enter the relevant account assignment references.
- 4. In the Posting Control area, you choose the Reversal Reason.

You can also enter the Posting Date and the Posting Period of the account assignment reference transfer.

The Test Run indicator is marked, after a successful test run you can run the reversal without setting this indicator.

- 5. In the Output area, the Display Positions Indicator is marked.
- 6. Execute the app.
- 7. The system lists the selected positions. If it is unable to find an account assignment reference, however, then neither the posting date nor the old account assignment reference are displayed for the position. This position is then not taken into account as part of the reversal.


Once the account assignment reference transfer has been reversed, the system displays a posting log from which you can branch to an error log.

**Supported Device Types**

Desktop

Tablet

**Related Information**

Transfer Account Assignment Reference

###### Assign Account Assignment Reference

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Account Assignment References > Assign Account Assignment Reference | L5 | trm08 p.179 | loio `8f0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8f0eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to:

display the existing account assignment reference allocations.

change the allocation of an account assignment reference to a Subledger Position.

You can only change an account assignment reference if no posting has yet been made for the position.

**Note:**

If a posting has already been made for a subledger position, then the account assignment reference can only be changed using an Account Assignment Reference Transfer. To access the account assignment reference transfer, you choose Accounting Account Assignment Reference Transfer Execute .

**Integration**

See also: Account Assignment References

**Features**

The functionality is only available in the back-end system. Find Assign Account Assignment Reference function in the application menus of the Money Market, Foreign Exchange, Securities, Derivatives, and Debt Management areas, choose Master Data

Position Indicator Assign Account Assignment Reference (transaction TPM3).

**Note:**

In the Loans Management area, choose Accounting Closing Operations Parallel Valuation Areas Position Indicator Assign Account Assignment Reference .

**Selection**

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

If you use the integration with Public Sector Management, the system automatically derives the values for the fields fund, grant, functional area, and profit center from the master data records of the assigned cost center or WBS element, when you enter the cost center and the WBS element,

For more information, see also Integration with SAP Public Sector Management (PSM).

**Note:**

WBS element, cost center, profit center, and functional area are additional differentiation criteria available for OTC transactions and securities.

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

Output

If a posting has already been made for a selected position, the corresponding row is merely displayed. You can no longer use this function to change or delete this allocation. The system lists the existing account assignment references according to the selections you made.

If no postings have yet been made for a position, you can change the entry in the Account assignment reference field. You have the following options:

Allocate a different account assignment reference to these positions

Delete the allocation ( Delete assignment) .

To have the account assignment reference determined by the system, choose the function key (Determine account assignment reference) . The system then uses the settings you have made in the IMG activities for automatic account assignment reference determination.

You can also create new allocations (( Create assignment ). In this case, the system checks if the position has been fully defined according to the Differentiation Terms The system lists the existing account assignment references according to the selections you made. for that position.

You cannot define a second allocation for a position.

To have the account assignment reference determined by the system, choose the function key (Determine account assignment reference) . The system then uses the rules you have made in Customizing for automatic account assignment reference determination.


**Activities**

In the application menus of the Money Market , Foreign Exchange, Securities, Derivatives, and Debt Management areas, choose Master Data Position Indicator Assign Account Assignment Reference .


In the Loans Management area, choose Accounting Closing Operations Parallel Valuation Areas Position Indicator Assign Account Assignment Reference .

