# Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) - SAP TRM Knowledge Base (branch split)

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

##### Hedge Accounting for Positions (P-HA)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) | L4 | trm09 p.206 | loio `49bff48439731b93e10000000a42189b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/49bff48439731b93e10000000a42189b.html?locale=en-US)

**Use**

With Hedge Accounting for Positions (P-HA), you can manage hedging relationships with which you document how you use financial instruments to hedge risks arising from your treasury positions. You can map the following types of hedging relationships using Hedge Accounting for Positions (P-HA):

Fair Value Hedges (FVH)

In accordance with the applicable regulations for hedge transactions (IAS/IFRS and US GAAP), you can map FVHs using a hedging relationship, as well as perform hedge accounting for the designated subpositions.

The following hedging scenarios are available for FVHs:

110 FVH: Price Risk with Adjusted Spot-Spot Value Without Foreign Currency

By means of this hedging scenario, you have the option of assigning your shareholdings (hedged items), which you have hedged against variations in their market value by using forward stock transactions (hedging instruments), to one another within a hedging relationship.

However, for stock positions in foreign currency, using this hedging relationship does not hedge the foreign exchange risk that also arises. For a valuation during the term of the hedging relationship, the security valuation is posted to the P/L (profit and loss statement), whereas the foreign currency valuation continues to be posted to OCI (other comprehensive income).

120 FVH: Stocks Hedged with OTC Option

Using this hedging scenario, you can hedge the price risk of stock positions by means of an OTC option. With this scenario, the price risk of the stock is hedged below the strike price.

130 FVH: Stock Hedged with Total Return Swap

- 150 FVH: Bond Hedged with Interest Rate Swap - Final Maturities Similar

- 151 FVH: Bond Hedged with Interest Rate Swap - Final Maturities Not Similar


160 FVH: Bond (Liability) Hedged with Interest Rate Swap - Final Maturities Similar

Units of Valuation (UoV)

You can map the units of valuation (UoV) permitted by German accounting principles using a hedging relationship. During the valuation, the market value of the hedged item is added to the market value of the hedging instrument, and only at this point are the book value and write-ups/write-downs calculated based on the applicable valuation settings.

A unit of valuation does not distinguish between the various risk categories, since the total market value is always considered.

With the legal regulations and comments as of June 30, 2010, mathematical effectiveness tests are not necessary for valuation units.

The following hedging scenarios are available for UoVs:

510 UoV: Forward Exchange Transactions as Hedging Instruments

- 520 UoV: Swaps as Hedging Instruments

- 521 UoV: Futures as Hedging Instruments

- 522 UoV: Forward Securities Transactions as Hedging Instruments

- 523 UoV: Forward Contracts as Hedging Instruments


- 530 UoV: Forward Exchange Transaction Hedged with Forward Exchange Transactions

- 531 UoV: Swap Hedged with Swaps

- 532 UoV: Forward Securities Transaction Hedged with Forward Securities Transactions


Cash Flow Hedges

A cash flow hedge (CFH) hedges the risk of fluctuations in a cash flow.

The following hedging scenarios are available for CFHs:

710 CFH: Security Hedged by Interest Rate Swap

720 CFH: Loan Hedged by Interest Rate Swap

Here the variable interest flows from the security/loan are converted into fixed interest rate interest items by the interest rate swap.

**Note:**

The Hedge Accounting for Exposure Items (FX Risk) process also uses the Hedge Accounting for Positions infrastructure, but the scenarios are handled differently. The process is integrated with the Hedge Management and Accounting of Net Open Exposures (FX Risk).

For more information about the process, see also Hedge Accounting for Exposure Items

**Features**

Manage Hedging Relationships

You create, designate, document, perform effectiveness tests, roll over, and dedesignate hedging relationships in the central function Manage Hedging Relationships (transaction TPM100).

Using the Group 1 (TPM_HR_GROUP1) and Group 2 (TPM_HR_GROUP2) fields, you can assign attributes to the hedging relationships. You can select the hedging relationships based on the groupings.

Documentation

You can generate the detailed documentation of hedging relationships either automatically or manually.

Effectiveness Test

You can perform prospective and retrospective effectiveness tests for fair value hedges and cash flow hedges.

The following methods are available for performing effectiveness tests:

|Effectiveness test method|Available For|Prospective or Retrospective|
|---|---|---|
|Dollar Offset Method|Fair Value Hedges Cash Flow Hedges*|Prospective Retrospective|
|Schleifer-Noise Method|Fair Value Hedges Cash Flow Hedges*|Prospective Retrospective|
|Linear Regression|Fair Value Hedges Cash Flow Hedges*|Prospective Retrospective|
|Critical Term Match Method|Cash Flow Hedges|Prospective|


* For cash flow hedges, the hedged item is replaced for the effectiveness test by the hypothetical derivative.

You can start the effectiveness test for several hedging relationships simultaneously using the Perform Effectiveness Test function (transaction TPM110).

There is a report available that provides an overview of the ineffective hedging relationships (transaction TPM112).

You need the structure curve for market data change rates to execute the prospective effectiveness test for the following scenarios:

110 FVH: Price Risk with Adjusted Spot-Spot Value Without Foreign Currency

120 FVH: Stocks Hedged with OTC Option

130 FVH: Stock Hedged with Total Return Swap

You can find the Define Market Data Structure Curves function in the application menu under Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Tools Define Structure Curve for Market Data Change Rates .

Assign the respective structure curve in the Manage Hedging Relationships function on the Effectiveness Test tab and then on the Test Plan tab in the Test Plan Details area.

Accounting

Enter net present values (transaction JBNV)

In this transaction, you can define net present values for financial transactions/loans. The values defined here can be included in the valuation (transaction TPM1).

Determine net present values (transaction TPM60)

You can use this transaction to calculate and store the net present value for the selected financial transactions of the Transaction Manager and for the loan for a specific key date. The net present values are calculated by the Market Risk Analyzer and saved (table VTVBAR, view V_VTVBAR). The results can be included in the valuation. You can look at the results using the Enter Net Present Values function.

Valuation of the designated hedged items and hedging transactions takes place in accordance with the hedge accounting rules during the term of the hedging relationships using the Execute Valuation function. The valuation flows of the

designated subposition are posted in accordance with the hedge accounting rules and the rules intended for the freestanding subposition for nonhedged positions in the position management procedure.

For a key date of a designation/dedesignation of a hedging relationship, the system automatically performs a valuation of the affected transactions/positions during the designation phase/dedesignation phase.

For hedging relationships that map fair value hedges, the Execute Classification function (transaction TPM101) is available. Using this function, you can classify valuation flows for the designated subpositions into effective and ineffective parts, and you can execute the Reverse Classification function (transaction TPM102).

If, during the term of a hedging relationship, there are sales/position outflows for the affected positions, you have to execute the Distribute Position Outflows to Subpositions function (transaction TPM103). Using this function, you specify the subpositions from which positions are removed.

Workflow

You can set up and release workflows for the business transactions Designation and Dedesignation and for the documentation.

Legacy Data Transfer

Using the legacy data transfer, you can also transfer hedging relationships managed outside of SAP systems to Hedge Accounting for Positions.

Legacy Data Transfer

**Initialization**

You can use initialization functions to transfer existing hedging relationships to a new valuation area.

**Limitations**

It is not possible to exchange the treasury positions in hedging relationships. Therefore, you cannot perform a valuation class transfer for treasury positions in hedging relationships. In addition, you cannot carry out a securities account transfer if the securities account is a differentiation criterion of the position.

**Prerequisites**

If you want to use these functions, you must first make the required settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions .

See also: Overview: Customizing (P-HA)

The following authorization objects are used in Hedge Accounting for Positions:

|Authorization Objects|Comments|
|---|---|
|T_HREL_AUT Authorization for Hedging Relationship|Using this authorization object, you can specify which activities are allowed for a hedging relationship in a company code and a valuation area. Possible Activities 01 Add or Generate 02 Change 03 Display 06 Delete 43 Release 91 Reactivate 98 Mark for Release|
|T_THXE_ET Effectiveness Tests|Using this authorization object, you manage how the effectiveness test is performed within a hedging relationship of P-HA. In the following functions, the system checks whether the user is authorized to perform the effectiveness test for the company code, the valuation area, the hedging category, and the hedging profile: Manage Hedging Relationships (transaction TPM100) Perform Effectiveness Test (transaction TPM110) Possible Activities 01 Create or Generate 02 Change 03 Display |


|Authorization Objects|Comments|
|---|---|
| |06 Delete 94 Overwrite|


To be able to use the functions of the Risk Analyzer for calculating the net present values of positions and subpositions or financial transactions, you have to make the necessary settings in Customizing for the Risk Analyzer. You need to have activated financial object integration. The necessary evaluation types need to have been created and assigned.

For performing effectiveness tests and valuations, the necessary market data needs to have been entered in the market data tables. The necessary market structure curves, market data scenarios, and market data shifts must be maintained.

**Process**

Before creating a hedging relationship

You must create the hedged items and hedging instruments in Transaction Management.

Creation and designation of the hedging relationship

- 1. Create the hedging relationship in the Manage Hedging Relationships function (transaction TPM100) and assign the hedged item(s) and the hedging instrument(s) on the tabs for this.

- 2. Designation Phase


**Note:**

The positions assigned to a hedging relationship (as hedged items or as a hedging instrument) are managed in subpositions in Position Management, whereby a distinction is made between the freestanding subpositions and the designated subpositions.

A freestanding subposition is generated for the positions by assigning a hedged item and a hedging instrument to a hedging relationship.

If designation then occurs later on, the freestanding subpositions are reduced by the designated part and a subposition is generated for the designated part.

You can see whether subpositions can exist - and if so, which - for positions in the position list (transaction TPM12). This list contains a Subpositions column in which each position that has a subposition(s) has an icon. You can choose the icon to display the subpositions. In the Free column of this list, you can see whether the respective subposition is a freestanding or a designated subposition.

- a. Execute the Designate function for the hedging relationship.

Enter the designation amounts and, if necessary, the alternative market data for the designation.

The hedging relationship is converted to the status Planned Designation. For cash flow hedges, the hypothetical derivative is also generated.

- b. If execution of effectiveness tests is planned for the selected type of hedging relationship, perform a prospective effectiveness test for the hedging relationship. You do this in the Manage Hedging Relationships function on the Effectiveness Test tab.
- c. Now you can/must create and release the documentation for the hedging relationship in the Manage Hedging Relationships function on the Documentation tab.


**Note:**

Whether or not the documentation is required or optional depends on your settings for the selected hedging profile in the Customizing activity Define Hedging Profiles.

A release approval workflow can be defined for releasing the documentation.

d. Designate the hedging relationship using the Change Designation function.

The hedging relationship receives the status Designated.

**Note:**

A release approval workflow can be defined for releasing the designation.

- 3. Depending on the setting in Customizing for the derived business transactions, they may have to be posted using the Fix and Post Derived Business Transactions function (transaction TPM18).


Managing the Hedging Relationship During its Term

If effectiveness tests have been specified for the hedging relationship, you have to perform retrospective and prospective effectiveness tests (either using a test plan or manually) during the term of the hedging relationship. As long as they are effective, the valuation results are updated in accordance with the hedge accounting rules.

**Note:**

You can start the effectiveness test for several hedging relationships simultaneously using the Perform Effectiveness Test function (transaction TPM110).

If the effectiveness test shows the hedging relationship to be ineffective, the hedging relationship must be dedesignated immediately and hedge accounting is not allowed to take place.

The hedged items and hedging instruments of the hedging relationships can be valuated during the term of the hedging relationship. Valuation is performed using the Execute Valuation function (transaction TPM1) of the Transaction Manager. During valuation, the system first checks whether the results of the last effectiveness test were positive, and whether the test is still valid at the time valuation is performed. If these conditions are met, the system valuates the designated subpositions in accordance with the hedge accounting rules. The freestanding subpositions are valuated according to the valid position management procedure.

After valuation of the positions, for the FVH hedging relationships, you can perform classification (transaction TPM101) for the valuation flows of the designated subpositions to group them into effective and ineffective parts.

If parts of the positions in the hedging relationship are sold during its term, you must define which subposition this stems from (freestanding or designated) using the Distribute Position Outflows to Subpositions function (transaction TPM103). If the designated subposition is affected, the position assigned to this must also be reduced accordingly in the hedging relationship.

Rollover of the Hedging Relationship

You can roll over (as a whole or in part) hedging relationships that use forward securities transactions.

You can roll over a hedging relationship in one of two different ways:

Automatic rollover of the hedging relationship by means of rollover of the forward securities transaction

If you roll over the forward securities transaction that is part of a hedging relationship, the system automatically rolls over the hedging relationship. The planned designation date of the hedging relationship is updated with the new end date of the rolled over forward securities transaction.

Rollover of the hedging relationship by means of replacing the designated forward securities transaction at the end of its term with a new forward securities transaction

With both of these methods, it is possible to roll over the hedging relationship as a whole or only a partial amount of the hedging relationship.

Dedesignation at the End of the Hedging Relationship

- 1. The dedesignation is also performed in a two-step process. When you execute the Dedesignate function, the hedging relationship receives the status Planned Dedesignation.
- 2. On the key date of the dedesignation, if necessary, you now perform a retrospective effectiveness test for the hedging relationship.
- 3. After the effectiveness test has been performed successfully, you can execute the dedesignation in its final form. The system automatically performs the last valuation of the hedging relationship.
- 4. Depending on the setting in Customizing for the derived business transactions, they may have to be posted using the Fix and Post Derived Business Transactions function (transaction TPM18).

- 5. For FVH hedging relationships, you must then perform classification (transaction TPM101) of the valuation flows.


**Note:**

If a release approval workflow was defined for the dedesignation, the dedesignation must also be released.

**More Information**

Manage Hedging Relationships

###### Hedge Accounting Rules

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Hedge Accounting Rules | L5 | trm09 p.213 | loio `af5312e21a174491a05d5dcdd686fa26` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/af5312e21a174491a05d5dcdd686fa26.html?locale=en-US)

A hedge accounting rule (HA rule) is assigned to each scenario in a system table.

These rules specify how the hedged item and the hedging transaction are valuated before designation, during designation, during the term, and during dedesignation of the hedging relationship.

|Scenario|Hedge Accounting Rule|
|---|---|
|110 FVH: Price Risk with Adjusted Spot-Spot Value Without Foreign Currency|100 Hedge Adjustment P&L|
|120 FVH: Stocks Hedged with OTC Option|150 Hedge Adjustment P&L / OCI|
|130 FVH: Stock Hedged with Total Return Swap|100 Hedge Adjustment P&L|
|150 FVH: Bond Hedged with Interest Rate Swap - Final Maturities Similar|200 Amortization / Hedge Adjustment P&L / Credit Spread OCI|
|151 FVH: Bond Hedged with Interest Rate Swap - Final Maturities Not Similar|200 Amortization / Hedge Adjustment P&L / Credit Spread OCI|


|Scenario|Hedge Accounting Rule|
|---|---|
|160 FVH: Bond (Liability) Hedged with Interest Rate Swap - Final Maturities Similar|300 Amortization / Hedge Adjustment P&L|
|510 UoV: Forward Exchange Transactions as Hedging Instruments|400 Valuation Unit|
|520 UoV: Swaps as Hedging Instruments|400 Valuation Unit|
|521 UoV: Futures as Hedging Instruments|400 Valuation Unit|
|522 UoV: Forward Securities Transactions as Hedging Instruments|400 Valuation Unit|
|523 UoV: Forward Contracts as Hedging Instruments|400 Valuation Unit|
|530 UoV: Forward Exchange Transaction Hedged with Forward Exchange Transactions|400 Valuation Unit|
|531 UoV: Swap Hedged with Swaps|400 Valuation Unit|
|532 UoV: Forward Securities Transaction Hedged with Forward Securities Transactions|400 Valuation Unit|
|710 CFH: Security Hedged with Interest Rate Swap|500 Hedge Adjustment OCI / Write-Up and Write-Down P&L|
|720 CFH: Loan Hedged with Interest Rate Swap|500 Hedge Adjustment OCI / Write-Up and Write-Down P&L|

###### HA Rule 100: Hedge Adjustment P&L

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Hedge Accounting Rules > HA Rule 100: Hedge Adjustment P&L | L6 | trm09 p.214 | loio `27923097f65e42d290727b11ec2517dc` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/27923097f65e42d290727b11ec2517dc.html?locale=en-US)

**Use**

The Hedge Accounting rule 100Hedge Adjustment P&L is used in the following hedging relationships:

110FVH: Stock Hedged with Forward Stock Transaction

130FVH: Stock Hedged with Total Return Swap

With this HA rule, the write-ups and write-downs for the valuation of the hedged stock are posted as a hedge adjustment. The hedging instrument is valuated as before.

**Prerequisites**

In Customizing for the Transaction Manager under General Settings Accounting , you need to make the required settings for the valuation in the following Customizing activities:

In the Customizing activity Assign Update Types for Valuation, assign the update types to be used for the flows of the valuation (such as for the write-ups and write-downs).

In Customizing activity Assign Alternative Update Types for Position Outflows, enter the alternative update types for posting the hedge adjustment (condition: P-HA: Hedge Adjustment). In this way, the hedge adjustment is posted to a separate (P&L) account.

**Features**

Valuation Before the Start of a Hedging Relationship

Write-ups and write-downs in the security are written to the position component 1002 (Security Valuation).

The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

Valuation at the Start of the Hedging Relationship (Designation)

During a designation, transfer postings are made from the free-standing subpositions to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of derived business transactions.

Valuation at the start of the hedging relationship uses the same procedure as valuation before the start of the hedging relationship.

Valuations During the Hedging Relationship

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

With a key date valuation, a check is run as to whether the hedging relationship is effective both retrospectively and prospectively. The result of the valuation can only be posted if effectiveness is given. In the case of ineffectiveness, the hedging relationship has to be dedesignated manually.

Valuations as part of derived business transactions also affect business transactions in the future. For example, with a designation, valuation is performed at the time of the dedesignation. For this reason, the existence of a valid effectiveness test is not a prerequisite for creating the derived business transaction. Consequently, valuation as part of a derived business transaction can

also be performed for an ineffective hedging relationship. It is necessary for there to be a valid effectiveness test at the time when you fix the derived business transaction. In the case of ineffectiveness, the hedging relationship has to be dedesignated manually.

Hedged Item Valuation

In the case of effectiveness

Write-ups and write-downs in the security are written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (For internal calculation: To be classified). The update rules are determined from the settings made in the Customizing activity Assign Alternative Update Types for Position Outflows.

In the case of ineffectiveness

Write-ups and write-downs in the security are written to the position component 1002 (Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

Hedging Instrument Valuation

In the case of effectiveness

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation) as well as to position component 1300 (For internal calculation: To be classified). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

In the case of ineffectiveness

Write-ups and write-downs in the security are written to the position component 1002 (Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

A classification (transaction TPM101) can be used to split the valuation results determined into effective and ineffective portions. For this, the position component 1300 (For internal calculation: To be classified) of the hedged item and of the hedging instrument is transferred to the position components 1302 (Effective) and 1303 (Ineffective). Once the classification has been performed, the position component 1300 (For internal calculation: To be classified) acquires the value zero.

**Example:**

1. Valuation

Valuation of a stock (hedged item) and of a forward stock transaction (hedging instrument). The hedging relationship is effective on the valuation key date.

Stock: Write-up +100

Forward stock transaction: Write-down -90

Values of the position components for the stock

|1300 For internal calculation: To be classified|100.00|
|---|---|
|1301 Hedge Adjustment|100.00|
|1303 Effective|0|
|1304 Ineffective|0|


Values of the position components for the forward stock transaction

|1002 Security Valuation|-90.00|
|---|---|
|1300 For internal calculation: To be classified|-90.00|
|1303 Effective|0|
|1304 Ineffective|0|


2. Classification

After classification has been performed, the following values are achieved for the position components:

Values of the position components for the stock

|1300 For internal calculation: To be classified|0|
|---|---|
|1301 Hedge Adjustment|100.00|
|1303 Effective|90.00|
|1304 Ineffective|10.00|


Values of the position components for the forward stock transaction

|1002 Security Valuation|-90.00|
|---|---|
|1300 For internal calculation: To be classified|0|


|1303 Effective|-90.00|
|---|---|
|1304 Ineffective|0|


Valuation at the End of the Hedging Relationship

With a dedesignation, the hedged subpositions or the subpositions to be hedged are transferred to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated for the last time as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the valuation results are classified as part of a derived business transaction.

Manual Designation of an Ineffective Hedging Relationship

With a manual dedesignation, an additional retrospective effectiveness test is included in the test plan. This test needs to be executed manually. If the test is effective, the valuation performed as part of the dedesignation is performed in the Effective mode. If the test is ineffective, the valuation performed as part of the dedesignation is performed in the Ineffective mode. A classification is also performed as part of a derived business transaction.

###### HA Rule 150: Hedge Adjustment P&L / OCI

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Hedge Accounting Rules > HA Rule 150: Hedge Adjustment P&L / OCI | L6 | trm09 p.217 | loio `c66cabab0b3a4483961f1e509ab09153` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c66cabab0b3a4483961f1e509ab09153.html?locale=en-US)

**Use**

The HA rule 150Hedge Adjustment P&L / OCI is used in the hedging scenario 120FVH: Stocks Hedged with OTC Option.

**Prerequisites**

In Customizing for the Transaction Manager under General Settings Accounting , you need to make the required settings for the valuation in the following Customizing activities:

In the Customizing activity Assign Update Types for Valuation, assign the update types to be used for the flows of the valuation (such as for the write-ups and write-downs).

In Customizing activity Assign Alternative Update Types for Position Outflows, enter the alternative update types for posting the hedge adjustment (condition: P-HA: Hedge Adjustment). In this way, the hedge adjustment is posted to a separate (P&L) account.

**Features**

The HA rule 150Hedge Adjustment P&L / OCI is almost identical to rule 100 Hedge Adjustment P&L apart from the following exception: In the case of the HA rule 100, the entire write-up/write-down amount is written to the components 1301 (Hedge Adjustment) and 1300 (For internal calculation: To be classified) during valuation. In the case of the HA rule 150, the write-up amount that is written to components 1301 and 1300 during valuation does not exceed a threshold value. The amount that is in excess of the threshold value is written to the component 1002 (Security Valuation) using a separate posting line. The threshold value is determined from the strike price of the stock option.

###### HA Rule 200: Amortization / Hedge Adjustment P&L / Credit Spread OCI

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Hedge Accounting Rules > HA Rule 200: Amortization / Hedge Adjustment P&L / Credit Spread OCI | L6 | trm09 p.217 | loio `06a16b9421ed4f38912670e79218cd92` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/06a16b9421ed4f38912670e79218cd92.html?locale=en-US)

**Use**

The Amortization / Hedge Adjustment P&L / Credit Spread rule is used in the following scenarios:

- 150FVH: Bond Hedged with Interest Rate Swap - Final Maturities Similar

- 151FVH: Bond Hedged with Interest Rate Swap - Final Maturities Not Similar


**Prerequisites**

In Customizing for the Transaction Manager under General Settings Accounting , you need to make the required settings for the valuation in the following Customizing activities:

In the Customizing activity Define Position Management Procedure, you need to include the following valuation steps in the position management procedure for these positions:

- 1. Amortization
- 2. One-step valuation or security valuation


In the Customizing activity Assign Update Types for Valuation, assign the update types to be used for the flows of the valuation (such as for the write-ups and write-downs).

In Customizing activity Assign Alternative Update Types for Position Outflows, enter the alternative update types for posting the hedge adjustment (condition: P-HA: Hedge Adjustment). In this way, the hedge adjustment is posted to a separate (P&L) account.

**Features**

Valuation Before the Start of a Hedging Relationship

Amortizations are assigned to the position components 1007 (= Amortization). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation". Write-ups and write-downs in the security are written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation".

Valuation at the Start of the Hedging Relationship (Designation)

During a designation, transfer postings are made from the free-standing subpositions to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of a derived business transaction. Amortizations are assigned to the position components 1007 (= Amortization). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation". Write-ups and writedowns in the security are written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation". In addition, the write-up or write-down is written to the component 1029 (= Hedge Amortization), whereby the derived component 9004 (= Amortized Acquisition Costs) is adjusted to the fair value at the time of designation. This produces a new effective interest rate for subsequent amortizations. The system determines the update type using the settings in the Customizing activity "Assign Update Types for Derived Business Transactions" in the "P-Hedge Accounting: Transfer Postings Between Subpositions" area in the "Hedge Amortization" field.

Valuations During the Hedging Relationship

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions.

With a key date valuation, a check is run as to whether the hedging relationship is effective both retrospectively and prospectively. The result of the valuation can only be posted if effectiveness is given. In the case of ineffectiveness, the hedging relationship has to be dedesignated manually.

Valuations as part of derived business transactions also affect business transactions in the future (for example, with a designation, valuation is performed at the time of the dedesignation). For this reason, the existence of a valid effectiveness test is not a prerequisite for creating the derived business transaction. Consequently, valuation as part of a derived business transaction can also be performed in the case of an ineffective hedging relationship. However, at the time when you fix the derived business transaction, the hedging relationship must be effective. In the case of ineffectiveness, the hedging relationship has to be dedesignated manually.

Hedged Item Valuation

In the case of effectiveness

Amortizations are assigned to the position component 1007 (Amortization). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation. Write-ups and writedowns in the security are divided into two parts:

Hedge Adjustment

The hedge adjustment results from the difference between the hedge fair value and the hedge amortized costs. The hedge fair value is calculated during valuation by discounting the future cash flows.

Credit Spread

The credit spread results from the difference between the market value of the bond (transaction FW17) and the hedge fair value.

A detailed log for the valuation log shows how the hedge adjustment and the credit spread are calculated.

The hedge adjustment is written to position component 1301 (Hedge Adjustment) as well as to position component 1300 (For internal calculation: To be classified). The update date is calculated using the Customizing activity Alternative Update Types for Position Outflows.

The credit spread is written to the position component 1002 (Security Valuation). The update type is calculated using the settings made in the Customizing activity Assign Update Types for Valuation (update type for Security Write-Up or Security Write-Down).

In the case of ineffectiveness

Amortizations are assigned to the position component 1007 (= Amortization). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation". Write-ups and writedowns in the security are divided into two parts:

Hedge Adjustment

The hedge adjustment results from the difference between the hedge fair value and the hedge amortized costs. The hedge fair value is calculated during valuation by discounting the future cash flows.

Credit Spread

The credit spread results from the difference between the market value of the bond (transaction FW17) and the hedge fair value.

A detailed log for the valuation log shows how the hedge adjustment and the credit spread are calculated. The hedge adjustment is written to the position component 1002 (Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

The credit spread is written to the position component 1002 (Security Valuation). The update type is calculated using the settings made in the Customizing activity Assign Update Types for Valuation (update type for Security Write-Up or Security Write-Down).

Hedging Instrument Valuation

In the case of effectiveness

Write-ups and write-downs in the security are written to position component 1002 (Security Valuation) as well as to position component 1300 (For internal calculation: To be classified). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

In the case of ineffectiveness

Write-ups and write-downs in the security are written to the position component 1002 (Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation".

A classification (transaction TPM101) can be used to split the valuation results determined into effective and ineffective portions. For this, the position component 1300 (For internal calculation: To be classified) of the hedged item and of the hedging instrument is transferred to the position components 1302 (Effective) and 1303 (Ineffective). Once the classification has been performed, the position component 1300 (For internal calculation: To be classified) acquires the value zero.

Valuation at the End of the Hedging Relationship

With a dedesignation, the system transfers the hedged subpositions or the subpositions to be hedged to the free-standing subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. In addition, the component 1024 (Hedge Amortized Costs) or the derived component 9004 (Amortized Acquisition Costs) is adjusted, producing a new effective interest rate on the free-standing subposition. The system determines the update type using the settings in the Customizing activity Assign Update Types for Derived Business Transactions in the P-Hedge Accounting: Transfer Postings Between Subpositions area in the Hedge Amortization field. A classification is also performed as part of a derived business transaction.

Manual Dedesignation of an Ineffective Hedging Relationship

With a manual dedesignation, an additional retrospective effectiveness test is included in the test plan. This test needs to be executed manually. If the test is effective, the valuation performed as part of the dedesignation is performed in the "Effective" mode. If the test is ineffective, the valuation performed as part of the dedesignation is performed in the Ineffective mode.

Graphical Display

[figure TRM09-F055 - Hedge Adjustment: FVH Bond Hedged with Interest Rate Swap (Fixed Payer Swap), Available for Sale]

Hedge Adjustment: FVH Bond Hedged with Interest Rate Swap (Fixed Payer Swap), Available for Sale

###### HA Rule 300: Amortization / Hedge Adjustment P&L

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Hedge Accounting Rules > HA Rule 300: Amortization / Hedge Adjustment P&L | L6 | trm09 p.221 | loio `fa2cdd49411044bdbc3c6b07c833ff27` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fa2cdd49411044bdbc3c6b07c833ff27.html?locale=en-US)

**Use**

The HA rule 300Amortization / Hedge Adjustment P&L is used in the hedging scenario 160FVH: Bond (Liability) Hedged with Interest Rate Swap - Final Maturities Similar.

**Prerequisites**

In Customizing for the Transaction Manager under General Settings Accounting , you need to make the required settings for the valuation in the following Customizing activities:

In the Customizing activity Define Position Management Procedure, you need to include the following valuation steps in the position management procedure for these positions:

- 1. Amortization
- 2. One-step valuation or security valuation


In the Customizing activities Define One-Step Price Valuation Procedure and Define Security Valuation Procedure, set the Execute Solely in the Case of Hedge Accounting checkbox.

In the Customizing activity Assign Update Types for Valuation, assign the update types to be used for the flows of the valuation (such as for the write-ups and write-downs).

In Customizing activity Assign Alternative Update Types for Position Outflows, enter the alternative update types for posting the hedge adjustment (condition: P-HA: Hedge Adjustment). In this way, the hedge adjustment is posted to a separate (P&L) account.

**Features**

Valuation Before the Start of a Hedging Relationship

Hedged item:

Amortizations are assigned to the position component 1007 (= Amortization). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation". Before the start and after the end of the hedging relationship, no security valuation occurs for the hedged item.

Hedging Instrument:

Write-ups and write-downs in the security are written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

Valuation at the Start of the Hedging Relationship (Designation)

With a designation, the system transfers the hedged subpositions or the subpositions to be hedged from the free-standing subpositions. Before these transfer postings are made, the free-standing subpositions are valuated as part of a derived business transaction: Hedged item: Amortizations are assigned to the position component 1007 (= Amortization). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation". No security valuation is performed for the hedged item. Hedging Instrument: Write-ups and write-downs in the security are written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

Valuations During the Hedging Relationship

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions. With a key date valuation, a check is run as to whether the hedging relationship is effective both retrospectively and prospectively. The result of the valuation can only be posted if effectiveness is given. In the case of ineffectiveness, the hedging relationship has to be dedesignated manually. Valuations as part of derived business transactions also affect business transactions in the future (for example, with a designation, valuation is performed at the time of the dedesignation). For this reason, the existence of a valid effectiveness test is not a prerequisite for creating the derived business transaction. Consequently, valuation as part of a derived business transaction can also be performed for an ineffective hedging relationship. However, at the time when you fix the derived business transaction, the hedging relationship must be effective. In the case of ineffectiveness, the hedging relationship has to be dedesignated manually (see Dedesignation of an Ineffective Hedging Relationship).

Hedged Item Valuation

In the case of effectiveness

Amortizations are assigned to the position component 1007 (= Amortization). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation". The write-ups and write-downs in the security result from the difference between the fair value at the time of the designation (this

value has to be entered manually during designation) and the market value on the valuation key date. A detailed log for the valuation log shows how the write-up/write-down is calculated.

Write-ups and write-downs in the security are written to position component 1301 (= Hedge Adjustment) as well as to position component 1300 (For internal calculation: To be classified). The update type is determined using the settings made in the Customizing activity "Assign Update Types for Valuation" and can be overwritten with a different update type using the Customizing activity "Alternative Update Types for Position Outflows" (condition: PHedge Accounting: Hedge Adjustment). In this way, the hedge adjustment can be posted in a separate account.

In the case of ineffectiveness

Amortizations are assigned to the position component 1007 (= Amortization). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation". The write-ups and write-downs in the security result from the difference between the fair value at the time of the designation (this value has to be entered in the market data container during designation) and the market value on the valuation key date. A detailed log for the valuation log shows how the write-up/write-down is calculated. Write-ups and writedowns are written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

Hedging Instrument Valuation

In the case of effectiveness

Write-ups and write-downs in the security are written to position component 1002 (= Security Valuation) as well as to position component 1300 (For internal calculation: To be classified). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

In the case of ineffectiveness

Write-ups and write-downs in the security are written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

A classification (transaction TPM101) can be used to split the valuation results determined into effective and ineffective portions. For this, the position component 1300 (= For internal calculation: To be classified) of the hedged item and of the hedging instrument is transferred to the position components 1302 (Effective) and 1303 (Ineffective). Once the classification has been performed, the position component 1300 (For internal calculation: To be classified) acquires the value zero.

Valuation at the End of the Hedging Relationship

During a dedesignation, transfer postings are made from the hedged subpositions or to the subpositions to be hedged to the freestanding subpositions. Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated as part of derived business transactions. Valuation at the end of the hedging relationship uses the same procedure as valuation during the hedging relationship. A classification is also performed as part of a derived business transaction.

Manual Dedesignation of an Ineffective Hedging Relationship

With a manual dedesignation, an additional retrospective effectiveness test is included in the test plan. This test needs to be executed manually. If the test is effective, the valuation performed as part of the dedesignation is performed in the "Effective" mode. If the test is ineffective, the valuation performed as part of the dedesignation is performed in the "Ineffective" mode.

Graphical Display

[figure TRM09-F056 - Hedge Adjustment (Bond (Liability) Hedged with Fixed Payer Swap)]

Hedge Adjustment (Bond (Liability) Hedged with Fixed Payer Swap)

###### HA Rule 400: Valuation Unit

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Hedge Accounting Rules > HA Rule 400: Valuation Unit | L6 | trm09 p.224 | loio `54c86801cd7e443ca2f9c5a7198b0ec4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/54c86801cd7e443ca2f9c5a7198b0ec4.html?locale=en-US)

**Use**

The HA rule 400: Valuation Unit is used in the following hedging scenarios:

510 UoV: Forward Exchange Transactions as Hedging Instruments

- 520 UoV: Swaps as Hedging Instruments

- 521 UoV: Futures as Hedging Instruments

- 522 UoV: Forward Securities Transactions as Hedging Instruments

- 523 UoV: Forward Transactions as Hedging Instruments


- 530 UoV: Forward Exchange Transactions Hedged with Forward Exchange Transactions

- 531 UoV: Swaps Hedged with Swaps

- 532 UoV: Bonds Hedged with Security Transactions


**Features**

Valuation Before the Start of a Hedging Relationship

The positions combined in a valuation unit can be valuated independently of each other. Write-ups and write-downs in the security are written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation".

Valuation at the Start of the Hedging Relationship (Designation)

During a designation, transfer postings are made from the free-standing subpositions to the hedged subpositions to be hedged. In the case of a valuation rule "Valuation Unit", no implied valuations of the free-standing positions are made prior to these transfer postings.

Valuations During the Hedging Relationship

With valuations, it is ensured that all position that are combined in a valuation unit are valuated together. It is not possible to valuate a single hedged item or a single hedging instrument. For the valuation of the hedged item, the market values of the hedging instruments are added to the market value of the hedged item. In this way, a write-up/write-down is performed on this total amount. All hedging instruments are valuated at the market value of zero. A detailed log for the valuation log shows how the market value of the hedged item is determined. Write-ups and write-downs in the security are written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity "Assign Update Types for Valuation".

Valuation at the End of the Hedging Relationship

During a dedesignation, transfer postings are made from the hedged subpositions or to the subpositions to be hedged to the freestanding subpositions. In the case of a valuation rule "Valuation Unit", no implied valuations of the free-standing positions are made prior to these transfer postings.

###### HA Rule 500: Hedge Adjustment OCI / Write-Ups and Write-Downs P&L

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Hedge Accounting Rules > HA Rule 500: Hedge Adjustment OCI / Write-Ups and Write-Downs P&L | L6 | loio `bd3b8ac5c11446b3a10e4b7247b9c798` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bd3b8ac5c11446b3a10e4b7247b9c798.html?locale=en-US)

**Use**

The HA rule 500Hedge Adjustment OCI / Write-Ups and Write-Downs P&L is used in the following hedging scenarios:

710 CFH: Security Hedged with Interest Rate Swap

720 CFH: Loan Hedged with Interest Rate Swap

**Prerequisites**

In Customizing for the Transaction Manager under General Settings Accounting , you need to make the required settings for the valuation in the following Customizing activities:

In the Customizing activity Assign Update Types for Valuation, assign the update types to be used for the flows of the valuation (such as for the write-ups and write-downs).

In Customizing activity Assign Alternative Update Types for Position Outflows, enter the alternative update types for posting the hedge adjustment (condition: P-HA: Hedge Adjustment).

In the Customizing activity Assign Update Types for Derived Business Transactions, define the update types for the classification in the P-Hedge Accounting: Classification area.

**Features**

Valuation Before the Start of a Hedging Relationship

Amortizations are assigned to the position component 1007 (= Amortization).

Write-ups and write-downs in the security are written to the position component 1002 (= Security Valuation).

The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

Valuation at the Start of the Hedging Relationship (Designation)

During a designation, transfer postings are made from the free-standing subpositions to the hedged subpositions or to the subpositions to be hedged. Before these transfer postings are made, the free-standing subpositions are valuated as part of a derived business transaction. Valuation at the start of the hedging relationship uses the same procedure as valuation before the start of the hedging relationship.

Valuations During the Hedging Relationship

Valuations during hedging relationships are performed as key date valuations (transaction TPM1) or as part of derived business transactions. Examples of valuations as part of derived business transactions are the valuations for designation and dedesignation.

With a key date valuation, a check is run as to whether the hedging relationship is effective both retrospectively and prospectively.

The result of the valuation can only be posted if effectiveness is given.

In the case of ineffectiveness, the hedging relationship has to be dedesignated manually. Valuations as part of derived business transactions also affect business transactions in the future (for example, with a designation, valuation is performed at the time of the dedesignation). For this reason, the existence of a valid effectiveness test is not a prerequisite for creating the derived business transaction. Consequently, valuation as part of a derived business transaction can also be performed for an ineffective hedging relationship. However, at the time when you fix the derived business transaction, the hedging relationship must be effective. In the case of ineffectiveness, the hedging relationship has to be dedesignated manually (see also: Dedesignation of an Ineffective Hedging Relationship).

Hedging Instrument Valuation

In the case of effectiveness

Write-ups and write-downs in the security are divided into an effective part and an ineffective part. For this, the value change of the hedging instrument is classified with the value change of the hedged item.

The effective write-up/write-down amount is written to the position component 1301 (= Hedge Adjustment). The update type is determined using the settings made in the Customizing activity Assign Update Types for Valuation and can be overwritten with a different update type using the Customizing activity Alternative Update Types for Position Outflows (condition: P-Hedge Accounting: Hedge Adjustment). This enables you to post the hedge adjustment to a separate account.

In addition, a separate posting item is used to write the effective write-up/write-down amount to the position component 1303 (= Effective). The system determines the update type using the settings in the Customizing activity Assign Update Types for Derived Business Transactions in the P-Hedge Accounting: Classification area.

The ineffective write-up/write-down amount is written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation. In addition, a separate posting item is used to write the ineffective write-up/write-down amount to the

position component 1304 (= Ineffective). The system determines the update type using the settings in the Customizing activity Assign Update Types for Derived Business Transactions in the P-Hedge Accounting: Classification area.

In the case of ineffectiveness

Amortizations are assigned to the position component 1007 (= Amortization). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

Write-ups and write-downs in the security are divided into an effective part and an ineffective part. For this, the value change of the hedging instrument is classified with the value change of the hedged item. A detailed log for the valuation log shows how the split of the valuation result is achieved.

The effective write-up/write-down amount is written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation. In addition, a separate posting item is used to write the effective write-up/write-down amount to the

position component 1303 (= Effective). The system determines the update type using the settings in the Customizing activity Assign Update Types for Derived Business Transactions in the P-Hedge Accounting: Classification area.

The ineffective write-up/write-down amount is written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation. In addition, the ineffective write-up/write-down amount is written to the position component 1304 (= Ineffective). The system determines the update type using the settings in the Customizing activity Assign Update Types for Derived Business Transactions in the P-Hedge Accounting: Classification area.

Hedged Item Valuation

In the case of effectiveness and in the case of ineffective

Amortizations are assigned to the position component 1007 (= Amortization). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation. Write-ups and writedowns in the security are written to the position component 1002 (= Security Valuation). The update type is determined on the basis of the settings made in the Customizing activity Assign Update Types for Valuation.

Valuation at the End of the Hedging Relationship

During a dedesignation, transfer postings are made from the hedged subpositions or to the subpositions to be hedged to the freestanding subpositions.

Before these transfer postings are made, the hedged subpositions or the subpositions to be hedged are valuated as part of derived business transactions. Valuation at the end of the hedging relationship corresponds to valuation before the start of the hedging relationship.

Manual Dedesignation of an Ineffective Hedging Relationship

With a manual dedesignation, an additional retrospective effectiveness test is included in the test plan. This test needs to be executed manually.

If the test is effective, the valuation performed as part of the dedesignation is performed in the "Effective" mode.

If the test is ineffective, the valuation performed as part of the dedesignation is performed in the "Ineffective" mode.

###### Overview: Customizing (P-HA)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Overview: Customizing (P-HA) | L5 | trm09 p.227 | loio `3b92a9f4c04b4acfa724d78432a72588` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3b92a9f4c04b4acfa724d78432a72588.html?locale=en-US)

|Customizing Activity|Use|Activities|
|---|---|---|
|Define and Activate Groups|You can use groups to enter additional information on hedging relationships in the function Manage Hedging Relationships (transaction TPM100). You do this on the Hedging Relationship Details tab in the Grouping Fields screen area.|1. Set the Grouping Active indicator for grouping 1, 2, or 3. 2. Define a description for the grouping. 3. Save your entries. |


|Customizing Activity|Use|Activities|
|---|---|---|
| |For grouping 1 and grouping 2, you define the values to be assigned in the application menu for Hedge Accounting for Positions under Treasury and Risk Management Transaction Manager Hedge Accounting for Positions Master Data Grouping Key 1 / Grouping Key 2 . If you activate the 3rd grouping, you can define a text of your choice for a hedging relationship in this field.| |
|Number Ranges|Here you first define number ranges for the following objects: Hedging relationships Hedged items Hedging instruments Hypothetical derivatives Under Assign Number Ranges, define for each company code and valuation area which of the number ranges defined above is used.| |
|Effectiveness Test| | |
|Settings for Linear Regression| |Define Condition Types BAdI: Linear Regression Assessment Method Enhancement|
|Define Critical Term Type|Here, you define the critical term types that are used for the critical term match method.| |
|Effectiveness Test Method|Here, you define the effectiveness test methods that you want to use. In the Customizing activity Define Hedging Profiles, you assign these effectiveness test methods.|Example: 1. Choose New Entries. 2. Assign a three-digit code for the method and a name. 3. Choose the category of the effectiveness test method. The following categories are available: 11Dollar Offset Ratio 12Schleifer Noise Method 13Dollar Offset Basis Point 21Linear Regression with Time Reference 22Linear Regression with Market Data Sets |


|Customizing Activity|Use|Activities|
|---|---|---|
| | |31Critical Term Match Method 91Upload Dollar Offset Ratio 92Upload Linear Regression 4. Choose the offset calculation category. 5. Define the end date and start date for the prospective effectiveness test. 6. Define in which intervals the dollar offset test is effective. 7. Under Dividend Inheritance, you define whether dividend payments are considered in the effectiveness test. If you want dividend payments to be considered, you need to define which ones. 8. Save your entries. |
|Alternative setting to delivery scenarios|The following is defined in a scenario: Which product categories in a hedging relationship are permitted for the hedged items and the hedging instruments Which current value category is used The scenarios are system settings. You can use only the scenarios provided by SAP. Example: Scenario 110 is adjusted using FVH exchange rate risk. Spot-spot value date (or currency risk) is intended for the following: Product categories permitted for hedged items in a hedging relationship: 010 Stocks 020 Investment certificates 160 Shareholding Product categories permitted for hedging instruments in a hedging relationship:|Example 1. Choose New Entries. 2. Choose scenario 110. 3. Choose the product category of the product type to be excluded. For hedged items, choose product categories 010, 020, or 160. For hedging instruments, choose product category 740. 4. Choose the product type you want to exclude. 5. Set the Not Permitted indicator. 6. Save your entries. |


|Customizing Activity|Use|Activities|
|---|---|---|
| |740 Forward securities transaction As the current value calculation category, the category 210 Adjusted Intrinsic Spot Value is designated. In the Customizing activities Alternative Setting to Delivery Scenarios: Hedged Item and Alternative Setting for Delivery Scenarios: Hedging Instrument, you can exclude certain product types (ones based on the permitted product categories) from being used in the hedging relationships. All entries here are optional. The system runs with the scenarios provided by SAP. You can make different settings from those delivered as standard. When both tables are empty, the system operates without error.| |
|Define Hedging Profiles|A hedging profile is assigned to each hedging relationship in the function Manage Hedging Relationships (transaction TPM100) on the Hedging Relationship Details tab in the Risk and Profile area. In a hedging profile, you define which scenario is valid for the hedging relationship, which effectiveness test methods are used, how often the effectiveness test is performed, and for how long (in days) an effectiveness test is valid, as well as whether documentation occurs automatically and, if so, which PDF form is used for this. Here, you can make the following settings for the test plan of the hedging relationships: The test plan serves as a proposal; all tests are valid The dates of the test plan are default values. Only the dates for the designation and the dedesignation are mandatory. The function Perform Effectiveness Test applies the dates of the test plan. During the valuation, the system checks - using the settings in the hedging profile for the validity of the effectiveness test in days - whether the last effectiveness test is still valid at the time the valuation is performed.|Example: 1. Choose New Entries. 2. Assign a three-character name and a description for the profile. 3. Choose scenario 110. 4. Choose the effectiveness test methods you want for the prospective and retrospective effectiveness test. 5. Specify the validity of an effectiveness test in days. 6. Define the rhythm for the test plan. Monthly Quarterly Annually Manually 7. If you want to documentation of the hedging relationships for this profile to be generated automatically, set the Automatic Documentation indicator and specify the PDF form to be used. SAP provides the form TR_F_THX_NOTE_HREL. 8. Save your entries. |


|Customizing Activity|Use|Activities|
|---|---|---|
| |The test plan is mandatory, additional tests are optional The dates of the test plan are mandatory. An effectiveness test is always valid until the next test date. The settings in the hedging profile relating to the validity of the effectiveness test are obsolete. However, you can perform additional effectiveness tests. However, such tests are not considered by the valuation. Effectiveness tests are disabled (for example, shortcut method) If you opt for these settings, no effectiveness tests can be performed for the hedging relationships. The effectiveness test status of the hedging relationships is Always Effective. You can select this setting for hedging profiles that you use to portray hedging relationships in accordance with the shortcut method. With the shortcut method, a hedging relationship is always effective, without this being tested explicitly. For hedging profiles used to portray valuation units, you must select this setting. For the valuation units relating to German law, there is no obligation to perform effectiveness tests for hedging relationships. For this reason, there is no effectiveness test in the hedging scenarios for the unit of valuation.| |
|Update Types| | |
|Define Update Types and Assign Usages|Here you define all the required update types.| |
|Assign UpdateTypes for Business Transactions (HM) to Product Types|Here you assign the update types to be used for each product type for the following business transactions of P-HA:| |


|Customizing Activity|Use|Activities|
|---|---|---|
| |Designation Dedesignation Classification| |
|Release|If you want to use a release approval procedure in P-HA for the documentation on a hedging relationship and the business transactions designation and dedesignation (such as the dual control principle), you can set up release workflows in the following Customizing activities. For these release workflows, the SAP Business Workflow is used for which you must define the necessary settings in Customizing for Basis under Business Management SAP Business Workflow Maintain Standard Settings . | |
|Documentation|The release object TRM_HMD is available for the release workflow for documentation.|See the documentation on the Customizing activities.|
|Designation/Dedesignation|The release object TRM_HM is available for the release workflow for designation/dedesignation.| |
|Uploaded Retrospective Effectiveness Assessments|The release object TRM_HME is available for the release workflow for uploaded effectiveness assessments.| |
|Settings for Documents for P-HA in Document Management (CA-DMS)|In P-HA, you can store the following documents in a hedging relationship: Documentation about the hedging relationship (see also: Documentation of a Hedging Relationship Documents relating to the retrospective effectiveness assessment (see also: Uploading Effectiveness Tests These documents are stored in Document Management (CA-DMS). For this, you need to make some settings in Customizing for DMS. See also:Customizing Settings for Document Management for TRM Documents | |
|Documentation| | |
|BAdI: Documentation|If, for automatic documentation, you want to use your own PDF forms instead of the form defined by SAP, you can use this BAdI.| |
|Initialization of Hedging Relationships in Parallel Valuation Areas| | |
|Additional settings in the Transaction Manager for P-HA| | |
|Change Message Control|In this Customizing activity, you can configure the appearance (the message category) of system messages in P-HA to suit your requirements. Message 255 'Sicherungsbeziehung &1 in Acc.kreis &2 und Bew.bereich &3 ist betroffen' is issued when a position outflow affects a hedging relationship. Define whether the message is issued as a warning (W) or as an an error (E).|You find the Customizing activity under Transaction Manager General Settings  Tools Configurable Messages Change Message Control . 1. Call the Customizing activity. 2. Choose the work area: TPM_TRGTreasury Position Management: Cross-Package Messages. 3. Define the settings you want for message 255. |


|Customizing Activity|Use|Activities|
|---|---|---|
| |You can control the message category userdependently and differently in dialog and in a batch run. If you do not make any entries here, the message is issued as an error. **Note:** If you have chosen W as the message category here, you must execute function Distribute Position Outflows to Subpositions (transaction TPM103) after such a position outflow.|4. Save your entries.|
|Assign Update Types for Derived Business Transactions |On the following tabs, make the settings for P-HA: Classification Hedging-Related Transfer Postings Value Adjustment Position Outflows Reconciliation flows Currency Swap You also define the update types for the classification of hedging reserve and the costs of hedging reserve. In this activity, additional update types for balance sheet transfers are also defined. The update types defined are then assigned to the existing Accounting Framework settings.|You find the Customizing activity under Transaction Manager General Settings  Accounting Derived Business Transactions Assign Update Types for Derived Business Transactions .|
|Define Account Determination|Enter the posting specifications here for the update types relevant for account determination.|You find the Customizing activity under Transaction Manager General Settings  Accounting Link to Other Accounting Components Define Account Determination .|
|Define Position Management Procedure|In the Hedge Accounting for P-HA area, specify the evaluation type to be used. The position management procedure for exposure subitems can be determined using various criteria: Accounting code Valuation area Valuation class Product category Product type|You find the Customizing activity under Transaction Manager General Settings  Accounting Settings for Position Management Define Position Management Procedure .|


|Customizing Activity|Use|Activities|
|---|---|---|
|Assign Position Management Procedure|In this activity, you define the rules that govern how the position management procedures are assigned to the positions.|You find the Customizing activity under Transaction Manager General Settings  Accounting Settings for Position Management Assign Position Management Procedure .|
|Define Valuation Procedure|In the Risk Category for Hedge Accounting (P-HA) area, you enter the risk category.|Under Transaction Manager General Settings Accounting Settings for Position Management Key Date Valuation , you make the settings for the valuation procedure.|
|Alternative Update Types for Position Outflows|Here, you specify which alternative update types are applied for valuating in Hedge Accounting.|Under Transaction Manager General Settings Accounting Settings for Position Management Derived Business Transactions Alternative Update Types for Position Outflows , you enter the alternative update types for valuation for the Hedge Accounting condition if you want a position to be posted differently to the Hedge Accounting rules.|
|Settings in the Risk Analyzers| | |
|Activate Financial Object Integration Define Derivation Strategies for Subledger Positions/Subpositions BAdI: Subledger Positions and Subpositions| |You find these Customizing activities under Treasury and Risk Management Basic Analyzer Settings Automatic Integration of Financial Objects in Transaction Master Data Subledger Positions and Subpositions .|

###### Manage Hedging Relationships (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Manage Hedging Relationships | L5 | trm09 p.234 | loio `ed31c9aa938f4dacb526951f0365711b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ed31c9aa938f4dacb526951f0365711b.html?locale=en-US)

**Use**

This is the central function within Hedge Accounting for Positions where hedging relationships are created and managed.

In the Hedging Relationship area, you see the number and the name of the hedging relationship. By choosing the pushbutton, you can display the flows of the hedging relationship as well as call up and perform the business transactions (designate, dedesignate, reverse, undo, and reactivate) for a hedging relationship.

You also see here the current status of the hedging relationship and the status of the effectiveness test.

**Prerequisites**

You have made the settings in Customizing for Hedge Accounting for Positions. For more information on Customizing, see Hedge Accounting for Positions (P-HA).

**Activities**

- 1. Call the function from the application menu of Transaction Manager under Hedge Accounting for Positions Master Data Manage Hedging Relationship (transaction TPM100).
- 2. Now select the hedging relationships that you want to edit. To do this, first define the work area that you want by choosing the company code, valuation area, and fiscal year. You can then restrict the number of hedging relationships to be chosen by entering specifications for thehedging relationship details and/or by choosing their status. Choose Start.

If you want to create a new hedging relationship, choose Create.

- 3. A list of the selected hedging relationships appears, and, by double-clicking, you can branch to the respective hedging relationship to view or process it.

###### Creating Notes on a Hedging Relationship

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Creating Notes on a Hedging Relationship | L5 | trm09 p.235 | loio `df7e04119f2744028f1dce27d3bac142` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/df7e04119f2744028f1dce27d3bac142.html?locale=en-US)

**Use**

You can use this function for language-specific notes to do the following:

Create the notes for a hedging relationship and store them

Display and change existing notes

The subscreen displays which notes exist. The notes are created with note type THX_HR TTXID.

You can make a selection to edit individual texts/notes. All notes for a hedging relationship can be stored. The notes can be created in different languages.

**Activities**

- 1. To create or change a note in the change mode of the hedging relationship, choose alongside the number of the hedging relationship.
- 2. Create a short description for the note.
- 3. By choosing the Editor pushbutton, you call up an entry screen. Create your note here and then choose Back.
- 4. With the Other Languages pushbutton, you can also create the note in other languages.
- 5. Save the hedging relationship once you have left the note function.

###### Documentation of a Hedging Relationship

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Documentation of a Hedging Relationship | L5 | trm09 p.235 | loio `428c2971096b4072b3cac2567e404dfd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/428c2971096b4072b3cac2567e404dfd.html?locale=en-US)

**Use**

A hedging relationship can be documented. Documentation on a hedging relationship provides information about the type of hedged risk as well as a history of the effectiveness test.

Documentation can be created automatically or manually.

**Integration**

Documents are always managed using Document Management (DMS), independently of whether you have created the documentation automatically or manually.

A release workflow can be set up for the documentation.

The creation of documentation can be the prerequisite for releasing the planned designation of a hedged relationship.

When the creation of documentation is used as the prerequisite for releasing the planned designation, the documentation must have the status Released at the time when the planned designation is released.

**Prerequisites**

The Customizing settings need to have been made for the documentation.

Under Transaction Manager General Settings Hedge Accounting for Positions Define Hedging Profile , you specify whether documentation is optional or required and whether it is created automatically or manually.

Under Transaction Manager General Settings Hedge Accounting for Positions Documentation

In the document management system, certain settings need to have been made.

For more information on Customizing, see Overview: Customizing (P-HA).

**Features**

The documentation has versions.

###### Designation of a Hedging Relationship

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Designation of a Hedging Relationship | L5 | trm09 p.236 | loio `69cede06c87c4947b1cbadd344001cde` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/69cede06c87c4947b1cbadd344001cde.html?locale=en-US)

**Use**

With designation, you make a hedging relationship effective.

Designation is performed in two steps. When you execute the Designate function for the first time, the hedging relationship receives the status Designation Planned. For a cash flow hedge, the hypothetical derivative is also generated.

In this status, you can now perform the prospective effectiveness test and create and release the documentation. In the second step, the final designation is performed using the function Change Designation, which changes the status of the hedging relationship to Designated.

**Prerequisites**

You have assigned hedged item and hedging instrument to the hedging relationship.

**Features**

Alternative Market Data for the Designation

While performing the designation, you can use the Enter Market Data for Designation pushbutton to enter alternative market data especially for the designation. You can enter alternative market data on the following tab pages:

Securities Account

In the Securities area, you enter the security price to be applied.

Net Present Values

Alternative Interest Curves

The data entered here is only used for the specific hedging relationship.

You have the option of only designating partial amounts of the transactions/positions involved

During the designation, the hedged item and hedging instrument are valuated as a derived business transaction on the key date of the designation. Furthermore, the net present values of the interest cashflow of the hedged item as well as the net present value of the hedging instrument are calculated for the cashflow hedge.

###### Effectiveness Tests

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Effectiveness Tests | L5 | trm09 p.237 | loio `49c0a04ee0970e80e10000000a42189b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/49c0a04ee0970e80e10000000a42189b.html?locale=en-US)

**Use**

You perform prospective and retrospective effectiveness tests for a hedging relationship either in the function Manage Hedging Relationships on the Effectiveness Test tab page or in the function Perform Effectiveness Tests for one or more hedging relationships.

The effectiveness of a hedging relationship is the prerequisite for the value distribution after valuation in accordance with the principles of Hedge Accounting. Hedging relationships that are not effective are not allowed to be evaluated according to these principles.

You can perform the effectiveness test of a hedging relationship at any time during the lifetime of a hedging relationship.

The system performs the effectiveness test in accordance with the settings defined in the relevant hedging profile.

The following effectiveness test methods are available in Hedge Accounting for Positions:

Dollar Offset Method

(prospective and retrospective)

Schleifer Noise Method (prospective and retrospective)

Linear Regression (prospective and retrospective)

Critical Term Match Method (prospective)

You can also perform the effectiveness test externally and then upload the retrospective effectiveness assessment into the system.

See also:Uploading Effectiveness Tests

You can perform the effectiveness test for all selected hedging relationships whose test plan includes an effectiveness test on a key date (indicator According to Test Plan) or as a manual test (indicator Manual Test).

If you set the indicator Test run, the effectiveness test is performed as a simulation only.

**Note:**

This function is not available for valuation units.

**Prerequisites**

In Customizing for Hedge Accounting for Positions, the Test Plan Category field is available in the activity Define Hedging Profiles. Here, you can make the following settings for the test plan of the hedging relationships:

The test plan serves as a proposal; all tests are valid

The dates of the test plan are default values. Only the dates for the designation and the dedesignation are mandatory.

The function Perform Effectiveness Test applies the dates of the test plan.

During the valuation, the system checks - using the settings in the hedging profile for the validity of the effectiveness test in days - whether the last effectiveness test is still valid at the time the valuation is performed.

The test plan is mandatory, additional tests are optional

The dates of the test plan are mandatory. An effectiveness test is always valid until the next test date. The settings in the hedging profile relating to the validity of the effectiveness test are obsolete.

However, it is possible to perform additional effectiveness tests. However, such tests are not considered by the valuation.

Effectiveness tests are disabled (for example, shortcut method)

If you select these settings, it is not possible to perform effectiveness tests for the hedging relationships.

The effectiveness test status of the hedging relationships is Always Effective.

You can select this setting for hedging profiles that you use to portray hedging relationships in accordance with the shortcut method. With the shortcut method, a hedging relationship is always effective, without this being tested explicitly.

For hedging profiles used to portray valuation units, you must select this setting.

For the valuation units relating to German law, there is no obligation to perform effectiveness tests for hedging relationships. For this reason, there is no effectiveness test in the hedging scenarios for the unit of valuation.

When performing prospective effectiveness tests, you can use the market data structure curves, the basis point shift, market data scenarios, or the market data shift. The scenario to be used is assigned for each hedging relationship in function Manage Hedging Relationships (transaction TPM100) on tab Effectiveness Test.

For more information on Customizing, see Hedge Accounting for Positions (P-HA).

**Features**

If an effectiveness test was already performed, the program displays the hedged effectiveness measurement.

The retrospective effectiveness assessment program calculates the measurement result for one or more periods (from start to finish) and displays the result. The result displays the delta amounts and the totals for the hedging instrument (derivative) and the hedged item. The program also issues the determined effectiveness rate and the decision whether the hedging relationship is effective or not.

The effectiveness measurement displays the effectiveness of a hedging relationship up until the last measurement date or, if no effectiveness test was performed until now, to the start date of the hedging relationship.

A detailed log is issued for both effectiveness test types.

This log contains information on the calculation and values this was based on. If you have performed an effectiveness test, you cannot generate a second detailed log for the same day and for the same calculation type.

**Activities**

- 1. From the application menu, choose Treasury and Risk Management Transaction Manager Hedge Accounting for Positions Effectiveness Test Perform Effectiveness Test .
- 2. Enter your selection criteria in the different entry fields:


- 3. Choose Program Execute .

###### Hypothetical Derivative (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Effectiveness Tests > Hypothetical Derivative | L6 | trm09 p.284 | loio `6fd79fefb597432980a91f883b3ee179` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6fd79fefb597432980a91f883b3ee179.html?locale=en-US)

**Use**

If the critical terms of a hedged underlying transaction (such as interest rate adjustment dates or the interest rate reference) do not match those of the hedging transaction, you can use a hypothetical derivative to test the effectiveness of the hedging relationship.

The hypothetical derivative represents a perfect hedging instrument and is a modified version of the actual hedging instrument that would completely cover the risk involved.

To use the hypothetical derivative in a hedge strategy, you need to use a suitable calculation type and hedge strategy. In Customizing, choose Transaction Manager General Settings Hedge Accounting for Exposures Effectiveness Test Define

Calculation Types and then set the Hypoth. perfekt. You make the required hedge strategy settings under Define Hedge Strategies.

Hypothetical derivatives are simply a means for the system to make calculations if no valuations or postings have been made. For this reason, hypothetical derivatives are not displayed as real transactions. SAP therefore recommends that you use separate product types for hypothetical derivatives.

**Features**

Effectiveness Test and Posting

The system compares the changes in value of the actual hedging instrument (either cumulatively or for selected periods) with the changes in value of the hypothetical derivative. Since both involve hedging instruments, the changes in value do not offset each other.

The hedging relationship is effective if the ratio between the change in value of the actual hedging instrument and the change in value of the hypothetical derivative fall within the determined effectiveness range.

###### Dollar Offset Method

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Effectiveness Tests > Dollar Offset Method | L6 | trm09 p.239 | loio `f11f45c9f2f247d7bb74396b5d2523c3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f11f45c9f2f247d7bb74396b5d2523c3.html?locale=en-US)

You use the dollar offset method to check the effectiveness of a hedging relationship.

A hedging relationship is effective when the ratio of the changes in fair value of the hedged item and the hedging transaction falls within a specific range. This range is specified in Customizing.

For the dollar-offset-effectiveness test, the result must be between a range of 80-125% to be classed as effective.

###### Schleifer Noise Method

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Effectiveness Tests > Schleifer Noise Method | L6 | trm09 p.240 | loio `0aa0fd32f043461593ac8fc0a92a1f20` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0aa0fd32f043461593ac8fc0a92a1f20.html?locale=en-US)

**Definition**

The schleifer noise method is a variant of the dollar offset method that is used to check the effectiveness of a hedging relationship.

**Use**

With the dollar offset method for checking the effectiveness of a hedging relationship, the results may contradict the actual economic reality. In this way, very small changes in the values can cause a hedging relationship to be classed as ineffective even though this is not borne out in reality (problem of small numbers).

[figure TRM09-F062 - With the dollar offset method for checking the effectiveness of a hedging relationship, the results may contradict the actual economic reality. In this way, very small changes in the values can cause a hedging relationship to be classed as ineffective even though this is not borne out in reality (problem of small numbers).]

Problem with Small and Large Numbers in the Dollar Offset Method

The schleifer noise method allows you to circumvent the problem of small numbers. With this effectiveness test method, you enter a threshold value (in percent) to specify the highest amount that value fluctuations can reach without affecting the effectiveness valuation.

[figure TRM09-F063 - Schleifer Noise Method (Formula)]

Schleifer Noise Method (Formula)

In addition to using a noise threshold value (NT), you can also specify a transition speed (s). The transition speed determines the transition of a hedging relationship from being effective to ineffective. The transition speed influences the transition area between

the area where the threshold value dominates and the area where it is not influential. The greater the transition speed, the smaller the transition area.

###### Linear Regression

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Effectiveness Tests > Linear Regression | L6 | trm09 p.241 | loio `2bc49d89bd3d4862aebb7ae99cb5a604` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2bc49d89bd3d4862aebb7ae99cb5a604.html?locale=en-US)

**Use**

The effectiveness of a hedging relationship in Hedge Accounting for P-HA can be determined prospectively or retrospectively using the linear regression analysis.

The following parameters can be calculated:

Gradient of the regression lines

Intercept of the regression lines

R2 Coefficient

t-Test

**Prerequisites**

In Customizing for Financial Supply Chain Management under Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Positions , you need to make the following settings:

Under Effectiveness Test Effectiveness Test Methods , you create one or more methods for the type Linear Regression.

When creating the effectiveness test methods for linear regression, you can choose between three methods.

Independent: Store directly in the method the values for the parameters to be determined.

Gradient an R2: Under Settings for Linear Regression Define Condition Type , you need to create condition types in which you store the values for the parameters. In the effectiveness test method, assign the condition type to be used.

Customer Enhancement BAdI: For this method, use the BAdI under Settings for Linear Regression BAdI: Linear Regression Assessment Method Enhancement .

Specify for the prospective effectiveness test whether market data scenarios, market data shifts, market data structure curves, or basis point shifts are used to determine the required data.

Assign a new hedging profile to the methods.

For performing effectiveness tests and valuations, the necessary market data must be entered in the market data tables. The necessary market structure curves, market data scenarios, and market data shifts must be maintained.

###### Critical Term Match Method

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Effectiveness Tests > Critical Term Match Method | L6 | trm09 p.241 | loio `04a29b88dfd74378952fc4f3dd11c078` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/04a29b88dfd74378952fc4f3dd11c078.html?locale=en-US)

**Use**

With this effectiveness test method for hedging relationships, some important business data (the critical terms) of the hedged item and of the hedging instrument are checked as to whether they match. If the critical terms match, it can be assumed that the hedging relationship is effective.

As per IAS 39, the prospective effectiveness test can be used for some hedging relationships to test the effectiveness of the hedging relationship using the critical term match method.

**Example:**

In the case of an interest rate swap, it can be assumed that there is a complete hedge when the following criteria match for a hedged item (such as a securities position) and for a hedging instrument (such as an interest rate swap):

Designated nominal amounts

Currency

Start date

Due date

Reference interest rate

Spread

Interest calculation method

Calendar

You can use the critical term match method for the following scenarios:

710CFH: Security Hedged with Interest Rate Swap

720CFH: Loan Hedged with Interest Rate Swap

**Note:**

The parameters often do not match, in which case other methods need to be applied.

If the effectiveness test has failed for a hedging relationship and you want to establish the effectiveness of that hedging relationship using a different effectiveness test, you have to create a new hedging relationship and assign to it a different hedging profile with different effectiveness tests.

To check the effectiveness (prospectively and retrospectively) of a cashflow hedge hedging relationship using other effectiveness test methods alongside the critical term match method, the hypothetical derivative is used.

**Prerequisites**

In Customizing for Hedge Accounting for Positions under Effectiveness Test Define Critical Term Type , you can create a critical term type and specified which terms need to be applied to check the effectiveness.

Under Effectiveness Methods, you have created a method that applies the Critical Term Match Method as the type of effectiveness test method and you have also assigned here the critical term type defined above.

Under Define Hedging Profile, you have created a profile and have assigned to it as prospective effectiveness method the effectiveness test method defined above.

**Features**

The following critical terms can be compared:

(Designated) nominal amounts

Currency

Start date

Here, the start dates of the hedged item and the hedging instrument are compared. However, in the case of a security position, the comparison applies the date of the first purchase of the security.

Due date

The comparison applies the due dates of the security/loan and of the hedging instrument.

Reference interest rate

The reference interest rates are checked to see if they match.

Spread

The fixed interest rate that is added to or subtracted from the reference interest rate used is compared.

Interest calculation method

Calendar

Partner rating

The rating of the issuer/lender is compared against the rating of the partner of the hedging instrument.

Credit spread

The credit spread of the security/loan and that of the hedging instrument are compared under the assumption that it does not change during the term of the hedging relationship.

You enter the credit spreads in the market data under Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Credit Spread .

###### Uploading Retrospective Effectiveness Assessments

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Effectiveness Tests > Uploading Retrospective Effectiveness Assessments | L6 | trm09 p.243 | loio `04769b506660b656e10000000a445394` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/04769b506660b656e10000000a445394.html?locale=en-US)

**Use**

In cases where you use linear regression analysis or the dollar offset method to check the effectiveness of hedging relationships, you can perform the effectiveness test outside of the SAP system, enter the results manually in the system, and upload the retrospective effectiveness assessment in file form (for example, as a text file or a spreadsheet).

The documents uploaded for the retrospective effectiveness assessment are stored in Document Management (CA-DMS).

You can set up a release workflow for the uploaded documents to achieve dual control.

**Prerequisites**

- 1. In Customizing, you need to define effectiveness test methods that allow retrospective effectiveness assessments to be uploaded (effectiveness test method category 91Upload Dollar Offset or 92Upload Linear Regression).

You need to assign these effectiveness test methods to hedging profiles.

- 2. Set up the release workflow for the release object TRM_HME.
- 3. To be able to use this function, you need to make settings in DMS.


See also:

Overview: Customizing (P-HA)

Customizing Settings for Document Management for TRM Documents

**Activities**

- 1. Choose Transaction Manager Hedge Accounting for Positions Master Data Hedging Relationship Management .
- 2. Select the hedging relationship for which you want to upload the retrospective effectiveness assessment.
- 3. Go to the Effectiveness Test tab.
- 4. Choose to switch to the change mode.
- 5. On the Run Test tab, select the line for the date on which you performed the effectiveness test and choose Upload Effectiveness Test. On the dialog box that appears, double-click the icon in the columns PET (Prospective Effectiveness Test) and RET (Retrospective Effectiveness Test) to select the effectiveness test that you would like to upload. The dialog box for the effectiveness test appears. On the Effectiveness Test Results tab, you manually enter the results of the test. You can use the following fields for the dollar offset method:

Start Date of Test Period

End Date of Test Period

Effectiveness Ratio

Test Status

Here, you decide whether the effectiveness test qualifies the hedging relationship as Effektiv or Ineffektiv.

Total of Value Changes to Hedging Instruments

Total of Value Changes to Hedged Items

Valuation Currency

For the linear regression, you can use the following fields:

Start Date of Test Period

End Date of Test Period

Test Status

Here, you decide whether the effectiveness test qualifies the hedging relationship as Effektiv or Ineffektiv.

Valuation Currency

Slope

Inter Ratio

R2 (Coefficient of Determination/Correlation Coeffizient)

T-Statistics for Slope

- 6. On the Upload tab, upload the document as follows:


**Note:**

The only required entry field is the test status.

- a. Choose . The system creates a line for version 01.


- b. In the Documentation Details area, choose .
- c. On the dialog box that appears, go to the Document Data tab and enter a description (which can be longer than one line) for the document to be uploaded.

The document now has the status H1Created.

- d. Now choose . In the following dialog box, enter your workstation application (such as TRMTreasury_ All Files) in the Application field. Enter a description in the Description field. In the Original field, use the input help to select the document. You can assign more than one document.

Once you have uploaded all of the documents, save your entries.

In the next dialog box that appears, select the Content Repository (such as THXT_HDOC_DMS).

- e. Choose .

###### Display Effectiveness Test Results (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Effectiveness Tests > Display Effectiveness Test Results | L6 | trm09 p.245 | loio `5a0389bf51bc495589fe62560b3e3d9d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5a0389bf51bc495589fe62560b3e3d9d.html?locale=en-US)

Get detailed information on effectiveness test results and the hedging instruments of hedging relationships.

**Context**

If effectiveness testing is active for your hedging profiles and hedging areas, a prospective effectiveness test is automatically executed during the release of designation. Using this report, you can display the results of this effectiveness tests. In addition, details for the hedging instruments are shown and navigation to the hedging relationship and also to the hedge documentation is provided.

**Procedure**

- 1. Call the function in the area menu under Hedge Accounting for Positions Effectiveness Test Display Effectiveness Test Results (transaction TPM112).
- 2. Under General Selections, you select the hedging relationships by the Company Code, Valuation Area, and Up to Key Date. You could also select by the number of the financial transactions, which are part of the hedging relationship, or by attributes of the hedging relationship, such as the Hedging Relationship Number, Profile, or Hedging Area.
- 3. Under Effectiveness Test Status, you can select the hedging relationships by the effectiveness test status of the hedging relationship.

If you set the Effective Hedging Relationships indicator, you get the effectiveness test results of hedging relationships for which the effectiveness test has been executed successfully and the hedging relationship is effective due to effectiveness criteria.

If you set the Ineffective Hedging Relationships indicator, you get the effectiveness test results of hedging relationships for which the effectiveness test has been executed successfully and the hedging relationship is ineffective due to effectiveness criteria.

If you set the Hedging Relationships with Effectiveness Calculation Errors indicator, you get a list of hedging relationships for which errors occurred during the execution of the effectiveness test.

If you set the Hedging Relationships Manually Set to Effective indicator, you get a list of effective hedging relationships, which are manually set to effective. (This function is not available for hedging relationships of the Hedge Accounting for Exposure Items process.)

- 4. Execute the report.


**Results**

You get a result list according to your selections. For the selected hedging relationships, you get a row for each hedging instrument of the hedging relationship. In the row, you get information on the effectiveness test and hedging instrument. You also can navigate to further information.

For hedging relationships, for which the effectiveness test has been successfully executed, you can find the results of the effectiveness test in the columns R2, Slope, Intercept Ratio, and t-Stat. Slope.

In addition, administrative information for the effectiveness test, such as Effectiveness Test Date, Effectiveness Test Type, MDS ID, Trigger, and Prospective Method are available.


The effectiveness test status is visualized by an icon at the end of the row ( = effective and = ineffective).


In addition, you get information for the hedging instrument, such as the following:

Number of the hedging instrument

Product type

Buy currency

Buy amount

Sell currency

Sell amount

Nominal amount

Nominal currency

Number of the hypothetical derivative

If you mark a line item, you can use the following buttons on top of the list:

**Display Effectiveness Test**

Display Hedging Relationships

You navigate to the hedging relationship details in the Manage Hedging Relationship function.

Display Hedge Documentation

You see the created file.

**Note:**

You can navigate to the hedging relationship by clicking the HR Number in the respective column.

You can navigate to the hedge documentation by clicking the icon in the Hedge Documentation column.


**Related Information**

Prospective Effectiveness Test Using Linear Regression

###### Valuating a Hedging Relationship

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Valuating a Hedging Relationship | L5 | trm09 p.246 | loio `f47961d151c342c0baba766f853e6161` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f47961d151c342c0baba766f853e6161.html?locale=en-US)

Use

The affected positions in a hedging relationship are valuated using the valuation function of the Transaction Manager. The valuation flows of the designated subposition are posted in accordance with the hedge accounting rules and the rules intended for the free-standing subposition for non-hedged positions in the position management procedure.

**Prerequisites**

You need to have made the Customizing settings for the valuation.

You need to have entered the required market data for the valuation.

**More Information**

Execute Key Date Valuation

###### Rollover of the Hedging Relationship

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Rollover of the Hedging Relationship | L5 | trm09 p.247 | loio `3c3190812f694475a3fa6268bcbde64a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3c3190812f694475a3fa6268bcbde64a.html?locale=en-US)

**Use**

You can roll over (as a whole or in part) hedging relationships that use forward securities transactions.

You can roll over a hedging relationship in two different ways:

If you roll over the forward securities transaction that is part of a hedging relationship, the system automatically rolls over the hedging relationship. The planned designation date of the hedging relationship is updated with the new end date of the rolled over forward securities transaction.

The hedging relationship is also rolled over when you replace the designated forward securities transaction at the end of its term with a new forward securities transaction

With both of these rollover methods, you can roll over the hedging relationship as a whole or only for a partial amount.

**Prerequisites**

In Customizing for Hedge Accounting for Positions under Update Types Assign Update Types for Hedge Man. Business Transactions to Product Types , you have to assign the required update types in the new columns for the rollover.

###### Dedesignation of a Hedging Relationship

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Dedesignation of a Hedging Relationship | L5 | trm09 p.247 | loio `bdcaebecf8e6484093a74f7cab55efd1` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bdcaebecf8e6484093a74f7cab55efd1.html?locale=en-US)

A hedging relationship is ended with dedesignation.

Possible reasons for the dedesignation of a hedging relationship:

The underlying transaction is sold or settled

The hedging instrument is sold or exercised

The effectiveness test is not passed

Management decides to close the hedging relationship

Dedesignation is performed in two steps. When you execute the Dedesignate function for the first time, the hedging relationship receives the status Dedesignation Planned.

With this status, you can only perform retrospective effectiveness tests. In the second step, the final dedesignation is performed using the function Change Dedesignation, which changes the status of the hedging relationship to Dedesignated.

During the dedesignation phase, the system automatically performs the last valuation of the hedging relationship.

For fair value hedges, you need to perform a classification for the designated subpositions at the time of the dedesignation.

###### Classification

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Classification | L5 | trm09 p.248 | loio `c4327e66178e43e3920fe3dc98f3e2ce` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c4327e66178e43e3920fe3dc98f3e2ce.html?locale=en-US)

**Use**

After valuation of one or more hedging relationships, you can depict for hedging relationships the fair value hedges that perform the classification.

Before a dedesignation, you have to perform the classification.

The classification analyzes the valuation flows created for the designated subpositions. This determines the effective and ineffective parts.

**Example:**

Example:

Valuation results and the resulting classification

|Valuation on March 31.| |
|---|---|
|Hedging Instrument:|-18 depreciation|
|Hedged item:|20 write-up|
|Classification on March 31.| |
|Sicherungsinstrument:|-18 effective|
|Grundgeschaft:|+18 effective + 2 ineffective|


**Prerequisites**

The selected hedging relationships have the status "Designated".

The designated subpositions have already been valuated.

###### Distributing Position Outflows to Subpositions

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Distributing Position Outflows to Subpositions | L5 | trm09 p.248 | loio `4cec0dcdd51d4c94bb98093f31b53bad` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4cec0dcdd51d4c94bb98093f31b53bad.html?locale=en-US)

When you sell a position or partial position that is part of a hedging position, you have to specify after the sale the subposition from which it originates.

**Legacy Data Transfer (Hedge Accounting for Positions)**

**Purpose**

You can the legacy data transfer to transfer existing and designated hedging relationships into the SAP -system on a key date to continue hedging relationships in the new environment. To do this, you dedesignate all hedging relationships in the old system and transfer all hedge components to the new positions and subpositions. The key date of legacy data transfer is set by the system to the key date of the legacy data transfer of the affected subledger positions. Transfer of legacy data is controlled by the selectoptions. Component values are read from control tables and are transferred to hedging relationships.

**Prerequisites**

You have executed legacy data transfer for subledger positions in general already.

**Process**

Define new hedging relationship within transaction TPM100 by choosing function Edit Create within Legacy Data Transfer. Create hedged item and hedging instrument and save your entries.


Make the required settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Tools -> Legacy Data Transfer Hedging Relationships (PHA) Data for Securities with Subpositions and Data for OTC Transactions with Subpositions. .


Data for securities with subpositionsFor securities positions of a hedging relationship that is identified by company code, hedged item, hedging instrument, and fiscal year, you define the component values which are transferred to the system. The column Transfer is marked after successful legacy data transfer.

Data for OTC transactions with subpositions

For OTC transactions of a hedging relationship which are identified by company code, hedged item, hedging instrument and fiscal year you define component values which are transferred to the system. The column Transfer is marked after successful legacy data transfer.

Enter the data in the Customizing tables.

Execute legacy data transfer

According to the select options the system reads data from the customizing tables and transfers data to the system.

General selections:

Company code

Valuation area

Hedging relationship

Fiscal year

Key date

Posting control:

Posting date

Posting period

Document date

Accounting update flag

Test run flag

Output

The result is displayed in an ALV -list.

Execution

The system generates a designation transaction which can be displayed by transaction TPM100 later. For each entry in the customizing table of the subposition component values, the system generates flows in order to update the treasury ledger subpositions. The business transactions are saved in status Scheduled . You can reverse the legacy data transfer for hedging relationships. After reversal, you are able to update the customizing tables with the component values.

###### Legacy Data Transfer (Hedge Accounting for Positions)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Legacy Data Transfer (Hedge Accounting for Positions) | L5 | trm09 p.213 | loio `470cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/470cda531198434de10000000a174cb4.html?locale=en-US)

Initialization of Hedging Relationships in Parallel Valuation

Forward Securities Transactions.

Total Return Swaps.

###### Initialization of Hedging Relationships in Parallel Valuation Areas

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Positions (P-HA) > Initialization of Hedging Relationships in Parallel Valuation Areas | L5 | trm09 p.250 | loio `98182a50276fbd10e10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/98182a50276fbd10e10000000a423f68.html?locale=en-US)

**Use**

The existing hedging relationships in a valuation area can be transferred to another valuation area.

When the initialization run is started, the system uses your selection criteria to read the initialization data from the tables and transfer it to the hedging relationships in the new valuation area.

**Integration**

These reports belong to Hedge Accounting for Positions.

**Prerequisites**

You need to have already initialized the product groups in the valuation area.

Create the hedging relationships using the function Manage Hedging Relationships (transaction TPM100) in the new valuation area by choosing Edit Copy to Initialization .

Enter the number (if you are using external number assignment), the name of the hedging relationships, and the hedging relationship details. On the following tab pages, assign the hedged item and at least one hedging transaction, and save your entries.

Enter the initialization data for the hedging relationships in Customizing for the Transaction Manager under General Settings Hedge Accounting for Positions Initialization of Hedging Relationships Define Data for Securities with Subpositions and Define Data for OTC Transactions with Subpositions.

Define Data for Securities with Subpositions

For security transactions of a hedging relationship identified by company code, hedged item, hedging instrument, and fiscal year, you specify the position components as you want them to be transferred to the new valuation area.

After the data has been initialized, the Data Transferred indicator is set in the last column.

Define Data for OTC Transactions with Subpositions

For OTC transactions of hedging relationships identified by company code, hedged item, hedging instrument, and fiscal year, you specify the position components as you want them to be transferred to the new valuation area.

After the data has been initialized, the Data Transferred indicator is set in the last column.

**Features**

Initialize Hedging Relationships in Parallel Valuation Areas

Selection

Based on your selection criteria, the system reads the data from the tables and transfers it to the hedging relationship.

General Selections

Company Code

Valuation Area

Posting Control

Test Run indicator

Set this indicator and then perform a test run. Check the log. If the test run is successful, you can start the update run.

Execute the function.

Output

The system issues a log.

The system generates the following business transactions:

Initialize the Hedging Relationship

This business transaction corresponds to the Designation business transaction that is used in the function Manage Hedging Relationships (transaction TPM100).

Initialize Positions

For each line in the initialization table, the system generates flows for the hedged items and hedging transactions to post the values to the position components.

The business transactions acquire the status Planned.

Reverse the Initialization of Hedging Relationships in Parallel Valuation Areas

The initialization can be reversed.

After reversal, you can make changes in the initialization tables.

