# Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) - SAP TRM Knowledge Base (branch split)

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

##### Hedge Accounting for Exposures (E-HA)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) | L4 | trm09 p.251 | loio `b3401750a6bb4569e10000000a44176f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b3401750a6bb4569e10000000a44176f.html?locale=en-US)

**Use**

With Hedge Accounting for Exposures (E-HA), you can manage hedging relationships with which you document how you use financial instruments to hedge your risk positions (exposures) against foreign exchange risks, interest rate risks, and commodity price risks.

With E-HA, you can portray fair value hedges (FVH) and cash flow hedges (CFH) including net investment hedges (NIH) for foreign subsidiaries.

E-HA enables you to run effectiveness checks for your hedging relationships and document your hedging relationships. It also offers valuation and accounting functions for hedge accounting purposes.

[figure TRM09-F070 - E-HA enables you to run effectiveness checks for your hedging relationships and document your hedging relationships. It also offers valuation and accounting functions for hedge accounting purposes.]

**Implementation Considerations**

In Customizing for the Transaction Manager, you need to make the settings for Hedge Accounting for Exposures under General Settings Hedge Accounting for Exposures .

**Integration**

You can administrate your exposures in Exposure Management 2.0. Both Exposure Management applications are integrated with Hedge Accounting for Exposures.

Further, you can import exposures from Money Market and Loans Management or exposures from external systems into EHA. Of course, you can also create exposures manually in the hedge plan.

See also:

Exposure Management 2.0: Transferring Exposures to E-HA

Exposure Upload from Money Market or Loans

Exposure Upload from an External System

To calculate the market values of a derivative financial instrument, Hedge Accounting for Exposures uses Mark-to-Market Valuation (storage of mark-to-market valuation transactions) in Risk Management.

There is a connection to Market Data Supply. This is important for subsequent effectiveness checks.

Key Date Valuation (valuation for accounting purposes, performed on transactions against the market value) reads saved NPVs from mark-to-market valuation. Unrealized gains and losses are distributed to accounts on the basis of Hedge Accounting principles.

With the key date valuation and the realized gains and losses, integration to Financial Accounting is automatic.

[figure TRM09-F071 - With the key date valuation and the realized gains and losses, integration to Financial Accounting is automatic.]

**More Information**

Exposure Management 2.0

Hedging Relationships

Expiration of Risks

Closing Operations

Information System

BAPIs in Hedge Accounting for Exposures

###### Fair Value Hedge (FVH)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Fair Value Hedge (FVH) | L5 | trm09 p.254 | loio `010cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/010cda531198434de10000000a174cb4.html?locale=en-US)

You can use a fair value hedge to hedge the exposure to recognized assets or liabilities and unrecognized firm commitments against changes in fair value. Changes in fair value are usually due to exchange rate risks or interest rate risks, and influence the net earnings of a company.

If the fair value hedge is effective, the changes in value of both the hedging instrument and the underlying transaction that result from the hedged risk need to be included in the profit and loss statement as affecting net income.

The fair value hedge adjusts the book value of the underlying transaction. This adjustment is only permitted if hedge management is in use. This procedure applies to financial instruments that are valued at amortized cost ( held to maturity , loans and receivables ) as well as to financial instruments designated as available for sale .

**Note:**

If you use a fair value hedge to hedge an unrecognized firm commitment as an underlying transaction, the change in fair value is shown as an asset or a commitment in the balance sheet. At the same time, an offsetting posting is made via the profit and loss statement. If the firm commitment is actually used as an asset or liability, the acquisition costs are adjusted by the cumulated changes in value.

See also:

Fair Value Hedge (FVH) to Hedge Foreign Currency Risk

Fair Value Hedge (FVH) to Hedge Interest Rate Risk

###### Fair Value Hedge ( FVH ) to Hedge Foreign Currency Risk

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Fair Value Hedge (FVH) > Fair Value Hedge ( FVH ) to Hedge Foreign Currency Risk | L6 | trm09 p.254 | loio `040cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/040cda531198434de10000000a174cb4.html?locale=en-US)

The International Accounting Standards ( IAS ) 21 and the Financial Accounting Standards Board ( FASB ) – Statement No. 52 stipulate that changes in value of monetary assets or liabilities (such as interest rate instruments in foreign currency) that result from fluctuations in the foreign currency need to be included in profit or loss.

This does not apply, however, to monetary transactions that are used as hedging instruments in a cash flow hedge or net investment hedge.

Hedge Accounting is used only for selected monetary assets and liabilities since the changes in value of the hedging instrument and the underlying transaction have usually already been recognized in profit and loss.

However, in the case of non -monetary financial instruments classified as Available for Sale ,IAS 21 and FASB Statement No. 115 state that changes in value need to be recognized in equity and not affect profit and loss. For this reason, a fair value hedge could be used for non-monetary assets and liabilities.

**Example:**

You hedge the fair value of a foreign stock against the risk of fluctuations in foreign currency. The stock represents the exposure.

**Note:**

Since the system cannot load stocks as exposures, it is not currently possible to map fair values hedges to hedge exchange rate risks.

###### Fair Value Hedge (FVH) to Hedge Interest Rate Risk

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Fair Value Hedge (FVH) > Fair Value Hedge (FVH) to Hedge Interest Rate Risk | L6 | trm09 p.255 | loio `070cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/070cda531198434de10000000a174cb4.html?locale=en-US)

When you hedge an underlying transaction with fixed interest payments using a hedging transaction with variable interest, the fixed interest payments represent the exposure.

A fair value hedge can be used to attempt to transform the fixed payment flows into variable ones. This applies to all funds transactions, such as fixed-term deposits, interest rate instruments, or loans.

See also:

FVH: Interest Rate Swap Used as a Hedging Transaction

FVH: Cross-Currency Interest Rate Swap Used as a Hedging Transaction

FVH: Interest Rate Swap and a Cross-Currency Interest Rate Swap Used as a Hedging Transaction

###### FVH: Interest Rate Swap Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Fair Value Hedge (FVH) > Fair Value Hedge (FVH) to Hedge Interest Rate Risk > FVH: Interest Rate Swap Used as a Hedging Transaction | L7 | trm09 p.255 | loio `100cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/100cda531198434de10000000a174cb4.html?locale=en-US)

Use in Hedge Accounting for Exposures

As part of the effectiveness test, the system calculates the net present value (fair value) of the interest rate swap and the exposure on the valuation key date. The calculation of the interest rate swap does not include accrued interest but is rather the clean price. These values are then compared.

**Note:**

If you were to include accrued interest in the net present value, this would usually result in an ineffective hedging relationship.

To calculate the net present value of the exposure, the system takes markup (spread) into account. The basic concept of the markup is that the yield curve used to discount the underlying transaction is shifted by a constant spread. The markup represents the default risk at the time the hedging relationship is created. The parallel shift of the yield curve enables you to differentiate between the credit risk and interest rate risk. The markup is constant so that changes to the credit risk do not affect the effectiveness test.

To value the underlying transaction and the interest rate swap, the system runs a foreign currency valuation and security valuation. If the hedging relationship is partially or completely effective, the total change in fair value (clean price) of the underlying transaction is recorded on the profit and loss statement.

**Note:**

If the interest rate swap and underlying transaction are in local currency, the total effect is derived from the interest rate effect. However, when using a foreign currency, the total effect depends on the interest rate and foreign exchange.

When you value a financial asset or liability, you always need to enter the foreign exchange effect or underlying transaction in foreign currency on the profit and loss statement. If the hedging relationship is effective, the interest rate effect is also taken into account in profit and loss. You can also use a hypothetical derivative.

Creating a Hedging Relationship

To create a hedging relationship, proceed as follows:

1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting

Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).

- 2. Create a new hedge plan and choose the risk category Interest Rate Risk. You can also set the Single Hedged Item indicator.
- 3. On the Hedged Item tab page, choose the hedge category Fair Value Hedge.
- 4. For the hedging relationship, specify the interest rate swap that you entered as the hedging instrument. Choose hedge strategy 500 Benchmark Clean Price and specify a spread.


**Recommendation:**

In the case of interest rate risk, the system automatically loads the transaction or interest payments belonging to a transaction as an exposure. If you set the Single Hedged Item indicator, the exposures are only assigned to one hedged item. We recommend setting this indicator if you only want to use an interest rate swap to hedge an interest rate instrument with multiple interest payments.

**Note:**

Depending on the underlying transaction, the system automatically assigns Financial Asset or Financial Liability to the Transaction Category field, or Position or Cash Flow to the Transaction Activity field.

**Recommendation:**

We recommend that you choose one value so that the net present value of the underlying transaction corresponds to the market value at the start of the hedging relationship.

Selecting the Hedge Strategy

The standard Customizing setting available is hedge strategy 500 with calculation type 201 Interest Rate Instrument: Benchmark without Accrued Interest. If you decide to use another hedge strategy, it must use a calculation type based on calculation category 201.

Settings in the Money Market and Position Management Areas

The standard setting defined in Customizing for the underlying transaction is product type 55B Interest Rate Instrument, Hedge Acc. which is assigned to valuation procedure 3002 Money Market Transactions: Underlying Transaction, Hedge Acc.

The standard Customizing setting for the hedging instrument is product type 62C Int. Rate Swap: Hedge Accounting which is assigned to valuation procedure 3000 Derivatives: Hedging Inst., Hedge Acc.

See also:

Fair Value Hedge (FVH) to Hedge Interest Rate Risk

###### FVH: Cross-Currency Interest Rate Swap Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Fair Value Hedge (FVH) > Fair Value Hedge (FVH) to Hedge Interest Rate Risk > FVH: Cross-Currency Interest Rate Swap Used as a Hedging Transaction | L7 | trm09 p.256 | loio `0a0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0a0cda531198434de10000000a174cb4.html?locale=en-US)

Use in Hedge Accounting

As part of the effectiveness test, the system calculates the net present value (fair value) of the cross-currency interest rate swap and the exposure on the valuation key date. The calculation of the interest rate swap does not include accrued interest but is rather the (clean price). These values are then compared.

**Note:**

If you were to include accrued interest in the net present value, this would usually result in an ineffective hedging relationship.

To calculate the net present value of the exposure, the system takes markup (spread) into account. The basic concept of the markup is that the yield curve used to discount the underlying transaction is shifted by a constant spread. The markup represents the default risk at the time the hedging relationship is created. The parallel shift of the yield curve enables you to differentiate between the credit risk and interest rate risk. The markup is constant so that changes to the credit risk do not affect the effectiveness test.

To value the underlying transaction and the cross-currency interest rate swap, the system runs a foreign currency valuation and security valuation. If the hedging relationship is partially or completely effective, the total change in fair value (clean price) of the underlying transaction is recorded on the profit and loss statement.

**Note:**

If the cross-currency interest rate swap and underlying transaction are in local currency, the total effect is derived from the interest rate effect. However, when using a foreign currency, the total effect depends on the interest rate and foreign exchange.

When you value a financial asset or liability, you always need to enter the foreign exchange effect or underlying transaction in foreign currency on the profit and loss statement. If the hedging relationship is effective, the interest rate effect is also taken into account in profit and loss. You can also use a hypothetical derivative.

Creating a Hedging Relationship

To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Create a new hedge plan and choose the risk category Interest Rate Risk. You can also set the Single Hedged Item indicator.
- 3. On the Hedged Item tab page, choose the hedge category Fair Value Hedge.
- 4. For the hedging relationship, specify the cross-currency interest rate swap that you entered as the hedging instrument. Choose hedge strategy 500 Benchmark Clean Price and specify a spread.


**Recommendation:**

In the case of interest rate risk, the system automatically loads the transaction or interest payments belonging to a transaction as an exposure. If you set the Single Hedged Item indicator, the exposures are only assigned to one hedged item. We recommend setting this indicator if you only want to use a cross-currency interest rate swap to hedge an interest rate instrument with multiple interest payments.

**Note:**

Depending on the underlying transaction, the system automatically assigns Financial Asset or Financial Liability to the Transaction Category field, or Position or Cash Flow to the Transaction Activity field.

**Recommendation:**

We recommend that you choose one value so that the net present value of the underlying transaction corresponds to the market value at the start of the hedging relationship.

Selecting the Hedge Strategy

The standard Customizing setting available is hedge strategy 500 with calculation type 201 Interest Rate Instrument: Benchmark without Accrued Interest. If you decide to use another hedge strategy, it must use a calculation type based on calculation category 201.

Settings in the Money Market and Position Management Areas

The standard setting defined in Customizing for the underlying transaction is product type 55B Interest Rate Instrument, Hedge Acc, which is assigned to valuation procedure 3002 Money Market Transactions: Underlying Transaction, Hedge Acc.

The standard Customizing setting for the hedging instrument is product type 62D Cross-Currency Int. Rate Swap: Hedge Accounting which is assigned to valuation procedure 3000 Derivatives: Hedging Inst., Hedge Acc..

See also:

Fair Value Hedge (FVH) to Hedge Interest Rate Risk

###### FVH : Interest Rate Swap and a Cross-Currency Interest Rate Swap Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Fair Value Hedge (FVH) > Fair Value Hedge (FVH) to Hedge Interest Rate Risk > FVH : Interest Rate Swap and a Cross-Currency Interest Rate Swap Used as a Hedging Transaction | L7 | trm09 p.258 | loio `0d0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0d0cda531198434de10000000a174cb4.html?locale=en-US)

**Example:**

Your local currency is EUR. You want to use a cross-currency interest rate swap to hedge the interest rate risk of an interest rate instrument with fixed interest in USD. You have two options:

You can use one cross-currency interest rate swap as a hedging transaction to convert USD (fixed) to EUR (variable) for example. This is the standard method delivered with the system.

You can also hedge your exposure using a USD interest rate swap (USD, fixed, to USD, variable) and a USD/EUR crosscurrency interest rate swap (USD, variable, to EUR, variable).

**Note:**

Usually, you cannot assign more than one hedging transaction to an exposure since the nominal amount of the exposure has already been hedged with the first hedging transaction.

If your hedging transactions are linked by the reference category HMT – Reference in Hedge Accounting , you can still only assign them to one exposure even if the total nominal amount of the hedging transactions exceeds the exposure value. The system calculates the effectiveness for each hedging transaction and compares the underlying and exposure.

The actual effectiveness of the hedge is usually only derived from the group of assigned hedging transactions.

During the valuation, each hedging transaction is considered individually. The same restrictions apply as for the effectiveness test. If you use the second method, you need to ensure that the assignment is appropriate from a business point of view.

See also:

Fair Value Hedge (FVH) to Hedge Interest Rate Risk

###### Cash Flow Hedge (CFH)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) | L5 | trm09 p.258 | loio `e00bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e00bda531198434de10000000a174cb4.html?locale=en-US)

Cash flow hedges are transactions that are used to hedge against the risk of variations in future cash flows (interest rate risks or foreign currency risks).

Hedge Accounting

Hedge accounting for cash flow hedges is used mainly for hedging instruments.

According to IAS 39, in the case of effective cash flow hedges, the effective portion of the change in value of the hedging instrument is recognized in equity. The amounts in equity are written off on a pro rata basis and posted to the profit and loss statement once the hedging relationship has been dissolved.

The ineffective portions of the changes in value of hedging instruments are posted directly to the profit and loss statement.

See also:

Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk

Cash Flow Hedge (CFH) to Hedge Interest Rate Risk

###### Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk | L6 | trm09 p.259 | loio `e30bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e30bda531198434de10000000a174cb4.html?locale=en-US)

In the case of a planned transaction in foreign currency, fluctuations in the foreign currency may result in the payment amount being greater than expected. You can hedge this risk with a cash flow hedge . The payment represents the exposure.

To map a hedging relationship, the following product types are provided for the hedging instrument:

Money market transactions: Fixed-term deposit, Commercial Paper, Interest rate instrument

Forward exchange transaction

Option on forward exchange transaction

Currency option collar

Cross currency interest rate swap

See also:

CFH: Fixed Term Deposit, Commercial Paper, or Interest Rate Instrument Used as a Hedging Transaction

CFH: Cap/Floor Used as a Hedging Transaction

CFH: Option on Forward Exchange Transaction Used as a Hedging Transaction

CFH: Currency Option Collar (Option Spread) Used as a Hedging Transaction

CFH: Cross Currency Interest Rate Swap Used as a Hedging Transaction

Cash Flow Hedge (CFH) to Hedge Interest Rate Risk

###### CFH: Fixed Term Deposits, Commercial Paper, or Interest Rate Instruments Used in a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk > CFH: Fixed Term Deposits, Commercial Paper, or Interest Rate Instruments Used in a Hedging Transaction | L7 | trm09 p.259 | loio `da0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/da0bda531198434de10000000a174cb4.html?locale=en-US)

Use

Valuation and Effectiveness Test

Non-derivative financial instruments can only be used to hedge foreign currency effects. The valuation and effectiveness test therefore only use the foreign currency effect (spot method).

As part of the effectiveness test, on the valuation key date, the system translates the nominal values for the defined hedging transactions and the corresponding exposures at the spot rate and then compares them. All the interest flows and amortization flows associated with the money market transaction are ignored.

If the test proves the hedging relationship to be 100% effective, the foreign currency effect is posted to equity (OCI) without affecting profit and loss.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two scenarios:

If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.

If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.

**Note:**

Alternatively, you can use a hypothetical derivative in the effectiveness test.

Creating a Hedging Relationship

You have already created a money market transaction using the transaction Create Financial Transaction (FTR_CREATE). To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Generate a new hedge plan and specify the risk category Exchange Rate Risk.
- 3. Create a new exposure on the Exposure tab page. Specify the nominal amount. Choose the transaction category Planned Transaction or Firm Commitment as well as the transaction activity Purchase or Sale.
- 4. Create a new hedged item of the Hedged Item tab page using the exposure you created previously. Choose the hedge category Cash Flow Hedge.Save your entries.
- 5. Specify your hedging instrument as the money market transaction that you have already created on the Hedging Relationship tab page. Select the 100 - CF Spot Rate Period/Period hedge strategy.


**Prerequisites**

Customizing Settings

Selecting the Hedge Strategy

We recommend that you use the hedge strategy 100 (CF Spot Rate Period/Period) with calculation type 100 that are defined as standard in Customizing.

If you decide to use a different hedge strategy, it must use a calculation type based on calculation category 001 Cash Flow Differences Acc. to Spot Rate and on Cash Flow Determination Method 1 (FAS133). To create a hedge strategy, go to Customizing for the Transaction Manager and choose General Settings Hedge Accounting for Exposures Effectiveness Test Define Hedge Strategies .

Product Types

In Customizing for the Transaction Manager you can use product type 55C (Interest Rate Transaction: Hedging Instr. Hedge Acc.) under Money Market Transaction Management Product Types Define Product Types .

Product type 55C is assigned to position management procedure 3003 (Money Market Transactions Used as Hedging Instr., Hedge Acc). This setting is made in Customizing for the Transaction Manager under Accounting Settings for Position Management Assign Position Management Procedure .

For fixed-term deposits and commercial papers, you can define individual product types and assign position management procedure 3003.

See also:

Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk

###### CFH: Forward Exchange Transaction Used in a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk > CFH: Forward Exchange Transaction Used in a Hedging Transaction | L7 | trm09 p.261 | loio `e90bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e90bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

Valuation and Effectiveness Test

As part of the effectiveness test and valuation for forward exchange transactions, you can decide whether to view only the foreign currency effect (spot method) or the interest rate and foreign currency effects together (full fair value method).

Spot Method:

As part of the effectiveness test, on the valuation key date the system translates the nominal values for the defined hedging transactions and the corresponding exposures at the spot rate. It then compares these values.

For the valuation of the forward exchange transaction, the system takes into account the foreign currency effect and the interest rate effect.

If the hedging relationship is 100% effective, the system posts the foreign currency effect to equity (OCI) without affecting net income. The interest rate effect, however, is recorded in the income statement.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two posting scenarios:

If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.

If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.

Full Fair Value Method:

As part of the effectiveness test, the system calculates the net present value of the forward exchange transaction and the exposure on the valuation key date. It then compares these values.

For the valuation of the forward exchange transaction, the system takes into account the foreign currency effect and the interest rate effect.

If the hedging relationship is 100% effective, the system posts the foreign currency effect to equity where it has no affect on net income. The interest rate effect, however, is posted as affecting net income in the income statement.

If an effective hedging relationship is not 100% effective, the system differentiates between two posting scenarios as mentioned above.

**Note:**

Alternatively, you can use a suitable hypothetical derivative for both methods in the effectiveness test.

Creating a Hedging Relationship

You have the following two options when you create a hedging relationship:

- Option A:

You create the forward exchange transaction at the same time as the exposure, hedging relationship, and corresponding hedging instrument.

In the application menu, choose Treasury and Risk Management Transaction Manager Foreign Exchange Trading Create Financial Transaction (transaction FTR_CREATE).

Create a forward exchange transaction. Choose product type 60B Foreign Exchange (FX) Hedge Accounting with transaction type 102 Foreign Exchange (FX) Hedge Accounting Forward Transaction. On the Structure tab page, enter the required transaction conditions.

Choose the Hedge Accounting tab. Enter the transaction category Cash Flow Hedge and the activity category Planned Transaction or Firm Commitment.

Choose hedge strategy 100 CF Spot Rate Period/Period or 200 NPV Period/Period.

- Option B:


You have already created the forward exchange transaction and now want to create a hedging relationship.

From the application menu, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (transaction THMEX).

Specify the risk category Exchange Rate Risk and the required data for the new hedge plan. Choose the transaction activity Planned Transaction or Firm Commitment. Specify the transaction activity Purchase or Sell.

Choose the Hedged Item tab page and select the relevant exposure.

Specify the transaction category Financial Asset or Financial Liability. Choose the hedge category Cash Flow Hedge.

On the Hedging Relationship tab page, specify the hedging instrument using one of your foreign exchange transactions with a freely-defined derivative volume. Choose hedge strategy 100 CF Spot Rate Period/Period or 200 NPV Period/Period.

Selecting the Hedge Strategy

Spot Method:

SAP recommends that you use the hedge strategy 100 (CF Spot Rate Period/Period) with calculation type 100 that are entered as the default values in Customizing.

If you decide to use a different hedge strategy, it must use a calculation type based on calculation category 001Cash Flow Differences Acc. to Spot Rate, and on Cash Flow Determination Method 1 (FAS133: Usage of 30(b)).

Full Fair Value Method:

SAP recommends that you use hedge strategy 200 NPV Period/Period in the standard system with calculation type 200.

If you decide to use a different hedge strategy, it must use a calculation type based on calculation category 100 NPV and on Cash Flow Determination Method 1 (FAS133: Usage of 30(b...)).

**Prerequisites**

Customizing Settings

Spot Method:

In the Foreign Exchange area, there is no corresponding product type available in the standard system in Customizing for the Transaction Manager. To define a forward exchange transaction as a hedging transaction, in Customizing for the Transaction Manager, choose Foreign Exchange Transaction Management Product Types Define Product Types . You then copy product type 60B - Foreign Exchange (FX) Hedge Accounting as your new product type.

Then assign this product type to position management procedure 3004 (Money Market Transactions Used as Hedging Instr., Hedge Acc.). In Customizing for the Transaction Manager, choose General Settings Accounting Settings for Position Management Assign Position Management Procedure .

You also need to make the required settings in Customizing for the Transaction Manager by choosing General Settings Hedge Accounting for Exposures Effectiveness Test .

Full Fair Value Method:

For the Foreign Exchange area, the product type 55B Foreign Exchange (FX) Hedge Accounting is available in the standard Customizing settings for the Transaction Manager. This product type is assigned to the position management procedure 3001 Derivatives: Mark-to-Market as Hedging Instr., Hedge Acc..

See also:

Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk

###### CFH: Option on Forward Exchange Transaction Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk > CFH: Option on Forward Exchange Transaction Used as a Hedging Transaction | L7 | trm09 p.263 | loio `fe0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fe0bda531198434de10000000a174cb4.html?locale=en-US)

**Valuation and Effectiveness Test**

As part of the effectiveness test and the valuation for options on forward exchange transactions, you can decide whether to view only the foreign currency effect of the underlying (spot method) or the total effect of the option (full fair value method: interest rate effect and foreign currency effect of the forward exchange transaction as well as the time value of the option).

**Note:**

Alternatively, you can use a suitable hypothetical derivative for both methods in the effectiveness test.

Spot Method:

As part of the effectiveness test and on the valuation key date, the system translates the nominal values of the forward exchange transaction (underlying) and the corresponding exposures at the spot rate and then compares them.

During the option valuation for the forward exchange transaction, the system takes into account the foreign currency effect and interest rate effect as well as the time value of the option.

If the hedging relationship is 100% effective, the foreign currency effect of the forward exchange transaction is posted in equity without affecting profit and loss. The time value of the option and the interest rate effect of the forward exchange transaction are recognized however on the profit and loss statement.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two scenarios:

If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.

If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.

Full Fair Value Method:

As part of the effectiveness test, the system calculates the intrinsic value of the option as well as the net present value of the exposure on the valuation key date. It then compares these values. When the system calculates the intrinsic value of the option, it converts the values of the underlying flows using the forward rate and then discounts them. If the amount is negative, it is set automatically to zero.

During the option valuation, the system takes the total value of the option into account (interest rate effect and foreign exchange effect of the forward exchange transaction as well as the time value of the option).

If the hedging relationship is 100% effective, the total value of the option is posted in equity without affecting profit and loss.

If an effective hedging relationship is not 100% effective, the system differentiates between two scenarios as mentioned above.

**Creating a Hedging Relationship**

To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Specify the risk category Exchange Rate Risk and the required data for the new hedge plan. Choose the transaction category Planned Transaction or Firm Commitment. Specify the transaction activity Purchase or Sell.
- 3. Choose the Hedged Item tab page and select the relevant exposure. Choose the hedge category Cash Flow Hedge.
- 4. On the Hedging Relationship tab page, specify one of the options that you entered as the hedging instrument. Choose the hedge strategy 405 Options: Intrinsic Value Spot Rate or 400 - Option Intrinsic Value, Forward Rate Disc. Period/Period.


**Selecting the Hedge Strategy**

Spot Method:

We recommend that you use the hedge strategy 405 (CF Spot Rate Period/Period) with calculation type 405 that are defined as standard in Customizing.

If you decide to use a different hedge strategy, it must use a calculation type based on calculation category 11 Options: Intrinsic Value, Spot Rate and on Cash Flow Determination Method 1 (FAS133: Usage of 30(b)...).

**Note:**

If hedge strategy 405 is not available in your system, in Customizing for the Transaction Manager, choose General Settings Hedge Accounting for Exposures Effectiveness Test Define Calculation Types .

Copy calculation type 400 and change the ID to 405. Enter the description Option: Intrinsic Value, Spot Rate Period/Period and select calculation category 11Option: Intrinsic Value, Spot Rate.

In Customizing for the Transaction Manager, choose General Settings Hedge Accounting for Exposures Effectiveness Test Define Hedge Strategies .

Create a copy of hedge strategy 400 with ID 405. Change the description to Option: Intrinsic Value, Spot Rate Period/Period and enter 405 under Assmt Calc Type and Measmt CalcType.

Full Fair Value Method:

We recommend that you use hedge strategy 400 (Option, Intrinsic Value, Forward Rate, Disc. Period/Period) defined as standard in Customizing together with calculation type 400.

If you decide to use a different hedge strategy, it must use a calculation type based on calculation category 13 Options: Intrinsic Value, Forward Rate, Disc. and on Cash Flow Determination Method 1 (FAS133: Usage of 30(b)...).

**Customizing Settings**

Spot Method and Full Fair Value Method:

In Customizing for the Transaction Manager, you can use the standard product type 76X OTC Forex Option, Hedge Acc. To use this, choose OTC Derivatives Transaction Management Product Types Define Product Types .

Product type 76X is assigned to the position management procedure 3000 (Derivatives: Mark-to-Market as Hedging Instr., Hedge Acc.). You find this setting in Customizing for the Transaction Manager under General Settings Accounting Settings for Position Management Assign Position Management Procedure .

Full Fair Value Method Only:

To ensure that the time value is also posted to equity (and not recorded in profit and loss) when determining the effectiveness of the hedging relationship, you need to make the following settings in Customizing for the Transaction Manager:

Choose General Settings Accounting Hedge Accounting for Exposures Update Types Assign Update Types for Hedge Accounting .

Double-click on the line for position management procedure 3000.

Under Treatment of Time Value, choose B No Classification of Time Value.

**See also:**

Hypothetical and Perfect Derivative

Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk

###### CFH: Foreign Exchange Collars Used as Hedging Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk > CFH: Foreign Exchange Collars Used as Hedging Transactions | L7 | trm09 p.266 | loio `dd0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dd0bda531198434de10000000a174cb4.html?locale=en-US)

**General Information on Foreign Exchange Collars**

Foreign exchange collars (option spreads) involve the purchase of a call option and the sale of a put option, or vice versa.

**Example:**

On 01.01. of the current year you intend to purchase goods on 01.02. the following year at a value of USD 1,000. Your local currency is EUR. The exchange rate for USD is 1.20 on 01.01. of the current year.

If the exchange rate drops in the meantime, however, the payment you make in EUR will be greater than expected. To hedge this risk, you buy a European call option to purchase USD 1,000 at an exchange rate of 1.17 (USD/EUR). You pay a premium of USD 12 to buy the option.

To clear the premium payment, you sell a European put option so that the sale of USD 1,000 occurs at an exchange rate of 1.23 USD/EUR.

The exercise key date for both options is 01.01 the following year.

In this example, you use a foreign exchange collar to hedge an exchange rate of less than 1.17. At the same time, profit gained due to a higher exchange rate is limited to the amount that you would receive if the exchange rate were to increase to 1.23. The exchange rate spread from 1.17 to 1.23 allows you to profit from favorable exchange rate developments.

You can also use foreign exchange collars (also known as range forwards) to determine upper and lower limits to exercise purchase and sale transactions.

**Mapping Foreign Exchange Collars in the System**

Foreign exchange collars are mapped in the system using two options on forward exchange transactions. The two options are linked to each other with a reference from category OPTOption Spread. To create and use both options directly in an option spread, on the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Foreign Exchange

Trading Currency Option Entry - Spread (transaction TI4B).

Alternatively, you can create both options separately then link them with reference HMTReference in Hedge Accounting of theOPTOptions Spread. To do this, on the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Derivatives Back Office Reference Create (transaction TBR6).

**Valuation and Effectiveness Test**

Usually, you cannot assign more than one option to an exposure since the nominal amount of the exposure has already been hedged with the first option. You can therefore only hedge exposures with foreign exchange collars if the options are linked to the reference of category OPTOption Spread or HMTReference in Hedge Accounting. You can use the reference to assign more than one option to the exposure, even if the total nominal amount of the options exceeds the exposure value. In this case, the system checks only the maximum nominal amount of a reference.

The effectiveness test and measurement are carried out separately for each currency option. When doing this, the system compares the values of the underlying with the exposure. In practice, the effectiveness of the hedge is determined by the group of assigned derivatives.

Creating a Hedging Relationship

To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Specify the risk category Exchange Rate Risk and the required data for the new hedge plan. Choose the transaction activity Purchase or Sell.
- 3. Choose the Hedged Item tab page and select the relevant exposure. Specify the transaction category Planned Transaction or Firm Commitment. Choose the hedge category Cash Flow Hedge.
- 4. On the Hedging Relationship tab page, specify the first option of the currency option collar. If you have assigned an option to a currency option collar, the system displays the Reference Category and Reference fields.
- 5. Choose the hedge strategy 405 Options: Intrinsic Value Spot Rate or 400 Option Intrinsic Value, Forward Rate Disc. Period/Period.
- 6. Create another hedging relationship and specify the second option of the currency option collar as the hedging instrument. Choose the hedge strategy that you selected for the first option.


See also:

Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk

###### CFH: Cross Currency Interest Rate Swap Used as a Hedging Transaction (1 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk > CFH: Cross Currency Interest Rate Swap Used as a Hedging Transaction | L7 | trm09 p.267 | loio `d70bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d70bda531198434de10000000a174cb4.html?locale=en-US)

**Valuation and Effectiveness Test**

As part of the effectiveness test and the valuation for the cross-currency interest rate swap, you can decide whether to view only the foreign currency effect (spot method) or the total effect of the option (full fair value method: interest rate effect and foreign currency effect).

Spot Method:

As part of the effectiveness test and on the valuation key date, the system translates the nominal values of the cross-currency interest rate swap and the corresponding exposures at the spot rate and then compares them. All the interest flows associated with the cross-currency interest rate swap are ignored.

To value the cross-currency interest rate swap, the system runs a foreign currency valuation and security valuation.

If the hedging relationship is 100% effective, the system posts the foreign currency effect to equity (OCI) without affecting net income. The interest rate effect, however, is recorded in the income statement.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two scenarios:

- 1. If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.
- 2. If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.


Full Fair Value Method:

As part of the effectiveness test, the system calculates the net present value of the cross-currency interest rate swap and the exposure on the valuation key date. It then compares these values.

To value the cross-currency interest rate swap, the system takes into account the foreign currency effect and the interest rate effect.

If the hedging relationship is 100% effective, the total effect (forex effect and interest rate effect) is recognized in equity without affecting profit and loss.

If an effective hedging relationship is not 100% effective, the system differentiates between two posting scenarios as mentioned above.

**Note:**

Alternatively, you can use a suitable hypothetical derivative for both methods in the effectiveness test.

**Creating a Hedging Relationship**

To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Specify the risk category Exchange Rate Risk and the required data for the new hedge plan.
- 3. Choose the transaction activity Planned Transaction or Firm Commitment. Specify the transaction activity Purchase or Sell.
- 4. Choose the Hedged Item tab page and select the relevant exposure.
- 5. Specify the transaction category Planned Transaction or Financial Liability.
- 6. Choose the hedge category Cash Flow Hedge.
- 7. On the Hedging Relationship tab page, specify one of your cross-currency interest rate swaps that you entered as the hedging instrument.
- 8. Choose hedge strategy 100 CF Spot Rate Period/Period or 200 NPV Period/Period.


**Selecting the Hedge Strategy**

Spot Method:

We recommend that you use the hedge strategy 100 (CF Spot Rate Period/Period) with calculation type 100 that are defined as standard in Customizing.

If you decide to use a different hedge strategy, it must use a calculation type based on calculation category 003 Cash Flow Differences Acc. to Spot Rate and on Cash Flow Determination Method 1 (FAS133: Anwendung.v.30(b)...).

Full Fair Value Method:

We recommend that you use hedge strategy 200 NPV Period/Period available in Customizing in the standard system with calculation type 200.

If you decide to use a different hedge strategy, it must use a calculation type based on calculation category 100 NPV and on Cash Flow Determination Method 1 (FAS133).

**Customizing Settings**

In Customizing for the Transaction Manager, you need to define product type 62D (Cross-Currency Interest Rate Swap, Hedge Acc.). To do this, choose Listed Derivatives Transaction Management Product Types Define Product Types

.


Product type 62D must be assigned to position management procedure 3000 (Derivatives: Hedging Instr., Hedge Acc.). This setting is made in Customizing for the Transaction Manager under Accounting Settings for Position Management Assign Position Management Procedure .

To use a cross-currency interest rate swap as a hedging instrument, you need to select Awith Reset in the input help Generation Type of Flows for Realization for position management procedure 3000. You do this in Customizing for the Transaction Manager by choosing General Settings Accounting Hedge Accounting for Exposures Assign Update Types for Hedge Accounting .

**See also:**

Hypothetical and Perfect Derivative

Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk

###### Cash Flow Hedge (CFH) to Hedge Interest Rate Risk

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Interest Rate Risk | L6 | trm09 p.269 | loio `fb0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fb0bda531198434de10000000a174cb4.html?locale=en-US)

In the case of a planned transaction, interest rate trends may result in the payment amount being greater than expected. You can hedge this risk with a cash flow hedge . The payment represents the exposure.

To map a hedging relationship, the following product types are provided for the hedging instrument:

Interest rate swap

Cap/floor

Cap/floor collar

FRA (Forward Rate Agreement)

Cross currency interest rate swap

See also:

CFH: Interest Rate Swap Used as a Hedging Transaction

CFH: Cap/Floor Used as a Hedging Transaction

CFH: Cap/Floor Collar Used as a Hedging Transaction

CFH: FRA Used as a Hedging Transaction

CFH: Cross Currency Interest Rate Swap Used as a Hedging Transaction

CFH: Cross Currency Interest Rate Swap and Interest Rate Swap Used as a Hedging Transaction

Cash Flow Hedge (CFH) to Hedge Foreign Currency Risk

###### CFH: Interest Rate Swap Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Interest Rate Risk > CFH: Interest Rate Swap Used as a Hedging Transaction | L7 | trm09 p.270 | loio `e60bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e60bda531198434de10000000a174cb4.html?locale=en-US)

**Valuation and Effectiveness Test**

As part of the effectiveness test, the system determines the forward rates of the variable interest payments of the interest rate swap and the assigned variable interest payments of the exposure. These values are discounted on the valuation key date and then totaled for the underlying transaction and hedging transaction. Both totals are then compared.

For the interest rate swap, the system runs a foreign currency valuation and security valuation.

If the hedging relationship is 100% effective, the total effect is recognized in equity without affecting profit and loss.

**Note:**

If the underlying transaction and the hedging transaction (interest rate swap) are concluded in local currency, the total effect comprises only the interest rate effect. If a foreign currency is involved, the total effect comprises the interest rate and foreign currency effects. The system cannot manage these effects separately in the effectiveness test.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two scenarios:

If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.

If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.

Alternatively, you can use a hypothetical derivative in the effectiveness test.

**Creating a Hedging Relationship**

To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Transaction Manager Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (transaction THMEX).
- 2. Specify Interest Rate Risk as the risk category.
- 3. Once the underlying transaction has been uploaded, Liabilities or Financial Assets are displayed under the Transaction Category, and Position or Cash Flow are displayed under Transaction Activity. You can also specify the underlying transaction manually.
- 4. Choose the Hedged Item tab page and select the hedge category Cash Flow Hedge.
- 5. On the Hedging Relationship tab page, specify the interest rate swap that you entered as the hedging instrument.
- 6. Select the hedge strategy 103 CF Forward Discounted, Cumulated.


**Note:**

If the Single Hedged Item indicator is set, the system assigns all the loaded exposures (an interest rate instrument or the interest payment in a transaction) to only one hedged item. We recommend setting this indicator if you want to hedge multiple interest payments for an interest rate instrument using an interest rate swap.

Selecting the Hedge Strategy

We recommend that you use the hedge strategy 103 CF Forward Discounted, Cumulated delivered as standard in Customizing with the calculation type 103.

If you decide to use a different hedge strategy, this strategy must use a calculation type based on calculation category 003 Cash Flow Differences, Forward Rate Discounted and on Cash Flow Determination Method 2 (FAS133: DIG G7 method 1).

**Customizing Settings**

In Customizing for the Transaction Manager, you can use the standard product type 62C (Interest Rate Swap, Hedge Accounting) by choosing OTC Derivatives Transaction Management Product Types Define Product Types .

Product type 62C is assigned to position management procedure 3000 (Derivatives: Hedging Instr., Hedge Acc.). This setting is made in Customizing for the Transaction Manager under Accounting Settings for Position Management Assign Position Management Procedure .

**See also:**

Hypothetical and Perfect Derivative

Cash Flow Hedge (CFH) to Hedge Interest Rate Risk

###### CFH: Cap/Floor Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Interest Rate Risk > CFH: Cap/Floor Used as a Hedging Transaction | L7 | trm09 p.271 | loio `f80bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f80bda531198434de10000000a174cb4.html?locale=en-US)

**Valuation and Effectiveness Test**

As part of the effectiveness test, the system determines the sum of the intrinsic values of each caplet on the valuation key date. The intrinsic value of a caplet is found by subtracting the strike amount from the value of the interest flow. (If the result is negative, the system sets it automatically to zero.) The value is translated using the forward rate and is then discounted.

This result is then compared with the change in value of the underlying transaction. The change in value is determined by subtracting the strike amount from the interest flows of the exposure, translating the amount with the forward rate, and then discounting it. If this results in a negative value, it is also set to zero.

Floors are calculated in the same way. For caps and floors, the system runs a foreign currency valuation and security valuation.

If the hedging relationship is 100% effective, the total effect is recognized in equity without affecting profit and loss.

If the underlying transaction and the hedging transaction (interest rate swap) are concluded in local currency, the total effect comprises only the interest rate effect. If a foreign currency is involved, the total effect comprises the interest rate and foreign currency effects. The system cannot manage these effects separately in the effectiveness test.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two scenarios:

If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.

If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.

**Note:**

Alternatively, you can use a hypothetical derivative in the effectiveness test.

**Creating a Hedging Relationship**

To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Specify Interest Rate Risk as the risk category.

If the Single Hedged Item indicator is set, the system assigns all the loaded exposures (an interest rate instrument or the interest payment in a transaction) to only one hedged item. We recommend setting this indicator if you want to hedge multiple interest payments for an interest rate instrument using a cap or floor.

- 3. Once the underlying transaction has been uploaded, Liabilities or Financial Assets are displayed under the Transaction Category, and Position or Cash Flow are displayed under Transaction Activity. You can also select the underlying transaction manually.
- 4. Choose the Hedged Item tab page and select the hedge category Cash Flow Hedge.
- 5. On the Hedging Relationship tab page, specify the interest rate swap that you entered as the hedging instrument.
- 6. Select the hedge strategy 103 CF Forward Discounted, Cumulated.


**Selecting the Hedge Strategy**

We recommend that you use the hedge strategy 103 CF Forward Discounted, Cumulated delivered as standard in Customizing with the calculation type 103.

If you decide to use a different hedge strategy, this strategy must use a calculation type based on calculation category 003 Cash Flow Differences, Forward Rate Discounted and on Cash Flow Determination Method 2 (FAS133: DIG G7 method 1).

**Customizing Settings**

In Customizing for the Transaction Manager the product types 62C (Int. Rate Swap: Hedge Accounting) and 61D (FLOOR Hedge Accounting) are delivered with the standard system. To select these, choose OTC Derivatives Transaction Management Product Types Define Product Types .

These product types are assigned to the position management procedure 3000 (Derivatives: Mark-to-Market as Hedging Instr., Hedge Acc.). This setting is made in Customizing for the Transaction Manager under Accounting Settings for Position Management Assign Position Management Procedure .

See also:

Hypothetical and Perfect Derivative

Cash Flow Hedge (CFH) to Hedge Interest Rate Risk

###### CFH:Cap/Floor Collar Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Interest Rate Risk > CFH:Cap/Floor Collar Used as a Hedging Transaction | L7 | trm09 p.272 | loio `ec0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ec0bda531198434de10000000a174cb4.html?locale=en-US)

**General Information About Cap/Floor Collars**

Cap/Floor collars combine the purchase of a cap and the sale of a floor or the sale of a cap and the purchase of a floor.

**Example:**

You take out a loan on 01.01 of the current year. The monthly interest rate is variable. The term is one year. On 31.12. of the previous year, the interest rate was 3.5 percent.

As a guarantee against the interest rate risk, you buy a cap with a strike of 3.75.

You pay EUR 1200 as a premium. To clear this premium payment, you buy a floor with a strike of 3.25.

This cap/floor collar allows you to hedge against an interest rate that would exceed 3.75. At the same time, you limit profit realized due to a lower interest rate to the amount that you would receive if the interest rate were to drop to 3.25. You need to take into account the uncertainty of interest rate developments in the interest rate spread of 3.25 to 3.75.

**Mapping Cap/Floor Collars in the System**

The system maps cap/floor collars by linking the hedging transactions (cap and floor) with each other using a reference category HMT Reference in Hedge Management. You can access the transactions for the references on the SAP Easy Access screen by choosing Treasury and Risk Management Transaction Manager Money Market/Forex/Derivatives/Securities Back Office Reference (transaction TBR6).

**Valuation and Effectiveness Test**

Usually, you cannot assign more than one hedging transaction to an exposure since the nominal amount of the exposure has already been hedged with the first hedging transaction. Therefore, it is only possible to hedge exposures with cap/floor collars using the reference of category HMT Reference in Hedge Management. You can use the reference to assign more than one hedging transaction to the exposure, even if the total nominal amount of the cap/floor collar exceeds the exposure value. In this case, the system checks only the maximum nominal amount of a reference.

The effectiveness test and valuation are carried out separately for each hedge transaction. When doing this, the system compares the values of the underlying with the exposure.

**Creating a Hedging Relationship**

To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Specify Interest Rate Risk as the risk category.
- 3. Set the Single Hedged Item indicator. If this indicator is set, the system assigns all the loaded exposures (an interest rate instrument or the interest payment in a transaction) to only one hedged item.
- 4. Choose the Hedged Item tab page and select the hedge category Cash Flow Hedge.
- 5. On the Hedging Relationship tab page, specify the first hedging transaction as the hedging instrument. If the cap or floor was assigned to a collar, the fields Reference Category and Reference are displayed.
- 6. Select the hedge strategy 103 CF Forward Discounted, Cumulated.
- 7. Create another hedging relationship and specify the second hedging transaction as the hedging instrument. Select the hedge strategy 103 CF Forward Discounted, Cumulated.


See also:

Cash Flow Hedge (CFH) to Hedge Interest Rate Risk

###### CFH: FRA Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Interest Rate Risk > CFH: FRA Used as a Hedging Transaction | L7 | trm09 p.274 | loio `ef0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ef0bda531198434de10000000a174cb4.html?locale=en-US)

**Mapping Cap/Floor Collars in the System**

A forward rate agreement (FRA) represents an agreement on a future interest rate. A FRA is used to hedge against falling or rising interest rates.

**Valuation and Effectiveness Test**

As part of the effectiveness test, the system differentiates between a variable and fixed part of the FRA. The system sets the fixed portion to zero and determines the forward interest rates for the variable part of the FRA and the assigned variable interest payment of the exposure. These values are discounted on the valuation key date and then totaled for the underlying transaction and hedging transaction. Both totals are then compared.

If the test proves the hedging relationship to be 100% effective, the total effect is posted to equity capital (OCI) without affecting profit and loss.

**Note:**

If the underlying transaction and the hedging transaction (FRA) are concluded in local currency, the total effect comprises only the interest rate effect. If a foreign currency is involved, the total effect comprises the interest rate and foreign currency effects. The system cannot manage these effects separately in the effectiveness test.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two scenarios:

If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.

If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.

**Note:**

Alternatively, you can use a hypothetical derivative in the effectiveness test.

**Creating a Hedging Relationship**

To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Specify Interest Rate Risk as the risk category.
- 3. Once the underlying transaction has been uploaded, Liabilities or Financial Assets are displayed under the Transaction Category, and Position or Cash Flow are displayed under Transaction Activity. You can also select the underlying


**Note:**

If the Single Hedged Item indicator is set, the system assigns all the loaded exposures (an interest rate instrument or the interest payment in a transaction) to only one hedged item. We recommend that you set this indicator. The reason for this is that a FRA refers to only one interest payment whilst the interest rate instrument usually covers multiple interest payments.

transaction manually.

- 4. Choose the Hedged Item tab page and select the hedge category Cash Flow Hedge.
- 5. On the Hedging Relationship tab page, specify the FRA that you entered as the hedging instrument.
- 6. Select the hedge strategy 103 CF Forward Discounted, Cumulated.


**Selecting the Hedge Strategy**

We recommend that you use the hedge strategy 103 CF Forward Discounted, Cumulated delivered as standard in Customizing with the calculation type 103.

If you decide to use a different hedge strategy, this strategy must use a calculation type based on calculation category 003 Cash Flow Differences, Forward Rate Discounted and on Cash Flow Determination Method 2 (FAS133: DIG G7 method 1).

**Customizing Settings**

In Customizing for the Transaction Manager, you can use the standard product type 63B (FRA Hedge Accounting) by choosing OTC Derivatives Transaction Management Product Types Define Product Types .

Product type 63B is assigned to position management procedure 3000 (Derivatives: Hedging Instr., Hedge Acc.). This setting is made in Customizing for the Transaction Manager under Accounting Settings for Position Management Assign Position Management Procedure .

See also:

Hypothetical and Perfect Derivative

Cash Flow Hedge (CFH) to Hedge Interest Rate Risk

###### CFH: Cross Currency Interest Rate Swap Used as a Hedging Transaction (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Interest Rate Risk > CFH: Cross Currency Interest Rate Swap Used as a Hedging Transaction | L7 | trm09 p.275 | loio `f20bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f20bda531198434de10000000a174cb4.html?locale=en-US)

**Valuation and Effectiveness Test**

As part of the effectiveness test, the system determines the forward interest rates of the variable interest payments of the crosscurrency interest rate swap, and the variable interest payments of the assigned exposure. These values are discounted on the valuation key date and then totaled for the underlying transaction and hedging transaction. Both totals are then compared.

To value the cross-currency interest rate swap, the system runs a foreign currency valuation and security valuation.

Unlike other interest rate instruments, cross-currency interest rate swaps are characterized by a one-off repayment at the end of the term. This future cash flow is usually linked to a currency risk. To ensure that only the interest rate effect is posted as part of the effectiveness test for the hedging relationship, the system first subtracts the change in value caused by the repayment from the total value of the cross-currency interest rate swap.

When you use a cross-currency interest rate swap to hedge interest rate risk, it is important that the critical terms of the hedging transaction match those of the underlying transaction (particularly the nominal values). If this is not the case, the system subtracts the wrong amount from the value of the cross-currency interest rate swap.

As part of this operation, only the foreign currency effect associated with the repayment of the underlying transaction is subtracted from the value of the cross-currency interest rate swap. The total effect of all the interest payments from the cross-

currency interest rate swap is posted to equity without affecting profit and loss.

Since it is not technically possibly to separate the value of the repayment from the value of the cross-currency interest rate swap, the system first calculates the change in value of the underlying transaction and deducts this from the total change in value of the cross-currency interest rate swap. The difference represents the interest rate effect that the system posts to equity. The change in value of the underlying transaction is recorded on the profit and loss statement.

Alternatively, you can use a hypothetical derivative in the effectiveness test.

**Creating a Hedging Relationship**

To create a hedging relationship, proceed as follows:

- 1. On the SAP Easy Access screen, choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Specify Interest Rate Risk as the risk category.
- 3. Once the underlying transaction has been uploaded, Liabilities or Financial Assets are displayed under the Transaction Category, and Position or Cash Flow are displayed under Transaction Activity. You can also select the underlying transaction manually.
- 4. Choose the Hedged Item tab page and select the hedge category Cash Flow Hedge.
- 5. On the Hedging Relationship tab page, specify the cross-currency interest rate swap that you entered as the hedging instrument.
- 6. Select the hedge strategy 103 CF Forward Discounted, Period/Period.


**Note:**

If the Single Hedged Item indicator is set, the system assigns all the loaded exposures (an interest rate instrument or the interest payment in a transaction) to only one hedged item. We recommend setting this indicator if you want to use only one cross-currency interest rate swap to hedge an interest rate instrument with multiple interest payments.

**Selecting the Hedge Strategy**

We recommend that you use the hedge strategy 103 (CF Forward Discounted, Period/Period) with calculation type 103 that are defined as standard in Customizing.

If you decide to use a different hedge strategy, this strategy must use a calculation type based on calculation category 003 Cash Flow Differences, Forward Rate Discounted and on Cash Flow Determination Method 2 (FAS133: DIG G7 method 1(.

**Customizing Settings**

In Customizing for the Transaction Manager, you need to define product type 62D (Cross-Currency Interest Rate Swap, Hedge Acc.). To do this, choose Listed Derivatives Transaction Management Product Types Define Product Types .

Product type 62D must be assigned to position management procedure 3000 (Derivatives: Hedging Instr., Hedge Acc.). This setting is made in Customizing for the Transaction Manager under Accounting Settings for Position Management Assign Position Management Procedure .

**See also**

Cash Flow Hedge (CFH) to Hedge Interest Rate Risk

###### CFH: Cross Currency Interest Rate Swap and Interest Rate Swap Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Cash Flow Hedge (CFH) to Hedge Interest Rate Risk > CFH: Cross Currency Interest Rate Swap and Interest Rate Swap Used as a Hedging Transaction | L7 | trm09 p.277 | loio `f50bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f50bda531198434de10000000a174cb4.html?locale=en-US)

**Example**

Your local currency is EUR. You intend to hedge the interest rate risk of an interest rate instrument with variable interest in USD using a cross-currency interest rate swap. You have two options:

- Option A:

You can use a cross-currency interest rate swap as a hedging transaction to convert USD (variable) to EUR (fixed), for example. This is the standard method delivered with the system.

- Option B:


You can hedge your exposure using a combination of an interest rate swap (USD, variable, to USD, fixed) and a crosscurrency interest rate swap (USD, fixed, to EUR fixed).

Usually, you cannot assign more than one hedging transaction to an exposure since the nominal amount of the exposure has already been hedged with the first hedging transaction.

If the hedging transactions are linked by the reference category HMT Reference in Hedge Accounting, you can still assign multiple hedging transactions to an exposure, even if the total nominal amount of the hedging transactions exceeds the exposure value.

The system also carries out the effectiveness test for this method for each hedging transaction in which it compares the underlying with the exposure. The valuation is run in the same way.

**See also:**

Cash Flow Hedge (CFH) to Hedge Interest Rate Risk

###### Net Investment Hedge (NIH) in a Foreign Operation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Net Investment Hedge (NIH) in a Foreign Operation | L6 | trm09 p.277 | loio `c10bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c10bda531198434de10000000a174cb4.html?locale=en-US)

The Hedge of a Net Investment in a Foreign Subsidiary (or Foreign Operation ) involves hedgingforeign currency risk (see IAS/ IFRS 39).

In the case of an effective net investment hedge, the changes in value of the hedging instrument that result from foreign currency fluctuations are posted to equity capital without affecting profit and loss (as opposed to being recognized in profit and loss). The changes in value are transferred from equity capital to profit and loss once the net investment is returned.

The following product types are delivered as standard to map hedging relationships in hedging transactions:

Money market transactions: Fixed-term deposit, Commercial Paper, Interest rate instrument

Forward exchange transaction

Option on forward exchange transaction

Cross currency interest rate swap

See also:

NIH: Fixed Term Deposits, Commercial Paper, or Interest Rate Instruments Used in a Hedging Transaction

NIH: Forward Exchange Transaction Used in a Hedging Transaction

NIH: Option on a Forward Exchange Transaction Used in a Hedging Transaction

NIH: Cross Currency Interest Rate Swap Used in a Hedging Transaction

Hypothetical and Perfect Derivative

###### NIH: Fixed Term Deposit, Commercial Paper, Interest Rate Instrument Used as Hedging Transactions

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Net Investment Hedge (NIH) in a Foreign Operation > NIH: Fixed Term Deposit, Commercial Paper, Interest Rate Instrument Used as Hedging Transactions | L7 | trm09 p.278 | loio `c40bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c40bda531198434de10000000a174cb4.html?locale=en-US)

**Valuation and Effectiveness Test**

As part of this test, the system takes into account the foreign exchange effect resulting from the foreign currency valuation. All the interest flows and amortization flows associated with the money market transaction are ignored.

If the test proves the hedging relationship to be 100% effective, the foreign currency effect is posted to equity (OCI) without affecting profit and loss.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two scenarios:

If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.

If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.

As part of the effectiveness test, on the valuation key date the system translates the nominal values for the defined hedging transactions and the corresponding exposures at the spot rate. It then compares these values.

**Creating a Hedging Relationship:**

You have already created a money market transaction using Create Financial Transaction ( FTR _CREATE). To create a hedging relationship, proceed as follows:

- 1. On the SAPEasy Access screen, choose Treasury and Risk Management Transaction Manager Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX) .
- 2. Generate a new hedge plan and specify the risk category Exchange Rate Risk .
- 3. Create a new exposure on the Exposure tab page. Specify the nominal amount. Choose the transaction category Financial Asset or Financial Liability and the transaction activity Net Investment .
- 4. Create a new hedged item of the Hedged Item tab page using the exposure you created previously. Choose the hedge category Cash Flow Hedge . Save your entries.
- 5. Specify your hedging instrument as the money market transaction that you have already created on the Hedging Relationship tab page. Choose hedge strategy 100 – CF Spot Rate Period/Period or another shortcut strategy.


Selecting the Hedge Strategy

Spot Method:

Differences Acc. to Spot Rate, and on Cash Flow Determination Method 1 ( FAS133) . To create a hedge strategy, in Customizing for the Transaction Manager , choose General Settings Hedge Accounting for Exposures Effectiveness Test Define Hedge Strategies.

**Forward Method:**

If you use the forward method, and the critical terms do not match (see FAS 133 Derivatives Implementation Group Implementation Issue No. H8 ) you need to use a hypothetical derivative to map the hedging relationship.

**Customizing Settings**

In Customizing for the Transaction Manager , you need to define product type 55C ( Interest Rate Instrument, Hedging Instr., Hedge Acc .). To do this, choose Money Market Transaction Management Product Types Define Product Types .

Product type 55C must be assigned to position management procedure 3003 ( Money Market Transactions Used as Hedging Instr., Hedge Acc. ). This setting is made in Customizing for the Transaction Manager under Accounting

Settings for Position Management Assign Position Management Procedure . For fixed-term deposits and Commercial Paper, you can define individual product types and assign position management procedure 3003 in the same way.

See also:

Hypothetical (Perfect) Derivative

Net Investment Hedge (NIH) in a Foreign Operation

###### NIH: Forward Exchange Transaction Used As a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Net Investment Hedge (NIH) in a Foreign Operation > NIH: Forward Exchange Transaction Used As a Hedging Transaction | L7 | trm09 p.279 | loio `be0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/be0bda531198434de10000000a174cb4.html?locale=en-US)

Valuation and Effectiveness Test

Spot Method:

As part of the effectiveness test, on the valuation key date the system translates the nominal values for the defined hedging transactions and the corresponding exposures at the spot rate. It then compares these values.

For the valuation of the forward exchange transaction, the system takes into account the foreign currency effect and the interest rate effect. Only the foreign exchange effect is considered, however, in the effectiveness test.

If the hedging relationship is 100% effective, the system posts the foreign currency effect to equity (OCI) without affecting net income. The interest rate effect, however, is recorded in the income statement.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two posting scenarios:

If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.

If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.

**Forward Method:**

If you use US GAAP, and the critical terms of the underlying transaction match those of the hedging transaction (see FAS 133 Derivatives Implementation Group Implementation Issue No. H8 ), you can post the foreign currency and interest rate effects to equity without running the effectiveness test beforehand. If the critical terms are different, you need to use a hypothetical derivative for this method.

**Creating a Hedging Relationship**

You have two options when creating a hedging relationship:

**Option A:**

You create the forward exchange transaction at the same time as the exposure, hedging relationship, and corresponding hedging instrument.

- 1. On the SAPEasy Access screen, choose Treasury and Risk Management Transaction Manager Foreign Exchange Trading Create Financial Transaction (FTR_CREATE).You use this transaction to create the forward exchange

transaction and exposure as well as the hedging relationship with the hedging instrument.

- 2. Create a forward exchange transaction. Choose product type 60B – Foreign Exchange (FX) Hedge Accounting with transaction type 102 – Foreign Exchange (FX) Hedge Accounting – Forward Transaction . On the Structure tab page, enter the required transaction conditions.
- 3. On the Hedge Management tab page, specify the transaction category Financial Asset . The system automatically uses the Net Investment activity category.
- 4. Choose hedge strategy 100 – CF Spot Rate Period/Period or a shortcut method.


**Option B:**

You have already created the forward exchange transaction and now want to create a hedging relationship.

- 1. On the SAPEasy Access screen, choose Treasury and Risk Management Transaction Manager Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX) .
- 2. Specify the risk category Exchange Rate Risk and the required date for the new hedge plan. Choose Net Investment as the transaction activity.
- 3. Choose the Hedged Item tab page and select the relevant exposure.
- 4. Specify the transaction category Financial Asset or Financial Liability. Choose the hedge category Cash Flow Hedge .
- 5. On the Hedging Relationship tab page, specify the hedging instrument using one of your foreign exchange transactions with a freely-defined derivative volume. Choose hedge strategy 100 – CF Spot Rate Period/Period or a shortcut method.


Selecting the Hedge Strategy

Spot Method:

Differences Acc. to Spot Rate, and on Cash Flow Determination Method 1 ( FAS133) .

**Forward Method:**

If you use the forward method but the critical terms do not match, you need to use a hypothetical derivative to map the hedging relationship.

**Customizing Settings**

In the Foreign Exchange area, there is no corresponding product type available in the standard system in Customizing for the Transaction Manager. To define a forward exchange transaction as a hedging transaction, in Customizing for the Transaction Manager, choose Foreign Exchange Transaction Management Product Types Define Product Types. You then copy product type 60B – Foreign Exchange (FX) Hedge Accounting as your new product type.

Assign this product type to position management procedure 3004 – Money Market Transactions as Hedging Instruments, Hedge Acc . To do this, in Customizing for the Transaction Manager, choose General Settings Accounting Settings for Position Management Assign Position Management Procedure .

You also need to make the necessary settings in Customizing for the Transaction Manager under General Settings Hedge Accounting for Exposures Effectiveness Test.

See also:

Hypothetical (Perfect) Derivative

Net Investment Hedge (NIH) in a Foreign Operation

###### NIH: Option on a Forward Exchange Transaction Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Net Investment Hedge (NIH) in a Foreign Operation > NIH: Option on a Forward Exchange Transaction Used as a Hedging Transaction | L7 | trm09 p.281 | loio `cd0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cd0bda531198434de10000000a174cb4.html?locale=en-US)

Valuation and Effectiveness Test

Spot Method:

As part of the effectiveness test and on the valuation key date, the system translates the nominal values of the forward exchange transaction (underlying) and the exposure at the spot rate and then compares them.

During the option valuation for the forward exchange transaction, the system takes into account the foreign currency effect and interest rate effect as well as the time value of the option.

If the hedging relationship is effective, the foreign currency effect of the forward exchange transaction is posted to equity (OCI) without affecting profit and loss. The time value of the option and the interest rate effect of the forward exchange transaction are posted to profit and loss.

**Forward Method:**

If the critical terms of the underlying transaction do not match those of the hedging transaction (nominal values and currencies, for example) you can post the foreign currency effect and interest rate effect to equity without having to run the

effectiveness test first.

If some of the critical terms are different, you need to use a hypothetical derivative to map the hedging relationship.

**Creating a Hedging Relationship**

You have already created the forward exchange transaction and now want to map a hedging relationship. To do this, proceed as follows:

- 1. On the SAPEasy Access screen, choose Treasury and Risk Management Transaction Manager Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX).
- 2. Specify the risk category Exchange Rate Risk and the required data for the new hedge plan. Choose Net Investment as the transaction activity.
- 3. Choose the Hedged Item tab page and select the relevant exposure. Specify the transaction category Financial Asset or Financial Liability.
- 4. On the Hedging Relationship tab page, specify the option on the forward exchange transaction that you created as the hedging instrument.
- 5. Choose hedge strategy 405 – Option Intrinsic Value, Spot Rate or a shortcut strategy.


Selecting the Hedge Strategy

Spot Method:

If you use the spot method, we recommend that you choose the hedge strategy defined in the sample Customizing settings: 405 – Option: Intrinsic Value, Spot Rate .


If hedge strategy 405 is not available in your system, in Customizing for the Transaction Manager, choose General Settings Effectiveness Test Define Calculation Types . Copy calculation type 400 and change the ID to 405. Enter the description

Option: Intrinsic Value, Spot Rate and select calculation category 11 – Option: Intrinsic Value, Spot Rate .

In Customizing for the Transaction Manager , choose General Settings Effectiveness Test Define Hedge Strategies . Create a copy of hedge strategy 400 with ID 405. Change the description to Option: Intrinsic Value, Spot Rate and enter 405 under Assmt Calc Type and Measmt CalcType.

**Forward Method:**

If you use the forward method but the critical terms of the underlying transaction do not match those of the hedging transaction (see FAS 133 Derivatives Implementation Group Implementation Issue No. H8 ) we recommend that you use a shortcut strategy.

**Customizing Settings**

In the OTC Derivatives area, you can use product type 76X ( OTC Forex Option, Hedge Acc .) which is available in the sample Customizing settings. This product type is assigned to position management procedure 3000 ( Derivatives : Hedging Instr., Hedge Acc. ).

You also need to make the necessary settings in Customizing for the Transaction Manager under General Settings Hedge Accounting for Exposures Effectiveness Test Define Calculation Types and Define Hedging Relationships.

You need to assign the appropriate update types to enable the time value to be posted to equity when you use a shortcut strategy. To do this, in Customizing for the Transaction Manager, choose General Settings Accounting Hedge Accounting . Under Treatment of Time Value, choose B No Classification of Time Value for position management procedure 3000.

See also:

Hypothetical (Perfect) Derivative

Net Investment Hedge (NIH) in a Foreign Operation

###### NIH: Cross-Currency Interest Rate Swap Used as a Hedging Transaction

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Cash Flow Hedge (CFH) > Net Investment Hedge (NIH) in a Foreign Operation > NIH: Cross-Currency Interest Rate Swap Used as a Hedging Transaction | L7 | trm09 p.283 | loio `ca0bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ca0bda531198434de10000000a174cb4.html?locale=en-US)

Valuation and Effectiveness Test

Spot Method:

As part of the effectiveness test and on the valuation key date, the system translates the nominal values of the crosscurrency interest rate swap and the corresponding exposure at the spot rate and then compares them. All the interest flows associated with the cross-currency interest rate swap are ignored.

To value the cross-currency interest rate swap, the system runs a foreign currency valuation and security valuation.

If the hedging relationship is 100% effective, the foreign currency effect is posted to equity (OCI) without affecting profit and loss. The interest rate effect, however, is always recorded on the profit and loss statement.

If an effective hedging relationship is not 100% effective, the system differentiates between the following two scenarios:

If the change in value of the hedging transaction is greater than the change in value of the hedged item, the foreign currency effect is posted proportionately to the profit and loss account.

If the change in value of the hedging transaction is less than the change in value of the hedged item, the hedging transaction value is posted to equity and not recognized in profit and loss.

**Forward Method:**

If you use US GAAP, and the critical terms of the underlying transaction match those of the hedging transaction (see FAS 133 Derivatives Implementation Group Implementation Issue No. H8 ), you can post the foreign currency and interest rate effects to equity without running the effectiveness test beforehand. If the critical terms are different, you need to use a hypothetical derivative.

**Creating a Hedging Relationship**

To create a hedging relationship with a cross-currency interest rate swap used as a hedging instrument, proceed as follows:

- 1. On the SAPEasy Access screen, choose Treasury and Risk Management Transaction Manager Hedge Accounting for Exposures Hedging Relationships Hedge Plan (THMEX) .
- 2. Choose the risk category Exchange Rate Risk for the hedge plan.
- 3. Enter the required exposure data. Choose the transaction category Financial Asset or Financial Liability. Specify Net Investment as the transaction activity.


- 4. On the Hedged Items tab page, choose the exposures to be hedged. Specify the hedge category Cash Flow Hedge .
- 5. On the Hedging Relationships tab page, assign a cross-currency interest rate swap as the hedging instrument or create a corresponding hedging transaction. Choose hedge strategy 100 – CF Spot Rate Period/Period or any shortcut strategy.


Selecting the Hedge Strategy

Spot Method:

If you use the spot method, you should also use the standard hedge strategy 100 ( CF Spot Rate Period/Period ). To determine the cash flow, use method 1 - FAS133 . If you decide to use a different hedge strategy, it must use a calculation type based on calculation category 001 Cash Flow Differences Acc. to Spot Rate, and on Cash Flow Determination Method 1.

**Forward Method:**

If you use the forward method and the critical terms match, we recommend that you use a shortcut strategy.

**Customizing Settings**

In the Listed Derivatives area, you can use the standard product type 62D ( Cross-Currency Interest Rate Swap, Hedge Acc .). The standard procedure assigned to this product type is position management procedure 3000 ( Derivatives: Hedging Inst. Hedge Acc .). You can make these settings in Customizing for the Transaction Manager by choosing OTC Derivatives Transaction Management Product Types Define Product Types.You can also chooseGeneral Settings

Accounting Settings for Position Management Assign Position Management Procedure.

You also need to make the necessary settings in Customizing for the Transaction Manager under General Settings Hedge Accounting for Exposures Effectiveness Test.

See also:

Hypothetical (Perfect) Derivative

Net Investment Hedge (NIH) in a Foreign Operation

###### Hypothetical Derivative (2 of 2)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Hypothetical Derivative | L5 | trm09 p.239 | loio `c70bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c70bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The hypothetical derivative is available for hedging relationships that use the following hedging scenarios:

710 Security Hedged with Interest Swap

720 Loan Hedged with Interest Swap

The hypothetical derivative is required for performing the effectiveness tests (except for the critical term match method). During the effectiveness test, the hypothetical derivative represents the hedged item.

**Prerequisites**

In Customizing for Hedge Accounting for Positions under Effectiveness Test Effectiveness Test Methods , you have created the methods that you would like to use for the prospective and retrospective effectiveness tests and you have selected as the , you have created a profile and have assigned to it for the prospective and retrospective effectiveness checks the effectiveness test methods defined above.type of effectiveness test method for these methods the dollar offset method, the schleifer noise method, or the linear regression.

If you want to use the critical term match method for the prospective effectiveness test, you also create an effectiveness test method for it.

Under Define Hedging Profile

In the Hypothetical Derivative Creation Category field, you specify whether the hypothetical derivative to be created has a net present value of zero or whether the net present value corresponds to net present value of the designated swap with inversed plus/minus sign.

**Features**

During designation of the hedging relationship, the system automatically generates the hypothetical derivative by creating a corresponding hypothetical interest swap for the variable security position/loan. The interest swap applies the dates and the variable cash flow of the security position/loan. The system calculates the fixed side of the hypothetical derivative so that, at the time of the designation, the net present value of the interest swap is zero or corresponds to the negative net present value of the hedging instrument. If there is alternative market data for the designation, the system applies it in the creation of the hypothetical derivative.

**Related Information**

Hypothetical Derivative (Hedge Accounting for Exposure Items)

###### Hedging Relationships

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Hedging Relationships | L5 | trm09 p.286 | loio `cf0ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/cf0ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

In hedging relationships, hedged items (created for exposures that have arisen from your underlying transactions) are assigned to hedging instruments (deployed to hedge the risks of the hedged item).

Within Hedge Accounting for Exposures, the hedging relationships are created and managed in a hedge plan.

**Features**

You manage your hedging relationships in a hedge plan (transaction THMEX)

You use the function Effectiveness Test (transaction THM80) to perform prospective and retrospective effectiveness assessments as well as effectiveness valuations. A hedging relationship becomes effective when the change in value of the derivative is connected to a significant extent to the change in value of the hedged exposure.

A prospective effectiveness assessment is used to determine whether a hedging relationship can be assumed to be effective over a period in the future. You can perform a prospective effectiveness assessment by performing an effectiveness valuation with a market data scenario. You can perform the effectiveness assessment using different calculation methods. Which calculation method is used is dictated by the underlying hedge category (Cash Flow Hedge, Fair Value Hedge, and Net Investment in Foreign Subsidary) as well as by the product category of the hedging instrument.

**Note:**

However, you can also perform the prospective effectiveness assessment in an external system and then import it. See also:Transferring Prospective Effectiveness Assessments

A retrospective effectiveness assessment determines the effectiveness of a hedging relationship for a period in the past. You can perform the effectiveness assessment using different calculation methods. Which calculation method is used is dictated by the underlying hedge category (Cash Flow Hedge, Fair Value Hedge, and Net Investment in Foreign Subsidary) as well as by the product category of the hedging instrument.

Effectiveness valuation valuates the derivative and the exposure both at the start and at the end of the valuation period and then divides the valuation difference of the derivative in a designated part and a freestanding part. The designated part is compared against the valuation difference of the exposure (or against the valuation difference of that part of the exposure that is allotted to the derivative). If the designated part exceeds the valuation difference, this part is deemed ineffective and the remaining part is deemed effective. With the valuation (transaction TPM1), it is possible to post these parts differently; typically, the effective part is posted to other comprehensive income (OCI), and the other parts are posted in the P&L.

With the valuation of financial transactions using key date valuation (transaction TPM1), the valuation recognizes the involvement of the transactions in hedging relationships and performs valuation in accordance with the rules for Hedge Accounting.

For the valuation key date, key date valuation automatically performs a retrospective effectiveness assessment to establish whether the hedging relationship has proved to be effective in the past period.

If the retrospective effectiveness assessment deems the hedging relationship to be effective, key date valuation performs the prospective effectiveness assessment as the next step of the effectiveness test. If the prospective effectiveness assessment also deems it to be effective, an effectiveness valuation is performed and posted.

If the retrospective effectiveness assessment deems the hedging relationship to be ineffective, you need to dissolve the hedging relationship. See also:Dissolve Ineffective Hedging Relationships

You can also print the documentation of hedging relationships (transaction THM86).

**More Information**

Hedging Relationship Status Overview

Reverse a Single Hedging Relationship Dedesignation

Reverse a Single Hedging Relationship Dissolution

Exposure Upload from Money Market or Loans

Exposure Upload from an External System

###### Hedge Plan

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Hedging Relationships > Hedge Plan | L6 | trm09 p.287 | loio `9b0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9b0dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This function is the single point of entry for managing your hedge plans and the related hedging relationships.

Your hedging relationships are always assigned to one hedge plan.

In a hedge plan, you specify which risk category applies (exchange rate risk, interest rate risk, or a commodity price risk).

Within a hedge plan, you assign the related exposures.

You then create hedged items for the exposures for which you want to hedge the risks. Using hedge strategies, you specify how you want the effectiveness test to be performed. A hedging relationship is the result of assigning/designating hedging instruments to hedged items.

**Activities**

Choose Transaction Manager Hedge Accounting for Exposures Hedging Relationships Hedge Plan (transaction THMEX).

- 1. As the first step in Hedge Accounting for Exposures, create a hedge plan.


In ah hedge plan, you can group together exposures according to specific criteria. You might, for example, use one hedge plan to manage all exposures that represent a certain product group.

To create a new hedge plan, choose and enter the hedge plan details. Besides the hedge plan ID and the name of the hedge plan, you enter the start date and end date as well as the risk category. The start date of the hedge plan is typically the valid-from date of the exposure that begins first. Likewise, the end date is the date on which the last exposure affects net income. In the case of a forecasted sale, this date would be the (anticipated) receivables date; in the case of a forecasted purchase, it would be the date on which the receivable for the original purchase was posted. For all exposures in the hedge plan, the risk category uniquely determines the risk to be hedged (exchange rate risk, interest rate risk, or commodity price risk).

In the case of interest rate risks, you must also enter the nominal amount and the currency of the interest rate instrument. You can also select the Single Hedge indicator. In this way, you can set a restriction so that the hedge plan contains only one hedged item; consequently, all exposures are assigned to that hedged item. The hedged item then corresponds to the interest rate instrument to be hedged, and the exposure corresponds to the individual cash flows of that interest rate instrument. All the exposures are part of a single hedged item, and all cash flows of this interest rate instrument belong to the same interest rate instrument. If you do not set this indicator, each exposure represents an individual hedged item that must be hedged separately - as is also the case with exchange rate risks.

- 2. The list of hedge plans provides an overview of all the hedge plans already created. When you select a hedge plan, the hedge plan details appear in the lower section of the screen. From here, you can navigate to the exposures and hedging relationships entered by choosing .


The E-Hedge Accounting screen appears. Details of the hedge plan are shown in the upper part of the screen.

Beneath those details, you can use the tabs Exposure, Hedged Item, and Hedging Relationship.

- 3. The Exposure Tab


On this tab, you see all exposures for a hedge plan.

The exposures may have been transferred from Exposure Management 1.0 or Exposure Management 2.0. You may have imported exposures from Money Market and loan contracts or from external systems.

You can also create exposures manually.

You can create the following exposure categories:

Forecasted Purchase/Sale

Firm Commitments: Purchase/Sale

Financial Assets: Cash Flow Transactions, Position Transactions, and Net Investments

An exposure consists of one or more transactions, the sum of which equals the value (volume) of the exposure. A transaction is defined by its transaction category and transaction activity. The transaction category defines the category to which a transaction is assigned (for example, forecasted transaction or firm commitment). The transaction activity serves to further specify the transaction category. This could be the decision as to whether a forecasted transaction is a purchase or a sale, for example.

To create a new transaction, choose and enter the appropriate details.

Enter the transaction category, the transaction activity, the transaction ID, as well as the nominal amount, and the transaction currency.

Other important entries are the valid-from date and the due date. The valid-from date is the date from which the transaction is valid. This can be either the start date of the transaction or the date for which the transaction was forecasted. The start date of the transaction must not fall before the date on which the hedge plan becomes valid. In the case of an individual hedged item with one interest rate instrument, the valid-from date corresponds to the start date of the interest rate instrument for all entered exposures/transactions. The Due On date describes the expiry date of the transaction or the exposure. This is the latest date on which profit and loss can be affected.

If you have already entered an exposure (consisting of at least one transaction), you can use the Exposure field to decide whether you want to create a new transaction for that exposure or whether you want a new exposure to be generated when

you create the transaction.

- 4. Exposures represent cash flows or positions that can be hedged against a specific risk. As soon as you as you decide to hedge a specific exposure, you create a hedged item for that exposure on the Hedged Item tab. A hedged item indicates initially only the intention to hedge an exposure. You perform the actual hedging on the Hedging Relationship tab by assigning a suitable financial transaction as a hedging instrument.
- 5. The Hedged Item Tab

- a. Choose .


- b. Choose an underlying hedge category.

Cash Flow Hedge

Fair Value Hedge

Net Investment in Foreign Subsidiary

A cash flow hedge and a fair value hedge differ with respect to the risk hedged. Whereas cash flow hedges cover potential fluctuations in future cash flows, fair value hedges are used to hedge against changes in the fair value of an underlying transaction. A net investment in foreign subsidiary is a special kind of cash flow hedge.

- c. Using the target ratio, you can define a target value to be hedged (in percent) according to your risk guidelines.

The actual ratio for the exposure to be hedged appears in the Actual Ratio field. The system calculates the actual ratio as soon as you incorporate a derivative financial instrument, or a specific part thereof, as a hedging instrument in a hedging relationship. The actual ratio is that portion of an exposure (in percent) that is hedged at a given time.

- d. Select the exposure.
- e. You can choose a hedge strategy here. The hedge strategy that you choose is then valid for all hedging instruments assigned to that hedged item. If you do not assign a hedge strategy here, you need to select the hedge strategy when you assign/designate the hedging instruments.

See also:Hedge Strategies

- f. You can enter the start and end of reclassification for the hedged item.

See also:

Manual Equity Capital Reclassification (transaction THM54)

Automatic Equity Capital Reclassification (transaction THM58)

- g. Save your entries.


- 6. The Hedging Relationship Tab


**Note:**

In contrast to an exposure, a hedged item relates to a specific valuation area. The system first assumes that a hedged item needs to be created in the leading valuation area. Use the Change Valuation Area function to create the hedged item in another valuation area.

On this tab, you designate the financial transaction and the volume that is to be used to hedge the hedged item entered.

The system supports the following product categories as hedging instruments:

Foreign Exchange

Cap/Floor

Swap

FRA

OTC Options (only foreign exchange)

**Note:**

At least one side of the transaction must have the local currency of the company code.

In hedging relationships with the risk category Exchange Rate Risk, you can assign multiple hedging instruments to a hedged item. It is also possible to assign a financial transaction with the same plus/minus sign as the hedged item. However, the total of the designated amounts of all assigned hedging instruments must not have the same plus/minus sign as the hedged item.

In hedging relationships with the risk category Commodity Price Risk, you can assign multiple hedging instruments to a hedged item. The hedging instruments must not have the same plus/minus sign as the hedged item.

You enter the amount that you wish to use for the hedge in the Designated Amount field (in the case of hedging relationships with the risk category Exchange Rate Risk) or in the Designated Volume: Hedged Item field (in the case of hedging relationships with the with the risk categories Interest Rate Risk and Commodity Price Risk).

Further, other than the date from which the hedging relationship is to take effect, you also enter the hedge strategy to be used later for the effectiveness test. The hedge strategy defines all the parameters that are required to determine the effectiveness. Here, the system allows you to select only hedge strategies that are also permitted for the derivatives to be valuated. In the case of options, for example, the only hedge strategies available for selection are those with calculation categories that are also suitable for options.

**Note:**

You define hedge strategies in Customizing for the Transaction Manager under General Settings Hedge Accounting for Exposures (E-HA) Effectiveness Test Define Hedge Strategies . The hedge strategies that you define here are then available for selection in the application.

###### Hedge Strategy

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Hedging Relationships > Hedge Plan > Hedge Strategy | L7 | trm09 p.290 | loio `890eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/890eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

A hedge strategy is a set of rules that you use to define how the effectiveness of a hedge is valuated. It comprises a number of parameters that determine how the effectiveness test is performed. Apart from the assessment types, these parameters also include calculation types for the effectiveness assessment and for effectiveness measurement.

**Note:**

Once you have stored a hedging relationship, you can no longer change the assignment of the hedge strategy. It is only possible to change the hedge strategy when the relevant hedging relationship has been dissolved and a new hedging relationship has been created.

With each effectiveness test, the value that was calculated for the last valuation key date is subtracted from the value for the current key date. If valuation has not previously taken place, the value calculated on the start date of the hedging relationship is subtracted.

**Prerequisites**

You create the assessment types, the calculation types, and the hedge strategies in Customizing for the Transaction Manager under General Settings Hedge Accounting for Exposures Effectiveness Test .

**Features**

Each calculation type relates to a calculation category allocated by the system. You can use the following calculation categories:

- 001 = Cash Flow Differences: Spot Value

In the case of exchange rate risks, the cash flow(s) of the derivative and the hedged item (assigned exposure volumes) is (are) calculated separately at the spot rate on the valuation key date. The respective cash flows of the derivative and the hedged item are then added. The due dates are not taken into account. In the case of interest rate risks, the interest for all interest periods is derived from the reference interest rate effective on the valuation key date. The same interest rate is used for all cash flows within a time period. It is irrelevant when the cash flows were generated. Example: In the case of a hedging instrument with three-month coupons and reference interest rate LIB_USD_03, the interest rate effective on the valuation key date for LIB_USD_03 is used to calculate the interest of all future coupons.

- 002 = Cash Flow Differences: Forward Rate

In the case of exchange rate risks, the cash flow(s) of the derivative and the hedged item (assigned exposure volumes) is (are) calculated separately at the forward rate of the corresponding due date. The respective cash flows of the derivative and the hedged item are then added. In the case of interest rate risks, the yield curve on the valuation key date is used to derive the effective forward interest for the respective interest period. The forward interest is used to calculate the

anticipated interest. The interest amount calculated is not discounted. Example (simplified): A three-month coupon that starts in three years. The yield curve shows a three-year and four-year interest rate. You derive the interest rate that is effective in three years for three months from the start of term.

- 003 = Cash Flow Differences: Forward Rate Discounted

In the case of exchange rate risks, the respective cash flows of the derivative and the hedged item (assigned exposure volumes) are discounted using the effective currency yield curve on the valuation key date. They are then translated into the local currency at the spot rate effective on the valuation key date. The respective cash flows of the derivative and the hedged item are then added. For interest risk, the procedure described in calculation category 002 is used. The resulting interest is then discounted for the respective dates (last valuation date/start date of the hedging relationship and current valuation key date) according to the yield curve effective on the valuation key date.

- 004 = Cash Flow-Differences: Spot Rate (With Interest Accrual)

- This calculation category corresponds to category 001; however, with this category, the accrued interest is subtracted. In other words, the accrued interest is determined automatically when calculating cash flow differences.

005 = Cash Flow-Differences: Forward Rate (With Interest Accrual)

- This calculation category corresponds to category 002; however, with this category, the accrued interest is subtracted. In other words, the accrued interest is determined automatically when calculating cash flow differences.

006 = Cash Flow-Differences: Forward Rate Discounted (With Interest Accrual)

- This calculation category corresponds to category 003; however, with this category, the accrued interest is subtracted. In other words, the accrued interest is determined automatically when calculating cash flow differences.




- 011 = Options: Intrinsic Value Spot Rate


- This calculation category is only valid for forex options. It corresponds to calculation category 001 (cash flow differences: spot rate). The intrinsic value of the option is calculated at the spot rate on the valuation key date. If the intrinsic value is less than zero, it is set to zero. (There is no negative option value). The cash flows of the hedged item are calculated at the spot rate on the valuation key date, in the same way as calculation category 001.


- 012 = Options: Intrinsic Value Forward Rate

- This calculation category is only valid for forex options. It corresponds to calculation category 002 (cash flow differences: forward rate). The intrinsic value of the option is calculated at the forward rate that is effective on the settlement date of the underlying forex transaction (or in the case of American-style options, at the forward rate that is effective on the next possible exercise date after valuation). If the calculated intrinsic value is below zero, it is set to zero. The cash flows of the hedged item are valued at the forward rate of their respective due dates, according to the procedure used for calculation category 002.

013 = Options: Minimum Value (Intrinsic Value Forward Rate Discounted)

- This calculation category is only valid for forex options. It corresponds to calculation category 003 (cash flow differences: forward rate discounted). The intrinsic value of the option is calculated by discounting the relevant cash flow based on the currency yield curve effective on the valuation key date. The discounted cash flow is then translated into the local currency at the spot rate effective on the valuation key date. If the intrinsic value is below zero, it is set to zero. The exposure cash flows are discounted using the currency yield curve effective on the key date. They are then translated using the spot rate effective on the key date, according to the procedure presented in category 003.




- 021 = Hypothetical Derivative

This calculation category is only valid for interest rate swaps (including cross-currency interest rate swaps) and forex options for cash flow hedge items.

A derivative is created according to the hedged item (that is, the exposure) and is assigned to the hedging relationship along with the hedging instrument. This dummy, or hypothetical derivative, is then used instead of the hedged item to determine its value in hedge accounting. The hypothetical derivative must fulfill the same critical requirements as the underlying exposures: same reference interest rate, same caps and floors, and zero market value at the start of the hedging relationship.

The hypothetical derivative may or may not be valued at the clean price. This is shown by the "Clean Price" indicator in the calculation category definition.

- 022 = Clean Price Hypothetical Derivative

This category corresponds to category 021, the only difference being that this category subtracts the accrued interest.

- 023 = Intrinsic Value Hypothetical Derivative


For this derivative, this method corresponds to category 013. In contrast to category 013, however, the exposure is not valuated at the net present value but instead at the intrinsic value of the hypothetical derivative. It is useful to use category 023 when the hedging instruments and the hypothetical derivative are FX options, caps, or floors.

- 031 = Correlation

This calculation category is only valid for interest rate swaps (including cross-currency interest rate swaps) and forex options for cash flow hedge items.

The correlation method retrieves historical correlation data (uploaded regularly to the system) and uses this data to determine the effectiveness of a hedging relationship.

- 032 = Correlation Clean Price


100 = Net Present Value

The net present value of a derivative is calculated according to the TR-MRM method. In the case of exchange rate risks, the cash flows of the exposure are discounted using the currency yield curve effective on the valuation key date. They are then translated at the spot rate effective on the valuation key date and added. For interest rate risks, the forward rates for the interest period are calculated according to the method presented in calculation category 002 (cash flow differences forward rate). That means that the yield curve effective on the valuation key date is used to derive the forward interest effective for the individual interest periods. This interest rate is used to calculate the anticipated interest. The calculated interest amounts are then discounted according to the yield curve effective on the valuation key date.

150 = Clean Price (Net Present Value With Interest Accrual)

The clean price is the net present value minus the interest accrued for the current period up to the valuation key date. The procedure is the same as for the net present value (category 100). However, in the case of the interest rate risk, the accrued interest is subtracted from the net present value calculated.

170 = Spot/Spot Calculation for Commodities

- 200 = Interest Rate Instrument: Benchmark

You can use this category to perform calculations based on the benchmark reference interest rate. The reference interest rate effective on the valuation key date is used either as the par rate or the risk-free rate, depending on the definition of the reference interest rate. The markup (spread) of the underlying exposure on the reference interest rate effective on the valuation key date is calculated by deducting the reference interest rate from the effective interest rate (see below) on the start date (see below). This markup is added to the reference interest rate effective on the valuation key date and the result determines the discount factor for all future cash flows. (The same procedure is also used at the start of the period in which the reference interest rate effective at that time is used and discounted at the start of the period.)

The swap valuation for this calculation category is performed in the same way as for category 003.

Several prerequisites must be met before this category can be used:

The hedged item must not have variable cash flows.

The Effective Interest Rate field must be filled for the hedged item.

The hedging relationship must have reference interest rates either on the start date of the hedged item or on the start date of the hedging relationship. (If the dates are different you can decide which one to choose. However, the reference interest rate at the start must never exceed the effective interest rate).

- 201 = Interest Rate Instrument: Benchmark With Interest Accrual


This category corresponds to category 20; however, with this category, the accrued interest is subtracted.

###### Hedging Relationship Status Overview

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Hedging Relationships > Hedging Relationship Status Overview | L6 | trm09 p.293 | loio `f00ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f00ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

This function provides an overview of all the existing versions for a selected hedging relationship. You can select hedging relationships on the basis of the company code, hedge plan ID, transaction, portfolio, and the date on which the hedging relationship was created. A green traffic light indicates the current version. Other versions have a red traffic light.

**Features**

You can also use this function to reverse dedesignations and dissolutions that have already been processed by the hedge management application. However, you cannot use it to reverse dedesignations and dissolutions processed by other applications, such as the application for exposure expiration. When you select a dissolved version, you are prompted to enter a reversal reason. If you want to reverse an OCI reclassification, you are prompted to confirm the reversal posting. The system automatically recreates the previous version of the hedging relationship.

**Activities**

- 1. Choose Hedge Accounting for Exposures → Hedging Relationships → Hedging Relationship Status Overview .


Enter your selection criteria in the following entry fields:

- a. Company Code
- b. Up to and Incl. Due Date
- c. Hedge Plan ID
- d. Hedge Item ID
- e. Hedge Category
- f. Transaction Category
- g. Transaction Activity


- 2. You can simulate the upload by setting the Test run indicator. In this case, the system displays the data, but no changes are made to the database. If you do not set this indicator, the system actually reverses the exposure expiration.

###### Reverse a Single Hedging Relationship Dedesignation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Hedging Relationships > Reverse a Single Hedging Relationship Dedesignation | L6 | trm09 p.294 | loio `b80ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b80ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to reverse the dedesignations for a group of hedging relationships.

**Activities**

- 1. Enter your selection criteria in the following entry fields:
- 2.

- a. Company Code
- b. Transaction
- c. Hedge Item ID


- 3. The system determines the dedesignated hedging relationships. Choose Execute to select the dedesignations you want to reverse.
- 4. You can simulate the reversal by setting the Test Run indicator. In this case, the system displays the data, but no changes are made to the database. If you do not set this indicator, the reversal is saved to the database.

###### Reverse a Single Hedging Relationship Dissolution

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Hedging Relationships > Reverse a Single Hedging Relationship Dissolution | L6 | trm09 p.294 | loio `800ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/800ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

This function reverses the dissolution of a single hedging relationship.

**Prerequisites**

Before you can reverse the dissolution of a hedging relationship, you must first check the status of the derivative. The dissolution cannot be reversed if the derivative has been fully assigned to other hedging relationships, or if the derivative has been valued since dissolution of the hedging relationship. If both checks are successful, you can reverse the OCI reclassification that was carried out when the hedging relationship was dissolved and create a new version of the hedging relationship. The new version should correspond to the version before dissolution. The system displays the results of the reversal, or the reason why it was unable to perform the reversal.

**Features**

The system determines the hedging relationship on the basis of the values you enter for key fields (such as company code, derivative and number of the hedged item). You can use the Test run indicator to test the reversal before you update the database.

**Activities**

1. Enter your selection criteria in the following entry fields:

- 1. Company Code
- 2. Transaction
- 3. Hedge Item ID
- 4. CFM Reversal Reason


1. You can simulate the reversal by setting the Test Run indicator. In this case, the system displays the data, but no changes are made to the database. If you do not set this indicator, the reversal is saved to the database.

###### Exposure Upload from Money Market or Loans

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Hedging Relationships > Exposure Upload from Money Market or Loans | L6 | trm09 p.295 | loio `d80dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d80dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this report to upload interest rate exposures from money market instruments with the category "interest rate instrument" automatically. Fixed interest exposures are imported to Hedge Accounting for Exposures as fair value hedges, and variable interest exposures as cash flow hedges.

**Prerequisites**

Before you run the import, you must create a hedge plan for interest rate risks in Hedge Accounting for Exposures.

After the first import, you can have the interest rate exposure updated on an ongoing basis. You use the update mode to import the calculated interest amounts after processing an interest rate adjustment in the money market area.

**Features**

This function does not import charges or flows for discounts or premiums. The upload is restricted to functional currency cash flows.

**Activities**

Enter your selection criteria in the following entry fields:

Company Code

Hedge Plan

Transaction

Due Date

You can simulate the upload by setting the Test Run indicator. In this case, the system displays the data, but no changes are made to the database. If you do not set this indicator, the system actually uploads the data.

###### Exposure Upload from External Source

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Hedging Relationships > Exposure Upload from External Source | L6 | trm09 p.296 | loio `830eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/830eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

In general, exposures that take the form of planned purchases or sales are not managed in the system by the corporate treasury department. They may even be decentralized and managed by the operational units. Often, the hedge manager processes the planning data using an external tool, such as Excel. However, to take advantage of Hedge Accounting for Exposures, these exposures and the subsequent hedging instruments must be entered in the system.

When exposures are managed outside the Hedge Accounting application (transaction THMEX), you would normally need to recreate these exposures manually in the Hedge Accounting application. For more information, see Hedge Accounting/Hedging Relationships .

To simplify this process, exposures managed outside the Hedge Accounting application can be imported into a central repository (risk object) using the external data transfer ( EDT ) function. This repository is the source of exposure information for Hedge Accounting (E-HA) , and the data no longer has to be entered manually.

The function for importing external exposure data to the risk object repository is designed to work with aggregated period-based figures, such as monthly forecasted purchases or sales. Once the forecasted figures have been created in Hedge Accounting, they need to be adjusted upwards or downwards as forecasts are modified. This is done by updating the external exposure data in the risk object repository.You can define any date in the future as the due date for extending or rolling over a financial contract.

**Activities**

- Step 1: External Data Transfer


The first step is to upload the exposures to the risk object repository using the external data transfer function.

For a technical overview of the process for transferring external data, see SAP Library under External Data Transfer.

The settings for external data transfer involve three activities:

- 1. Data preparation
- 2. Customizing
- 3. Application settings for the external data transfer run


The external data transfer program uses an import (receiver) structure called a transfer category to map external data to risk objects.The external exposure upload program recognizes the transfer category 040. You can use this transfer category to upload external data to the risk object repository using the direct input functionality of the Business Data Toolset (BDT).

The master data structure of the risk object contains the global risk object data, such as the activity category, external number, and status.The external number of the risk object must begin with '&HM', followed by the external risk object ID, such as ʻ&HM1234567’. Leading and trailing zeros are significant. If the risk object ID does not follow this naming convention, the external upload function (transaction THMRO) will not function correctly.

The basic transactions are grouped together in a hierarchy within the risk object. Level 1 of the risk object item structure (basic transaction structure) contains the basic transactions and, where relevant, optional information for each basic transaction. Level 2 of the risk object item structure (flow data structure) contains the cash flows for individual basic transactions.

The risk object hierarchy allows several basic transactions to be created for each risk object ID. The dates for the start and end of term can differ for each basic transaction. However, the Hedge Accounting application ignores any differences in the term start and end dates and sets one term start date and one term end date for the hedging relationship, encompassing all the start/end dates for the different transaction terms.


The Hedge Accounting application views the hierarchy as a grouping of cash flows without a specific parent-child relationship.

- Step 2: External Exposure Upload (Transaction THMRO)


The external exposure upload creates and updates hedge accounting data by capturing all the risk object exposures uploaded in step 1.Using these risk object exposures, the system automatically creates a hedge plan and subsequent hedge accounting exposure data for the Hedge Accounting application. In the Hedge Accounting application, you can then link the exposures to hedging instruments manually.

The original data is stored in the risk object master data repository. Consequently, periodic updates of the hedge accounting exposure data created from risk object exposures must be carried out using the external exposure upload (THMRO). Only hedge accounting exposure data created via the risk object will be affected by the update.

Risk object exposures with the same currency and due date are automatically aggregated for the upload to Hedge Accounting.

You can use the external exposure to create the hedge accounting data, and then to update it later on. These two steps and the corresponding data entries are described below:

Creating Hedge Accounting Data

To create hedge accounting exposures from risk object exposures, you run the external exposure upload program. The following selection options are available:

General Selections :

Enter a company code (mandatory).

Enter an external risk object number to restrict the selection (optional).

Hedge Accounting :

Choose Create. The system then creates hedge accounting exposure data based on the risk object exposures.

Risk Object ID Linked to / Cash Flows Linked to :

Single Plan : If you choose this option, the system creates a separate hedge plan for each risk object.This hedge plan contains all the cash flows for a single risk object.

Multiple Plans : If you choose this alternative, you have an additional option. You can create a hedge plan containing all the cash flows for a single risk object, or a hedge plan containing all the cash flows from several risk objects.In addition, the menu bar contains an extra function that allows you to add all the cash flows of a risk object to an existing hedge plan, rather than creating a new one.

When you execute the external exposure upload, the system displays a validated list of the hedge plan/exposures from an external source. This validation ensures that the exposures that are going to be created do not already exist in Hedge Accounting.

For each risk object, you can change the descriptive Plan Text and Transaction Text .

The system creates the hedge plan ID and the transaction/exposure ID in the background upon saving. The system determines the hedge accounting transaction activity on the basis of the hedge accounting transaction category (for example, "forecasted transaction") in conjunction with the risk object cash flow type (for example, "sale").

Updating Hedge Accounting Data

Once hedge accounting exposures have been created from risk object exposures, you perform subsequent updates using the update function of the external exposure upload. The following selection options are available:

General Selections :

Enter a company code (mandatory).

Enter an external risk object number (optional).

Hedge Accounting :

To update hedge accounting exposure data, choose Update. The system then updates the hedge accounting data based on the risk object exposures.

Plans Valid After :

If you enter a date in this section (optional), the system only selects hedge plans that expire after the specified date.

When you execute the external exposure upload, the system displays a validated list of the hedge plan/exposures from an external source. This validation ensures that the exposures that are going to be updated already exist in Hedge Accounting.

The list display assigns the exposure amounts and due dates of the risk objects to the corresponding hedge accounting exposures. Any financial contracts with "rollover" status that are linked to the hedge accounting exposure are checked before display. Therefore, all financial contracts linked to E-HA exposures that are subject to rollover must be rolled over before you run the external exposure upload.

The risk object information is used to update Hedge Accounting.

If there has been a key date valuation for the hedging relationship, the following applies:

- 1. If the new exposure amount is zero, the exposure is assumed to be improbable. As a consequence, the hedging relationship is dissolved and all OCI balances are reclassified.
- 2. If the new exposure amount falls below the designated hedge amount, but is greater than zero, the designated amount in the hedging relationship is adjusted to the new, lower amount. The difference between the old and new designated amounts determines any OCI reclassifications.


If there has been no key date valuation for the hedging relationship, the following applies:

- 1. If the new exposure amount is zero, the existing hedging relationship is deleted.
- 2. If the new exposure amount falls below the designated hedge amount, but is greater than zero, the designated amount in the hedging relationship is adjusted to the new, lower amount.

###### Expiration of Risks

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Expiration of Risks | L5 | trm09 p.298 | loio `780dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/780dda531198434de10000000a174cb4.html?locale=en-US)

Process Flow

For more information, see:

Exposure Expiration

Reverse Exposure Expiration

Hedge Plan Expiration

Hedging Relationship Dedesignation

Reverse Hedging Relationship Dedesignation

###### Exposure Expiration

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Expiration of Risks > Exposure Expiration | L6 | trm09 p.299 | loio `a10dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a10dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This report enables you to monitor the expiration of the exposure you have selected. It dissolves all the hedging relationships that are assigned to expired exposures (this includes reclassification of OCI in cash flow hedges). The only exception is for forecasted purchases in cash flow hedges. In this case, the corresponding hedging relationships are dedesignated, not dissolved. This is because OCI should only be reclassified at the time the underlying exposure actually affects net income (for example, a finished product is made from a purchased product tied to a hedging relationship; OCI is reclassified only when the receivable for the finished product is posted).

**Activities**

Choose Hedge Accounting for Exposures Risks Expiration Exposure Expiration .

The Exposure Expiration screen appears.

Enter your selection criteria in the following entry fields:

Company Code

Up to and Including Due Date

Hedge Plan

Hedge Item ID

Hedge Category

Transaction Category

Transaction Activity

You can simulate the exposure expiration by selecting the Test Run field.

In the test run the system displays the data without making changes to the database. If you do not set this indicator, the system saves the values to the database and dissolves or dedesignates the hedging relationship.

Choose Program Execute .

###### Reverse Exposure Expiration

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Expiration of Risks > Reverse Exposure Expiration | L6 | trm09 p.299 | loio `ad0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ad0eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This function determines dissolved and dedesignated hedging relationships processed by the function Exposure Expiration. It only considers dedesignated hedging relationships that are assigned to cash flow hedges with planned purchases. Dissolved hedging relationships belong to cash flow hedges with planned sales, for example.

**Features**

If you carry out a test run, the system merely displays the list of selected hedging relationships. If you carry out an update run, it reverses all the selected hedging relationships and reverts to the previous version.

**Activities**

- 1. Enter your selection criteria in the following entry fields:
- 2.

- a. Company code
- b. Transaction date
- c. Hedge plan ID
- d. Hedge item ID
- e. Transaction activity


- 3. You can simulate the reversal by setting the Test run indicator. In this case, the system displays the data, but no changes are made to the database. If you do not set this indicator, the system actually reverses the exposure expiration.

###### Hedge Plan Expiration

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Expiration of Risks > Hedge Plan Expiration | L6 | trm09 p.300 | loio `1b0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1b0dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This report shows all hedging relationships of hedge plans expiring on a certain date, and dissolves them. It thus ensures that all hedging relationships of a hedge plan are dissolved at the latest upon hedge plan expiration. For plans containing forecasted purchases, the expiration date may be the date when the underlying exposure(s) affect earnings.

**Activities**

- 1. Choose Hedge Accounting for Exposures Risks Expiration Hedge Plan Expiration .
- 2. The Hedge Plan Expiration screen appears.
- 3. Enter your selection criteria in the following entry fields:
- 4.


- a. Company code
- b. Up to & including expiration date
- c. Hedge plan ID
- d. Hedge item ID
- e. Hedge category


- f. Transaction category
- g. Transaction activity


- 5. If you select the Test Run field, you can also run the hedge plan expiration as a simulation. In this test run, data will be displayed only without any database changes being carried out. If it is not flagged values are stored on the database and the appropriate action is triggered (dedesignation or dissolve).
- 6. Choose Program Execute .

###### Dissolution of the Hedging Relationship

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Expiration of Risks > Dissolution of the Hedging Relationship | L6 | trm09 p.301 | loio `a10eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a10eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this program to manually dissolve one or more hedging relationships, for example, all hedging relationships of a derivative, on a specific date.

Hedging relationships cannot be dissolved on a date that was before a successful effectiveness test.

**Activities**

- 1. Choose Hedge Accounting for Exposures Expiration of Risks Dissolving of Hedging Relationship (Transaction THM14).
- 2. The Dissolving of Hedging Relationship screen appears.
- 3. Enter your selection criteria in the following entry fields:

Company Code

Valuation Area

Dedesignation Date (day on which the decoupling comes into effect)

Hedging Relationship Details

Hedge Plan

Hedge Item ID

Transaction

Product Type

Hedged Item Currency

Posting Control

You can set the No Test for Reclass. indicator.

You can execute the program first in a test run.

Output Control

You can set the Special Fields indicator.

You can choose a layout.

- 4. Choose Program Execute .

###### Reverse Hedging Relationship Dedesignation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Expiration of Risks > Reverse Hedging Relationship Dedesignation | L6 | trm09 p.302 | loio `e50dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e50dda531198434de10000000a174cb4.html?locale=en-US)

Use

You can use this report to reverse the dedesignation of individual or also multiple hedging relationships, such as hedging relationships of a derivative.

Prerequisites

You have to dedesignate the hedging relationships by selecting Hedging Relationship Dedesignation before you can use this function.

Activities

- 1. Choose Hedge Accounting for Exposures Risks Expiration Reverse Hedging Relationship Dedesignation.
- 2. The Reverse Hedging Relationship Dedesignation screen appears.
- 3. Enter your selection criteria in the following entry fields:

Company Code

Valuation Area

Key Date (of dedesignation)

Hedge Item ID

Transaction

Product Type

- 4. Choose Program Execute .

###### Closing Operations in Hedge Accounting for Exposures

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures | L5 | trm09 p.302 | loio `f67b1c5037001614e10000000a445394` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f67b1c5037001614e10000000a445394.html?locale=en-US)

**Use**

The menu section Period-End Closing contains all the programs that are necessary for preparing a valuation (key date valuation or the calculation of realized gains and losses). You need to perform valuation before you can execute the transactions in the Accounting section of the menu.

**Process**

- 1. Closing

- 2. Accounting

###### Closing

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Closing | L6 | trm09 p.302 | loio `0f0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0f0dda531198434de10000000a174cb4.html?locale=en-US)

Use

Execute the following reports so that you can then carry out a valuation (key date valuation or realized gains/losses):

Determining Net Present Values

Define Net Present Values on Inception Date

Enter Net Present Values

Interest Rate Adjustment for Exposures

###### Define Net Present Values on Inception Date

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Closing > Define Net Present Values on Inception Date | L7 | trm09 p.303 | loio `7a0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7a0eda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to define the net present values of derivative financial instruments on the inception date.

If you use the market data in the system to calculate the value at the inception date, this value will differ slightly from the value an external business receives. Forward exchange transactions and interest rate swaps should have a value of ʻ0’ and currency options should be valued “at the money”.

The program selects all the derivative transactions for a derivative category and enters the value on the inception date in the NPV table. However, if a value has already been entered and saved in the NPV table, it is not overwritten. In the case of currency options, the system calculates a premium for the transactions and saves this only as a current market value. If this does not meet your requirements, you will have to alter the value later or exclude it from the beginning.

All values are saved in company code currency using the rate type that you entered in the selection screen.

**Activities**

- 1. Choose Hedge Accounting for Exposures Period-End Activities Closing Define Net Present Values on Inception Date (transactionTHM30).
- 2. The Define Net Present Values on Inception Date screen appears.
- 3. Enter your selection criteria in the following fields:

Company Code

Term Start

Transaction

Product Type

Contract Type

Price/NPV Type

FX-Forward Transactions

FX-Options

OTC-Interest Rate Instruments

- 4. If you select Test Run , you can run Define Net Present Values on Inception Date as a simulation.

In the test run, the system displays data without making changes to the database. If you do not select the field, the values will be saved on the database.

- 5. ChooseProgram Execute .

###### Interest Rate Adjustment for Exposures

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Closing > Interest Rate Adjustment for Exposures | L7 | trm09 p.303 | loio `500dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/500dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This function fixes the interest rates for variable rate interest exposures. At a specific, predefined date, the variable interest rate of the exposure is set to the actual rate for that date. This information is needed in the exposure in order to calculate the value of the hedged item accurately.


Do not use this function with exposures that are tied to a money market instrument. The Financial Transaction field in the hedge plan indicates if the exposures were created from a money market instrument. These should always be updated with the Exposure Upload from Money Market or Loansfunction. In this case, first fix the interest flows as usual for a money market instrument, then run the exposure upload report in update mode. This fixes the exposure interest flows within Hedge Management.

**Prerequisites**

Before this report can be run, a valid reference interest rate value must exist for the requested date.These values can be uploaded on a regular basis using a standard datafeed.

**Activities**

After uploading the market data for the required reference interest rates, you can run the Interest Rate Adjustment for Exposures

.

Entry fields:

Adjustment per (date): Mandatory field. Exposures that have a fixing date up to and including this date are adjusted.

Company code : Optional selection field We recommend filling this field to optimize performance.

Hedge Plan ID : Optional selection field that can be used if you want to adjust the exposures for a single hedge plan.

Test Run (checkbox): Leave the box checked to run in test mode to see the actual rates and any errors that may occur. Remove the check in order to perform the update.

Any processing errors (for example, no rate found on the fixing date) are displayed in the resulting tree structure. The highest error level is displayed at the root level, so that you can see at a glance if all records have been successfully updated.

When the Test Run checkbox is deactivated, the program updates all selected exposures and their underlying transactions with the applicable fixed value for the reference interest rate.

###### Accounting (3 of 3)

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting | L6 | trm09 p.304 | loio `460dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/460dda531198434de10000000a174cb4.html?locale=en-US)

Use

After you have completed closing, you can carry out the accounting tasks for the effectiveness measurement.

For more information, see:

Transfer of Prospective Effectiveness Assessment

Reverse Transfer of Prospective Effectiveness Assessment

Hedge Strategy

Dissolve Ineffective Hedging Relationships

Reverse Dissolution of Ineffective Hedging Relationships

Manual Equity Capital (EC) Reclassification

Reverse Manual Equity Capital Reclassification

Automatic Equity Capital Reclassification

Reversal of Automatic Equity Capital Reclassification

Fair Value Changes to Be Posted

Reverse Fair Value Changes to be Posted


Hedge Accounting for Exposures supports parallel valuation areas.

You make the valuation area-dependent settings for Hedge Accounting for Exposures in the relevant Customizing activity.

###### Transfer of Prospective Effectiveness Assessment

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Transfer of Prospective Effectiveness Assessment | L7 | trm09 p.305 | loio `300dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/300dda531198434de10000000a174cb4.html?locale=en-US)

Use

You carry out the prospective effectiveness assessment for a hedging relationship as an effectiveness measurement with a market data scenario or in an external system.

**Note:**

You can use this function in Hedge Accounting for Exposures to transfer the result of this test.

If you double-click the Effective column in the report, the green icon changes to red and the corresponding hedging relationship is marked as Ineffective in the future.

When you save your data, the hedging relationship that was marked as ineffective in the future is either dedesignated or dissolved. This depends on the Customizing settings you have made for the corresponding valuation area. However, nothing happens as a result of the transfer if the hedging relationship is indicated as effective.

Activities

1. Choose Hedge Accounting for Exposures Closing Operations Accounting Transfer Prospective Effectiveness Assessment .

The Transfer Prospective Effectiveness Assessment screen appears.

- 1. Enter your selection criteria in the following entry fields:
- 2.


- a. Company Code
- b. Valuation Area
- c. Hedge Plan ID
- d. Hedge Item ID


- e. Hedging Relationship Number
- f. Financial Transaction
- g. Product Type
- h. Key Date


3. Choose Program Execute .

###### Reverse Transfer of Prospective Effectiveness Assessment

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Reverse Transfer of Prospective Effectiveness Assessment | L7 | trm09 p.306 | loio `b60dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b60dda531198434de10000000a174cb4.html?locale=en-US)

Use

You can use this report to reverse prospective effectiveness assessments for the hedging relationships that match your selection criteria. It lists all the data records for which prospective effectiveness assessments exist. To reverse a prospective effectiveness assessment, select the data record and choose Reversal .

If the assessment was positive, the table of prospective effectiveness assessments contains a corresponding entry. When you reverse the assessment, the system removes this table entry and refreshes the ALV display.

If the assessment was negative, the hedging relationship will have either been dissolved or dedesignated, depending on the Customizing settings. When you reverse the assessment, the system sets the hedging relationship back to its former status, removes the entry from the prospective effectiveness assessment table and refreshes the ALV display.

###### Dissolve Ineffective Hedging Relationships

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Dissolve Ineffective Hedging Relationships | L7 | trm09 p.306 | loio `5e0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5e0dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

With this report you can select hedging relationships that have proved ineffective over the most recent assessment period and dissolve them.

**Activities**

Choose Hedge Accounting for Exposures Period-End Activities Retrospective Effectiveness Assessment .

The Retrospective Effectiveness Assessment screen appears.

Enter your selection criteria in the following entry fields:

Company Code

Hedge Plan ID

Hedge Item

Hedge Category

Transaction

Product Type

Valuation Key Date

Choose Program Execute .

###### Reverse Dissolution of Ineffective Hedging Relationships

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Reverse Dissolution of Ineffective Hedging Relationships | L7 | trm09 p.307 | loio `e80cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e80cda531198434de10000000a174cb4.html?locale=en-US)

Use

This function reverses the dissolution of ineffective hedging relationships carried out using the function Retrospective Effectiveness Assessment: Dissolve Ineffective Hedging Relationships. It lists all the hedging relationships that correspond to

your selection criteria. If you select a data record and choose Reverse , the system reverts to the version of the hedging relationship that existed before the dissolution.

###### Manual Equity Capital (EC) Reclassification

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Manual Equity Capital (EC) Reclassification | L7 | trm09 p.307 | loio `3d0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3d0dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This report allows the user to manually reclassify all or parts of the equity capital balances of the selected hedging relationship(s).

**Activities**

Choose Hedge Accounting for ExposuresaClosing OperationsaAccounting → Manual EC Reclassification.

The Manual EC Reclassification entry screen appears.

Enter your selection criteria in the following entry fields:

Company code

Hedge plan ID

Hedge item ID

Transaction

Product type

Transaction category

Transaction activity

If you flag the Show Items With 0 EC Balance field, items with zero equity capital are included in the hedging relationships shown (no equity capital is available for reclassification for these hedging relationships, though).

Choose ProgramExecute .

###### Reverse Manual Equity Capital Reclassification

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Reverse Manual Equity Capital Reclassification | L7 | trm09 p.307 | loio `f90ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f90ada531198434de10000000a174cb4.html?locale=en-US)

Use

This function reverses equity capital reclassification postings generated using the Manual Equity Capital Reclassification function.

###### Automatic Equity Capital Reclassification

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Automatic Equity Capital Reclassification | L7 | trm09 p.308 | loio `830ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/830ada531198434de10000000a174cb4.html?locale=en-US)

Use

You can use this report to automatically reclassify the equity capital balances of all or some of the selected hedging relationships.


You plan to purchase a raw material in a foreign currency. You want to hedge the foreign currency risk of this transaction with a derivative (forward exchange transaction or currency option). To do this, in Hedge Accounting you must define a hedging relationship - a cash flow hedge - between the planned transaction and the derivative. If the hedging relationship is effective, the profit or loss of the derivative is entered in the equity capital balance (according to IAS 39 95). The raw material purchased is recognized as an asset in the balance sheet. Note:

Cash flow hedges are hedging instruments that are used to hedge cash flow fluctuations.

Effective hedging relationships balance the fluctuations at a fixed amount.

According to IAS 39.95, after the transaction and hedging relationship have been concluded, the following options are available for handling equity capital in hedging relationships:

You can reclassify gains and losses entered in the equity capital account as expense or revenue. The reclassification occurs in the same period in which the asset is included in the profit and loss statement.

You can follow gains and losses entered in the equity capital account when you calculate the acquisition costs of the asset item.


SAPprovides the first reclassification option (1.) to help you manage equity from hedge relationships.

Manual and Automatic Equity Capital Reclassification:

If the raw material is used in only one finished product, the asset item is posted to the profit and loss statement in the period in which the finished product is sold. In this case, use Manual Equity Capital Reclassification

If the raw material is used in more than one finished product, the asset item may be transferred to the profit and loss statement over multiple periods. (Example: The planned transaction is an exposure (purchase) with the hedging instrument "cash flow hedge"). You determine the period for the hedge item using the parameters Start of Reclassification and End of Reclassification . Over this period, the automatic equity reclassification function transfers the equity from the hedging relationship to the profit and loss statement on a linear basis.

Development of Automatic Equity Capital from Hedging Relationship

[figure TRM09-F081 - Activities]

Activities

Enter the required data for the following:

General Selections

Hedge Accounting for Exposures

Hedging Instrument

Reclassification Parameters (Key Date)

Choose test run or update run.

The system creates a log of the automatic equity capital reclassification, and provides an overview of the linear distribution of the equity capital you want to reclassify.


Manual reclassification is not taken into account during this period.

To reverse reclassification, execute the report program Reversal of Automatic Equity Capital Reclassification (transactionTHM59).

###### Reversal of Automatic Equity Capital Reclassification

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Reversal of Automatic Equity Capital Reclassification | L7 | trm09 p.309 | loio `3a0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3a0dda531198434de10000000a174cb4.html?locale=en-US)

This function reverses equity capital reclassification postings generated using the Automatic Equity Capital Reclassification function.

###### Fair Value Changes to Be Posted

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Fair Value Changes to Be Posted | L7 | trm09 p.310 | loio `700dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/700dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This function displays all the fair value changes that have been calculated for the selected hedge items in effective hedging relationships. You can use this information to determine the necessary postings for the underlying exposures. You can also indicate whether the postings have already been executed. If this is the case, you can assign an accounting document.

**Activities**

- 1. Choose Hedge Accounting for Exposures Period-End Activities Accounting Fair Value Changes to Be Posted .
- 2. The Fair Value Changes to Be Posted screen appears.
- 3. Enter your selection criteria in the following entry fields:

- a. Company Code
- b. Valuation Date
- c. Hedge Plan ID
- d. Hedge Item ID
- e. Transaction Category
- f. Transaction Activity


- 4. If you set the indicator Only Changes not Transferred, the system does not display hedging relationships for which this function has already been executed for the same date, and which have been flagged as fair value changes posted to FI. Unless you select the indicator Only Changes not Transferred, the system displays all the fair value hedging relationships.
- 5. Choose Program Execute .
- 6. To assign an FI posting document, select the relevant hedging relationship and choose Assign Accounting Document.
- 7. Enter your selection criteria in the following entry fields:

- a. Accounting Document
- b. Fiscal Year


- 8. Choose Execute.

###### Reverse Fair Value Changes to be Posted

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Closing Operations in Hedge Accounting for Exposures > Accounting > Reverse Fair Value Changes to be Posted | L7 | trm09 p.310 | loio `8b0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8b0dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to reverse a fair value change that has already been posted.

**Activities**

In the general ledger, you must first reverse the FI document assigned to the hedging relationship by the function Fair Value Changes to be Posted . You record this reversal in the hedge management application by entering the reversed G/L account document in the posting line of the hedging relationship.

###### Information Systems

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems | L5 | trm09 p.311 | loio `7d0eda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7d0eda531198434de10000000a174cb4.html?locale=en-US)

The Information Systems section under Hedge Accounting for Exposures contains the following functions:

Effectiveness Test

Account Balances

Hedge Plan Overview

Hedging Relationships per Derivative

Prematurely Reclassified OCI

Hedge Accounting: Change Documents

Hedging Relationship Documentation

To use these functions, choose Treasury and Risk Management Transaction Manager Hedge Accounting for Exposures Information Systems.

###### Effectiveness Test

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems > Effectiveness Test | L6 | trm09 p.311 | loio `db0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/db0dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to perform effectiveness measurements and effectiveness assessments during the entire lifetime of a hedging relationship:

Effectiveness Measurement

An effectiveness measurement displays the effectiveness of a hedging relationship up until the last measurement date or, if no effectiveness test was performed until now, to the start date of the hedging relationship. Effectiveness measurements represent the basis for value distribution following a valuation, in accordance with hedge accounting principles.

If you require an effectiveness measurement for an evaluation date on which a key date valuation has already been executed or gains and losses have been realized, the program displays the saved effectiveness measurement

Effectiveness assessment

An effectiveness assessment calculates the valuation result for one or more periods (from start date to end date) and displays the result. The result displays the delta amounts and the totals for the financial transaction (derivative) and the hedged item (exposure). The program also issues the determined effectiveness rate and the decision regarding whether the hedging relationship is effective or not (Yes/No).

**Prerequisites**

In Customizing, you can define your preferred calculation types for both the effectiveness assessment and the effectiveness measurement, independently of the calculation types currently used to valuate the relevant hedging relationships.

**Features**

A detailed log is available for both functions. Each log contains information about the calculation and the values that it was based on.

If you have performed an effectiveness test, you cannot generate a second detailed log for the same day and for the same calculation type.

Effectiveness can be calculated using the dollar-offset method (either with simple offset method or with the extended offset method using the Noise Threshold Value and Transition Speed) or using Regression Analysis.

**Activities**

- 1. Choose Hedge Accounting for Exposures Information System Effectiveness Test (transaction THM80).
- 2. In the Evaluation Date field, enter the evaluation date.
- 3. In the Hedging Relationship area, use the selection criteria Company Code (mandatory field), Valuation Area, Hedging Instrument, Hedged Item ID, and Hedge Plan to specify the hedging relationships for which you would like to perform the effectiveness test.
- 4. In the Scope of Effectiveness Calculation area, specify how you want the effectiveness test to be performed. First, specify whether you want to perform an effectiveness measurement or an effectiveness assessment.

Performing an Effectiveness Measurement

You can specify the horizon of the evaluation and a scenario.

Performing an Effectiveness Assessment

In the Assessment Type area, you specify whether you want to perform the effectiveness assessment prospectively and/or retrospectively. Further, you enter the parameters for the prospective/retrospective effectiveness assessment. These parameters are, other than the start date and end date, the market data scenarios used as the basis for the assessment.

- 5. In the Calculation Alternatives area, you can specify whether you want to perform the calculation as defined in the hedge strategy of the hedging relationship or whether you want to apply different parameters for the calculation.

- 6. In the List Output area, you specify the display currency and can set the No Inactive Instruments indicator.
- 7. Choose Program Execute .


**Note:**

For the hedging relationships of a hedge plan with the risk category "Exchange Rate Risk", you can set the Test on Hedged Item Level indicator for the effectiveness assessment. In this case, the system performs the effectiveness assessment for a hedged item and for all hedging instruments assigned to that hedged item.

If you do not set this indicator, the system performs the effectiveness assessment at the hedging instrument level. Not setting this indicator is useful if you have a 1:1 assignment of the hedged item to the hedging instrument within your hedging relationships.

###### Noise Threshold Value and Transition Speed

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems > Effectiveness Test > Noise Threshold Value and Transition Speed | L7 | trm09 p.312 | loio `1b0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1b0cda531198434de10000000a174cb4.html?locale=en-US)

**Simple Offset Method**

To check the effectiveness of a hedging relationship, you can use the simple offset method. As part of this method, the value changes in the hedging transactions and the underlying transactions of a hedging relationship are compared. The ratio of the two

amounts is referred to as the hedge ratio (HR).

The disadvantage of this method is the resulting strong fluctuations for small value changes in the underlying and hedging transaction. This can lead to effective hedging relationships being classified incorrectly as ineffective relationships.

**Enhanced Offset Method and Noise Threshold Value**

To limit the impact of small changes in value on the effectiveness test, you can use the enhanced offset method.This method involves entering a noise threshold value that you use to determine a limit that value fluctuations can reach without affecting the effectiveness valuation.

**Note:**

To determine a noise threshold value, in Customizing for the Transaction Manager, choose General Settings Hedge Accounting for Exposures Effectiveness Test Define Calculation Types. Double-click on the relevant calculation type and specify a percentage rate under Threshold Value .

The system determines the absolute threshold value from the percentage rate and the nominal amount of the underlying transaction. This is either added or subtracted without changing the plus/minus signs in the numerators and denominators.

If you do not specify a noise threshold value, the system uses the simple offset method set as the default.

**Transition Speed**

In addition to using a noise threshold value, you can also specify a transition speed.This determines the transition of a hedging relationship from being effective to ineffective. The transition speed influences the transition area between the area where the noise threshold value dominates and the area where it is not influential and therefore ineffective. The greater the transition speed, the smaller the transition area.

Depiction of the Noise Threshold Value and Transition Speed

[figure TRM09-F083]

###### Regression Analysis

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems > Effectiveness Test > Regression Analysis | L7 | trm09 p.314 | loio `d0a7d65378024308e10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d0a7d65378024308e10000000a174cb4.html?locale=en-US)

**Use**

Regression analysis enables you to determine the relationship between a hedged item and the hedging instrument. Regression analysis enables you to test for retrospective and prospective effectiveness with regard to exposures, hedged items, and hedging instruments. You can calculate the following parameters to check the effectiveness:

Gradient of the regression lines

Intercept of the regression lines

Coefficient of determination R2

t-test

**Integration**

The regression analysis is available in Hedge Management for Exposures.

**Prerequisites**

You need to make the following settings in Customizing by choosing Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Hedge Accounting for Exposures Effectiveness Test :

Define Calculation Types

Create a calculation type for linear regression.

When you define calculation types, select the effectiveness category (EffTestCat) 02 Regression Analysis. You also need to specify the significance level.

Define Assessment Types

You set an upper and lower limit for the effectiveness ratio and define a range in which the hedging relationship is effective. The assessment types defined can be used at a later stage when you define the hedge strategy.

Under Linear Regression, make your regression analysis settings:

Coefficient Determination

Gradient from

Intercept from

T-Stat. of Gradient

Eff. Control

- 1: Only R-squared is taken into account
- 2: R-squared and gradient are taken into account
- 3: R-squared, gradient, and intercept are taken into account
- 4: R-squared, gradient, intercept, and t-test are taken into account


Define Hedge Strategies

The hedge strategy comprises several parameters that determine how the effectiveness test is carried out. Apart from the assessment types, these parameters also include calculation types for the retrospective effectiveness assessment and the effectiveness measurement.

Create a hedge strategy and assign your required calculation types and assessment types.

Effectiveness assessment type

Effectiveness assessment calculation type

Valuation calculation type

Cash flow position

Effectiveness assessment

Prospective calculation type

You need to make the following settings to determine the data points for the regression analysis:

Enter the number of data points.

Type of time interval

You can use this function to define the data points for the relevant interval. For types “2” and “3”, the time is split on the basis of the factory calendar. To maintain the calendar, choose SAP Reference IMG SAP NetWeaver

General Settings Maintain Calendar (transaction SCAL).

- 1 (Split without taking calendar into account)

- 2 (Split and adjust based on calendar)


- 3 (Split based on working days)


Calendar

Specify the calendar that you want to use.

Type of Public Holiday Shift

Use the Type of Public Holiday Shift to specify how a data point should be moved if the date is not a working day according to the factory calendar you are using.

Shift forward to next working day

Shift backwards to previous working day

**Note:**

Regression analysis provides better results with at least 30 data points. For this reason, we recommend that you use this number of points for your analysis.

**Features**

The following formula is used for the regression lines:

[figure TRM09-F084 - Regression line]

Regression line

where


= explained variable


= intercept


= gradient of the regression line


= explanatory variable

R2 is calculated as the coefficient of determination and corresponds to the square of the correlation coefficient R in simple regression tests. It is calculated from the covariance and independent variance.

[figure TRM09-F089 - Coefficient of determination]

Coefficient of determination

R2 falls in the interval [0.1].


= mean of the exposure values


= mean of the hedging instrument values

The t-test is a hypothesis test. In the regression analysis, it tests the distribution of regression coefficients.

To calculate the values of the slope coefficient and the intercept coefficient for the given data points:

Using the β values and X values, you can compute the values of Y.

Calculation of adjusted R :

2

[figure TRM09-F092 - = adjusted coefficient of determination]

= adjusted coefficient of determination

where n is the sample size.

Analysis of Variance (ANOVA) is the statistical test used to analyze the total variability of the dataset. The following entries are required so that the ANOVA table can be filled:

Total sum of squares (SST):

SST measures the total variation in the dependent variable. SST is equal to the sum of squared difference between the actual Y values and the mean of Y:

[figure TRM09-F093 - SST]

SST

Regression sum of squares (SSR):

SST measures the variation in dependent variables. It is the sum of the squared distances between the predicted Y values and the mean of Y:

[figure TRM09-F094 - SSR]

SSR

Sum of squared errors (SSE):

SSE measures the unexplained variation in dependent variables. SSE is the sum of the squared distances between the actual Y values and the predicted Y values on the regression line:

[figure TRM09-F095 - SSE]

SSE

ANOVA table:

|Source of Variation|Degree of Freedom|Sum of Squares|Mean|
|---|---|---|---|
|Regression (explained)|K = 1|SSR|MSR = SSR/K|
|Error (unexplained)|n-2|SSE|MSE = SSE/(n-2)|
|Total|n-1|SST| |


The number of degrees of freedom corresponds to the total number of observations in the sample (= n) minus the number of independent (linear) restrictions applied to them.

The general rule is: Degrees of freedom = (n − number of parameters estimated)

###### Account Balances

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems > Account Balances | L6 | trm09 p.318 | loio `830dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/830dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This report provides the OCI and P&L balance for derivatives and their hedging relationships as of the selected date.

**Activities**

Choose Hedge Accounting for ExposuresInformation SystemAccount Balances.

The OCI per Hedging Relationship entry screen appears.

Enter your selection criteria in the following entry fields:

Company code

Transaction

Product type

Key date

Choose ProgramExecute .

###### Hedge Plan Overview

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems > Hedge Plan Overview | L6 | trm09 p.318 | loio `980dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/980dda531198434de10000000a174cb4.html?locale=en-US)

Use

This report provides an overview of all the hedge plans in whatever risk category you choose. The components of the individual hedge plans are shown in a tree structure. For each plan, all corresponding objects for Hedge Accounting for Exposures are listed: hedged items, exposures, transactions, and the assigned derivative contracts. At the individual levels, detailed information is shown for each object.

###### Hedging Relationships per Derivative

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems > Hedging Relationships per Derivative | L6 | trm09 p.318 | loio `860ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/860ada531198434de10000000a174cb4.html?locale=en-US)

Use

This report shows the derivatives and the exposures they are hedging. It is thus possible to report on the derivatives that are hedging/are not hedging exposures, and where hedge capacities remain.

**Activities**

Choose Hedge Accounting for Exposures → Information System → Hedging Relationships per Derivative .

The Hedging Relationships per Derivative screen appears.

Enter your selection criteria in the following entry fields:

- 1. Company code
- 2. Product type
- 3. Financial transaction
- 4. Key date


If you flag the field display derivative w/o hedge, derivatives that are not designated to any hedging relationship are also displayed.

Choose Program → Execute.

###### Prematurely Reclassified OCI

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems > Prematurely Reclassified OCI | L6 | trm09 p.319 | loio `c70dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c70dda531198434de10000000a174cb4.html?locale=en-US)

**Use**

This report shows all OCI balances that have been reclassified prematurely, that is, before the underlying exposure affected earnings, or was scheduled to affect earnings. It thus provides the exception reporting required.

**Activities**

Choose Hedge Accounting for ExposuresInformation SystemPrematurely Reclassified OCI .

The Exception Report: OCI Reclassification Prior to Due Date entry screen appears.

Enter your selection criteria in the following entry fields:

Company code

Reclassification date

Hedge plan ID

Hedge item ID

Transaction

Product type

Hedge category

Transaction category

Transaction activity

Choose ProgramExecute .

###### E-Hedge Accounting: Change Documents

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems > E-Hedge Accounting: Change Documents | L6 | trm09 p.320 | loio `de0dda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/de0dda531198434de10000000a174cb4.html?locale=en-US)

Features

Change documents are written to document changes on the database. They are available for the following:

Hedged items

Hedging relationships

Hedge plan

FX exposure transactions

Interest rate exposure transactions

Activities

Every new entry and data change in Hedge Accounting for Exposures is logged. You can display the changes using the Change Documents for E-Hedge Accounting function. The selection can be restricted to specific hedge plans, hedging items, versions of hedging relationships, and exposures.


No change documents are written for the exposures.

The time period and the name of the last person who changed the selection can also be specified.

###### Printing Hedging Relationship Documentation

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > Information Systems > Printing Hedging Relationship Documentation | L6 | trm09 p.320 | loio `2e0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2e0cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use this function to print out the documentation for your hedging relationships.

Documentation at the Hedging Instrument Level

The documentation is created for one hedging instrument and the relevant hedged item.

This function is available for all hedging relationships.

Documentation at the Hedged Item Level

With this function, you can also create at the hedged item level documentation for hedging relationships of a hedge plan with the risk category Exchange Rate Risk. In this case, documentation is created for a hedged item and for all hedging instruments assigned to that hedged item.

**Prerequisites**

To create the documentation, you need to assign PDF forms in Customizing for the Transaction Manager under General Settings Hedge Accounting for Exposures Documentation Assign Forms to Hedging Relationships . These settings are

made in the context of the company code, valuation area, and risk category. You can also assign more specific forms by using the criteria product category, product type (of the hedging instrument), hedge category, and hedge strategy.

The PDF forms are generated using the SAP Interactive Forms by Adobe.

For documentation at the hedging instrument level, the standard form TR_F_THA_HR is delivered, as well as the following text modules:

**TR_SF_THA_EFFECTIVENESS**

to explain how the effectiveness of the hedging relationship is estimated in clearing changes in market value or cash flow in connection with the hedged risk.

**TR_SF_THA_RISK_CATEGORY**

to explain the risk category to be hedged

**TR_SF_THA_RISK_MANAGEMENT**

to explain the aims of risk management

**TR_SF_THA_STRATEGY**

to explain the hedge strategy

For documentation at the hedged item level, the standard form TR_F_THA_HREL is delivered.

You create and maintain the text modules using the SMARTFORMS function.

**Activities**

- 1. Choose Treasury and Risk Management Hedge Management and Accounting Hedge Accounting for Exposures Information Systems Documentation of Hedging Relationships (transaction THM86).
- 2. Specify the level at which you want to create documentation. You can also create at the hedged item level documentation for hedging relationships of a hedge plan with the risk category Exchange Rate Risk.
- 3. Using the General SelectionsCompany Code and Valuation Area as well as the entries that you make in the Details area, select the documentation to be printed.
- 4. Execute the function.

###### BAPIs in Hedge Accounting for Exposures

> **Path:** Treasury and Risk Management > Transaction Manager > Hedge Accounting > Hedge Accounting for Exposures (E-HA) > BAPIs in Hedge Accounting for Exposures | L5 | trm09 p.321 | loio `4f30e10484422784e10000000a42189d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4f30e10484422784e10000000a42189d.html?locale=en-US)

**Use**

In Hedge Accounting for Exposures, you can use the the BAPIs listed below.

For more information, see BAPIs for the Transaction Manager.

**Features**

BAPIs in Hedge Management

|Business Object|Key Fields|Methods|
|---|---|---|
|BUS5104 FTRHedgeMgmtData (Data for Hedge Management)|Company Code|Creating Data for Hedge Management in a Financial Transaction|


|Business Object|Key Fields|Methods|
|---|---|---|
| |Financial Transaction|BAPI_FTR_HM_CREATE|
|BUS5105 THAHedgePlan (Hedge Plan)|Company Code Hedge Plan|Create a Hedge Plan BAPI_THA_HEDGE_PLAN_CREATE Change a Hedge Plan BAPI_THA_HEDGE_PLAN_CHANGE Display a Hedge Plan BAPI_THA_HEDGE_PLAN_GETDETAIL Delete a Hedge Plan BAPI_THA_HEDGE_PLAN_DELETE|
|BUS5106 THATransFX (Foreign Exchange Transaction)|Company Code Hedge Plan Transaction ID|Create an FX Transaction BAPI_THA_TRANS_FX_CREATE Change an FX Transaction BAPI_THA_ TRANS_FX _CHANGE Display an FX Transaction BAPI_THA_ TRANS_FX _GETDETAIL Delete an FX Transaction BAPI_THA_ TRANS_FX _DELETE|
|BUS5107 THATransIR (Interest Rate Instrument)|Company Code Hedge Plan Transaction ID|Create an IR Transaction BAPI_THA_TRANS_ IR _CREATE Change an IR Transaction BAPI_THA_ TRANS_ IR _CHANGE Display an IR Transaction BAPI_THA_ TRANS_ IR _GETDETAIL Delete an IR Transaction BAPI_THA_ TRANS_ IR _DELETE|
|BUS5108 THATransCO (Transaction Relating to a Commodity)|Company Code Hedge Plan Transaction ID|Creating a CO Transaction BAPI_THA_TRANS_ CO _CREATE Making Changes to a CO Transaction BAPI_THA_ TRANS_ CO _CHANGE Displaying a CO Transaction BAPI_THA_ TRANS_ CO _GETDETAIL Deleting a CO Transaction BAPI_THA_ TRANS_ CO _DELETE|


**BAPIs in Exposure Management 1.0**

|Business Object|Key Fields|Methods|
|---|---|---|
|BUS5115 TEMExposure (Exposure)|External Exposure ID Origin of an exposure Original system|Create an Exposure BAPI_TEM_EXPOS_CREATE Change an Exposure BAPI_ TEM_EXPOS _CHANGE Display an Exposure BAPI_ TEM_EXPOS _GETDETAIL Delete an Exposure BAPI_ TEM_EXPOS _DELETE List of exposures BAPI_ TEM_EXPOS _GETLIST|


**Note:**

With the BAPIs, you can create hedge plans and exposures without user interaction.

- BAPIs in Exposure Management 2.0


|Business Object|Key Fields|Methods|
|---|---|---|
|BUS5990 TEXExposure|External Document Reference Exposure Origin Logical System|Create Raw Exposure BAPI_TEX_EXPOSURE_CREATE Change Raw Exposure BAPI_TEX_EXPOSURE_CHANGE Delete Raw Exposure BAPI_TEX_EXPOSURE_DELETE Get Raw Exposure Details BAPI_TEX_EXPOSURE_GETDETAIL Start Release Workflow for Raw Exposures BAPI_TEX_EXPOSURE_STARTRELEASE|

