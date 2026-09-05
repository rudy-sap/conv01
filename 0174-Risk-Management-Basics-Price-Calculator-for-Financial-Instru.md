# Risk Management > Basics > Price Calculator for Financial Instruments - SAP TRM Knowledge Base (branch split)

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

##### Price Calculator for Financial Instruments

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments | L4 | trm02 p.108 | loio `b0a1c7531dc61d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b0a1c7531dc61d4be10000000a174cb4.html?locale=en-US)

The price calculator documentation describes the market price calculators for the various financial instruments.

Price calculator documentation exists for each financial instrument. The documentation contains product-specific sections, and refers to subroutine documentation applicable to the valuation of numerous financial instruments (for example, the calculation of forward rates or zero bond discounting factors).

The price calculator documentation consists of the following sections for each financial instrument:

Use

This part contains information about the financial instrument and its variants that can be valued and depicted in the system. If other valuation results in addition to the market price are calculated, these are listed here.

Integration / Calculation Basis

This part specifies the calculation bases, in which all the initial parameters necessary for determining the market price are displayed.

This section also contains references to descriptions of subroutines, necessary for calculating certain initial parameters. The subroutine descriptions do not generally contain any product specific information. They are generally applicable to more than one financial instrument.

Scope of Functions / Valuation

This part contains the description of the valuation process. The formulae for market price valuation are shown here.


Note that the system carries out the NPV valuation for all products in double precision format. All report outputs are generated in currency format. They are therefore rounded to 2 decimal places. This could lead to rounding differences.

###### Price Calculator

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator | L5 | trm02 p.108 | loio `001cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/001cda531198434de10000000a174cb4.html?locale=en-US)

###### Account Transactions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Account Transactions | L6 | trm02 p.108 | loio `3b1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3b1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for money market transactions calculates current market values, time values, and future market values (the future point in time is the horizon) on the basis of a due date scenario and simulated interest payments.

Both asset and liability accounts can be held. An account is defined by a currency and an account number. The validity of the conditions can be limited to a certain time period and assigned a particular interest calculation method. When valuing, the conditions valid on the evaluation date are taken into account. Only the product interest rate is needed for the gap analysis. Revenues and balances can be kept according to value or booking date.

In the first step, revenues are added to the balance. By creating a due date scenario, "fictional" balance flows (with a distinction between asset and liability balances) can be simulated for each account. If a due date scenario is missing, it is assumed that the balance flows take place directly on the evaluation date. The interest rate cash flows are calculated for the simulated interest payments according to the Customizing settings.

**Integration/Calculation Basis**

In order to value an account when the Customizing settings prescribe a due date scenario, then alternatively a par coupon or zero coupon yield curve in the transaction currency, has to be entered for the evaluation date.

If the display currency for an evaluation is different from the transaction currency of the account, the relevant currency rate is needed. If the horizon comes after the evaluation date and the transaction currency differs from the display currency, you need to enter a par or zero coupon yield curve to calculate a forward transaction on the horizon.

Zero bond discounting factors are needed as further input parameters in order to discount the cash flow. Only the zero coupon calculation method can be used to define zero bond discounting factors.

If a due date scenario is missing, no calculation basis is needed.

**Scope of Functions/Valuation**

If a cash flow was generated in accordance with a due date scenario, it only contains flows whose payment date and value are known (time-wise, they are all either on or after the evaluation day). The first step reduces the cash flow to those flows which have due dates later than the horizon. Depending on the method of calculation (par or zero coupon method), the NPV of the individual payments is calculated for the horizon, using the yield curve of the transaction currency. The value of the account (in the transaction currency) is the sum of the NPVs of the cash flows.

[figure TRM02-F126 - The following abbreviations/definitions are used:]

The following abbreviations/definitions are used:

|ti|Expiration date of the cash flow (i = 1,..n)|
|---|---|
|Ci|Cash flow at time ti|
|BW(Ci)|Net present value on the horizon of the cash flow Ci due on ti|
|NPV|Net present value|


[figure TRM02-F127 - If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.]

If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

**Money Market**

Money Market Transactions

Use

Money market transactions are, for example, fixed-term deposits, commercial papers, interest rate transaction and current account style instruments.

The market price calculator for money market transactions calculates current market values, time values, and future market values (the future point in time is the horizon).

Money market transactions can be created both as investments (asset-side transactions), or as money raised (liability-side transactions). Both the maturity term as well as the beginning of the maturity term can be set so that they are variable. For fixed interest rate agreements, the frequency of the interest payments can be individually determined. You can also process several fixed interest rates for different interest periods.

Commercial papers are created like fixed term deposits, with a period (term) beginning and end. In contrast to fixed term deposits, interest is only paid at maturity. The nominal amount is the entire payment at the end, made up of the principal and interest payments combined. Thus, the nominal volume (= principal payment) is smaller than the nominal amount. As an alternative to an interest rate, a purchase or sale price can also be set up. This means that commercial papers can be handled and valuated as zero bonds.

**Integration / Calculation Basis**

In order to value a fixed term deposit, the transaction data, and a yield curve in the transaction currency, has to be entered for the evaluation date.

With the help of the Treasury Management component, a cash flow is generated when a money market transaction is created. The cash flow consists of interest payments, which "flow" at particular points in time, and a principal payment. Because the fixed interest rates are given, the all interest payments are known.

Zero bond discounting factors are calculated from the yield curve framework.

If the transaction currency differs from the evaluation currency of the money market transaction, the transaction currency is converted into the evaluation currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the evaluation date using the yield curves from the transaction and evaluation currencies.

**Scope of Functions / Valuation**

In the first step, the cash flow is reduced to those flows which have due dates later than the horizon. The value of the money market transaction (in the transaction currency) is the sum of the NPVs of the cash flows.

The following abbreviations/definitions are used:

|t i :|Expiration date of the cash flow (i = 1,..n)|
|---|---|
|C i :|Cash flow at time t i|
|BW(C i ):|Net present value on the horizon of the cash flow C i due on t i|
|NPV:|Net present value|


[figure TRM02-F128 - If the evaluation currency differs from the transaction currency, the NPV is calculated using the forward currency rate.]

If the evaluation currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

###### Money Market

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Money Market | L6 | trm01 p.39 | loio `fd6356703c3e4065aafd1a32fdcdc373` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fd6356703c3e4065aafd1a32fdcdc373.html?locale=en-US)

Money Market: Fixed Term Deposit/Loan

Securities

Securities: Money Market Fund

Trade Requests of End-to-End Processes

With a trade request, you trigger the conclusion of a financial transaction (trade) on an external trading platform. You can create trade requests with the following categories:

Hedge

A trade request with the trade request category Hedge was created as an FX hedge request in the Hedge Management Cockpit. When the hedge request is released with the Process Hedge Requests app, a trade request is generated automatically.

The requested trade of this kind of trade request can have one of the following instrument categories:

FX Forward

FX Spot

FX Option

FX Non-Deliverable Forward

FX Swap

FX Non-Deliverable Swap

FX Collar

B/S Hedge

A trade request with the trade request category B/S Hedge was created as a balance sheet exposure hedge request by the Generate Balance Sheet Exposure Hedge Requests report (scheduled as a batch job). When the balance sheet exposure hedge request is released with the Process Hedge Requests - Balance Sheet FX Risk app, a trade request is generated automatically.

The requested trade of this kind of trade request can have one of the following instrument categories:

FX Forward

FX Option

FX Non-Deliverable Forward

FX Collar

FX Spot

Cash

A trade request with the trade request category Cash was created as a cash request in the Manage Memo Records app. When the cash request is released with the Manage Memo Records app, a trade request is generated automatically.

The requested trade of this kind of trade request can have one of the following instrument categories:

Foreign Exchange

FX Forward

FX Spot

**Money Market**

Money Market: Fixed Term Deposit/Loan

Commodity FX Integration

A trade request with the trade request category Commodity FX Integration was created as an FX request in the FX

Exposure and FX Hedge Request Management app on SAP Business Technology Platform. When the cash request is released using the FX Exposure and FX Hedge Request Management on SAP Business Technology Platform, a trade

request is automatically created and released . The requested trade of this kind of trade request can have one of the following instrument categories:

Foreign Exchange

FX Non-Deliverable Forward

FX Forward

Manual

A trade request with the trade request category Manual was created manually in the Process Trade Requests app or with the Treasury Trade Request - Read, Create (API_TREASURYTRADEREQUEST) API.

The requested trade of this kind of trade request can have one of the following instrument categories:

Foreign Exchange

FX Forward

FX Spot

FX Option

FX Non-Deliverable Forward

FX Swap

FX Non-Deliverable Swap

FX Collar

**Money Market**

Money Market: Fixed Term Deposit/Loan

**Prerequisites**

Set up the Integration with External Trading Platforms scenario as described in the Administration Guide for the SAP Trading Platform Integration, especially the Technical Prerequisites.

Trade requests can have three possible sources: hedge requests, cash requests and balance sheet exposure hedge requests. To activate them, proceed as follows:

In order to create trade requests based on hedge requests in the Hedge Management and Accounting of Net Open Exposures (FX Risk) process, you must activate the checkbox for the SAP Trading Platform Integration on the Main Data tab in the hedging area master data.

In order to create trade requests based on cash requests, make the following settings as described under Cash Trade Requests:

In the Customizing activity Define Basic Settings, select the Enable Cash Request Integration checkbox.

You can find this Customizing activity in Customizing under Financial Supply Chain Management Cash and Liquidity Management General Settings .

In the Customizing activity Assign Planning Levels to Cash Trade Requests, assign planning levels to different statuses of cash trade requests.

You can find this Customizing activity in Customizing under Financial Supply Chain Management Cash and Liquidity Management Cash Management Memo Records .

Trade requests from balance sheet exposure hedge requests are created automatically, as described under Balance Sheet Exposure Hedge Request.

Depending on your back-end configuration (version 1.0 or 2.0), you can implement the following BAdIs in Customizing. You can find the BAdIs under Treasury and Risk Management Transaction Manager General Settings Transaction Management External Link Connect to Trading Platform via SAP Trading Platform Integration . For more information on back-end configuration, see SAP Trading Platform Integration > Administration Guide > Scope.

Integration via RFCs - Back-End Configuration V. 1.0

BAdI: SAP Trading Platform Integration: Overwrite General Mapping

BAdI: SAP Trading Platform Integration: Overwrite Product-Specific Mapping

Integration via Web Services - Back-End Configuration V. 2.0

BAdI: SAP Trading Platform Integration: Outbound Trade Request

BAdI: SAP Trading Platform Integration: Inbound Trade Request Confirmation

BAdI: SAP Trading Platform Integration: Fulfill or Cancel Trade Request

BAdI: SAP Trading Platform Integration: Create Trade

BAdI: SAP Trading Platform Integration: Fixing for Money Market Funds

BAdI: Retrieve Exchange Rate for Intercompany Trading

BAdI: Retrieve Counterparty Limits from Back End

BAdI: Check Counterparty Limits Before Trade

Refer to the PDF document attached to 3209441 for the set-up instructions for the automatic transfer of trade requests in your back-end system.


**More Information**

Trade Request

Process Trade Requests

Treasury Trade Request - Read, Create (API_TREASURYTRADEREQUEST) API

This inbound OData service enables you to read the existing treasury trade requests in your SAP S/4HANA system, such as hedge trade requests, B/S hedge trade requests, cash trade requests, or manual trade requests. The service also enables you to create manual trade requests for FX and MM instrument categories.

For more information about how to integrate the application with Treasury and Risk Management, see the product documentation at https://help.sap.com/trm_tpi.

The following documentation gives more insights into the settings you make in SAP S/4HANA:

Setup instructions for the 2F5 scope item in the SAP Best Practices Explorer

Hedge Management and Accounting of Net Open Exposures (FX Risk)

Hedge Management of Balance Sheet FX Risk

###### Fiduciary Deposits

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Money Market > Fiduciary Deposits | L7 | trm02 p.111 | loio `9ae1bd99134d4bb39da1141561c09b8f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9ae1bd99134d4bb39da1141561c09b8f.html?locale=en-US)

**Use**

In this function, you can calculate the net present value (NPV) of Fiduciary Deposit deals.

**Features**

To perform the calculations needed to determine the fair value of the deposit, the collateral and the swap agreement are treated separately. Later on, their separate valuations are totaled.

Collateral:

Collateral bonds are priced at market value whenever each of them is liquid enough to have a representative public quotation.

For any illiquid positions, it is necessary to use a valuation model that takes into account not only market conditions but also credit risk. Most of the illiquid assets have a plain vanilla cash flow pattern or, at most, one of the commonly used fixed income embedded derivatives (cap, floor, put, or call features).

Swap Agreement:

The valuation method used for this instrument is just cash flow discounting of both legs (the one that represents liabilities and the one that represents the collateral flows) using the Euro – CMS flat curve, and this way not quantifying any credit risk at all.

[figure TRM02-F129 - The valuation method used for this instrument is just cash flow discounting of both legs (the one that represents liabilities and the one that represents the collateral flows) using the Euro – CMS flat curve, and this way not quantifying any credit risk at all.]

**Activities**

To calculate the NPV of a fiduciary deposit deal, proceed as follows:

- 1. Create a fiduciary deposit transaction. See Fiduciary Deposit.

- 2. Open Treasury and Risk Management Accounting Analyzer Tools Maintain Financial Object .
- 3. Fill all required fields:

Enter the company code.

Select Derivatives/Money Market/Forex/Listed Transaction/Security Trans..

Enter the transaction number of the fiduciary deposit created.

Choose Change.

- 4. Choose Treasury and Risk Management Market Risk Analyzer Information System Mark-to-Market JBRX – NPV Analysis


- 5. Enter the following:

Evaluation currency

Evaluation type

Horizon

Evaluation date (preceding the fiduciary end date)

Transaction number and characteristics in the Characteristics tab.

- 6. Choose Execute.


**More Information**

For more information, see:

Valuation

Foreign Exchange

###### Forex Spot Transactions (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Foreign Exchange > Forex Spot Transactions (OTC) | L7 | trm02 p.113 | loio `bb1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bb1bda531198434de10000000a174cb4.html?locale=en-US)

NPV calculations are not made in the risk analysis for Forex spot transactions, since they are not subject to the risk of changing interest rates. If the forex positions resulting from forex spot transactions need to be valued in the gap analysis, then this can only be done by valuing the positions as balances in two accounts with two different currencies. They are then valued similarly to account transactions.

###### Forward Exchange Transaction

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Foreign Exchange > Forward Exchange Transaction | L7 | trm02 p.113 | loio `4cf37a555e21458ae10000000a42189b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4cf37a555e21458ae10000000a42189b.html?locale=en-US)

**Use**

The price calculator for forward exchange transactions calculates current market values as well as market/time values for a future date (horizon).

With forward exchange transactions, a specified amount of a currency is exchanged against another currency at a future key date using a specified exchange rate.

In transaction management, a cash flow is created when creating a forward exchange transaction. The cash flow consists of both exchange payments (agreed upon in the transaction) in both transaction currencies that are made upon maturity of the forward exchange transaction.

The yield curve framework is used to discount the cash flows. See also: Yield Curve Framework

**Key Features**

Valuation

If the due date of the transaction falls before the horizon, the forward exchange transaction has a value of zero at the horizon. The foreign exchange payments do not flow into any foreign currency balance in the component Risk Management.

If the due date of the transaction falls after the horizon, a value can be calculated. During the valuation, both cash flows that occur on the due date are discounted to the horizon using using the relevant yield curves (of both transaction currencies). The net present value of the forward exchange transaction is the difference between both cash flows discounted using the currency exchange rates (bid and ask rates) and converted into the evaluation currency.

The following definitions apply:

|C|Cash flow of the purchase side of the forward exchange transaction|
|---|---|
|D|Cash flow of the sales side of the forward exchange transaction|
|DV(C/D)|Value of cash flow C/D discounted to the horizon|
|C(C/D)|Currency of cash flow C/D|
|DC|Display currency|
|ER(C(C); DC)|(Forward) exchange rate C(C)/DC|
|NPV|Net present value|


NPV = DV(C) * ER(C(C); DC) — DV(D) * ER(C(D);DC)

In the evaluation type, on the Evaluation Control 2 tab page in the Foreign Exchange Valuation Method field, you can select one of the following values for the evaluation method for future foreign exchange cash flow:

Discounting Before Currency Translation

If you choose this option, cash flows are then discounted by using the cash flow currency yield curves. Finally, the system uses spot rates to translate currency into the valuation currency. This method is also called the zero coupon method.

Currency Translation Before Discounting

If you choose this option, the cash flows are translated by using forward rates and are then discounted by using the valuation currency yield curve. This method is also called the par method.

In the case of NDFs, a different logic can be selected: If the Take Fixing Date and Settlement Currency into Account value is defined when considering fixing details for foreign exchange, forward translation into the settlement currency is executed on the fixing date and is discounted by the payment date.

**Note:**

The net present value of a non-deliverable forward (NDF) is also calculated using this formula. After an NDF has been fixed, the net present value of an NDF is only the clearing amount discounted to the horizon and converted into the display currency.

NPV = DV(A) * ER(C(CA);DC)

where: CA = Clearing amount

In the evaluation type, if you have specified the Currency Translation Before Discounting value on the Valuation Control 2 tab page as the valuation method for future foreign exchange cash flows, you can select the Take Fixing Date and Settlement Currency into Account setting to calculate the net present value of NDFs in the Currency Translation: Consideration of Fixing Details field.

In this case, the cash flows are translated into the settlement currency on the fixing date using the forward rates, and are then discounted by using the settlement currency yield curve on the payment date. Finally, the valuation currency is translated by using the spot rate.

Derivatives

###### Forward Stock Transactions (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Forward Stock Transactions (Listed) | L7 | trm02 p.115 | loio `961bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/961bda531198434de10000000a174cb4.html?locale=en-US)

Use

The market price calculator for forward stock transactions calculates current market values, time values, and future market values (the future point in time is the horizon).

Forward stock transactions are agreements to purchase or sell stocks at an agreed upon price at some point in the future.

**Caution:**

To evaluate forward stock transactions in risk analysis, you must create the transactions as orders to be exercised in the future, and then assign the order a flow type that has the Forward transaction flag set in Customizing. Otherwise, when you maintain a financial object for an order, you do not see the Risk Management part.

**Scope of Functions / Valuation**

The value of the forward transaction on the horizon is the difference (discounted to the horizon) between the forward price and the agreed purchase or selling price, multiplied by the number of shares of stock in the transaction.

The following distinctions need to be made before valuation:

The settlement date of the transaction is before the horizon

In this case, the bought or sold forward securities constitute a position. The forward stock transaction no longer has any value on the horizon.

The settlement date of the transaction is after the horizon

In this case, the value of the forward transaction is calculated.

The value of the forward transaction on the horizon is the difference (discounted to the horizon) between the forward price and the agreed purchase or selling price, multiplied by the number of shares of stock in the transaction.

The following abbreviations/definitions are used:

|St:|Number of stocks to be bought or sold on the expiration date|
|---|---|
|TK:|Agreed buy or sell price|
|AK:|Stock price on the evaluation date|
|BW(TK):|Net present value on the horizon of the cash flows from the sale or purchase|
|ZW(AK):|Price on the evaluation date valid until the horizon (no interest accrual)|
|K:|Call/put indicator|
|NPV:|Net present value|


[figure TRM02-F130 - If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.]

If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

###### Forward Stock Transactions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Forward Stock Transactions | L7 | trm02 p.116 | loio `dda8c8e1b54d4156972d2b7732ea0ba3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dda8c8e1b54d4156972d2b7732ea0ba3.html?locale=en-US)

The net present value for forward stock transactions at time t is calculated as follows:

[figure TRM02-F131 - The net present value for forward stock transactions at time t is calculated as follows:]

###### Forward Transactions on Bonds (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Forward Transactions on Bonds (Listed) | L7 | trm02 p.116 | loio `a21bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a21bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for forward security transactions calculates current market values, time values, and future market values (the future point in time is the horizon).

Forward security transactions are agreements to purchase or sell securities at an agreed upon price at a certain point in the future. This includes all bonds that can be maintained in the SAP System.

**Caution:**

To evaluate forward transactions on bonds in risk analysis, you must create the transactions as orders to be exercised in the future, and then assign the order a flow type that has the Forward transaction flag set in Customizing. Otherwise, when you maintain a financial object for an order, you do not see the Risk Management part.

**Integration / Calculation Basis**

In order to value a forward transaction on bonds, you need the transaction data, and alternatively a par coupon or zero coupon yield curve in the transaction currency for the evaluation date. In addition to the yield curve structure necessary for discounting generated cash flows (see initial parameters), it is possible that yield curve structures are also needed to calculate forward rates for variable interest payments.

If the display currency is different from the payment currency of the forward security transaction, the relevant currency rate is needed. If the horizon comes after the evaluation date, and the currency of a payment of the forward security transaction differs from the display currency when calculating a forward transaction on the horizon, a par or zero coupon yield curve structure will have to be entered in the display currency.

Zero bond discounting factors are needed as further input parameters in order to discount the cash flow. The zero and par coupon calculation methods can be used to define the zero bond discounting factors.

**Scope of Functions / Valuation**

If the horizon comes after the settlement date, the transaction has expired and the NPV is zero.

Otherwise the first step reduces the cash flow to those flows that are due before the settlement date of the transaction. This reduced cash flow is then increased by the cash flows from accrued interest, whose amounts are determined using the accrued interest calculator. Payment of the accrued interest is due on the settlement date of the transaction.

For securities with variable interest rates, the forward reference interest rates are also calculated. For interest rate agreements whose fixed and variable interest rates are tied to formulae, the amount of the resulting interest rates are calculated using the calculated forward rates (possibly taking interest floors and caps into consideration). The calculated interest payments are put into the cash flow, which only contains flows whose size and payment date are certain. According to either the par or zero coupon calculation method, the NPV is calculated to the horizon for both the individual payment flows as well as the cash flow from the purchase/sale or the bond, using the interest yield curves (corresponding to the transaction currency). The purchase or sale cash flow is the price multiplied by the nominal volume on the settlement date. The value of the forward security transaction (in the display currency) is the difference between the NPV of the payment flows converted to the display currency and the NPV of the cash flows from the sale/purchase of the bond, also converted to the display currency.

The following abbreviations/definitions are used:

|t i :|Expiration date of the cash flow|
|---|---|
|C i :|Cash flow at time point t (including the cash flow of the accrued interest) i|
|D:|Agreed buy or sell price|
|NV:|Nominal volume|
|BW(C i /D*NV):|Net present value on the horizon of the cash flows C or D*NV due on t i i|
|W(C i /D*NV):|Currency of cash flow C i /D*NV|


|AZ:|Display currency|
|---|---|
|WK(W(C i /D*NV);AZ):|Exchange rate W(C i /D)/AZ (ask or bid rate)|
|K:|Call/put indicator|
|NPV:|Net present value|


[figure TRM02-F132]

###### Forward Rate Agreements (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Forward Rate Agreements (OTC) | L7 | trm02 p.118 | loio `711bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/711bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for forward rate agreements (FRAs) calculates current market values, time values, and future market values (where future means the horizon).

An FRA is a means of hedging against rising or falling interest rates by agreeing an interest rate now to apply at a future date. This interest rate is compared to a reference interest rate Rk (for example the LIBOR for a given period) when the contract is being made.

A settlement payment is due on the settlement date (beginning for the interest rate hedge period). The settlement payment is calculated by taking the nominal sum from the difference between the contract and actual interest rates on the fixing date (normally two days before the settlement date). This amount is then discounted from the end of the hedge period (using the forward rate) back to the fixing date.

The NPV of the FRA depends on the position of the horizon. If it is before the settlement date, then the NPV is calculated on the horizon (back from the end of the hedge period). If the horizon is after the settlement date, then the NPV is zero.

**Integration and Data Used as the Basis for the Calculation**

Depending on the positioning of the evaluation date and the horizon, the following parameters must be used:

Evaluation date < horizon < fixing date < settlement date or evaluation date < fixing date < horizon < settlement date

To value a future, the transaction data - and alternatively a par coupon or zero coupon yield curve in the transaction currency - has to be entered for the evaluation date. In addition to the yield curve necessary for discounting generated cash flows (see initial parameters), a yield curve is also necessary to calculate forward rates for variable interest payments.

Fixing date < evaluation date < horizon < settlement date

To value a future, the transaction data - and alternatively a par coupon or zero coupon yield curve in the transaction currency - has to be entered for the evaluation date. In addition, you also need the interest rate Rf for the reference interest rate on the fixing date. If this interest rate is not available, the value of the interest rate is set to zero.

fixing date < settlement date < horizon

No values need to be preset.

To discount the payments, zero bond discounting factors are required as additional input parameters. The zero and par coupon calculation methods can be used to determine the zero bond discounting factors.

If the transaction currency differs from the display currency of the FRA, the transaction currency is translated into the display currency using the currency rate at the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the evaluation date using the yield curves from the transaction and display currencies.

The following methods are used to calculate the input parameters:

**Scope of Functions / Valuation**

Depending on the positioning of the evaluation date and the horizon, the NPV of the FRA is calculated as follows:

Evaluation date < horizon < fixing date < settlement date or evaluation date < fixing date < horizon < settlement date

First, the forward interest rate of the reference interest rate is calculated. The interest payments calculated from this are put into the cash flow, which as a consequence only contains cash flows for which the amount and payment date are known. Depending on the method of calculation (par or zero coupon method), the NPV of the individual cash flows is calculated (see input parameters) using the yield curve (appropriate to the transaction currency) from the settlement date of the FRA. The value of the FRA settlement payment (in transaction currency) is the difference between the NPVs of the two cash flows.

The following definitions apply:

|C:|Cash flow resulting from the agreed interest rate of the FRA|
|---|---|
|D:|Cash flow resulting from the forward reference interest rate|
|BW(C/D):|NPV of cash flows C/D on the settlement date|
|K:|Long/Short Indicator|
|SP:|Settlement Payment|


[figure TRM02-F133 - Hence the NPV of the FRA is the NPV of the settlement payment on the horizon, corresponding to which method of calculation is used (par or zero coupon method).]

Hence the NPV of the FRA is the NPV of the settlement payment on the horizon, corresponding to which method of calculation is used (par or zero coupon method).

If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

[figure TRM02-F134 - Fixing date < evaluation date < horizon < settlement date]

Fixing date < evaluation date < horizon < settlement date

The cash flow in this case only contains payments for which the amount and payment date are known. Depending on the method of calculation (par or zero coupon method), the NPV of the individual cash flows is calculated (see input parameters) using the yield curve (appropriate to the transaction currency) from the settlement date of the FRA. The value of the FRA settlement payment (in transaction currency) is the difference between the NPVs of the two cash flows.

The following definitions apply:

|C:|Cash flow resulting from the agreed interest rate of the FRA|
|---|---|
|D:|Cash flow resulting from the fixed forward reference interest rate|
|BW(C/D):|NPV of cash flows C/D at the end of the lead time.|
|K:|Long/Short Indicator|
|SP:|Settlement Payment|


[figure TRM02-F135 - Hence the NPV of the FRA is the NPV of the settlement payment on the horizon, corresponding to which method of calculation is used (par or zero coupon method).]

Hence the NPV of the FRA is the NPV of the settlement payment on the horizon, corresponding to which method of calculation is used (par or zero coupon method).

If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

fixing date < settlement date < horizon

The net present value of the forward rate agreement is zero.

###### Futures (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Futures (Listed) | L7 | trm02 p.120 | loio `211bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/211bda531198434de10000000a174cb4.html?locale=en-US)

Use

The price calculator prices listed futures on bonds, interest rates, indexes, and stocks.

**Prerequisites**

To price futures, the system needs the following data:

Transaction data

A yield curve in the transaction currency and for the evaluation date

Depending on the nature of the underlying transaction, it may also need additional data:

For futures on indexes, the system also needs the index values on which the underlying transaction is based.

For futures on interest rates, it uses the yield curve to calculate the forward rates for the variable interest payments.

For futures on bonds, the system generates a cash flow that consists of interest payments and a repayment for the fictitious underlying transaction.

If the evaluation currency and the transaction currency of the future are different, then the system calculates the forward exchange rate for the maturity date. This requires the following data:

The relevant exchange rate

A par coupon or zero coupon yield curve in the evaluation currency

For stock futures, the spot rate is used on the evaluation date.

**Features**

Net Present Value (NPV) Analysis

The price calculator determines the NPV of future transactions. The NPV depends on whether the horizon is before or after the maturity of the future and on whether the calling application delivers a market data scenario to the price calculator. If the horizon date is after the maturity date, the NPV of the transaction is zero.

If the horizon is before the maturity date and no market data scenario was provided, then the NPV of a future is zero. This is because the NPV is cleared each day to the margin account or clearing account.

For stock futures, the NPV depends on the evaluation type settings.

If a market data scenario is provided, the price calculator calculates the difference between the future value of the underlying transaction based on the market data scenario and the value of the underlying transaction on the horizon date based on the market data for the evaluation date. Cash flows aren’t discounted to the horizon.

[figure TRM02-F136 - where NPV is the NPV calculated by using current market data, and NPV is the NPV from scenario data.]

where NPV is the NPV calculated by using current market data, and NPV is the NPV from scenario data.

current scenario

The price calculator calculates the NPV of the underlying as follows:

Futures on Bonds

[figure TRM02-F137 - Futures on Bonds]

where CF are the cash flows of the bond, d are the discounting factors for the cash flows on the maturity date, p is the price defined in contract, and NV is the nominal volume. For technical reasons, the system discounts the cash flows as follows: First, it discounts the cash flows to the evaluation date, and then it discounts them to the maturity date of the future.

i i

Futures on Interest Rates

[figure TRM02-F138 - where contract value is the value of the contract, term is the term of the reference interest rate of the underlying, forward rate is the forward rate of the underlying on the maturity date based on the yield curve valid on the evaluation date, and forward rate is the price of the underlying as set out in the contract.]

where contract value is the value of the contract, term is the term of the reference interest rate of the underlying, forward rate is the forward rate of the underlying on the maturity date based on the yield curve valid on the evaluation date, and forward rate is the price of the underlying as set out in the contract.

yield curve

order

Futures on Indexes

[figure TRM02-F139 - where contract value is the value of the contract, index value is the value of the index of the underlying discounted to the maturity date, and index value is the index status of the underlying as set out in the contract.]

where contract value is the value of the contract, index value is the value of the index of the underlying discounted to the maturity date, and index value is the index status of the underlying as set out in the contract.

expiry date order

Futures on Stocks

The price calculator calculates the NPV of stock futures depending on the evaluation type settings, either as 0 due to daily margin payments or as

[figure TRM02-F140 - The price calculator calculates the NPV of stock futures depending on the evaluation type settings, either as 0 due to daily margin payments or as]

where

NPV = Net present value in evaluation currency

e

S (t ) = Spot FX rate from contract currency to evaluation currency on the evaluation date

c,e e

D (t t ) = Discount factor in contract currency on the evaluation date for the future settlement date

c e, s

N = Number of futures in the lot

f

N = Contract size, that is, the number of shares one future contract refers to

c

P (M) = Market price of the future in contract currency

c

P (C) = Contract price of the lot-generating transaction in contract currency

c

The contract currency is the currency in the lot-generating transaction that is the same as the currency maintained in the future master data. If no market price is found that is younger than the maximum security price age specified in the evaluation type, an error message is raised.

The following evaluation type settings influence the calculation of the NPV:

Security price type

Maximum age of price

Calculate by Contract Value indicator

This indicator is only considered for lot-based positions because the contract price of the lot-generating transaction is needed to calculate the NPV.

If this indicator is not set, the system will always consider the NPV of the position to be 0 due to daily margin payments.

FO for Pos. in Futures Account

The value Lot-Based Positions in Futures Accounts Have Priority is selected in the dropdown menu on the Financial Object Selection tab.

Sensitivity Analysis and Value-at-Risk Analysis

In the sensitivity analysis and value-at-risk analysis, the system calculates the time value of the underlying on the maturity date of the future, and uses the value as the value of the future. It uses various scenarios to do this (with and without shifts, for example).

If the horizon is before the maturity date of the future, then the NPV of the underlying is always included in the analysis as the value of the future on the maturity date. If the horizon is after the maturity date of the future, then the value of the future is zero.

**Note:**

The exchange rate risk of futures is always displayed as zero. If the evaluation currency and the transaction currency of the future are different, then the transaction is subject to currency risk only on the maturity date, as this is the first point in time when foreign currency is exchanged in return for the underlying. The currency risk on the margin account is ignored, as the clearing accounts aren’t part of the system.

###### Swaps (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Swaps (OTC) | L7 | trm02 p.123 | loio `6b1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6b1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for swaps calculates current market values, time values, and future market values (the future point in time is the horizon).

Swaps are agreements to exchange fixed and/or variable interest rates. Their individual variations can take almost any form. In addition to interest swaps (one transaction currency), you can also compose currency and cross-currency interest rate swaps (two transaction currencies). A principal swap can be processed at the beginning and/or the end of the validity period. Because condition items can be arranged variably, interest rate agreements can be arranged any way you like. In addition to fixed-rate payer and receiver swaps (exchange of fixed rates for variable), you can also perform basis swaps (exchange of variable interest rates calculated on different bases). Even interest rate agreements in which interest rates dependent on formulae can be used to some extent (using variable interest rates). The formula must be in the form V V + V V (where V is a fixed or variable interest rate). You can also work with fixed or variable interest rate floors and caps. For valuation, the interest rates which go above or below the agreed interest rate limit are replaced with the values of that limit. You can also create amortization and step-up swaps. Variable interest rate spreads can also be arranged as you choose. The frequency of interest payments can be freely adjusted as well.

1 2 3 4 i

**Note:**

The settlement currency is ignored during the calculation of the NPV of cross-currency interest rate swaps.

**Integration / Calculation Basis**

In order to value a swap, the transaction data, and alternatively a par coupon or zero coupon yield curve in the transaction currency, has to be entered for the evaluation date. In addition to the yield curves necessary for discounting generated cash flows, it is possible that additional yield curves are needed to calculate forward interest rates for variable interest payments.

With the help of the Treasury Management component, a cash flow is generated for each side of the swap when a swap is created. The cash flow consists of interest and principal payments, which "flow" at particular points in time. The amount of the interest payments is known for fixed interest rates. Only the reference interest rate is known for variable interest rates (perhaps contained in formulae and interest caps and floors).

Zero bond discounting factors are needed as further input parameters in order to discount the cash flow. The zero and par coupon calculation methods can be used to define the zero bond discounting factors.

If the transaction currency differs from the display currency of the swap, the transaction currency is changed into the display currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the evaluation date using the yield curves from the transaction and display currencies.

**Scope of Functions / Valuation**

In the first step, the cash flow is reduced to those flows which have due dates later than the horizon. For swaps with variable interest payments (on one or both sides), the forward reference interest rates are then calculated. For interest rate agreements whose fixed and variable interest rates are tied to formulae, the amount of the resulting interest rates is calculated using the calculated forward rates (possibly taking interest floors and caps into consideration). The calculated interest payments are put into the cash flow, which only contains flows whose size and payment date are certain.

**Note:**

If you have an interest rate fixing date which lies before the evaluation date and will result in a payment after the horizon, but which has not yet been made at the time of valuation, the first cash flow from the variable side is assumed to be zero, and will be listed in the detail log under fixed cash flows.

Depending on the method of calculation (par or zero coupon method), the NPV of the individual cash flows (both sides) is calculated for the horizon, using the yield curve of the transaction currency. The value of both sides of the swap (in the transaction currency) is the sum of the NPVs of the cash flows (from both sides). The NPV of the swap (in the display currency) is the difference between the value of the two sides of the swap, the value having been converted to the display currency using the (forward) currency rates.

The following abbreviations/definitions are used:

|t i :|Expiration date of the cash flow|
|---|---|
|C i :|Cash flow of the recipient side of the swap at time t i where i = 1,...,n|
|D i :|Cash flow of the payer side of the swap at time t i where i = 1,...,n|
|BW(C i / D i ):|Net present value on the horizon of the cash flows C and D due on t i i i|
|GW (ES):|Transaction currency of the receiver side of the swap|


|GW (ZS):|Transaction currency of the payer side of the swap|
|---|---|
|AW:|Display currency|
|WKG(GW(ES);AW):|(Forward) bid rate GW(ES) / AW on the horizon|
|WKB(GW(ZS);AW):|(Forward) ask rate GW(ES) / AW on the horizon|
|NPV:|Net present value|


[figure TRM02-F141]

###### Total Return Swap (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Total Return Swap | L7 | trm02 p.125 | loio `e62406316fe445cb90420585c06f3ea8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e62406316fe445cb90420585c06f3ea8.html?locale=en-US)

**Use**

You can calculate the net present value (NPV) of total return swap deals.

**Key Features**

The NPV is calculated by using market data entered into the system (price per leg or overall amount of the TRS).

[figure TRM02-F142 - The NPV is calculated by using market data entered into the system (price per leg or overall amount of the TRS).]

**Activities**

To calculate and view the NPV for a total return swap, go to the SAP Easy Access menu and choose Transaction Manager Derivatives Accounting Valuation TPM60 – Determine Net Present Values , and proceed as follows:

- 1. Select the OTC Transactions: Money, Foreign Exchange, OTC Derivatives checkbox in the Product Groups group box.
- 2. Select Product Type 64A for total return swaps.


- 3. Make any other selections in this screen, for example, Company Code or Transaction Type.
- 4. Select your evaluation parameters.
- 5. Choose Execute.
- 6. A list of NPVs that meet your selection criteria is displayed.


**See Also**

For more information, see:

Total Return Swap

###### Overnight Index Swap

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Overnight Index Swap | L7 | trm02 p.126 | loio `e41ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e41ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

The overnight index swap is a special form of the compound swap.

**Example:**

EONIA Swap (EUR)

Federal Fund Rate Swap (USD)

In an Overnight Index Swap, a fixed interest rate is swapped for a variable one. This is based on the call money fixing of the overnight index (for example, EONIA (= EURO OverNight Index Average), Federal Fund Rate).

**Prerequisites**

The conditions of the overnight index swap must be set up correctly.

See also:Overnight Index Swap.

The price calculator expects that the following parameters are always the same for a due date:

Nominal Amount

Reference Interest Rate

Nominal Currency

Cashflow Currency

**Features**

The values for the fixed and variable sides of the overnight index swap are calculated separately.

The NPV of the swap is the sum of the NPVs of both sides.

The existing future interest rate flows on the fixed side are discounted on the valuation key date.

On the variable side, the valuation takes place so:

All interest rate flows not due yet are calculated. If m of n future due call money fixings have already been made in a current interest period before the valuation due date, the remaining n m outstanding interest rates are calculated from the yield curve (forward rates).

The sum of all resulting interest payments on a due date are discounted on the valuation due date.

**Note:**

Through the overnight index swap, the function can valuate financial instruments with the following characteristics:

More than one interest payment on the variable side

All interest calculation methods are permitted.

The interest rates that are the basis for averaging need not be call money interest rates, but can also be the summation of 12 reinvested monthly interest rates for a year.

###### Securities Lending (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Securities Lending | L7 | trm02 p.127 | loio `f91ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f91ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

In securities lending transactions, the owner of the securities lends the stocks or bonds, which are returned after a specified period. The lender receives a payment for this.

**Integration**

The system prices the class positions in securities accounts for the securities lending transactions. To flag the securities as securities that have been lent, you save the securities in the lending securities account in Transaction Manager in SAP Treasury and Risk Management .

###### Repurchase Agreements (Repos)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Repurchase Agreements (Repos) | L7 | trm02 p.127 | loio `021bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/021bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

Repurchase agreements, or repos, represent a temporary transfer of securities in exchange for money. The basis of transaction is the obligation of the borrower to take back the securities pledged. The contract can oblige the lender to return the securities (real repurchase agreement), or merely gives him or her the right to return them (repurchase agreement with optional right).

The price calculator prices only real repurchase agreements. It is currently not able to price repurchase agreements with optional rights.

**Integration**

When you create a repurchase agreement, you define whether it is a repo with delivery , or a repo without delivery . For repurchase agreements with delivery, the underlying security is transferred from the borrower's security account to the lender's security account. For repurchase agreements without delivery, the underlying security remains in the borrower's security account. In both cases, the repurchase agreements are recorded in the borrower's accounts.

However, the price calculator does not distinguish between the product types repo with delivery , and repo without delivery . The system prices both as money market transactions. For more information, see Money Market Transactions . Repurchase

agreements have no effect on the securities position in Risk Analyzer.

**Scope of functions**

In the NPV calculation, the system takes the individual cash flows of the transaction, and discounts them to the horizon using yield curves (as per the transaction currency). The net present value of a repurchase agreement is the total of the cash flows discounted to the horizon, and the translated to the evaluation currency.

###### Spot Stock Transactions, Forward Stock Transactions and Stock Option Transactions Aggregated on an Index (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Spot Stock Transactions, Forward Stock Transactions and Stock Option Transactions Aggregated on an Index (Listed) | L7 | trm02 p.128 | loio `9c1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9c1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for spot stock transactions, forward stock transactions and stock option transactions aggregated on an index calculates current market values and future market values and time values (the future point in time is the horizon).

When using the variance/covariance approach for value at risk (VaR), you need the correlation between the individual risk factors. These are not always available for stock. Also, all historical rates of all stock classes in the position are not always maintained completely. In these cases, it is sensible to make use of the correlation of the stock to a common index, rather than the correlation between the individual stocks. This makes the index a risk factor and each stock class has a risk item in the index. The set up of the item in the index is based on the Capital Asset Pricing Model (CAPM).

To determine the value at risk in a stock class, the spot stock transactions, forward stock transactions and stock option transactions that need to be aggregated are set up in the index. For this, the beta-weighted item in the stock is set up as an item in the index. With this approach, you can depict items from forward stock transactions and stock options, as well as stock positions.

**Integration / Calculation Basis**

When valuing the transactions, you need to have the class data and the current price for the stock class for the evaluation date. The assigned ID number is the number of the security class.

In order to value the forward stock transactions and options on stocks, you need the transaction data, and alternatively a par coupon or zero coupon yield curve in the transaction currency for the valuation date.

You also need a price volatility curve relating to the option term.

If the display currency is different from the transaction currency, the relevant currency rate is needed. If the horizon comes after the evaluation date and the transaction currency differs from the display currency, you need to enter a par or zero coupon yield curve to calculate a forward transaction on the horizon.

**Scope of Functions / Valuation**

First a check is made to see if the stock class in question has been defined as a potential risk factor.

If this stock class has been defined as a potential risk factor, then there is no aggregation.

If this stock class has not been defined as a potential risk factor, then a check is made to see if it has been assigned to an index. This assignment is made in Customizing in an evaluation type.

If this stock class has been assigned to an index, then the spot stock position, the forward stock transactions and the stock option transactions based on this stock class are depicted on the specified index.

If this stock class has not been assigned to an index, then a check is made to see if a default index has been defined.

If a default index has been defined, then the spot stock transactions and derivative stock transactions are depicted on the default index.

First you calculate the net present value item of the spot stock position for the appropriate stock class from the number of units and the spot stock price (item ).

spot

You determine the net present value of forward stock transactions (item ) and stock options (item ) for the stock class concerned as described above. In addition, you determine the option delta.

forward option

The price change equivalent (pce) item in the underlying transaction of the option (position ) results from multiplying the current option price with the option delta.

opt pce

[figure TRM02-F143]

Then the net present value items are summarized and valued with the beta factor.

[figure TRM02-F144 - Then the net present value items are summarized and valued with the beta factor.]

Also, you determine the net present value of the transactions aggregated on the index.

[figure TRM02-F145 - Also, you determine the net present value of the transactions aggregated on the index.]

Net present value price risks arising from the transactions depicted on indexes are the result of the price change of each index. These are calculated by adding the item multiplied by the related index changeI of the aggregated transactions in the index and the net present value of the transactions depicted on the index.

[figure TRM02-F146 - Net present value price risks arising from the transactions depicted on indexes are the result of the price change of each index. These are calculated by adding the item multiplied by the related index changeI of the aggregated transactions in the index and the net present value of the transactions depicted on the index.]

###### Option Price Calculator (1 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator | L7 | trm02 p.129 | loio `e21bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e21bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use the option price calculator to calculate the NPV of options on transactions (bonds, swaps, FRAs, stocks), and to calculate the option delta.

**Features**

The following types of options can be valued:

Standard European options

Barrier options (up&out, up&in, down&out, down&in)

Hit-at-end-binary (digital) options

One-touch-binary (digital) options

Standard American options

The Hull-White model can be used to price American options on swaps and bonds. American options, whose underlying is not an interest rate instrument, are priced using a method that is based on the Cox-Ross-Rubinstein model.

Bermuda options on interest rate instruments

The system categorizes options firstly by their exercise type (European, American), and then by the type of the option itself.

###### General European Standard Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > General European Standard Options | L8 | trm02 p.130 | loio `4840c251a4ef4157e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4840c251a4ef4157e10000000a441470.html?locale=en-US)

**Use**

This function prices European options on stocks, bonds, and indexes as well as on call options and repayment options.

**Features**

Black-Scholes

The system uses the Black-Scholes formula to price options. The formula is slightly different for each type of underlying. The method used to price stock or bond options is used as a basis for pricing the other options.

The calculation formula is considered only in cases where the horizon lies between the purchase or sale of the option and its expiry date. In all other cases, the value of the option is zero.

Stock or Bond Options

The c (t , t , T, X) value of a call option and the p (t , t , T, X) value of a put option are calculated as follows:

S H E S H E

[figure TRM02-F147 - The c (t , t , T, X) value of a call option and the p (t , t , T, X) value of a put option are calculated as follows:]

where t is the horizon, t the evaluation date, T the expiry date of the option, X the strike of the option, R the riskfree forward interest rate on evaluation date t for the period from horizon date t to expiry date T, σ the volatility of the underlying for the time period from t to T, and N(x) the standard normal distribution; S(t ,T) is the forward spot price of the underlying:

H E

E H E E

[figure TRM02-F148 - where r is the risk-free interest rate for the period from evaluation date t to expiry date T of the option; q is the relevant dividend yield.]

where r is the risk-free interest rate for the period from evaluation date t to expiry date T of the option; q is the relevant dividend yield.

E

The Black-Scholes formula uses interest rates based on continuous compounding using interest calculation method act/365.

Index Options

Index options are treated in the same way as stock options. The index value is used as the spot price.

Currency Options

Currency options are treated in the same way as stock options. The exchange rate is used as the spot price. The risk-free interest rate is calculated as the difference between the interest rate of the local currency and the interest rate of the foreign currency.

Call Options and Unscheduled Repayment Options for Loans

Call options and unscheduled repayment options for loans are treated as call options (bond options) on loans. They are always short positions. For technical reasons, the pricing model prices only loans with precisely one call option and unscheduled repayment option correctly.

Swaptions

A swaption is an option on an interest rate swap that involves a fixed and variable leg. The buyer of the swaption gains the right to enter into a swap on a specified future date. The pricing model can price swaptions as interest rate options or as bond options.

Price swaptions as bond options

The system calculates the NPV of the swaption as an option on a fixed-rate bond where the option is exercised when the value of the fixed-rate bond is exceeds the value of the relevant variable-rate bond. The bond here is described by the fixed leg of the swap. The system uses the interest rate volatility and Macaulay duration to calculate the price volatility of the swaption (meaning the price volatility of the fixed leg). To determine the Macaulay duration, the price calculator calls up the cash flow discounting pricing model.

Price swaptions as interest rate options

The system calculates the NPV of the swaption as for that an option on a reference interest rate. The swap rate is used as the interest rate. The swap rate is calculated as the fair interest rate for a bond that corresponds to the fixed leg of the swap. The interest rate of the fixed leg of the swap is used as the strike.

Normal Distribution Model for Interest Rate Options

You can price some options (swaptions, caps/floors, and interest rate guarantees) using the normal distribution model.

The Black-Scholes model is based on the assumption that the values of the underlying are greater than zero. Since this is not always the case when interest rates are the underlying, market data providers also offer volatilities that, instead of applying the Black-Scholes model, use the normal distribution model, that is, the volatilities are not relative volatilities (%) but absolute volatilities in units of the underlying (% in the sense of an interest rate).

The normal distribution model uses the following formulas:

[figure TRM02-F149]

###### Standard American Options (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Standard American Options (OTC) | L8 | trm02 p.132 | loio `f11bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f11bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The binomial Black-Scholes-Richardson model is used to price standard American options.

**Integration and calculation bases**

The following parameters are used to call the price calculator for standard American options:

|Term:|Residual term of the option in days|
|---|---|
|Domrate:|Interest rate_1 in percentage|
|Forrate:|Interest rate_2 in percentage|
|Spot:|Spot amount|
|Strike:|Strike amount|
|Steps:|Number of steps in the binomial tree|
|Type of underlying:|Type of underlying|
|Vola:|Volatility|


|Put/call:|Put or call option|
|---|---|


**Scope of functions and valuation**

If the maturity date of the option has been reached, the intrinsic value of the option (difference between the spot and strike) is shown.

If the option term has not expired, the price is calculated as follows:

Starting from the end nodes, the exercise price and the holding value of the option are calculated backwards, for each node. The larger of the two is the option price at each node. A node value results from the total of the previous node values, weighted according to the likelihood of its occurrence.

lograte = log( 1 + domestic_rate / 100 ).

logforeign = log( 1 + foreign_rate / 100 ).

- d_time = days / 365 / steps."time in years per step"
- disc = 1 / exp( lograte * d_time ).


up = exp( vola * sqrt( d_time ) / 100 ).

uplog = log( up ).

down = 1 / up

ha = exp( ( lograte - logforeign ) * d_time ).

prob = ( ha - down ) / ( up - down ).

Holding value =

ij

(Price of the larger predecessor * Probability of upward movement+

Price of the smaller predecessor * Probability of a downward movement ) * Discount factor for one time step

= (P * prob + P * ( 1 - prob ) ) * disc

i+1,j i+1,j+1

Exercise price =

ij

Underlying price at time point i - Strike

= spot * exp( uplog * ( 2 * i - j ) ) - strike

P = max(exercise price | holding value )

ij ij ij

P = Price of the option

01

To improve the convergence, in the last time step before the exercise date the system calculates as the holding value the BlackScholes price of the option on each calculation node in terms of the residual validity period.It also applies Richardson extrapolation. This adjusts not only the oscillation of the option price based on the number of steps in the binomial tree, but also corrects the systematic deviation of the mean of the oscillation [see also Broadie, M. and Detemple, J.: "American Option

Valuation: New Bounds, Approximations, and a Comparison of Existing Methods, Review of Financial Studies 9.4 (1996), S.12111250].

###### Using the Hull-White Model to Price Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Using the Hull-White Model to Price Options | L8 | trm02 p.134 | loio `0c1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0c1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The system contains a model, which is based on the Hull-White model, for pricing options on interest rate instruments and Bermuda options. This model reproduces the current yield curve resulting from the market, and reflects the fact that volatility depends upon the term of the option. It also assumes that the variance of the interest rate is limited for transactions with long terms.

The Hull-White model can be particularly useful for caps and floors, and OTC options on bonds, loans, fixed-term deposits, forward rate agreements, and swaps.

**Integration**

The model requires the following market data:

Reference interest rates

The system uses reference interest rates to generate a yield curve for the evaluation date. In doing so, it uses the yield curve type defined in Customizing for the evaluation type or valuation rule. The yield curve is generated for the transaction currency.

Volatilities

The system requires the following parameters for interest rate volatilities: volatility parameter s and reversion rate a. It has to be able to read both parameters from the volatility database. The system reads the volatility type defined in Customizing for the evaluation type or valuation rule.

**Prerequisites**

The function for using the Hull-White model to price options is not a standard function. To be able to use the Hull-White model, you need to make the following Customizing settings:

You need to have already defined suitable yield curve types, and assigned a Hull-White volatility to them.

The system must contain master data and market data for the volatilities. If appropriate, you have calibrated the Hull-White model.

You need to have defined and set up a suitable valuation rule.

To define a valuation rule, go to Customizing of the Treasury and Risk Management and choose Basic Analyzer Settings Valuation Valuation Rule Define Valuation Rule .

To assign the valuation rule to an evaluation type, go to the Customizing of the Treasury and Risk Management and choose Basic Analyzer Settings Valuation Define and Set Up Evaluation Type .

On the Market Data Categories, under Yield Curve Volatility Type, specify the volatility types for the yield curve for the bid, ask, and middle rates.

On the Evaluation Control tab, choose the Hull-White valuation model, and enter a default step number and a maximum time step.

The model assumes that the interest rate options contain options on fixed-rate transactions. Therefore, you have to map options on variable-rate transactions as options on fixed-rate transactions. This is done in the system before the model is called. For more information, see Using the Hull-White Model to Price Interest Rate Options .

**Features**

The Hull-White model contains two methods. European options are priced using an analytical formula. American options and Bermuda options are priced using a trinomial tree method.

Analytical Solution for European Interest Rate Options

The system uses the value cb(t,T,S,X) as the basis for valuing a call option, and pb(t,T,S,X) for a put option with a zero bond as the underlying:

[figure TRM02-F150 - The system uses the value cb(t,T,S,X) as the basis for valuing a call option, and pb(t,T,S,X) for a put option with a zero bond as the underlying:]

[figure TRM02-F151 - where t = the horizon, T = the expiration date of the option, S = the end of the term of the underlying bond, NV = the nominal volume, X = the strike of the option, and F(x) = the cumulated normal distribution. The volatility sp is calculated from volatility parameter σ and reversion rate a]

where t = the horizon, T = the expiration date of the option, S = the end of the term of the underlying bond, NV = the nominal volume, X = the strike of the option, and F(x) = the cumulated normal distribution. The volatility sp is calculated from volatility parameter σ and reversion rate a

[figure TRM02-F152]

The following relationships also apply:

[figure TRM02-F153 - The following relationships also apply:]

[figure TRM02-F154]

[figure TRM02-F155]

[figure TRM02-F156 - where dM(t,T) is the discount factor from time point T to time point t, and fM is the short rate, which is defined as follows:]

.

where dM(t,T) is the discount factor from time point T to time point t, and fM is the short rate, which is defined as follows:

[figure TRM02-F157]

The system uses the following rule for the actual calculation:

[figure TRM02-F158 - The system uses the following rule for the actual calculation:]

[figure TRM02-F159]

where Xi is the strike at time point ti for cash flow CFi. The system uses the following relationships to calculate Xi. The first equation is solved iteratively for spot price R at time point T:

[figure TRM02-F160 - where Xi is the strike at time point ti for cash flow CFi. The system uses the following relationships to calculate Xi. The first equation is solved iteratively for spot price R at time point T:]

[figure TRM02-F161 - Trinomial Tree Method (Bermuda and American Interest Rate Options)]

Trinomial Tree Method (Bermuda and American Interest Rate Options)

The system generates a trinomial tree, which describes how the underlying may develop. The nodes (i, j) of the tree form a rightangled grid with the co-ordinates "time" and "interest rate". The evaluation date is the root node. All other nodes fill the time period from the evaluation date through to the end of the notification period for the last possible date on which the option can be exercised.

Each node has three secondary nodes, which, when compared with the primary node, represent a constant interest rate, a rising interest rate, or a falling interest rate. The system generates the trinomial tree so that it reproduces a valid yield curve in the evaluation. (This means that at any point in time, the weighted total of the interest rates on the nodes belonging to this time point is equal to the relevant interest rate in the yield curve when the node probability is used as the weighting.) The system stores the following figures on the nodes of the trinomial tree: Discounting factor, and the three transition probabilities from the primary node.

The system then calculates prices for the nodes of the trinomial tree. In doing so, it first discounts the cash flows that are after the exercise time point or, in the case of Bermuda options, the end of the notification period, to the last (in terms of dates) node. Then the prices for the previous nodes are calculated by discounting the prices of the subsequent nodes, and the cash flows that fall between the nodes. The end of the notification period and the exercise time point of a possible exercise date can be different. This means that the expected price for the future exercise date is also projected to the nodes. The system calculates the transition probabilities, discount factors, and the evaluation profile according to the Hull-White model as depicted in Brigo/Mercurio (2001) (Damiano Brigo und Fabio Mercurio: Interest Rate Models: Theory and Practice, New York 2001).

The algorithm used to generate the grid points in the trinomial tree recognizes that it is the number of grid points between the evaluation date and the end of the notification period that is critical for the calculation. The accuracy of the valuation hardly varies, regardless of whether you divide a term of 10 days into 10 intervals, or a term of three years into 10 intervals. The process in the system is as follows:

The system divides the period from the evaluation date to the end of the notification period into equal intervals. The system takes the default number of steps you defined in the valuation rule as the number of intervals. If you did not specify a default number of steps, the system takes 60 as the default number.

It repeats the first step for all the subsequent possible dates on which the option can be exercised, but continues using the prior grid points.

If the maximum time step, as defined in the valuation rule, is exceeded, the system adds more grid points. It does so by adding a grid point at the current point in the calculation so that the respective interval has the maximum time step. The system checks the length of the intervals only if you have defined a maximum time step in the valuation rule.


Therefore, the grid points of the trinomial tree are not always equidistant, and there can be more grid points than you defined in the valuation rule by specifying the default step number.

###### Calibration of the Hull-White Model

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Using the Hull-White Model to Price Options > Calibration of the Hull-White Model | L9 | trm02 p.136 | loio `8412da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8412da531198434de10000000a174cb4.html?locale=en-US)

**Use**

You use this function to calculate the volatility parameters of the Hull-White model from the current implied volatilities of the Black-Scholes model for swaptions or caplets.

You use this function if you want to use the Hull-White model to price interest rate options, and you have only the volatilities of the Black-Scholes model. Volatility values for the Black-Scholes model are provided by external sources such as Refinitiv or Bloomberg, and usually exist in the system. This is not normally the case for the volatility parameters of the Hull-White model.

The calibration of the Hull-White interest rate model is largely an optimization in which the system finds values for the Hull-White volatility parameters sigma σ and reversion rate a, in which the option prices, calculated using the Hull-White model or BlackScholes model, match as far as possible.

You have the following options for calibrating the Hull-White model:

Calibrating the model manually for a group of transactions

You call the calibration function manually using a separate transaction, or you can schedule the job in the Schedule Manager.

Using the price calculator to calibrate each transaction

If the central volatility database does not contain any Hull-White volatility parameters, the price calculator calls the calibration function automatically when it prices interest-rate options.

**Integration**

The calibration of the Hull-White model is used to prepare the data for valuation runs in Market Risk Analysis. The model is calibrated automatically in the price calculation immediately before a transaction is priced. You call the function for manual calibration independently of the valuation runs.

You can call the function for calibrating the model at any time manually in the (transaction RMHWCAL) or you can schedule the calibration in the Schedule Manager so that it takes place regularly. The name of the calibration program is RFTBB_HWCALIBRATION2.

**Note:**

The calibration process takes a relatively long time. In particular, the automatic calibration can lead to performance problems, as it is called for each transaction and each valuation method, and not for each potential exercise date. If the results of your analysis are to be exact to 5-10 percent of the NPV, then you should calibrate the model manually for a group of transactions. The system saves the Hull-White volatility values that are calculated to the database so that you can use these for multiple evaluations and transactions.

**Prerequisites**

In Customizing under Treasury and Risk Management Basic Functions Market Data Management Master Data Settings for Ref. Interest Rates and Yield Curves , you need to have already entered the settings for yield curves.

Since only current interest rates should be used to calibrate the Hull-White model, assign the read procedure Read back directly to the yield curve type.

In Customizing under Financial Supply Chain Management Treasury and Risk Management Basic Functions

Market Data Management Master Data Statistical Data Define Volatility Type , you need to have already defined a volatility type, and under Statistical Data Volatilities with Moneyness Master Data and Market Data for Volatilities

, you need to have stored values for the Black-Scholes volatility. For more information, see the document Central Volatility Database. We recommend that you create a separate volatility type for Hull-White volatility values.

Note the following properties of the calibration function:

In order to find the Hull-White volatility parameters σ and a , the system needs at least two Black-Scholes volatility values for different option terms and underlying terms.

You can calculate the volatility parameters σ and a for the Hull-White model from the Black-Scholes volatility values for swaptions or caplets. If you want to price swaptions and caplets using just the relevant values for swaptions and caplets, then you need to store the volatilities for the caplets and swaptions under a separate volatility type. You use the valuation rule to control how the volatilities are used. The reason for this is that the system cannot distinguish between the volatility values of swaptions and caplets without additional information.

The volatilities of swaptions and caplets are usually shown in a two-dimensional grid. You use the term of the option and the term of the underlying as the coordinates.

The following prerequisites apply for automatic calibration:

In Customizing for Treasury and Risk Management under Basic Analyzer Settings Valuation Define Valuation Rule , you have defined a valuation rule. Under Basic Analyzer Settings Valuation Define and Set Up Evaluation Types , you have assigned the volatility name for the implied Black-Scholes volatilities to the valuation rule.

You have defined an evaluation type, and assigned the volatility type for the implied Black-Scholes volatilities to it. You assign the volatility type to the evaluation type in the Interest Rate Volatility Types area. During the valuation process, the system usually interpolates the volatility values. The values are interpolated at different points on the level of the term of the option and the term of the underlying. If the standard setting is used, the system uses the nearest neighbor search to interpolate the values. However, we recommend that you use a smooth (at least linear) interpolation method. The interpolation is contained in a BAdI. You store your own implementation for this BAdI in Customizing for Treasury and Risk Management under Market Data Management Master Data Statistical Data Volatilities with Moneyness Define Interpolation of Volatilities .

**Note:**

To trigger the function for automatic calibration, define a Hull-White volatility type but do not assign it any volatility values. You assign this dummy Hull-White volatility type to the evaluation type in the Yield Curve Volatility Type area. In the valuation process, these settings prevent the system from using the volatility values already stored in the database.

**Features**

- 1. The system first selects the underlying yield curve, and the volatility values from the Black-Scholes model as grid points. The system proceeds as follows:


Calibrating the model manually for a group of transactions

The system selects only those values that actually exist in the central volatility database. It does not interpolate or extrapolate any volatility values.

You can use selection parameters to define how many volatility values or option prices the system uses as a basis for calibrating the Hull-White model.

Using the price calculator to calibrate each transaction

For Bermuda options, the system selects a Black-Scholes volatility value for each potential exercise date. If there is only one potential exercise date left, or the options to be priced are European or American, the system uses an additional grid point. This grid point is in the middle of the evaluation date and the maturity date of the option.

If required, the system interpolates the selected values.

- 2. The system uses the Black-Scholes model to calculate the option prices. It interprets the selected Black-Scholes volatility values as interest rate volatilities, and prices the swaptions and caplets accordingly as interest rate options, and not as bond options. The system uses the forward interest rate for the time span between the maturity of the option and the maturity of the underlying for the swap rate or cap rate.
- 3. The system optimizes these values using the Simplex method:

In the automatic calibration, the system takes the values σ=0.01 and a=0.1 as the starting values. In the manual calibration, you enter the values for σ and a , or the system uses historical values, which it reads from the central volatility database.

The system minimizes the following merit function:

[figure TRM02-F163]

where n is the number of option prices calculated by the Black-Scholes model, and σ is the associated implied volatility, which the system calculated from the selected option terms, underlying terms, and moneyness. V (σ,a) is the option prices calculated by the Hull-White model, σ (V (σ,a)) is the implied volatility of the BlackScholes model calculated from this value.

The system stops the calibration process when one of the following criterion is met:

- a. The maximum number of iteration steps is reached
- b. The values for χ and for the change in χ have not yet reached the maximum values


In the automatic calibration, the following values are predefined: χ=1.0, ∆χ=1*10 . The maximum number of iteration steps is 250.

- 4. If you call the manual calibration function for a group of transactions, if required the system saves on the database the volatility values σ and a that it calculated. The values it calculated for volatility parameters σ and a are annualized to 365 days. Unlike in the Black-Scholes model, the system saves the Hull-White volatility values as absolute values, and not as percentages. When these values are saved, the system uses the following key fields:


B/S,i

H/W,i B/S H/W, i

-8

|Field|Use for Hull-White Parameters|
|---|---|
|Validity date|Evaluation date|
|Volatility type|Volatility type that you used as a selection criterion|
|Term of the option|Largest value specified for the term of the option|
|Term of the underlying|Largest value specified for the entire term|
|Moneyness|Average of the specified strikes|


**Activities**

To use the function for calibrating the Hull-white model manually for a group of transactions, do the following:

- 1. In the area menu, choose Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Statistical Data Calibrate Hull-White Interest Rate Structure Model .

The system displays a selection screen.

- 2. Use selection criteria to define which Black-Scholes volatilities the system is to read from the database in order to calibrate the Hull-White model.


- 3. Decide whether the system is to use historical values as starting parameters for the calibration, and, if appropriate, enter the starting parameters for σ and a manually.
- 4. Decide whether the system is to use a fixed value for the sigma σ parameter or for reversion rate a during the calibration process, or whether these parameters should vary.
- 5. Define the criteria for ending the calibration process by specifying the maximum value for merit function χ, change in χ, and the number of iteration steps.
- 6. Decide whether the system is to start the calibration process as a test run, or whether it should save the results on the database.
- 7. Choose Execute.


The system displays a list of the parameters and the results of the calibration of the model.

If you did not start the calibration as a test run, the system saves the volatility parameters σ and a that were calculated to the central volatility database.

###### Using the Hull-White Model to Price Interest Rate Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Using the Hull-White Model to Price Interest Rate Options | L8 | trm02 p.140 | loio `121bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/121bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use the Hull-White model to price options on interest rate instruments. This model is based upon the assumption that the variance of the underlying is limited even for transactions with long terms. This is a realistic assumption where the underlying is an interest rate, which means that the Hull-White model is used in preference to the Black-Scholes model for pricing interest rate instruments.

**Integration**

In the SAP system, you can use either the Black-Scholes model or the Hull-White model to price European interest rate options. The Hull-White model is provided for the pricing of American-style interest rate options.

If you want to price interest rate options using the Hull-White model, then you specify this model in the Customizing for the valuation rule. You can also use the Black-Scholes model to price European swaptions as interest rate options.

**Prerequisites**

You need to have already created a valuation rule in which you defined that the Hull-White model is to be used as the valuation model. To define a valuation rule, in the Customizing for Risk Analysis choose Common Settings for Market Risk and ALM

Valuation Valuation Rule. To assign the valuation rule to an evaluation type, in the Customizing for Risk Analysis choose Common Settings for Market Risk and ALM Valuation Define Evaluation Type.

**Features**

The Hull-White model prices both European and American interest rate options. European-style options are priced using analytical formulas; American-style options are priced using the trinomial tree method. Since the calculation methods have been designed for OTC options on fixed-rate transactions, the system maps the underlying transactions to fixed-rate transactions before applying the calculation methods.

Preparation

The system first maps the underlying instruments to fixed-rate transactions. The following rules apply in this process:

All underlying instruments have to be created in the SAP system as long transactions. The initial cash flow resulting from the purchase of the instrument is negative; the cash flow resulting from the sale of the instrument on its maturity is positive.

The cash flows resulting from the initial purchase of the instrument, and the discounts and premiums, are not included in the valuation.

The price calculator needs the strike price as a price, and not as an interest rate. The strike price must be given as a clean price; when options are exercised in the time period between the start and the end of the fixed-rate period, accrued interest is not taken into account in the strike price. In the valuation process, the system converts the strike price from a clean price to a dirty price.

The underlying is handled as follows:

Fixed-rate transactions (all OTC transactions with fixed rates)

The cash flows are transferred as they are, and are not changed.

Bonds (all fixed-rate securities)

The cash flows are scaled to the amounts that flow when the option is exercised. The subscription ratio is used as the factor. (For example, for an option on ten bonds, the cash flows of the bonds are multiplied by ten).

Swaps

The system handles swaps as follows:

The floating side of the swap is removed; any spreads it contains are valued as fixed-rate payments, and these values are then used in the calculation.

Cash flows arising from the sale of the swap, and changes in the nominal value of the fixed side are used in the calculation. This also applies for cash flows that, strictly speaking, do not flow in reality.

In the case of payer swaptions, the plus/minus sign of all the cash flows of the basic instrument are reversed. The system converts the signs so that the underlying instrument is available for the step in which the transaction is valued as a long position. (In the case of a payer swaption, when the option is exercised the holder of the option pays the fixed-rate interest, and receives the floating part.)

In payer swaptions, the put/call indicator is set to put ; in receiver swaptions it is set to call .

If the exercise date is at the start of an interest period of the floating side, or falls within such a period, then the strike is set to the nominal amount of the current interest period of the floating side. Otherwise the nominal amount of the swap is taken as the strike price.

Caps and floors

If the underlying is a cap or a floor, the system prices the transaction as follows:

The cap is broken down into caplets, and the floor into floorlets.

If the interest period of the caplets and floorlets starts on or before the evaluation date, then the interest rate is already fixed. They are then priced by discounting the relevant cash flows.

Where this is not the case, the caplets and floorlets are priced as European options on a fixed-rate transaction. They have one interest period, and the interest rate is the same as the cap rate. In the case of a caplet, the put/call indicator is set to put ; for floorlets it is set to call .

The nominal amount is taken as the strike price.

Valuation

For more information about the pricing methods see Using the Hull-White Model to Price Options .

###### Caps (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Caps (OTC) | L8 | trm02 p.142 | loio `2d21dd5119c93a46e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2d21dd5119c93a46e10000000a44538d.html?locale=en-US)

**Use**

The market price calculator for caps calculates current market values as well as market/time values for a future date (horizon).

A cap contains a series of hedges to secure a particular reference interest rate R against an increase in the interest rate above a given value R (strike or cap rate). If the start of the term of the cap is before the horizon, the cap contains an existing fixed-rate transaction on the horizon. The value of the reference interest rate R is set at regular intervals of length t (for example, every six months). If the value of the reference interest rate R at time point k is above the highest interest rate R , the buyer of the cap receives the difference at time point (k + 1) .

k x

k

k t x t

The seller of the cap makes the following payment at time point (k+1) : t*NV*max(R -R ,0)

t k x

Notation:

R = Cap rate

x

NV = Nominal volume

Interest payments at time points: t, 2t, 3t,...,nt

If F is the forward rate for the period between k and (k+1) , and the interest rates R , R , and F are based on a compounding frequency t , then F can be taken as an approximation of the discount rate for the period between k and (k + 1) . Therefore, the payment made at time point (k+t) is the discounted difference from (k + 1) after k

k t t x k k k t t t t t

[figure TRM02-F164 - The advantage of this point of view is that it allows you to see every caplet as a European call on a t-periodic interest rate. The pay out is on the maturity of the option, though, and not a period later. The nominal value of the underlying for every option is:]

The advantage of this point of view is that it allows you to see every caplet as a European call on a t-periodic interest rate. The pay out is on the maturity of the option, though, and not a period later. The nominal value of the underlying for every option is:

[figure TRM02-F165]

**Integration**

To valuate a cap or a caplet, the transaction data - or, alternatively, a par coupon or zero coupon yield curve - must exist in the transaction currency for the evaluation date.

In addition, you need to specify a yield curve to calculate the forward rates F . If the start of the term of the cap is based on the evaluation date in the past, you have to specify the interest rate R of the fixing date for the current caplet. If this interest rate is not available, the value of the interest rate R is set at zero.

k f

f

You also need an interest volatility curve for the term of the option. The specified reference interest rate is the reference interest rate R used in the analysis.

k

The first step restricts the cap to those caplets that mature after the horizon.

Zero bond discounting factors are calculated from the yield curve of the transaction currency. These, along with zero interest rates, are used for determining the discounting factors at a later date. You can use the zero coupon calculation method for this.

In the first step, the spot is removed for each individual caplet. The spot is used later on in the option price formula. To calculate the spot, the forward calculator calculates the forward rate F of the agreed reference interest rate R . The run-up period is the time up to the start date of the individual caplet (or the term of the option).

k k

If the transaction currency differs from the display currency of the cap, the transaction currency is translated into the display currency using the currency rate at the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the evaluation date using the yield curves of the transaction and display currencies.

**Features**

The option price calculator for European options (applying either the Black Scholes formula or the normal distribution model) is called up for each caplet whose term begins after the horizon. It is called with the following parameters:

|Call/Put|Call|
|---|---|
|Term|Term up to the start of the caplet (same as the term of the respective option), given in days (start of the caplet - horizon).|


|Spot|Forward rate Fk|
|---|---|
|Strike|Cap rate Rx|
|Interest rate 1|0 (no forex option)|
|Interest rate 2|0|
|Volatility|Interest rate volatility of the reference interest rate R from the volatility curve with the term corresponding to that of the caplet. k|


The result is interest rate DI that is the difference between the reference interest rate R and the strike rate R . If this difference is less than 0, then 0 is used in all subsequent calculations. The rate is calculated on the due date of settlement payment (that is, at the end of the caplet).

k x

The net present value of a caplet (in the transaction currency) is the nominal volume multiplied by the interest rate difference DI, discounted from the due date of the settlement payment to the horizon:

NPV (caplet (i)) = K*t*NV*NPV(DI)

where

NPV (DI): Discounted interest rate difference

NV = Nominal volume

t = Compounding frequency

K = Call/put indicator

The NPV of the current caplet is calculated on the horizon (in the transaction currency). If the term of this caplet begins before the evaluation date, the interest difference (with zero as the floor), calculated from the given fixed rate of interest and the cap rate, is discounted to the horizon using the yield curve (according to the transaction currency of the current caplet). This value is then multiplied by the nominal volume NV and the compounding frequency t. If the beginning of the term of this caplet is after the evaluation date, the forward rate F is calculated from the agreed reference interest rate R using the forward calculator. The interest difference (with zero as the floor) from the calculated forward interest rate F and the cap rate is discounted to the horizon using the yield curve from the horizon (according to the transaction currency of the current caplet). This is then multiplied by the nominal volume NV and the compounding frequency t.

k k k

In addition to the formulas given already, the following are used:

If the start of the term of the caplet < the evaluation date:

NPV (caplet (current)) = K*t*NV*NPV(max(R —R ),0)

f x

If the start of the term of the caplet > the evaluation date:

NPV (caplet (current)) = K*t*NV*NPV(max(F —R ),0)

k x

The NPV of the cap is the sum of the NPVs of the individual caplets:

[figure TRM02-F166 - The NPV of the cap is the sum of the NPVs of the individual caplets:]

If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

###### Floors (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Floors (OTC) | L8 | trm02 p.145 | loio `3236dd5119c93a46e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3236dd5119c93a46e10000000a44538d.html?locale=en-US)

**Use**

The market price calculator for floors calculates current market values, time values, and future market values (the future point in time is the horizon).

A floor contains a series of hedges for securing a particular reference interest rate R against a fall in interest rates below a given value R (strike). If the start date of the term of the floor is before the horizon, the floor contains an existing fixed-rate transaction on the horizon The value of the reference interest rate R is set at regular intervals of length t (for example, every six months). If the value of the reference interest rate R at time point k is below the interest rate R , the buyer of the floor receives the difference at time point (k + 1) .

k x

k

k t x t

The seller of the floor makes the following payment at time point (k+1) : t*NV*max(R -R ,0)

t x k

Notation:

R = Floor rate

x

NV = Nominal volume

Interest payments at time points: t, 2t, 3t,...,nt

If F is the forward rate for the period between k and (k+1) , and the interest rates R , R , and F are based on a compounding frequency t , then F can be taken as an approximation of the discount rate for the period between k and (k + 1) . Therefore, the payment made at time point (k+t) is the discounted difference from (k + 1) after k

k t t x k k k t t t t t

[figure TRM02-F167]

The advantage of this point of view is that it allows you to see every floorlet as a European put on a t-periodic interest rate. The pay out is on the maturity of the option, though, and not a period later. The nominal value of the underlying for every option is:

[figure TRM02-F168 - The advantage of this point of view is that it allows you to see every floorlet as a European put on a t-periodic interest rate. The pay out is on the maturity of the option, though, and not a period later. The nominal value of the underlying for every option is:]

**Integration**

To valuate a floor or a floorlet, the transaction data - or, alternatively, a par coupon or zero coupon yield curve - must exist in the transaction currency for the evaluation date. In addition, you need to specify a yield curve for the calculation of the forward rates

F . If the start of the term of the floor is based on the evaluation date in the past, you have to specify the interest rate R of the fixing date for the current floorlet. If this interest rate is not available, the value of the interest rate is set at zero.

k f

You also need an interest volatility curve for the term of the option. The specified reference interest rate is the reference interest rate R used in the analysis.

k

The first step restricts the floor to those floorlets that mature after the horizon.

Zero bond discounting factors are calculated from the yield curve of the transaction currency. These, along with zero interest rates, are used for determining the discounting factors at a later date. You can use the zero coupon calculation method for this.

In the first step, the spot is removed for each individual floorlet. The spot is used later on in the option price formula. The forward calculator calculates the forward rate F of the agreed reference interest rate R . The run-up period is the time up to the start date of the individual floorlet (or the term of the option).

k k

If the transaction currency differs from the display currency of the floor, the transaction currency is translated into the display currency using the currency rate at the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the evaluation date using the yield curves of the transaction and display currencies.

**Features**

The option price calculator for European options (applying the Black-Scholes formula or the normal distribution model) is called up for each floorlet whose term begins after the horizon. It is called with the following parameters:

|Call/Put|Put|
|---|---|
|Term|Term up to the start of the floorlet (same as the term of the respective option), given in days (start of the floorlet - horizon).|
|Spot|Forward rate Fk|
|Strike|Floor rate Rx|
|Interest rate 1|0 (no forex option)|
|Interest rate 2|0|
|Volatility|Interest rate volatility of the reference interest rate R from the volatility curve with the term corresponding to that of the floorlet. k|


The following procedure is used to calculate the value of options:

The result is interest rate DI that is the difference between the reference interest rate R and the strike rate R . If this difference is less than 0, then 0 is used in all subsequent calculations. The rate is calculated on the due date of settlement payment (that is, at the end of the floorlet) and discounted to the horizon.

k x

The net present value of the floorlet (in the transaction currency) is the nominal volume (NV) multiplied by the interest rate difference DI and the compounding frequency t, discounted from the due date of the settlement payment to the horizon.

NPV (floorlet (i)) = K*t*NV*NPV(DI)

where

NPV (DI): Discounted interest rate difference

NV = Nominal volume

t = Compounding frequency

K = Call/put indicator

The NPV of the current floorlet is calculated on the horizon (in the transaction currency). If the term of this floorlet begins before the evaluation date, the interest difference (with zero as the floor), calculated from the given fixed rate of interest and the floor rate, is discounted to the horizon using the yield curve (according to the transaction currency of the current floorlet). This value is then multiplied by the nominal volume NV and the compounding frequency t. If the beginning of the term of this floorlet is after the evaluation date, the forward rate F is calculated from the agreed reference interest rate R using the forward calculator. The interest difference (with zero as the floor) from the calculated forward interest rate F and the floor rate is discounted to the horizon using the yield curve from the horizon (according to the transaction currency of the current floorlet). This is then multiplied by the nominal volume NV and the compounding frequency t.

k k k

In addition to the formulas given already, the following are used:

If the start of the term of the floorlet < the evaluation date:

NPV (floorlet (current)) = K*t*NV*NPV(max(R —R ),0)

x x

If the start of the term of the floorlet > the evaluation date:

NPV (floorlet (current)) = K*t*NV*NPV(max(R —F ),0)

x k

The NPV of the floor is the sum of the NPVs of the individual floorlets:

[figure TRM02-F169 - If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.]

If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

###### Stock Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Stock Options | L8 | trm02 p.147 | loio `5f1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5f1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for stock options calculates current market values, time values, and future market values (the future point in time is the horizon).

Options on stocks have two variants, call and put. Both the American and the European exercise possibilities are available. The buyer has the right to either buy (call) or sell (put) a stock on a particular date (when exercised according to European standards), or during a specified period (according to American standards), at an agreed-upon price (strike price).

When valuing an option, the theoretical price of the option on the horizon is determined. In addition to the forward price of the stock class from the horizon (spot rate), several other items go into the option formulae (Black-Scholes formula for European options, binomial tree for American). The other items are the strike price, the validity period, the risk-free interest rate on the horizon, and the price volatility of the stock. The calculation assumes 30 or 31 periods. The user needs to predetermine the price volatility of the stock.

As the future stock price on the horizon is not known, it has to be determined in terms of arbitrage. You want to have the stock as a position on the horizon. To achieve this, you can either use the price of the stock on the evaluation date and hold it until the horizon (and also the dividend payments), or you can call the stock on the horizon at the forward price. The latter allows you to invest an amount on the evaluation date, which gathers interest at the risk-free rate until the expiration date. Since both transactions have

the same value based on assumption of being free of arbitrage, the forward price is the one on the horizon. Our current release does not calculate the forward price. Instead it is easier to use the current price.

**Integration / Calculation Basis**

In order to value share options, you need the transaction data, and alternatively a par coupon or zero coupon yield curve in the transaction currency for the evaluation date.

For valuing options, you also need the relevant price volatility for the stock class, and the stock price.

The following input parameters are calculated, which later go into the option price formula:

Spot :

A spot is the valid price of a stock class in the transaction currency (in the current release this means the current price).

Volatility :

If a price volatility curve is available, then the volatility which goes into the option price formula is the one from the curve with a validity period the same as the one of the option.

Zero bond discounting factors are calculated from the yield curve of the transaction currency. These, along with zero interest rates, can potentially be used for determining risk-free interest rates at a later date.

You can use the zero coupon calculation method for this.

If the transaction currency differs from the display currency of the option, the transaction currency is changed into the display currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the evaluation date using the yield curves from the transaction and display currencies.

**Scope of Functions / Valuation**

The option price calculator for valuing European options and the one for valuing American ones (using the binomial tree) use the following parameters:

|Call/Put:|Call/Put|
|---|---|
|Term:|Term of the option in days (expiration date of the option to the horizon)|
|Spot:|See input parameters|
|Strike:|Agreed buy or sell price of the stock|
|Interest rate 1:|0 (no forex option)|
|Interest rate 2:|Risk-free interest rate on the horizon = zero interest rate of the interest yield curve on the horizon with a term equivalent to the option term. If the horizon is after the evaluation date, the option term is the time between the horizon and expiration date of the option.|
|Dividends:|None (in the current release, dividends are not accounted for)|
|Volatility:|Price volatility from the price volatility curve, with a term equivalent to the option term|


As a result, you get the simulated and standardized value of the option on the horizon (BW ). The NPV is then the calculated option price multiplied by the number of stocks (ST) the option is based on.

1

Along with the symbols given already, the following are also used:

NPV = KBWST

where:

|K:|Long/short indicator|
|---|---|


If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

###### Options on Bonds (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Options on Bonds (OTC) | L8 | trm02 p.149 | loio `8d1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8d1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for options on bonds calculates current market values, time values, and future market values (the future point in time is the horizon).

Options on bonds have two variants, call and put. At the moment, only the European type can be dealt with. The buyer can either buy (call) or sell (put) a bond on a particular date at an agreed-upon strike price (clean price of the bond in the issuing currency). Only options whose horizon is before the expiration date are valued.

In valuing the option, the NPV of the cash flow (interest and principal) from the underlying after the expiration date is calculated, is used to determine the theoretical price of the option on the expiration date. After deducting accrued interest, the theoretical clean price of the bond goes into the option price formula (Black-Scholes) as the spot, along with the strike price, term, risk free interest rate, and the price volatility. You can either enter the price volatility of the (forward) bond price yourself, or it can be calculated for

you using the duration and yield taken from the interest volatility.

**Integration / Calculation Basis**

In order to value bond options, you need the transaction data, and alternatively a par coupon or zero coupon yield curve in the transaction currency for the evaluation date. In addition to the yield curves necessary for discounting generated cash flows (see input parameters), it is possible that additional yield curves are needed to calculate forward interest rates for variable interest payments.

In addition, you need a price volatility curve for the bond in the underlying over the term of the option. If this is not available, you can use an interest volatility curve for the term of the option. The reference interest rate you give is the one closest to the reference interest rate in the yield curve, whose term most closely parallels that of the bond. For example, if the term of the fixed side of the swap is 4.25 years, the term for the reference interest rate in a yield curve has to be set to four years.

Depending on the calculation procedure, the following input parameters are calculated for later determining the risk free interest rate and the spot rate (both of which go into the price formula):

Zero coupon rates and zero bond discounting factors which are calculated using the zero and par coupon calculation methods.

If the underlying bond contains more than one currency when determining the spot rate, the currencies are converted into the call or put currency using the appropriate currency rates. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the horizon using the yield curve from the transaction currency on the evaluation date.

Spot

The spot is the NPV of the clean price (standardized to the nominal volume) of the bond on the expiration date of the option. Using the Treasury Management component, a cash flow is generated when a bond is created. The payment flow consists of principal and interest payments, which flow on particular dates, and are standardized to a nominal amount of 100,000. The amount of the interest payments is known for fixed interest rates. For variable interest rates, only the reference interest rate is known. It is calculated gradually using the forward calculator. For interest rate agreements whose fixed and variable interest rates are tied to formulae, the amount of the resulting interest rates is calculated using the calculated forward rates (possibly taking interest floors and caps into consideration). The extent of the resulting interest payments is also determined. On the one hand, payment flows are reduced by those cash flows whose due date is before the expiration date of the option. On the other hand, they are increased by the cash flows from the accrued interest, which is calculated using the accrued interest calculator. The cash flow from the accrued interest continues until the expiration date of the option. The NPV of the individual cash flows is calculated on the horizon according either to the par or zero coupon calculation methods. This is done using the yield curves, dependent on the transaction currency. It is the equivalent of the NPV of the individual cash flows first on the expiration date of the option, and again on the horizon. The value of the spot is the NPV of the sum of the cash flows, which have been changed into the transaction currency of the call or put price, using forward currency rates. The sum is standardized to the nominal volume of the bond

The following abbreviations/definitions are used:

|t i :|Expiration date of the cash flow|
|---|---|
|C i :|Cash flow at time point t i (including accrued interest payments)|
|BW(C i ):|Net present value on the horizon of the cash flow due on t i|
|W i :|Currency of cash flow C i|
|W k :|Currency of the call or put rate (issuing currency)|
|NV:|Nominal volume of the bond = 100,000|
|WK(W i ;W k ):|(Forward) currency rate (ask or bid) W i /W k on the horizon|
|NPV:|Market value|


[figure TRM02-F170 - Volatility]

Volatility

If a price volatility curve is available, then the volatility which goes into the option price formula is the one from the curve with a validity period the same as the one representative of the difference between the expiration date of the option and the horizon.

If no price volatility curve is available, the interest volatility is determined for the term according to the difference between the expiration date and horizon of the option (possibly linearly interpolated from the values of neighboring option terms). The price volatility calculator then converts it to a price volatility using the modified duration (based on the interest and principal payment flows from the bond after the expiration date of the option), and the forward zero yield. The yield is calculated from the given zero bond discounting factors and, is calculated for the remainder of the term of the bond (in relation to the expiration date of the option).

If the transaction currency differs from the display currency of the option (or the currency of the call or put sides), the transaction currency is changed into the display currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the horizon using the yield curves from the transaction and display currencies from the evaluation date.

**Scope of Functions / Valuation**

The option price calculator uses the following parameters (some of which are taken from the input parameters) when pricing European options (Black-Scholes formula):

|Call/Put:|Call/Put|
|---|---|
|Term:|Term of the option in days (expiration date of the option to the horizon)|
|Spot:|See input parameters|
|Strike:|Agreed call or put price of the security standardized to 1|
|Interest rate 1:|0 (no forex option)|
|Interest rate 2:|Risk-free interest rate = zero interest rate of the interest yield curve with a term equivalent to the option term.|
|Volatility:|See input parameters|


The difference (DZ) between the price of the bond and its call or put price on the expiration date of the option is standardized to the nominal volume of the bond, with a lower limit of zero. The NPV of the simulated DZ is then calculated.

The net present value of the interest option is the nominal volume (NV) multiplied by the interest difference DZ.

Along with the symbols given already, the following are also used:

[figure TRM02-F171 - where:]

where:

|K:|Call/put indicator|
|---|---|


If the display currency differs from the issuing currency (that is, the currency of the call or put price), the NPV is calculated using the forward currency rate.

###### Options on Indices (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Options on Indices (Listed) | L8 | trm02 p.151 | loio `531bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/531bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for index options calculates current market values, time values, and future market values (the future point in time is the horizon).

**Integration / Calculation Basis**

In order to value tradable options, you need the transaction data, and either a par coupon or zero coupon yield curve in the transaction currency for the evaluation date.

For valuing index options, you also need the corresponding index prices.

Zero bond discounting factors are needed to discount the cash flow. The zero and par coupon calculation methods can be used to define the zero bond discounting factors. For the par coupon calculation method, the rate valid for the validity term of the option is

taken from the par coupon yield curve on the evaluation date.

If the transaction currency differs from the display currency of the option, the transaction currency is changed into the display currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate (bid or ask price) is calculated for the evaluation date using the yield curves from the transaction and display currencies.

**Scope of Functions / Valuation**

The values of European options on indices are calculated with the Black-Scholes formula.

This uses the following parameters in the price formula:

Option strike price (dependent on quotation):

Option exchange rate (absolute value of the strike)

Spot rate of the underlying

Index volatility (for the term of the option)

Interest without risk (for the term of the option)

Using these input parameters, the option is valued through to the end of its term (exercise date).

###### Options on Futures (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Options on Futures (Listed) | L8 | trm02 p.152 | loio `591bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/591bda531198434de10000000a174cb4.html?locale=en-US)

**Caution:**

The market price calculator for options on futures is used only in conjunction with sensitivity analysis, and the value-at-risk approach in Risk Analysis.

Options on futures are priced in the same way as futures, since these are also handled by using a margin account. This means that only change risks are displayed for future-style options.

**Integration and calculation bases**

To price tradable options, the transaction data, or a par coupon or zero coupon yield curve, have to provided in the transaction currency and for the evaluation date.

The relevant market data for the underlying (such as index values for options in stock index futures) has to be provided for valuing the options on futures.

If the display currency and the transaction currency of the option are different, then the relevant exchange rate is required. If the horizon is after the evaluation date, and the transaction currency is different from the display currency, then a par coupon or zero coupon yield curve has to be provided in the display currency (bid or ask rates) in order to calculate a forward rate for the end of the term.

**Scope of functions and valuation**

The Black-Scholes model is used to price European options on futures.

The following parameters are used in the option price formula:

Strike of the option (depends upon the quotation type)

Spot of the underlying (corresponds to the future price)

- Securities price (for futures on fixed-rate securities)

- Forward rate (for futures on interest rates)

- Index price (for futures on indexes)


Volatility of the underlying of the option (for the term of the option)

- Volatility of the bond future (for futures on fixed-rate securities)

- Volatility of the forward rate (for futures on interest rates)

- Volatility of the index (for futures on indexes)


Dividends (for the products listed here, dividends are usually 0)

The system uses these input parameters to price the option to the horizon.

The premium for an option on a future is cleared in the same way as the underlying future contract. In accordance with the markto-market principle, options are settled daily (future style). This means that it is best to exercise the option on its maturity so that the option can be priced as a European option using the Black-Scholes model.

Since no option premium is paid when the option is purchased, the price of the future option has to be shown when the option matures.

The formula for pricing options on futures can be derived from the Black-Scholes formula for stock options, so that the stock price is replaced by the future price, and the short-term interest rate is set to zero. The short-term interest rate is irrelevant here because neither the underlying nor the option represents a capital commitment when a duplicate portfolio is generated.

Call = Future price x N(d1) – Strike x N(d2)

The rate is calculated based on the underlying as follows:

For options on an index future : Rate = number of contracts x index point value x future option

For options on an interest rate future : Rate = number of contacts x contract nominal / 100 x future option x M / 12 (M is the term of the underlying forward rate period in months).

For options on an bond future : Rate = number of contracts x contract nominal / 100 x future option

**Note:**

The exchange rate risk of futures is always displayed as zero. If the evaluation currency and the transaction currency of the future are different, then the transaction is subject to currency risk only on the maturity date, as this is the first point in time when foreign currency is exchanged in return for the underlying. The currency risk on the margin account is ignored, as the clearing accounts are not part of the system.

###### Currency Options / Currency Barrier Options (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Currency Options / Currency Barrier Options (OTC) | L8 | trm02 p.153 | loio `871bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/871bda531198434de10000000a174cb4.html?locale=en-US)

Use

The market price calculator for currency options / currency barrier options calculates current market values, time values, and future market values (the future point in time is the horizon).

A currency option is an option on a forward exchange transaction. There are both call and put options.

A currency barrier option is a currency option for which there is an additional condition known as a barrier. Currency barrier options also come in both the call and put variety. We distinguish between four main types of barrier option:

The "up & in" option, which means that a currency option becomes valid only when the currency rate in the underlying rises above a certain level (barrier).

The "up & out" option, which means that a currency option becomes invalid when the currency rate in the underlying rises above a certain level.

The "down & in" option, which means that a currency option becomes valid when the currency rate in the underlying falls below a certain level.

The "down & out" option, which means that a currency option becomes invalid when the currency rate in the underlying falls below a certain level.

Both the American and the European types of currency and currency barrier options can be created. The buyer has the right to exchange one currency for another at a price agreed upon earlier (with a currency barrier option, this assumes that the currency option is valid). The optional exchange takes place on a particular date (when exercised according to European standards), or during a specified period up to the expiration date (when exercised according to American standards). Only those currency and currency barrier options whose expiration date is after the horizon are valued.

**Integration / Calculation Basis (currency options only)**

To value a currency option, you need the transaction data and either a par coupon or zero coupon yield curve in the transaction currency (ask or bid rate) for the evaluation date.

You also need a currency volatility curve for the term of the option. The given currencies represent the two transaction currencies (currencies of the call and put sides of the underlying transactions).

The currency rates of both transaction currencies in relation to the display currency are needed. If the horizon comes after the evaluation date and the transaction currency differs from the display currency when calculating a forward currency rate on the horizon (currency of the put side of the underlying / display currency), a par or zero coupon yield curve structure will have to be

entered in the display currency.

**Specific Setting for NPV Calculation of Plain Vanilla FX Options**

In the evaluation type on the Evaluation Control tab, you can define whether the settlement or the termination flow of a plain vanilla FX option is used for the NPV calculation.

If you set the Consider Option Settlement Flow indicator, the system uses the settlement or the termination flow for the NPV calculation from the settlement or termination date onwards until the payment date.

In this case, you also need to make the following settings:

Set also the Select on Day of Cancellation/Settlement indicator in the evaluation type.

In the Customizing activity Assign Cash Flow Indicator to Flow Types, assign a cash flow indicator to the settlement flow. Do not set the flow as fictitious.

If you do not set this indicator, the system does not calculate an NPV for the FX option after the settlement or termination date.

**Scope of Functions / Valuation (currency options only)**

Depending on the type of option (American or European), the option price calculator uses the Black Scholes formula (for European options) or the binomial tree (for American options), along with the following values (some of which are taken from the input parameters):

|Field|Meaning|
|---|---|
|Call/Put|Call/Put|
|Term|Term of the option in days (expiration date of the option to the horizon)|
|Spot|Current currency rate or forward currency rate on the horizon of the two transaction currencies (currencies on the call and put sides of the underlying transaction)|
|Strike|Fixed currency rates of both transaction currencies in the underlying transaction of the option (currencies of the call and put sides of the underlying transaction)|
|Interest rate 1|Risk-free interest of the call side of the underlying transaction = zero interest rate of the given yield curve corresponding to the currency of the call side of the underlying transaction and the option term|
|Interest rate 2|Risk-free interest of the put side of the underlying transaction = zero interest rate of the given yield curve corresponding to the currency of the put side of the underlying transaction and the option term|
|Volatility|Currency volatility of both transaction currencies from a volatility curve with a term corresponding to the option term|


The future currency rate is modeled in the valuation. Currency options, like other types of option, are calculated using the option price formulas Black-Scholes for European options and the binomial tree (using 30 or 31 periods) for American options. These formulas require the strike price (the agreed upon exchange rate in the case of currency options), the spot rate (the current or forward exchange rate), the term of the option, and the volatility. In addition, currency options also require two risk-free interest rates (corresponding to the two transaction currencies).

The result calculated will be the NPV (on the horizon) of the currency difference (DZ) between the currency rate and the currency rate fixed in the underlying transaction on the exercise date of the option. This difference (DZ) is standardized to the nominal volume of the put side of the underlying transaction, and has a lower limit of zero.

The NPV of the currency option (in the currency of the put side of the underlying transaction) is the nominal volume (NV) of the put side of the underlying transaction multiplied by the currency difference (DZ).

[figure TRM02-F172 - Along with the symbols given already, the following are also used:]

Along with the symbols given already, the following are also used:

[figure TRM02-F173 - where:]

where:

|K:|Call/put indicator|
|---|---|


If the display currency differs from the put side of the underlying transaction of the currency option/currency barrier option, the NPV is calculated using the forward currency rate.

###### Equity Warrants (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Equity Warrants (OTC) | L8 | trm02 p.156 | loio `621bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/621bda531198434de10000000a174cb4.html?locale=en-US)

Equity warrants (OTC) can only be valued if they are entered as options (OTC). They are then valued similarly to options.

###### Swaptions (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Swaptions (OTC) | L8 | trm02 p.156 | loio `e0bfe451c3803a46e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e0bfe451c3803a46e10000000a44538d.html?locale=en-US)

**Use**

The market price calculator for swaptions calculates current market values, time values, and future market values (the future point in time is the horizon).

A swaption is an option on an interest swap with a purely fixed and a purely floating side, and is either a call option (buy) or put option (sell). The buyer can switch to a swap at a particular time. Swaptions are priced only if the maturity date is after the horizon.

To price a swaption, it must first be divided into two parts – a fixed-rate side, and a floating-rate side. Based on the settings in the evaluation type and the valuation rule, the system prices swaptions as follows:

As options on bonds when the Black-Scholes model is used

As options on bonds when the Hull-White model is used

As interest-rate options when the Black-Scholes model is used

As interest-rate options when the model for normally distributed interest rates is used

**Integration**

The following describes what happens when the Black-Scholes model is used to price swaptions as options on bonds.

To price a swaption, the transaction data - or, alternatively, a par coupon or zero coupon yield curve - must exist in the transaction currency for the evaluation date.

You also need an interest volatility curve for the term of the option. The reference interest rate you enter is the one corresponding to the reference interest rate in the yield curve whose term most closely parallels that of the fixed side of the swap. For example, if the term of the fixed side of the swap is 4.25 years, the term for the reference interest rate in a yield curve with annual grid points has to be set to four years.

Depending on the calculation procedure, the following input parameters are calculated for later determining the risk-free interest rate and the spot rate (both of which go into the price formula):

Zero coupon rates and zero bond discounting factors which are calculated using the zero and par coupon calculation methods.

Spot:

The spot is the NPV of the price (standardized to the nominal volume) of the fixed side of the swap on the expiration date of the option. Using the Treasury and Risk Management component, a cash flow is generated when the fixed side of the swap is created. The cash flow consists of interest and principal payments, which “flow” at particular points in time. Both the times and the amounts of the individual cash flows are known. The NPV of the individual cash flows is calculated on the horizon according to either the par or zero coupon calculation methods. This is done using the yield curves, dependent on the transaction currency of the fixed side of the swap. It is the equivalent of the NPV of the individual cash flows first on the expiration date of the option, and subsequently on the horizon. The value of the spot (in the transaction currency) is the absolute sum of the NPVs of the cash flows standardized to the nominal value of the swap.

The following definitions apply:

t: Maturity date of the cash flows

i

C: Cash flow at time t

i i

NPV(C): Net present value on the horizon of the cash flow due on t

i i

NV: Nominal volume of the swap

[figure TRM02-F174 - Volatility:]

Volatility:

The interest volatility is determined for the term, according to the difference between the expiration date and horizon of the option (if necessary linearly interpolated from the values of neighboring option terms). The price volatility calculator then converts it to a price volatility using the modified duration (based on the interest and principal payment flows from the fixed side of the swap), and the forward zero yield (calculated from the given zero bond discounting factors during the term of the swap), based on the following formula:

Price volatility = Forward rate * interest volatility * modified duration

Call/Put Indicator:

If the swap in the underlying of the swaption is a fixed interest recipient swap, the swaption can be viewed as a call on a fixed-interest bond corresponding to the fixed side of the swap. The "Call/Put" indicator is set to "Call". If the swap in the underlying of the swaption is a fixed interest payer swap, the swaption can be viewed as a put on a fixed-interest bond corresponding to the fixed side of the swap. The "Call/Put" indicator is set to "Put".

If the transaction currency differs from the display currency of the swap as an underlying, the transaction currency is translated into the display currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate (bid or ask price) is calculated for the evaluation date using the yield curves from the transaction and display currencies.

**Features**

The option price calculator uses the following parameters (some of which are taken from the input parameters) when pricing European options (Black-Scholes formula):

Call/Put: See input parameters

Term: Term of the option in days (expiration date of the option to the horizon)

Spot: See input parameters

Strike: 1 (the value of the swap standardized to the nominal volume from the floating side)

- Interest rate 1: 0 (no forex option)

- Interest rate 2: Risk-free interest rate = zero interest rate of the interest yield curve with a term equivalent to the option term.


Volatility: See input parameters

The price difference (DZ) between the standardized price of the fixed side of the swap and 1 (standardized price of the floating side of the swap) on the expiration date of the option is standardized to the nominal volume of the swap, with a lower limit of zero. The NPV of the simulated DZ is then calculated.

The net present value of the swaption is the nominal volume (NV) multiplied by the interest difference DZ.

In addition to the formulas given already, the following are used:

NPV=K*NV*DZ

where

K = Call/put indicator

If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

###### Valuation of Compound Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Valuation of Compound Options | L8 | trm02 p.159 | loio `bfd69c51d839270ae10000000a445394` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bfd69c51d839270ae10000000a445394.html?locale=en-US)

**Definition**

A compound option is an option on a currency option and can constitute the following:

Call on call

Call on put

Put on call

Put on put

**Use**

You can value compound options using the Market Risk Analyzer or transaction TPM60. Valuation is performed on the basis of the Geske and Rubinstein model. This model uses the formulas quoted below to value the compound options.

This model is relevant for European options. No separate valuation model is implemented in the system for valuing an American compound option or a compound option on an American option. Consequently, when compound options relate to American options, the system uses the same valuation model as for European options by way of an approximation.

**Structure**

The NPV of a compound option is calculated as follows for the different cases (call on call, call on put, put on call, and put on put):

[figure TRM02-F175 - The NPV of a compound option is calculated as follows for the different cases (call on call, call on put, put on call, and put on put):]

where

[figure TRM02-F176 - Legend]

Legend

|t1/t2|The times until the expiration dates of the compound option/underlying option, respectively|
|---|---|
|th|The time to horizon|
|r1/r2/rh|The risk-free interest rate for the time period t1/t2/th, respectively|
|q|The foreign risk-free interest rate for time t2|
|X1/X2|The strike prices of the compound option/underlying option, respectively|
|S|The spot of the underlying exchange rate|
|S*|The implied spot, that is, the spot for which the underlying option would have the value X1 at time t1|
|σ|The volatility of the underlying exchange rate|
|N|The univariate cumulative normal distribution function|
|M|The bivariate cumulative normal distribution function|


**More Information**

Options on Bonds (OTC)

Compound Option

###### Interest Rate Guarantees (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Interest Rate Guarantees (OTC) | L8 | trm02 p.160 | loio `75c6e451c3803a46e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/75c6e451c3803a46e10000000a44538d.html?locale=en-US)

**Use**

The market price calculator for interest rate guarantees (IRGs) calculates current market values, time values, and future market values (the future point in time is the horizon).

IRGs are options on forward rate agreements (FRAs) and come as either call or put. Both American and European exercise options are available. The buyer can set up an FRA at any time up to a particular date in the future (American), or on a specific date (European). If the horizon comes after the option term (or on the fixing date), there is no valuation of the IRG.

In valuing the IRG, the agreed fixed interest rate (R ) of the FRA serves as the strike for the option. The IRG is regarded as an option on a forward interest rate (R ), with the term and interest rate (R ) fixed in the FRA. The user enters the interest volatility.

f x f

IRGs of the European type are valued using the Black-Scholes formula or the normal distribution model. American IRGs are valued using the binomial tree (with 30 or 31 periods).

Underlying:

You can create an FRA in all of its forms and variations as an underlying. However, only "classic IRGs" can be valued, that is, those with an underlying FRA whose fixing date is before or on the expiration date of the option. The option always ends on the fixing date of the reference interest rate of the FRA.

**Integration**

To value an IRG, the transaction data - or, alternatively, a par coupon or zero coupon yield curve - must exist in the transaction currency for the evaluation date. In addition, you need a yield curve to calculate the forward rate. You also need an interest volatility curve for the term of the option. The specified reference interest rate is the reference interest rate R used in the analysis. Zero

x

bond discounting factors are calculated from the yield curve of the transaction currency. These, along with zero interest rates, can potentially be used for determining risk-free interest rates and discounting factors at a later date. You can use the zero coupon calculation method for this. The spot that later goes into the option price formula is also deleted. To do this, the forward calculator computes the forward rate for the agreed reference interest rate (R ) in the FRA of the underlying. . If the transaction currency differs from the display currency of the IRG, the transaction currency is changed into the display currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the evaluation date using the yield curves from the transaction and display currencies.

x

**Features**

Depending on the type of option (American or European), the option price calculator uses the Black Scholes formula or the normal distribution model (for European options) or the binomial tree (for American options), along with the following values (some of which are taken from the input parameters):

Call/Put: Call/Put

Term: Term of the option in days (expiration date of the option to the horizon)

Spot: See input parameters

Strike: Comparative interest rate fixed in the FRA of the underlying

- Interest rate 1: 0 (no forex option)

- Interest rate 2: Risk-free interest rate = zero interest rate of the interest yield curve with a term equivalent to the option term.


Volatility: Interest volatility of the forward interest rate R from the volatility curve with a term corresponding to the option term

x

NPV: Net present value

The calculated result is the simulated value of the NPV of the interest rate difference DZ (on the horizon) between the forward reference interest rate R of the FRA and the strike on the expiration date of the option. The NPV of the IRG is then the interest difference (DZ) multiplied by the term (LZ) of the reference interest rate R (given in years) and the nominal volume (NV).

x

x

In addition to the formulas given already, the following are used:

NPV=K*DZ/100*NV*LZ

where

- K: Call/Put indicator


If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

###### Digital Options (Hit-At-End Binary) (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Digital Options (Hit-At-End Binary) (OTC) | L8 | trm02 p.161 | loio `e81bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e81bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The price is calculated for European digital hit-at-end binary options. A digital option is a wager on an event that is characterized by the strike and the specification Up (=Call) or Down (=Put). When the option is exercised, a fixed amount known as the rebate is paid. A digital up 1.02 on the US dollar is a bet that the dollar will be at a higher rate than 1.02 EUR per dollar when the option is exercised. The exchange rate before or after the exercise date is irrelevant.

**Integration and Data Used as the Basis for the Calculation**

The price calculator for digital hit-at-end binary options is called up with the following parameters:

|Term:|Residual term of the option in days|
|---|---|
|Domrate:|Interest rate_1 in percentage|
|Forrate:|Interest rate_2 in percentage|
|Rebate:|Rebate|
|Rebate sign:|+/- sign of the rebate|
|Spot:|Spot amount|
|Strike:|Strike amount|
|Type of UL:|Category of the underlying|
|Vola:|Volatility|
|Put/Call:|Put or call option|


**Scope of Functions and Pricing**

If the expiration date of the option has been reached, then the intrinsic value of the option (rebate amount) is displayed.

If the value for the option term is positive, the option price is calculated as follows:

[figure TRM02-F177 - If the value for the option term is positive, the option price is calculated as follows:]

###### Digital Options (One Touch Binary) (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Digital Options (One Touch Binary) (OTC) | L8 | trm02 p.162 | loio `eb1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/eb1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The price is calculated for digital one touch binary options. A one touch digital pays a fixed amount, the rebate, as soon as the agreed price limit (barrier) has been reached. This can occur at any point in time during the term. This option type is always European, since premature exercising is not possible (the option pays automatically as soon as it is "in the money". This price calculator can also be used for calculating the rebate share of an out barrier option.

**Integration / Calculation Basis**

The price calculators for digital one touch binary options are called up with the following parameters.

Term: Remainder of the option term in days

Dom-rate: Interest rate 1 as a percentage

For-rate: Interest rate 2 as a percentage

Rebate

Rebate sign: +/- sign of the rebate amount

Spot

Barrier

Vola: Volatility

Up/Down: Upper/lower barrier indicator

**Scope of Functions / Valuation**

If the expiration date of the option is reached, the inner value of the option is displayed (the rebate amount).

If the option term has not expired, the price is calculated as follows:

[figure TRM02-F178 - If the option term has not expired, the price is calculated as follows:]

###### European Barrier Options (OTC)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > European Barrier Options (OTC) | L8 | trm02 p.163 | loio `ee1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ee1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

European barrier call and put options are valued using the Rubinstein process. Four circumstances can arise:

up&in

up&out

down&in

down&out

A rebate can also be paid. This is a fixed amount paid if the option cannot be exercised due to reaching or not reaching the barrier. For an up & out option, a fixed amount is paid as soon as the price reaches or exceeds the up & out point. For a down & in option, payment is made if the price does not reach the in-point during the term.

**Integration / Calculation Basis**

The price calculator for European barrier options is called up with the following parameters:

|Term:|Remainder of the option term in days|
|---|---|
|Dom-rate:|Interest rate 1 as a percentage|
|For-rate:|Interest rate 2 as a percentage|
|Rebate:|Rebate|
|Rebate sign:|+/- sign of the rebate|
|Spot:|Spot|
|Strike:|Strike|
|Barrier:|Barriers|
|Type UL:|Type of underlying|
|Vola:|Volatility|
|In/Out:|In/out type indicator|
|Up/Down:|Upper/lower barrier indicator|
|Put/Call:|Put/call option indicator|


**Scope of Functions / Valuation**

If the expiration date of the option is reached, the inner value of the option is displayed (the rebate amount).

If the option term has not expired, the price is calculated as follows:

lograte = log( 1 + opt_domestic_rate / 100)

logforeign = log( 1 + opt_foreign_rate / 100)

yearfrac = opt_days / 365

dom_disc = exp( lograte * -1 * yearfrac)

for_disc = exp( logforeign * -1 * yearfrac)

adjvola = opt_vola / 100

volaroot = adjvola * sqrt( yearfrac)

2 2

lambda = ( lograte - logforeign + ( adjvola / 2)) / adjvola )

eta = -1 for up-options

eta = 1 for down-options

phi = -1 for puts

phi = -1 for calls

N(x) = standard normal distribution of x

resign = + for positive rebates

- for negative rebates

The prices of the barrier options, depending on type, consist of a total of 6 addends.

- res1:

ex = phi * ( ( log( spot / strike ) / volaroot ) +

( lambda * volaroot))

ex2 = ex - ( phi * volaroot ).

- res1 = phi * spot * for_disc * N(ex) -

phi * strike * dom_disc * N(ex2).

res2:

ex = phi * ( ( log( spot / barrier ) / volaroot ) +

( lambda * volaroot))

ex2 = ex - ( phi * volaroot)

- res2 = phi * spot * for_disc * N(ex) -


- res3:


phi * strike * dom_disc * N(ex2)

2

yps = eta * ( ( log( barrier / spot / strike ) /

volaroot) + ( lambda * volaroot))

yps2 = yps - ( eta * volaroot)

- res3 = phi * spot * for_disc *


exp( log( barrier / spot) * 2 * lambda) * N(yps) -

phi * strike * dom_disc *

exp( log( barrier / spot) * ( 2 * lambda - 2)) * N(yps2)

- res4:


yps = eta * ( ( log( barrier / spot /

volaroot) + ( lambda * volaroot))

yps2 = yps - ( eta * volaroot)

res3 = phi * spot * for_disc *

exp( log( barrier / spot) * 2 * lambda) * N(yps) -

phi * strike * dom_disc *

exp( log( barrier / spot) * ( 2 * lambda - 2)) * N(yps2)

res5 (rebate addend for in-options):

ex1 = eta * ( ( log( spot / barrier) /

volaroot) + ( ( lambda - 1) * volaroot)).

yps1 = eta * ( ( log( barrier / spot) /

volaroot) + ( ( lambda - 1) * volaroot))

if resign = '-'

res5 = -1 * rebate * dom_disc * ( N(ex1) -

exp( log( barrier / spot) * ( 2 * lambda - 2)) * N(yps1))

else.

- res5 = rebate * dom_disc * ( N(ex1) -

exp( log( barrier / spot) * ( 2 * lambda - 2)) * N(yps1))

endif

- res6 (rebate addend for out-options):


This component is the same as a one touch option (see the documentation for one touch options).

Term > 0

For valuation you must differentiate between 24 constellations:

In - option

Up - option

Put ( Up&In Put )

Spot < Barrier

Strike >= Barrier

- Price = res1 - res2 + res4 + res5

Strike < Barrier

Price = res3 + res5

Spot > Barrier

Standard option, since already knocked in.

Call ( Up&In Call )

Spot < Barrier

Strike >= Barrier

- Price = res1 + res5

Strike < Barrier

- Price = res2 - res3 + res4 + res5


Spot > Barrier

Standard option, since already knocked in.

Down - option

Put ( Down&In Put )

Spot > Barrier

Strike >= Barrier

- Price = res2 - res3 + res4 + res5


Strike < Barrier

Price = res1 + res5

Spot < Barrier

Standard option, since already knocked in.

Call ( Down&In Call )

Spot > Barrier

Strike >= Barrier

- Price = res3 + res5


Strike < Barrier

- Price = res1 - res2 + res4 + res5

Spot < Barrier

Standard option, since already knocked in.

Out - option

Up - option

Put ( Up&Out Put )

Spot < Barrier

Strike >= Barrier

- Price = res2 - res4 + res6


Strike < Barrier

Price = res1 - res3 + res6

Spot > Barrier

Price = res6

Call ( Up&Out Call )

Spot < Barrier

Strike >= Barrier

Price = res6

Strike < Barrier

- Price = res1 - res2 + res3 - res4 + res6


Spot > Barrier

Price = res6

Down - option

Put ( Down&Out Put )

Spot > Barrier

Strike >= Barrier

- Price = res1 - res2 + res3 - res4 + res6

Strike < Barrier

Price = res6

Spot < Barrier

Price = res6

Call ( Down&Out Call )

Spot > Barrier

Strike >= Barrier

- Price = res1 - res3 + res6


Strike < Barrier

- Price = res2 - res4 + res6


Spot < Barrier

Price = res6

###### Double Barrier Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Double Barrier Options | L8 | trm02 p.169 | loio `ff1ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ff1ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

A double barrier option ceases to exist ( Knock-Out ) or comes into existence ( Knock-In ) if the price of the underlying reaches a lower barrier L or an upper barrier U before the option becomes due. The formulae below refer to the double-knock-out option only The price of a double-knock-in call is the same as the price of a portfolio from a bought standard call and a sold double-knock-out call, both having the same strike price and the same amount of the term remaining. The double-knock-in put can be constructed in the same way. Double-knock-out options are valued with the formula from Ikeda and Kunitomo (1992).

**Scope of Functions / Valuation**

The following applies in all subsequent cases:

- S = Current underlying price


X = Strike price


N(x) = Probability that a value occurs for a standard normal distribution

- q = Dividend yield as continuous interest
- r = Risk-free interest rate as continuous interest


- T = Remaining term in fractions of a year

L = Lower barrier

- U = Upper barrier


= Volatility of the underlying


n = Summed index

Call-up-and-out-down-and-out

The following is counted at option expiration T: c(S, U, L, T) = max(S-X, 0) if L < S < U for all points in time before T, otherwise 0.

[figure TRM02-F181]

where:

[figure TRM02-F182 - where:]

[figure TRM02-F183]

[figure TRM02-F184]

[figure TRM02-F185]

[figure TRM02-F186]

,

[figure TRM02-F187]

[figure TRM02-F188]

,

[figure TRM02-F189]



and specify the exponential growth constants for the lower (L) and upper (U) barriers, respectively. The SAP System uses only and .

[figure TRM02-F192]

[figure TRM02-F193 - Put-up-and-out-down-and-out]

Put-up-and-out-down-and-out

The following is counted at option expiration T: c(S, U, L, T) = max(S-X, 0) if L < S < U for all points in time before T, otherwise 0.

[figure TRM02-F194]

where:

[figure TRM02-F195]

[figure TRM02-F196]

[figure TRM02-F197]

[figure TRM02-F198]

[figure TRM02-F199]

,

[figure TRM02-F200]

[figure TRM02-F201]

,

[figure TRM02-F202]



and specify the exponential growth constants for the lower (L) and upper (U) barriers, respectively. The SAP System uses only and .

[figure TRM02-F205]

[figure TRM02-F206 - According to Ikeda and Kunitomo, it is sufficient to let the sum run from -5 to 5 for the call and put. The values are then sufficiently accurate.]

According to Ikeda and Kunitomo, it is sufficient to let the sum run from -5 to 5 for the call and put. The values are then sufficiently accurate.

###### Bermuda Options (2 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Bermuda Options | L8 | trm02 p.171 | loio `1e1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1e1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

A Bermuda option has predefined dates on which the option can be exercised. Before exercising an option, the holder of the option has to give prior notice. Each exercise opportunity has an exercise notice deadline, which is fixed and binding. For options with a European exercise type, the holder can give notice only at the end of the notification period. For options with an American exercise type, the holder can give notice at any time during the notification period (including the first day and the last day in the notification period). The lead time (the period between notice being given and the option being exercised) is fixed and is binding.

**Integration**

You create Bermuda options as generic transactions. For more information, see Bermuda Options.

**Prerequisites**

In the valuation rule, you need to have defined that the system applies the Hull-White model. To define a valuation rule, go to Customizing for Risk Analysis and choose Common Settings for Market Risk and ALM Valuation Valuation Rule . To assign

the valuation rule to an evaluation type, go to Customizing for Risk Analysis and choose Common Settings for Market Risk and ALM Valuation Define Evaluation Type .

**Features**

The price calculator uses a trinomial tree method to price Bermuda options. For more information, see Using the Hull-White Model to Price Options (section Trinomial Tree).

###### Basket Options and Average Spot Options

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Basket Options and Average Spot Options | L8 | trm02 p.172 | loio `061bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/061bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The price calculator uses one pricing model to price the following exotic options:

Basket Options (BO)

Basket options are options that usually have more than one underlying. The spot of a basket option is the total of the spots of the individual underlyings that make up the basket option. A basket option that has just one underlying is the same as a plain vanilla option.

Average Spot Options (ASpO)

Average spot options are options that have one underlying and whose value is based on an average, rather than on the current spot of the underlying. The average value is based on a time series; the spot of the underlying is fixed for each time point in this time series. The fixed spot values are totaled, and divided by the number of spot values. The calculation of the average in SAP's pricing model weights the spot values equally.

Average Spot Basket Options (ASpO)

Average spot basket options are options that usually have more than one underlying, and whose value is calculated as an average. The creation of average values is based on a time series; the spot of the underlying basket option is calculated for each time point in this time series. The resulting spot values are totaled, and divided by the number of spot values. The calculation of the average in SAP's pricing model weights the spot values equally.

Average spot options and basket options can be seen as variants of the average spot basket options. Therefore, it is possible to use the same pricing model for these three types of option. An average spot basket option with just one underlying is an average spot option. If only one date is entered in the calculation of the average value for an average spot basket option, then in this case the option can be treated as a basket option. If there is only one underlying and one date, the average spot basket option can be treated as a plain vanilla option in the calculation of the average.

**Caution:**

The price calculator can currently price only basket options and average spot options whose underlyings are foreign currency transactions.

The following constraints apply to the pricing model:

Calculation of the Discrete Average

The average is calculated only at certain specified time points.

Assumption of Equidistant Time Points in the Calculation of the Average

In the pricing process, the system has to calculate moments for the distribution of future spot values (in other words, spot values that are not fixed). To do this, the system has to assume that the time points used to calculate the average are

equidistant.

European Exercise Type

Since the option pricing is based on the Black-Scholes model, only European-style options can be priced.

Correlation options have components of basket options and average spot basket options. For information about how these options are priced, see the document Correlation Options.

**Integration**

You create average spot basket options, average spot options, and basket options as generic transactions. For more information, see the documents Basket Options and Average Spot Options in the bank transaction data documentation.

**Prerequisites**

To price average spot basket options, the system needs the correlations between the underlyings contained in the basket, as well as the usual market data. The correlation matrix must be positive semidefinite. You can use the statistics calculator to calculate correlations and adjust the correlation matrix if required so that it is positive semidefinite.

**Features**

The payment amount of an average spot basket option as a call option c or as a put option p is calculated as follows:

ASBO ASBO

[figure TRM02-F207 - The payment amount of an average spot basket option as a call option c or as a put option p is calculated as follows:]

where SP={t |1iN} is the number of time points used to calculate the average, M is the number of underlyings, X is the strike of the average spot basket option, and s (t ) is the spot of the jth underlying at time point t . The call option has a positive value, the put option has a negative value.

i

j i i

There is no explicit formula for the pricing of average spot basket options, average spot options, or basket options. SAP's pricing model is a more general version of the approximation method that Levy (1998) developed for average spot options. [see David F. DeRosa: Currency Derivatives. Pricing Theory, Exotic Options, and Hedging Applications, John Wiley & Sons: New York 1998]

The Levy approach is based on the principle that although the spot values s (t ) of average spot options are log normally distributed, this does not apply for their totals. However, it is assumed that the total of the spot values are distributed in a way that corresponds approximately to log normal distribution. Therefore, the system calculates the first two moments for the distribution of the total, and uses these as the moments of the approximation of log normal distribution. Then the system applies the BlackScholes formula for the actual pricing of the options.

j i

SAP's pricing model is a more general version of the Levy approach for average spot basket options. In particular, it considers the interrelationships between the two underlyings at different points in time. For average spot options, SAP's pricing model uses the Levy approach.

###### Correlation Options (2 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Correlation Options | L8 | trm02 p.173 | loio `1b1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1b1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

A correlation option comprises a basket option, plus a plain vanilla option for each underlying of the basket option. The long position of a correlation option contains a short position of a basket option and long positions of the plain vanilla options with an underlying. Alternatively, a correlation option can comprise an average spot basket option and its associated average spot options.

The nominal volumes of the options in the basket are the same as the nominal volumes of the individual options (in other words the plain vanilla options and the average spot options). The strike of the basket option is the same as the total of the strikes of the individual options. The other option parameters, such as the exercise type or the exercise date, are the same for all components of the correlation option.

**Integration**

You create correlation options as generic transactions. For more information, see Correlation Options.

**Prerequisites**

As for other transactions, the same valuation rule has to be used for all the components of a correlation option.

**Features**

The system calculates the value V (t) for a correlation option as the difference between the value of the portfolio of individual options and the value of the basket option:

correlation option

[figure TRM02-F208 - The system calculates the value V (t) for a correlation option as the difference between the value of the portfolio of individual options and the value of the basket option:]

where t is the horizon date and N is the number of options in the basket. This formula applies for both call and put options, and for correlation options that contain average spot options. For more information about pricing basket options, see Basket Options and Average Spot Options.

###### Forward Volatility Agreements

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Derivatives > Option Price Calculator > Forward Volatility Agreements | L8 | trm02 p.174 | loio `0f1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0f1bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

A forward volatility agreement is a forward transaction that is based on the volatility of an exchange rate. The forward volatility agreement is an agreement to buy or sell a straddle on a future date. A straddle is a combination of a call option and a put option that have the same underlying, exercise date and strike price. The term of the option starts on the forward date.

The strike of the straddle is fixed to the date on which the term of the options begins, and at the same time the forward spot is set for the exercise date of the straddle. The premium of the forward volatility agreement is also calculated and paid on the forward date. The forward volatility fixed at the start of the contract is taken as the basis.

**Integration**

You create forward volatility agreements as generic transactions. For more information see Creating Forward Volatility Agreements

.

**Features**

The amount paid for the forward volatility agreement is calculated as follows:

[figure TRM02-F209 - The amount paid for the forward volatility agreement is calculated as follows:]

where N is the nominal value of the forward volatility agreement, σ is the current volatility, σ is the agreed volatility, V is the value of the options.

fix straddle

The calculation rule is applied only if the horizon date is before or on the forward date. If the horizon date is after the forward date, the value of the forward volatility agreements is zero. The following formula provides the value v for a purchase of a straddle for the forward date: The sign (+/-) changes for a sale.

FVA

[figure TRM02-F210 - The calculation rule is applied only if the horizon date is before or on the forward date. If the horizon date is after the forward date, the value of the forward volatility agreements is zero. The following formula provides the value v for a purchase of a straddle for the forward date: The sign (+/-) changes for a sale.]

where s(t) is the

spot price of the underlying of the straddle, r(t ,t ) is the risk-free interest rate for the period t through to t , q(t ,t ) is the dividend rate for the period t through to t , σ is the volatility agreed on the contract date, σ(t,t ,T) is the forward volatility at time point t for the period t through to T , and N(x) is the cumulative normal distribution. Continuous compounding is used for interest rate r and dividend rate q ; yield curve r(t ,T) is used for forward rate r(t,T) , in which t is the evaluation date. The current forward volatility is calculated as follows:

1 2 1 2 1 2 1 2 fix F

F

E E

[figure TRM02-F211 - If the underlying of the straddle is an exchange rate, r is the risk-free interest rate for the local currency, and q the risk-free interest rate for the foreign currency. The spot value s(t) is the product of the amount in local currency, which is paid when the straddle matures, and the exchange rate valid on evaluation date t .]

If the underlying of the straddle is an exchange rate, r is the risk-free interest rate for the local currency, and q the risk-free interest rate for the foreign currency. The spot value s(t) is the product of the amount in local currency, which is paid when the straddle matures, and the exchange rate valid on evaluation date t .

E

The calculation rule uses the Black-Scholes formula for pricing options. This formula first prices the components of the straddle the call and put options - by using the forward interest rates and the current forward volatility. The values for the straddles are totaled and discounted, and the option premiums are deducted. This results in the calculation rule shown above for forward volatility agreements, in which the premium of the term is given by the fixed volatility σ .

fix

The calculation rule for forward volatility agreements applies where you use the same market data for the bid and ask rates. If this is not the case, the system uses a calculation rule that has separate premium calculation for the bid and ask rates.

Securities

###### Spot Stock Transactions (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Spot Stock Transactions (Listed) | L7 | trm02 p.175 | loio `931bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/931bda531198434de10000000a174cb4.html?locale=en-US)

Use

The market price calculator for spot stock transactions calculates current market values, time values, and future market values (the future point in time is the horizon).

Spot stock transactions involving stocks in the same class are bundled together and valued as positions for risk analysis.

**Integration / Calculation Basis**

When valuing a spot stock transaction, you need to have the transaction data and the stock price for the evaluation date.

If the horizon comes after the evaluation date, you need zero bond discounting factors in addition to the other input parameters for determining the forward stock price. Only the zero coupon calculation method is available for defining zero bond discounting factors.

If the transaction currency differs from the display currency of the stock position, the transaction currency is changed into the display currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate (bid or ask price) is calculated for the evaluation date using the yield curves from the transaction and display currencies.

To calculate the initial parameters you use the function module for the calculation of the zero bond discounting factors.

**Scope of Functions / Valuation**

The market value of a position on the evaluation date (horizon) is calculated by multiplying the number of stocks in the position by the stock price on the evaluation date (forward stock price on the horizon).

The following abbreviations/definitions are used:

|St:|Number of stocks to be bought or sold on the expiration date|
|---|---|
|AK:|Stock price on the evaluation date|
|ZW(AK):|Price on the evaluation date valid until the horizon (no interest accrual)|
|K:|Call/put-marker|
|NPV:|Net present value|


[figure TRM02-F212 - If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.]

If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

###### Subscription Rights (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Subscription Rights (Listed) | L7 | trm02 p.176 | loio `ae1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ae1bda531198434de10000000a174cb4.html?locale=en-US)

Subscription rights can only be valued if they are entered as stock. They are then valued similarly to spot stock transactions ( listed ) or forward stock transactions ( listed ).

###### Investments (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Investments (Listed) | L7 | trm02 p.176 | loio `a81bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a81bda531198434de10000000a174cb4.html?locale=en-US)

Investments can only be valued if they are entered as stock. They are then valued similarly to spot stock transactions ( listed ) or forward stock transactions ( listed ).

###### Investment Shares (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Investment Shares (Listed) | L7 | trm02 p.176 | loio `ab1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ab1bda531198434de10000000a174cb4.html?locale=en-US)

Investment shares can so far only be valued if they are entered as stock. They are then valued similarly to spot stock transactions (on the exchange) or forward stock transactions (on the exchange).

###### Participation Certificates (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Participation Certificates (Listed) | L7 | trm02 p.176 | loio `181bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/181bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for participation certificates calculates current market values, and market values or time values for a future point in time known as the horizon.

**Integration**

The market price calculator calculates the theoretical value of participation certificates in the same way as for bonds. Accrued interest is not taken into account, however. For more information see Bonds (Listed) .

**Prerequisites**

You create participation certificates in Transaction Manager as bonds for which the calculation of accrued interest is set to Trade Flat (no accrued interest).

To analyze participation certificates in Risk Analysis, you must not set the Calculate Accrued Interest indicator in the valuation rule.

**Features**

The system calculates the NPV of participation certificates as follows:

If a price is available, the participation certificate is treated as a stock.

If no price is available, the system calculates theoretical prices for the corresponding bond.

In both cases, accrued interest is not taken into account.

###### Bonds (Listed)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Bonds (Listed) | L7 | trm02 p.177 | loio `b41bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b41bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The market price calculator for bonds calculates current market values, time values, and future market values (the future point in time is the horizon).

Fixed interest bonds, zero bonds, and floaters can be established and valued as either standard or foreign currency bonds (with up to two foreign currencies: one for interest and another for principal payments). Both fixed and variable agreements can be created (for example fixed interest bonds; variable interest floaters). Interest rate agreements in which interest rates are linked formulae

can also be used to some extent. The formula must be in the form V 1*V 2+V 3*V 4 (where V i is a fixed or variable interest rate). You can also work with fixed or variable interest rate floors and caps. For valuation, the interest rates that go above or below the agreed interest rate limit are replaced with the values of that limit.

**Integration / Calculation Basis**

Depending on the Customizing settings, two types of valuation are possible for spot security transactions.

The NPV is the market price of the bond

The NPV is the theoretical price of the bond


The theoretical price of the bond is always used for valuing bonds in value-at-risk analyses.

Zero bond discounting factors are needed as further input parameters in order to discount the cash flow. The zero and par coupon calculation methods can be used to define the zero bond discounting factors.

If the transaction currency differs from the display currency of the bond, the transaction currency is changed into the display currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward

currency rate (bid or ask price) is calculated for the evaluation date using the yield curves from the transaction and display currencies.

**Business Calendar**

The system now calculates the time interval between the evaluation date and the date of the bond price in business days. Until now, calculations have been based on the time interval between the evaluation date and the date of the bond price in actual days, independent of any business calendar. This use of calendar logic enables you to determine the maximum age of the security price.

**Scope of Functions / Valuation**

For risk analysis, bonds are bundled together and valued as positions.

Security positions can be valued in two ways:

The NPV is the market price of the bond:

The NPV is calculated as the sum of the nominal volume of the security position multiplied by the current price of the bond, and the accrued interest up to the horizon. The exchange rate is used for conversions into the display currency.


The valuation of the market price of the bond can occur only under the following conditions:

Horizon = evaluation date

An exchange rate exists for the bond.

The price of the bond is not older than the maximum age specified in the evaluation type.

Valuation of the security using its cash flow is not activated. This is specified in the valuation rule settings for the evaluation type in securities control.

In all other cases, the NPV of the bond is calculated by using the theoretical price.

The following abbreviations/definitions are used:

|AK:|Current price of the security|
|---|---|
|NV:|Nominal volume of the security position|
|W(AK):|Currency of the current price of the security (issuing currency)|
|C:|Cash flow from the accrued interest|
|W(C):|Currency of cash flow C|
|AZ:|Display currency|
|WK(W(AK)/W(C) ; AZ):|Exchange rate W(AK)/AZ or W(C)/AZ on the horizon|
|K:|Long/short indicator|
|NPV:|Net present value|


[figure TRM02-F215 - The NPV is the theoretical price of the bond:]

The NPV is the theoretical price of the bond:

In the first step, the cash flow is reduced to those flows that have due dates later than the horizon. For security positions with variable interest rates, the forward reference interest rates are also calculated. For interest rate agreements whose fixed and

variable interest rates are tied to formulae, the amount of the resulting interest rates is calculated using the calculated forward rates (possibly taking interest floors and caps into consideration). The calculated interest payments are put into the cash flow, which only contains flows whose size and payment date are certain. The cash flows are then standardized according to the nominal volume of the security position. Depending on the method of calculation (par or zero coupon method), the NPV of the individual cash flows is calculated for the horizon, using the yield curve of the transaction currency. The value of the security position (in the display currency) is the NPV of the sum of the cash flows. These cash flows are standardized to the nominal volume of the position, and converted to the display currency using the appropriate (forward) exchange rate.

The following abbreviations/definitions are used:

|t i:|Expiration date of the cash flows|
|---|---|
|NV:|Nominal volume of the security position|
|C i:|Cash flow on date t i (with NV/100,000 standardized to the nominal volume)|
|BW(C i):|Net present value on the horizon of the cash flow C i due on t i|
|W i:|Currency of cash flow C i|
|WK(W i;AZ):|(Forward) currency rate (ask or bid) W i/AZ|
|K:|Long/short indicator|
|NPV:|Net present value|


[figure TRM02-F216]

###### Multicurrency Bonds

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Multicurrency Bonds | L7 | trm02 p.179 | loio `f31ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f31ada531198434de10000000a174cb4.html?locale=en-US)

Scope of Functions / Valuation

When calculating the net present value of the interest cash flow you must differentiate between four sets of circumstances for the determination of the interest amount:

|Interest amount|Exchange rate - nominal currency/cash|Exchange rate - nominal currency/cash|
|---|---|---|
| |flow currency - fixed|flow currency - variable|
|Interest rate fixed|The interest amount converted at the|The interest amount converted at the|
| |agreed exchange rate from the nominal|forward exchange rate valid on the cash|
| |amount currency to the cash flow currency|flow due date from the nominal amount|
| |is discounted in the cash flow currency on|currency to the cash flow currency is|
| |the horizon and then converted at the|discounted in the cash flow currency on the|
| |exchange rate valid on the horizon from the|horizon and then converted at the exchange|
| |cash flow currency to the evaluation|rate valid on the horizon from the cash flow|
| |currency.|currency to the evaluation currency.|


|Interest rate variable|The interest amount converted at the|The interest amount converted after|
|---|---|---|
| |agreed exchange rate after cancellation of|cancellation of the variable reference|
| |the variable reference interest rate from the|interest rate at the forward exchange rate|
| |nominal amount currency to the cash flow|valid on the cash flow due date from the|
| |currency is discounted in the cash flow|nominal amount currency to the cash flow|
| |currency on the horizon and then converted|currency is discounted in the cash flow|
| |at the exchange rate valid on the horizon|currency on the horizon and then converted|
| |from the cash flow currency to the|at the exchange rate valid on the horizon|
| |evaluation currency.|from the cash flow currency to the|
| | |evaluation currency.|

###### Bond Issues

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Bond Issues | L7 | trm02 p.180 | loio `151bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/151bda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The system prices bond issues in the same way as for positions of purchased securities, but it uses a minus sign instead.

**Integration**

You flag transactions as bond issues by saving the bonds in question in the liability securities account in Transaction Manager in SAP Treasury and Risk Management .

###### Asset-Backed Securities (ABS) + Mortgage-Backed Securities (MBS)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Asset-Backed Securities (ABS) + Mortgage-Backed Securities (MBS) | L7 | trm02 p.180 | loio `031cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/031cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

Asset-backed securities (ABS) result from the securitization of receivables, which the creditor (originator) sells in order to create liquidity. The creditor pools the receivables, and sells them to a trust set up for this purpose. The trust refinances the receivables by issuing tradable securities, which are backed by the receivables.

Mortgage-backed securities (MBS) are created in the same way, but the securitized assets are mortgage loans only. All other types of assets can be securitized in asset-backed securities.

**Prerequisites**

In order to price asset-backed securities and mortgage-backed securities, the system needs a yield curve and the repayment schedules or cash flows of the transaction. You create repayment plans in Transaction Manager of the SAP Treasury and Risk Management.

**Features**

To calculate the key figures for asset-backed securities and mortgage-backed securities, the price calculator uses the methods for bonds with repayment schedules.

###### Mapping Stocks to an Index

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Securities > Mapping Stocks to an Index | L7 | trm02 p.180 | loio `bf13da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bf13da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Mapping stocks to an index means aggregating more than one stock to an index. This index is then examined in risk analysis evaluations instead of individual stocks. The following two reasons explain the advantages of mapping stocks to an index.

- 1. In capital market theory, according to the Capital Asset Pricing Model (CAPM) the risk of each share can be split in to a systematic part (general risk) and an unsystematic part (specific risk). When setting up portfolios, you can eliminate the unsystematic part of the risk by the effects of diversification. However, the general risk remains. Only the beta factor is relevant as a measure of risk for an individual security in the portfolio. This is because it represents a fluctuation of the security relative to the market.
- 2. The ß-factor of a stock in relation to the market (= index) is calculated as follows:

[figure TRM02-F217]

- 3. When mapping stocks to an index, less market data is need for value at risk analysis . If mapping is not used, for a historical simulation using one historical time period of n days and one portfolio containing x stocks, you would need n times x stock prices. If you use mapping, for each stock you would need exactly one ß factor and n historical index positions, therefore x+n market parameters.


**Prerequisites**

You need to have carried out the following steps to enable the SAP System to display the risk of stocks mapped to an index:

- 1. Definition of the index
- 2. Assignment of individual classes to the index for the evaluation type you want to use
- 3. Creation of beta factors for the individual classes
- 4. Creation of the index position (for net present value analysis) and its history (for value at risk evaluations)
- 5. Only for value at risk evaluations: Inclusion of the index in the risk hierarchy as a risk factor


**Result**

The calculation of the risk of individual stocks takes place using the valuation of the index and of the retrograde calculation using beta factors.

**Example**

- Stock 1: 10 units in the portfolio, rate as at the day of evaluation EUR 80, beta factor 0.5
- Stock 2: 20 units in the portfolio, rate as at the day of evaluation EUR 120, beta factor 1.5


Index position at the date of evaluation EUR 2000

If mapping is not used:

|Stock 1|EUR 800 (EUR 10 X EUR 80)|
|---|---|
|Stock 2|EUR 2400 (EUR 20 X EUR 120)|


If mapping is used:

|Stock 1|EUR 500 (EUR 10 x EUR 200/2 x 0,5)|
|---|---|
|Stock 2|EUR 3000 (EUR 20 x EUR 200/2 x 1.5)|


**Special Features**

All single value analyses ignore mapping when calculating risk but still mark the individual risk items with the name of the index.

Note that in the case of sensitivity analyses and grid analysis , a risk analysis of mapped items only takes place when the index position of the risk factor changes. Changes to the individual stock prices have no effect.

You can store a simple mapping in the evaluation type for stocks that have not explicitly been assigned to an index in Customizing. Defined there is the index, and a standard beta factor that can be used for all stocks.

###### Trade Finance Transactions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Trade Finance Transactions | L6 | trm02 p.182 | loio `5747032d172749b9e10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5747032d172749b9e10000000a42189c.html?locale=en-US)

**Use**

Trade Finance transactions are Letter of Credits and Bank Guarantees.

The market price calculator for trade finance transactions calculates current market values and future market values (the future point in time is the horizon).

**Integration/Calculation Basis**

In order to value a trade finance transaction, the transaction data, and alternatively a par coupon or zero coupon yield curve in the transaction currency, has to be entered for the evaluation date.

The Transaction Manager generates a cash flow, when a trade finance transaction is created. The cash flow consists of principal payment, principal changes and - in case of the Letter of Credit - presentations.

Zero bond discounting factors are calculated from the yield curve framework in order to discount the cash flow.

If the transaction currency differs from the evaluation currency, the transaction currency is changed into the evaluation currency using the currency rate from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate is calculated for the evaluation date using the yield curves from the transaction and evaluation currencies.

**Scope of Functions/Valuation**

In the first step, the cash flow is reduced to those flows which have due dates later than the horizon. Depending on the method of calculation (par or zero coupon method), the NPV of the individual payments is calculated for the horizon, using the yield curve of the transaction currency. The value of the trade finance transaction (in the transaction currency) is the sum of the NPVs of the cash flows.

The following abbreviations/definitions are used:

|t i :|Expiration date of the cash flow (i = 1,..n)|
|---|---|
|C i :|Cash flow at time t i|
|BW(C i ):|Net present value on the horizon of the cash flow C i due on t i|


|NPV:|Net present value|
|---|---|


[figure TRM02-F218 - If the evaluation currency differs from the transaction currency, the NPV is calculated using the forward currency rate.]

If the evaluation currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

**Loans**

###### Loans

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Loans | L6 | trm01 p.179 | loio `a408374f7c8741be807b954f94fb511a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a408374f7c8741be807b954f94fb511a.html?locale=en-US)

Listed options and futures

OTC transactions (MM, TF, Forex, OTC Derivatives)

External Accounts

Exposure Items

By choosing one or more product groups, you can select the positions for these groups.

In addition to selecting the product groups, you can use the general selections to select the individual positions.

**Example**

When you select the product group Exposure Items the following area with exposure item specific selection criteria appears:

Exposure Items

Exposure Item ID

Exposure Subitem ID

Transaction Number

Hedging Relationship Number

This allows you to select exposure subitem data easily.

**Note:**

You can only select product groups for which the function can be used. If one of the product groups listed above is not available, the function cannot be used for this product group.

###### Loan Transactions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Loans > Loan Transactions | L7 | trm02 p.183 | loio `2f1bda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2f1bda531198434de10000000a174cb4.html?locale=en-US)

Use

The market price calculator for loan transactions calculates current market values, time values, and future market values (the future point in time is the horizon).

Both loans taken and loans given can be valued. Both fixed and variable interest rate agreements can be set up and valued. Principal repayment can be set up and valued using full payment at maturity, payment in installments, or annuity payments. Premiums and discounts can also be taken into account. A differentiation is also made between disbursed and non-disbursed loans.

**Integration / Calculation Basis**

In order to value a loan, the transaction data, or alternatively a par coupon or zero coupon yield curve in the transaction currency (ask or bid rate), has to be entered for the evaluation date. In addition to the yield curve structure needed for discounting generated cash flows (see initial parameters), it may be that a yield curve structure is also needed to calculate forward rates for variable interest payments.

With the help of the Treasury and Risk Management component, a cash flow is generated when a loan is created. The cash flow consists of interest and principal payments, which "flow" at particular points in time. The amount of the interest payments is known for fixed interest rates. For variable interest rates, only the reference interest rate is known. For disbursed loans, the cash flows are reported according to the Customizing settings and summarization rules.

Zero bond discounting factors are needed as further input parameters in order to discount the cash flow. The zero and par coupon calculation methods are available for defining zero bond discounting factors.

If the transaction currency differs from the display currency, the transaction currency is changed into the display currency using the currency rate (ask or bid rate) from the horizon. If the horizon is later than the evaluation date, the corresponding forward currency rate (bid or ask price) is calculated for the evaluation date using the yield curves from the transaction and display currencies.

**Scope of Functions / Valuation**

In the first step, the cash flow is reduced to those flows which have due dates later than the horizon. For loans with variable interest rates, a further step calculates the forward interest rates for the reference rates. The calculated interest payments are put into the cash flow, which only contains flows whose size and payment date are certain. Depending on the method of calculation (par or zero coupon method), the NPV of the individual payments is calculated for the horizon, using the yield curve of the transaction currency. The value of the loan (in the transaction currency) is the sum of the NPVs of the cash flows.

The following abbreviations/definitions are used:

|t i :|Expiration date of the cash flow (i = 1,..n)|
|---|---|
|C i :|Cash flow at time t i|
|BW(C i ):|Net present value on the horizon of the cash flow C i due on t i|
|NPV:|Net present value|


[figure TRM02-F219 - If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.]

If the display currency differs from the transaction currency, the NPV is calculated using the forward currency rate.

###### Net Present Value Calculations for Operating Exposures

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > Net Present Value Calculations for Operating Exposures | L6 | trm02 p.184 | loio `effb51f800ec444eb612e5ceb85ee23d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/effb51f800ec444eb612e5ceb85ee23d.html?locale=en-US)

**Use**

You can perform net present value calculations for raw exposures and exposure positions.

You can run value-at-risk analyses for operating exposures. By way of enhancement to the net present value analysis, the value-atrisk analysis takes into account the uncertainty of future market developments and also enables risks to be assessed consistently.

**Prerequisites**

Integration of Exposure Positions in Market Risk Analysis

**Features**

Foreign Exchange Exposures

The net present value of a foreign exchange exposure is calculated as follows:

NPV = foreign currency amount * DF

where

DF = discount factor resulting from the yield curve of the foreign currency. Discounting occurs from the due date to the horizon.

Within a foreign exchange exposure position, the individual partial amounts may be due on different dates (within the planning period). In such cases, the total NPV of the exposure position is calculated by adding together the individual NPVs on the different due dates.

###### NPV Calculation of Bank Accounts

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Price Calculator > NPV Calculation of Bank Accounts | L6 | trm02 p.184 | loio `fa9e146754b54b2c9b837edbfb660dd6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fa9e146754b54b2c9b837edbfb660dd6.html?locale=en-US)

The NPV of a bank account is the balance of a bank account at the key date or the latest available balance before the key date.

Depending of your settings for bank account balances in the evaluation type on the Evaluation Control 2 tab, the bank account balance is determined in the following ways:

Data source for bank account balance determination is One Exposure.

Data source for bank account balance determination are Bank Account Balances imported, manually entered, or uploaded from spreadsheet into Cash Management.

In this case, the latest available closing balance (of the chosen Cash Balance Type) for a date equal to or earlier than the key date is the NPV of the bank account. Therefore, the bank account balance is either the Ledger Balance, Value Date Balance, or the Available Balance.

For more information, about bank account balances, see also Manage Bank Account Balances.

**Related Information**

Define and Set Up Evaluation Types

###### Interface to External Price Calculators

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Interface to External Price Calculators | L5 | trm02 p.185 | loio `f61ada531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f61ada531198434de10000000a174cb4.html?locale=en-US)

**Use**

You can use an SAP interface to link external price calculators to the SAP System. This enables you to value transactions externally and then direct the valuation results back into the SAP System. You can do this in two different ways:

- Method A: Valuation is done using external price calculators based on market data (except for interest rates, basis spreads, and credit spreads) and transaction data provided by the SAP system.

- Method B: Valuation is done using external price calculators based on externally held market and/or transaction data. (These are referred to as fully external transactions)


The following can be identified as points in time, at which it is possible to branch to external functions:

- T1: Risk factor analysis

The external price calculator must inform the SAP System which market data or risk factors are needed for the valuation.

- T2: Valuation


Net present values and value at risk values are calculated by the external price calculator with the market data supplied by the SAP System.

**Prerequisites**

The RFC destination is defined in the SAP System. For more on this, see Displaying, maintaining and testing destinations. During the evaluation, the user has to check that the RFC server is running by checking the configuration of the relevant systems.

In order to externally value transactions in SAP (method A) you must activate external processing in the settings for the evaluation type. On the Control External Functions tab page you can also enter the RFC Destination and the RFC Function Name for both the external analysis and the external valuation.

###### Define and Set Up Evaluation Types

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Define and Set Up Evaluation Types | L5 | trm02 p.185 | loio `4149eeb39c10469698b19355e41dab60` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4149eeb39c10469698b19355e41dab60.html?locale=en-US)

Create evaluation types and change settings for existing evaluation types that are required for the calculation of the net present values of financial transactions/treasury positions.

**Context**

The settings in the evaluation types are required for the calculation of the net present value of financial transactions/treasury positions.

When you open the Calculate Net Present Values - With CVA and DVA, Calculate Market Risk Key Figures, Analyze NPV, and Sensitivity Key Figures - Single Analysis apps on the SAP Fiori Launchpad, you can choose an evaluation type.

Open the Define and Set Up Evaluation Types Customizing activity available in the Customizing of Treasury and Risk Management under Basic Analyzer Settings Valuation , and make the following settings:

Market Data Categories

On the Market Data Categories tab, you can assign yield curve types that you have defined under General Settings in the Define Yield Curve Types configuration activity.

When the net present values are calculated including CVA/DVA using the difference method, CVA/DVA is calculated as the difference between NPV and risk-free NPV. How these key figures are calculated depends on the settings made here in the evaluation type:

The risk-free NPV is calculated using the risk-free yield curve types without credit spreads. The (risk-based) NPV is calculated using the yield curve types, and can include credit spreads.

There are two ways of depicting credit risk:

Enter yield curve types containing a credit risk component in the Yield Curve Types area, and enter risk-free yield curves in the Risk-Free Yield Curve Types area. Do not use credit spreads.

Enter the same risk-free yield curves both for yield curve types and risk-free yield curve types. Use either parallel shift credit spreads or credit spread curves.

SAP recommends entering the same risk-free yield curve types both for yield curve types and risk-free yield curve types, and using credit spread curves by entering derivation IDs for them.

**Caution:**

To avoid credit risk effects being counted twice, do not use different yield curve types and credit spreads in parallel.

On the Market Data Categories tab, you also assign FX volatility types, exchange rate types, and basis spread curve types.

On the Market Data Categories tab, you can assign yield curve types that you have defined under General Settings in the Define Yield Curve Types configuration activity.

When the net present values are calculated including CVA/DVA using the difference method, CVA/DVA is calculated as the difference between NPV and risk-free NPV. How these key figures are calculated depends on the settings made here in the evaluation type:

The risk-free NPV is calculated using the risk-free yield curve types without credit spreads. The (risk-based) NPV is calculated using the yield curve types, and can include credit spreads.

There are two ways of depicting credit risk:

Enter yield curve types containing a credit risk component in the Yield Curve Types area, and enter risk-free yield curves in the Risk-Free Yield Curve Types area. Do not use credit spreads.

Enter the same risk-free yield curves both for yield curve types and risk-free yield curve types. Use either parallel shift credit spreads or credit spread curves.

SAP recommends entering the same risk-free yield curve types both for yield curve types and risk-free yield curve types, and using credit spread curves by entering derivation IDs for them.

**Caution:**

To avoid credit risk effects being counted twice, do not use different yield curve types and credit spreads in parallel.

On the Market Data Categories tab, you also assign FX volatility types, exchange rate types, and basis spread curve types.

Evaluation Control

Enter the security price type and the maximum age of price for securities.

In Risk Management, the securities price type controls the determination of securities rates from the SAP rate tables or the datafeed interface for valuation and price determination purposes.

Maximum number of days permitted between the evaluation date and the price date of the market data when market prices are used for the evaluation of a security

The system evaluates securities either using the market price or by calculating the theoretical price by discounting the cash flow of the transaction. The system first attempts the evaluation using market prices. You use the maximum age of the historical price to determine for how many days prior to the evaluation date the system should search for historical market prices. If no market prices are found within this time frame, the system calculates the theoretical price of the security.

The system interprets the number of days as calendar days.

Valuation Control

In this area, the following indicators are available:

Include Cash Flow on Horizon

This indicator controls whether payments on the date of the horizon are taken into account.

Accrued Interest Calc: Include Horizon

You use this indicator to control whether the date of the horizon is taken into account when accrued interest is calculated.

Select FX Netting Transactions

When transactions are rolled over or when forward exchange transactions are settled early, two new transactions are created in Treasury and Risk Management: a replacement transaction and an offsetting transaction.

You use this indicator to define whether the system includes the offsetting transactions in the valuation.

Select on Day of Cancellatn/Settlement

This indicator defines whether a canceled or settled transaction is selected and priced on the day on which it is canceled or settled.

Consider Option Settlement Flow

This indicator controls whether the settlement or the termination flow of a plain vanilla FX option is used for the NPV calculation.

If you set this indicator, the system uses the settlement or the termination flow for the NPV calculation from the settlement or termination date onwards until the payment date.

If you do not set this indicator, the system does not calculate an NPV for the FX option after the settlement or termination date.

Requirements

Set the Select on Day of Cancellation/Settlement indicator in the evaluation type.

In the Assign Cash Flow Indicator to Flow Types configuration activity, assign a cash flow indicator to the settlement flow. Do not set the flow as fictitious.

Calculate Intrinsic Value w. Spot Rate

The intrinsic value indicator is used to decide on the method used to calculate the intrinsic value of an option.

If the indicator is set:

Intrinsic value of call option = Max [(spot rate - strike), 0]

Intrinsic value of put option = Max [(strike - spot rate), 0]

If the indicator is not set:

Intrinsic value of call option = Max [(discount factor * (forward rate – strike )), 0]

Intrinsic value of put option = Max [(discount factor * (strike - forward rate)), 0]

Calculate YTM from Market Price NPV

This indicator controls whether a market price NPV is used for YTM calculation.

Securities and complex classes

With the default settings for YTM calculation, the theoretical NPV is used. If this indicator is set, the market price NPV is used for YTM calculations, provided that the NPV is calculated using the market price.

Spreads for Usage in Yield Curves

Basis Spread Curve Derivation

Basis Spread Curve Derivation for Evaluation Curves

This derivation ID controls how the system derives basis spread curves that are added to yield curves at runtime to form composite curves. It is relevant for yield curve types and basis spread curve types that are entered in the evaluation type/valuation rule and are used, for example, for discounting.

SAP delivers the derivation rule STD, which acts as follows:

Each discounting yield curve is adjusted against a curve with currency USD and a tenor of 3 months by adding suitable basis spread curves.

Use the following settings to adjust the yield curve used for discounting against the specified target currency / tenor using suitable basis spread curves.

Cross-Currency Adjustment for Discounting: Target Currency

Cross-Currency Adjustment for Disc.: Target Tenor (Term)

Cross-Currency Adjustmt for Disc.: Target Tenor (Time Unit)

Cross-Currency Adjustment for Discounting: Interm. Crcy

**Note:**

If no target currency / tenor is maintained by default USD with tenor 3 months is used.

If no intermediate currency is maintained, by default EUR is used.

Basis Spread Curve Derivation ID for Forward Curves

This derivation ID controls how the system derives basis spread curves that are added to yield curves at runtime to form composite curves. It is relevant for yield curve types that are entered as forward yield curve types in reference interest rate definitions, and for the basis spread curve types assigned to those yield curve types.

SAP delivers the derivation rule TENO, which acts as follows:

The tenor of the forward yield curve is compared against the tenor of the reference interest rate. If they differ, the system searches for a suitable tenor spread curve between the two tenors and adds it to (or subtracts it from, as appropriate) the forward yield curve.

Credit Spread Curve Derivation

Reference Entity Derivation for Business Partners

This derivation ID controls how the system derives reference entities representing the business partner involved in the transaction or position. On the basis of the credit spread curve structures of these reference entities, the system creates credit spread curves that are added to yield curves at runtime to form composite curves. It is relevant for yield curve types that are entered in the evaluation type/valuation rule and are used, for example, for discounting.

SAP delivers the standard derivation rule STD, which acts as follows:

In general, the system considers only reference entities for which the Use in Curve indicator is activated. The following search steps are performed:

- 1. For bond positions, the system searches for a reference entity using the security ID number. If a reference entity is found, it is used; otherwise, the search continues using the business partner.
- 2. The system searches for a reference entity using business partners (OTC deal counterparty or bond issuer) as follows:
- 3. If a BP hierarchy type is specified, the highest parent company in the hierarchy is determined; otherwise, the business partner itself is used.
- 4. The system searches for a reference entity using the business partner that has been determined in this way, and, if a reference entity is found, it is used.


5. If the system does not find a reference entity representing the business partner, the system searches for a substitute reference entity (for example, a reference entity that represents a rating) that is assigned to the partner.

Reference Entity Derivation for Your Own Companies

This derivation ID controls how the system derives reference entities representing one of your own company codes involved in the transaction or position. On the basis of the credit spread curve structures of these reference entities, the system creates credit spread curves that are added to yield curves at runtime to form composite curves. It is relevant for yield curve types that are entered in the evaluation type/valuation rule and are used, for example, for discounting.

SAP delivers the standard derivation rule STD, which acts as follows:

In general, the system considers only reference entities for which the Use in Curve indicator is activated. The following search steps are performed:

- 1. For bond positions, the system searches for a reference entity using the security ID number. If a reference entity is found, it is used; otherwise, the system continues the search using the company code.
- 2. Search for a reference entity using the company code:
- 3. The system searches for a reference entity that represents the company code of the transaction/position. If a reference entity is found, it is used. Otherwise, the system searches for a reference entity using the default company code specified in the evaluation type/valuation rule.


Own Default Company Code

Assign your default company code to the evaluation types considering credit spreads (such as Y002 Evaluation Type w. Credit Spr. and Y003Evaluation Type w. Bas&Crd Sp.) to influence how the system derives the reference entity for your own companies. The impact of this setting depends on the derivation ID selected for the reference entity derivation for your own companies.

The implementation of the delivered standard derivation ID STD for the derivation for your own companies considers the default company code as follows:

- 1. The system searches for a reference entity for the company code of the transaction/position
- 2. If the system could not find such a reference entity, it searches for a reference entity for the default company code.


Example

If there is just one credit spread curve for your company - independent of the particular company code - you can define one reference entity for one particular company code that you then enter as the default company code in the evaluation type/valuation rule.

Evaluation Control 2

Enter settings for the FX valuation on Evaluation Control 2 tab.

FX Valuation Method

The valuation method controls how the price calculators perform NPV calculations for financial transactions with future cash flows in different currencies, such as FX forwards.

Discounting Before Currency Conversion

If you select this option, cash flows are first discounted using the respective yield curves of the cash flow currencies, and then the system performs a currency translation into the evaluation currency using spot rates. This method is also referred to as the zero coupon method.

Currency Conversion Before Discounting

If you select this option, cash flows are first converted into the evaluation currency using forward rates and then discounted using the yield curve of the evaluation currency. This method is also referred to as the par method.

FX Fixing Details

This setting controls whether the fixing date and the settlement currency of a non-deliverable forward (NDF) are considered when performing the currency translation.

Ignore Fixing Date and Settlement Currency

The fixing date and the settlement currency are not considered by any FX conversion.

Consider Fixing Date and Settlement Currency

NPV Calculation

This setting is only relevant for NPV calculation if the valuation method for future FX cash flows is set to Currency Conversion Before Discounting. In this case, the cash flows are converted into the settlement currency using the forward rates at the fixing date and then discounted from the payment date using the yield curve of the settlement currency. Finally, the conversion to the evaluation currency is performed using the spot rate.

Volatility Smile Construction Method

The smile construction method controls how the system finds the volatility for an option with a given strike if the volatilities have a volatility type with moneyness definition Option Delta. The following settings are available:

Fixed Point Iteration

If you choose this setting, the system uses an iteration procedure to determine a consistent volatility/delta pair from the market data available. This method works best if market data is available in 5% delta intervals (that is, the moneyness is a multiple of 0.05).

Vanna-Volga Approximation

If you choose this setting, the system uses the Vanna-Volga method to calculate volatility approximately. This method requires the following three market data points:

25 delta call volatility, that is, a moneyness value of 0.25

At-the-money volatility, that is, a moneyness value of 0.5

25 delta put volatility, that is, a moneyness value of 0.75 or equivalently -0.25

Bank Account Balance

Data Source for Bank Account Balance

For determining the net present value of bank accounts, you must define from which data source you want the system to retrieve the bank account balance. The retrieved bank account balance is net present value of the bank account on the key date. You can choose between the following values:

One Exposure

Bank Account Balances

If you choose Bank Account Balances as data source, you must also choose the Cash Balance Type.

The system uses the latest available closing balance (of the chosen Cash Balance Type) as the net present values of the bank account on the key date.

Cash Balance Type

If you have chosen bank account balances as data source for bank account balance, you must also give the information, which balance type should be considered. You can choose between the following values:

Ledger Balance

Value Date Balance

Available Balance

For more information, about bank account balances, see also Manage Bank Account Balances.

**Procedure**

- 1. Choose an evaluation type in the structure on the left-hand side and double click on General Information.
- 2. Make the required changes.
- 3. Save your entries.

###### Yield Curve Framework

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework | L5 | trm02 p.192 | loio `a60b2251fa49fb50e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a60b2251fa49fb50e10000000a441470.html?locale=en-US)

**Use**

You use the Yield Curve Framework to define reference interest rates and enter their values. On the basis of the reference interest rates, you can create yield curves to help you determine mark-to-market net present values with the price calculator. They also enable you to create basis spreads and credit spreads for inclusion in calculations for the creation of basis spread curves and credit spread curves, which you can add to the yield curves and then make calculations on the basis of the combined curves (called "composite curves").

**Features**

Key Terms in the Yield Curve Framework

Reference Interest Rates

Yield Curves

Yield Curve Type

Creation of Yield Curves

Interpolation

###### Terms in the Yield Curve Framework

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Terms in the Yield Curve Framework | L6 | trm02 p.192 | loio `8d421453e0023047e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/8d421453e0023047e10000000a44538d.html?locale=en-US)

Here you get more details about terms used in the yield curve framework.

|Term|Definition|
|---|---|
|Reference Interest Rate|A value reference in the condition structure of an interestdependent financial transaction. Reference interest rates can be interbank rates on the international financial markets (such as €STR and EURIBOR). Reference interest rates form the grid points for yield curves. For more information, see also: Reference Interest Rates |
|Compounding Frequency|The compounding frequency determines how often interest is calculated.|
|Payment Frequency|The time interval between interest payments.|
|Interest Calculation Method|This method is a procedure for counting days in interest calculation. It is defined by the quotients taken from the daily method and the basic daily method. The daily method determines how the days for interest calculation are counted between two dates on the Gregorian calendar. The basic daily method determines how many days there is in a year for the purposes of interest calculation.|
|Yield Curve Type|A yield curve type contains one yield curve structure for each different currency. On the validity date, the yield curve structure generates a yield curve that serves as the basis for NPV calculation. You can assign any number of currencies to every yield curve type. The yield curve structures are based on the reference interest rates assigned. These reference rates are used to form the grid points for the currencies of the yield curve type. **Example:** A yield curve type covers a market segment such as the swap market or the bond market. A yield curve is used to determine the opportunity interest rate (such as for a product group like loans).|
|Yield Curve|A curve that is built from a record of reference interest rates for different terms. A yield curve is uniquely defined by its combination of the validity date, the yield curve date, and the currency.|
|Basis Spread|Basis spreads are premiums and discounts on one side of a basis swap that make the swap into a fair transaction. They can be used in the price calculator for the calculation of discount factors and forward interest rates. The spread relates to the first two reference interest rates assigned. **Example:** Cross-Currency Spread: Three-Month EURIBOR Versus Three-Month USD Libor, Five-Year Term The spread is the premium or discount on the EUR side.|


|Term|Definition|
|---|---|
| |Tenor Spread: Three-Month EURIBOR Versus Six-Month EURIBOR, Three-Year Term The spread is the premium or discount on the threemonth side.|
|Basis Spread ID|Key with which a basis spread is defined. This could relate to either a cross-currency spread or a tenor spread.|
|Basis Spread Curve Type|A basis spread curve type contains a basis spread curve structure for each combination of currency and tenor: A pair of tenors (like 3 months versus 6 months) for a given currency defines a tenor basis spread curve. A pair of currencies for a given tenor defines a crosscurrency basis spread curve. On the validity date, the basis spread curve structure generates a basis spread curve, which is combined with a yield curve during the NPV calculation. You can assign any number of currency/tenor pairs to every basis spread curve type The currency/tenor pair is defined on an abstract level. The concrete relationship to the quoted market data is defined by assigning the basis spread IDs to the grid points. The basis spread curve structures are based on the assigned basis spread IDs. The underlying reference rates assigned to these basis spread IDs need to fulfill the following requirements: Their currency needs to match the currency of the basis spread curve. Their time to maturity must be equal to the tenor of the basis spread curve.|
|Basis Spread Curve|A basis spread curve is the result, valid on a specific date, for a basis spread curve type for a concrete currency-tenor transition, which is combined with a yield curve during the NPV calculation. A basis spread curve does not exist on its own; it is only used in the context of the generation of a composite curve.|
|Credit Spread|A credit spread value always relates to a reference entity, a credit spread ID, a quotation type, and a rate date.|
|Credit Spread ID|Key with which a credit spread is defined. To be able to save market data for credit spreads, you additionally need to define reference units.|
|Reference Entity|The reference entity is the reference factor for a credit spread. **Example:** Examples of reference entities: Business partners ("reference debtor")|


|Term|Definition|
|---|---|
| |Company codes (for the storage of credit spreads belonging to your company) Security ID numbers Ratings|
|Credit Spread Value Structure|A credit spread curve structure defines the term structure of a credit spread curve. On the validity date, the credit spread curve structure, together with a reference entity, generates a credit spread curve, which is combined with a yield curve during the NPV calculation.|
|Credit Spread Curve|A credit spread curve is the result, valid on a specific date, for a credit spread curve type together with a reference entity that is combined with a yield curve during the NPV calculation. A credit spread curve does not exist on its own; it is only used in the context of the generation of a composite curve.|
|Composite Curve|A composite curve consists of exactly one yield curve and any number of spread curves. The properties of the yield curve determine the properties of the resulting composite curve. The yield curve framework allows you to define a set of basis spread curves that are added to the yield curve, both for forward yield curves and for yield curves that are assigned in the evaluation type/valuation rule. Further, it is possible to derive a credit spread curve for discounting.|

###### Reference Interest Rates

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Reference Interest Rates | L6 | trm02 p.195 | loio `933cff507cc38028e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/933cff507cc38028e10000000a44176d.html?locale=en-US)

A value reference in the condition structure of an interest-dependent financial transaction.

Reference interest rates can be interbank rates on the international financial markets (such as €STR and EURIBOR). Reference interest rates form the grid points for yield curves.

Reference interest rates form the grid points for yield curves.

They act as reference values in the condition structure of an interest-dependent financial transaction.

Interest conditions are used for the interest rate instrument on which the reference interest rate is based to describe when and how much interest is accrued. In this way, you influence the calculations that are made when building yield curves and determining forward interest rates.

The interest conditions that can be set for the reference interest have the following meaning:

Currency: Currency in which the underlying interest rate instrument is expressed.

Interest Calculation Method: Specifies the day count method and the method for calculating the number of days in a year.

Term/Time Unit: Specifies the term of the underlying interest rate instrument in the specified time unit.

Payment Frequency: Specifies the frequency with which interest payments are made. The payment frequency can be used to distinguish between par coupon and zero interest rates.

Compounding Frequency: Specifies the duration of the period during which interest is calculated. The following equation is used to calculate the interest on paid-in capital within a year:

[figure TRM02-F220 - m specifies the compounding frequency. For example, m=4 stands for quarterly compounding.]

m specifies the compounding frequency. For example, m=4 stands for quarterly compounding.

Calendar: The calendar that is selected here is used as the basis for the settings made in the fields "Number of Working Days" (in terms of interest determination) and "Shift Value Date to Working Day". If you have selected interest calculation method actW/252, the system uses this calendar to determine the public holidays on the basis of 252 working days per year.

Fixing Period: Specifies the duration in working days between the date of interest fixing and the start of the first interest period. Only positive values are considered; negative values are set to zero.

Shift Value Date to Working Day: Specifies the direction in which the payment date is shifted if it falls on a public holiday. After the shift, the payment date can fall either before or after the original date coinciding with a public holiday.

Maturity Dates at Month End: Dictates whether maturity dates are moved to the end of the month when the start of the interest term falls at the end of the month.

Forward Yield Curve Type: Yield curve type used to calculate the forward interest rates for the selected reference interest rate.

You can define reference interest rates using the Define Reference Interest Rates Customizing activity.

###### Yield Curves (2 of 2)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Yield Curves | L6 | trm02 p.196 | loio `67ae00518c19c557e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/67ae00518c19c557e10000000a44176d.html?locale=en-US)

**Use**

Yield curves are used to calculate net present values.

Before you can create yield curves, you first need to define yield curve types. From within the application, the required yield curve is calculated based on the settings made for the yield curve type, for the yield curve, and for the reference interest rates as well as on the basis of the current market data.

**More Information**

Yield Curve Type

Creation of Yield Curves

Interpolation

**Extrapolation**

Calculate Interest Rates from the Yield Curve Generated

###### Yield Curve Type

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Yield Curves > Yield Curve Type | L7 | trm02 p.196 | loio `b382b5516d77e75ee10000000a445394` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b382b5516d77e75ee10000000a445394.html?locale=en-US)

A yield curve type is the abstract description of a group of concrete curves. A yield curve type contains one yield curve structure for different currencies.

You define yield curve types using attributes that influence market data selection and properties such as payment frequency and

compounding frequency plus any number of currencies. As grid points on the curve, you assign reference interest rates to the currencies of the yield curve type. For this, you can only assign reference interest rates with a currency matching the selected currency.

On the validity date, the yield curve structure generates a yield curve that serves as the basis for NPV calculation.

**Structure**

Properties of the yield curve type that define how interest rates are calculated (see also: Calculate Interest Rates from the Yield Curve Generated):

Payment Frequency

Compounding Frequency

Quotation Type (for information purposes only)

Maximum Age

Property that defines the market data that can be used to create a concrete curve.

Extrapolation Method

Basis Spread Curve Type

This setting is relevant if a curve is used for forward calculations.

You achieve a concrete yield curve from the yield curve type by means of combining it with a currency.

At this level, you assign a calendar and an interest calculation method, the calculation procedure for the yield curve, the day count convention for interpolation, and the factory calendar for interpolation.

For more information, see also:

Calculation Procedures for yield curves

Day Count Convention for Interpolation

You then assign the reference interest rates that provide the market data as well as specify the time fence.

The yield curve attributes Underlying Term and Underlying Time Unit are used to find, for a specific basis spread curve type, suitable basis spread curves that can be combined with the yield curve for forward calculation.

Example

If you create a yield curve from swap records versus three-month EURIBOR, the underlying term of the yield curve is 3 and the period is Month.

###### Creation of Yield Curves

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Yield Curves > Creation of Yield Curves | L7 | trm02 p.197 | loio `adaf00518c19c557e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/adaf00518c19c557e10000000a44176d.html?locale=en-US)

You use this function to create yield curves. A yield curve is defined by the reference interest rates assigned to it. The system creates the yield curve using the market data that exists for the individual reference interest rates. More precisely, the system calculates discount factors on the grid points defined by the reference interest rates and zero rates that are constantly subject to interest calculation.

**Features**

[figure TRM02-F221 - Overview: Creating Yield Curves]

Overview: Creating Yield Curves

The system calculates discount factors using the bootstrapping method. This method ensures that the discount factors can be calculated from the available market data free of arbitrage. For this, the system performs the following steps:

- 1. Find market data


Search for interest rates for a specified date for all reference interest rates assigned to the yield curve. For this, the Direct Read-Back method is used, with specification of a maximum age:

Starting with the specified date, the system searches for the latest date in the past for which market data exists. This means that the system takes the specified date and then continues to set the read date to the proceeding date until it finds an interest rate for at least one of the reference interest rates assigned.

If the read date established in this way exceeds the maximum age (the read date is earlier than the date achieved by subtracting the maximum age from the specified date), the system behaves as if no market data were found. In such instances, the system does not create a yield curve.

If the read date established is not too far in the past, the system reads from the market data table the interest rates that exist for this date and for all reference interest rates assigned to the yield curve. It then uses the interest rates

found on the read date to build the yield curve for the specified date. This yield curve is then valid for the specified date.

**Note:**

You specify the permitted maximum age (in days) in the Customizing settings for the Market Data under Master Data Settings for Ref. Interest Rates and Yield Curves Define Yield Curve Types .


If the system does not find an interest rate for a reference interest rate that is marked as required, no yield curve is created.

- 2. Determining Payment Amounts and Payment Dates for the Assigned Reference Interest Rates


Using the interest conditions of the reference interest rates, the system calculates the payment amounts and payment dates of the individual reference interest rates for which market data was found:

Calculating the Start of the First Interest Period:

This date is achieved by adding the fixing period to the validity date. To determine the working days and public holidays, the system uses the calendar specified for the reference interest. If you have not specified a calendar, the system ignores the number of working days for the purpose of interest calculation: The start of the first interest period is in this case the same as the validity date. The start of the first interest period corresponds to the date on which capital was paid for the underlying interest rate instrument for the reference interest rate.

Calculating Payment Dates:

On the basis of the entries made for the Term/Time Unit and Payment Frequency fields for the reference interest, the system calculates the payment dates, from the start of the first interest period.

**Example:**

Term: 3 Years, Payment Frequency: Yearly, Start of First Interest Period: 17.5.2011

The system creates the payment dates 05/17/2012, 05/17/2013, 05/17/2014.

Depending on which setting you have made in Customizing for the Shift Value Date to Working Day indicator for the reference interest rate, the system moves the payment dates that were determined in the previous step to working days, based on the rule specified. The system applies the shifted payment dates in the following step.

Calculation of the quotients - resulting from the number of days divided by the name of days in the year - for each individual interest period of the reference interest rate, on the basis of the interest calculation method specified in Customizing for the reference interest rate. The payment date of the previous interest period is applied as the start date of each interest period (or, if the current interest period is the first interest period, the start date of that interest period is applied), and the payment date of the current interest period is applied as the end date of the interest period.

Calculation of the individual interest payments:

Multiplication of the interest rate found with the quotients calculated in the previous step by dividing the number of days by the number of days in the year. In the case of a zero interest rate with a term that is longer than a year, the interest share "C" of the repayment is achieved using the following equation:

[figure TRM02-F223 - Where R: zero interest rate, q: quotient resulting from the number of days divided by the number of days in the year.]

Where R: zero interest rate, q: quotient resulting from the number of days divided by the number of days in the year.

The system then sets as the date for the capital repayment the payment date of the last interest period.

- 3. Sorting the Market Data

The system sorts the interest rates found, ascending by term, and calculates the discount factors recursively in exactly the same sequence.

- 4. Calculation of Discount Factors

Together with the quoted interest rate, each reference interest rate implicitly provides a well-defined cash flow of n interest payments C (calculated in the step Determining Payment Amounts and Payment Dates for the Assigned Reference Interest Rates) including repayment of 100. The quoted interest rates are noted at par level, that is, the NPV of the cash flow of all future payments is the same as the outstanding debt of 100. To calculate the NPV, the system multiplies each individual payment (interest and capital repayment) with a discount factor d. You obtain the NPV equation (where d is usually equal to 1, d is not equal to 1 when the start date of the first interest period is not the same as the validity date):

[figure TRM02-F224]

.

The system now benefits from the fact that the yield curve has already been created up until event T and that, consequently, the discount factors d through d of the payment date T through T are already known. The discount factors are deemed to be known if they have previously been calculated or can be obtained using interpolation (yield curve framework). To calculate d , the above equation is activated towards d , as the following equation shows:

[figure TRM02-F225]

In this way, you obtain discount factors for all terms determined by the reference interest rates. This approach is known as bootstrapping.

- 5. Calculating Discount Factors for Zero Interest Rates with a Term Exceeding a Year

In the case of zero interest years with a term exceeding a year, the system calculates the discount factors differently to the above method. Instead, it uses the equation depicted below:

[figure TRM02-F226]

.

For zero interest rates with a term exceeding a year, this approach assumes a compounding frequency of one year.

- 6. Calculation of the Discount Factor d


i

i 0 0

n-1 0 n-1 0 n-1

n n

0

If the payment date T for discount factor d already falls after all payment dates (grid points) that were previously created in the yield curve, the system assumes that the continuous compounding zero interest rates are the same between the last available grid point and T and between T and the first interest payment date. As a grid point, the validity date on which the discount factor is always equal to 1 implicitly also applies to the yield curve.

0 0

0 0

If, however, a grid point with a longer term exists, the system interpolates d .

0

**Example:**

The reference interest rate with the shortest term in the yield curve has a term of one month, the payment frequency is monthly, and the start date of the interest period is two working days after interest fixing (after the validity date of the interest rate).

In this case, the system assumes that the continuous compounding zero interest rates between the validity date of the yield curve and the validity date of the interest rate, on the one hand, and the start date of the interest period and the end date of the interest period on the other hand are the same. Using this assumption, the system can calculate d0.

- 7. Filling Swap Gaps


Filling Swap Gaps by Interpolating Par Interest Rates

It is not always the case that all discount factors d through d are already known to the system. If, for example, reference interest rates for one-, two-, three-, four-, five-, seven-, and ten-year terms are assigned to a yield curve, there are missing grid points (the swap gaps) for six, eight, and nine years so that the system can use the abovecited equation. For example, for determining d , discount factor d is missing. The system cannot yet perform an extrapolation to determine d because this is only possible for a yield curve that has been created completely. For this reason, the system must use a different method to fill these gaps. The system uses linear interpolation. To calculate the interest rate for six years, the system interpolates the par rates of the reference interest rates with the terms of five and seven years, using linear interpolation and to the exact day, as shown in the following equation:

0 n-1

7 6 6

[figure TRM02-F227 - In this example, it is assumed that there is an interest payment once a year for all interest rates.]

In this example, it is assumed that there is an interest payment once a year for all interest rates.

For the terms T of the relevant reference interest rates, the quotient of the actual number of days divided by 365 is used. This interpolation of par interest rates occurs exclusively during the creation of the yield curve for the purpose of filling the swap gaps. When the yield curve has been created completely, however, the system interpolates using the method described in the section "Interpolation". If the interest conditions are different in the case of two reference interest rates that follow on from each other, whereby the interest calculation methods for R and R , for example, differ, the system calculates, at point in time T , an interest rate noted at par level in the interest calculation method for R , and deploys this interest rate in the above formula. For more information about calculating interest rates, see Calculate Interest Rates from the Yield Curve Generated. For the system to be able to apply the above formula, the interest conditions of the relevant interest rates must be identical (but the terms may differ).

i

5 7 5

7

After filling the gaps, the system calculates the missing discount factors (see Calculation of Discount Factors). Once all discount factors have been calculated up until the grid point with the longest term, the yield curve is complete.

Fill swap gaps by interpolation of zero interest rates (Customizing: Linear Interpolation of Zero Interest Rates (also for swap gaps))

Here, the system does not calculate additional grid points as in the Linear Interpolation of Continuously Compounded Zero Rates method. Instead, it linearly interpolates the zero interest rate of the previously calculated grid point and the unknown zero interest rate for the grid point that is to be entered, and uses these to calculate the net present values of interest payments to the swap gaps. Since the comparison that occurs cannot be solved algebraically, the system uses Newton's iteration. That way, no more additional grid points are displayed in the yield curve for the swap gaps. In the following example, the yield curve is created for a term of five years. The next grid point to be entered is that for seven years. The system calculates net present value PV for the grid point to be entered using the equation depicted in the figure below:

[figure TRM02-F228]

Discount factors d and d are unknown. The figures below illustrate the discount factors d and d :

6 7 6 7

[figure TRM02-F229 - Discount factors d and d are unknown. The figures below illustrate the discount factors d and d :]

[figure TRM02-F230 - These discount factors have the correct value if the equation illustrated in the figure below is satisfied:]

These discount factors have the correct value if the equation illustrated in the figure below is satisfied:

[figure TRM02-F231 - The system uses Newton's iteration method to solve the equation as follows:]

The system uses Newton's iteration method to solve the equation as follows:

For the NPV equation above the system represents zero interest rate Z fur 6 for six years as a linear interpolation of zero interest rate Z (already known) and Z (unknown), as the figure below illustrates:

6 5 7

[figure TRM02-F232 - For the NPV equation above the system represents zero interest rate Z fur 6 for six years as a linear interpolation of zero interest rate Z (already known) and Z (unknown), as the figure below illustrates:]

Terms T are - both here and above - the actual number of days divided by 365. This means that zero interest rate Z Z7 is now the only unknown variable needed for the calculation of discount factors d and d for the above NPV equation.

i 7 6 7

The system runs Newton's iteration method with the above NPV equation for unknown zero interest rate Z . It selects a starting value for zero interest rate Z and changes it using iteration steps until the value found for Z satisfies the equation illustrated in the figure below:

7 7

7

[figure TRM02-F233 - Then the system calculates discount factor d and inserts it together with Z , the grid point for seven years, in the yield curve. It is not necessary to insert a grid point for six years here because zero interest rate Z for 6 years is calculated using linear interpolation between Z and Z .]

Then the system calculates discount factor d and inserts it together with Z , the grid point for seven years, in the yield curve. It is not necessary to insert a grid point for six years here because zero interest rate Z for 6 years is calculated using linear interpolation between Z and Z .

7 7

6 5 7

###### Interpolation (Yield Curve Framework)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Yield Curves > Creation of Yield Curves > Interpolation (Yield Curve Framework) | L8 | trm02 p.202 | loio `d738ff507cc38028e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d738ff507cc38028e10000000a44176d.html?locale=en-US)

**Use**

The system uses this function to interpolate interest rates for terms that have not been created in the system.

**Features**

Using the discount factors d calculated along the grid points during the creation of the yield curve, the system calculates zero interest rates Z with continuous interest calculation (continuous compounding zero) by activating the following equation towards Z:

CC

[figure TRM02-F234 - The term T is always portrayed in the ACT/365 format and measured between the validity date of the yield curve and payment date.]

The term T is always portrayed in the ACT/365 format and measured between the validity date of the yield curve and payment date.

For the interest rates in this portrayal, the system performs linear interpolation to the exact day, that is, the interpolated continuous compounding zero rate Z is achieved using the following equation:

X

[figure TRM02-F235]

The system calculates the discount factor d using the following equation:

X

[figure TRM02-F236 - The system calculates the discount factor d using the following equation:]

[figure TRM02-F237 - Extrapolation]

**Extrapolation**

**Use**

The system performs an extrapolation on the completed yield curve if an interest rate or discount factor is requested for a term that is greater than the longest term of all grid points of the yield curve.

**Features**

In the Customizing settings for the yield curve, you can choose between the following methods:

- 1. Keep Continuously Interest-Bearing Zero Rate Constant

It is assumed that the continuously interest-bearing zero rate for all terms in the extrapolation area is the same as the last available continuously interest-bearing zero rate in the yield curve.

For this, the following equation is applied:

[figure TRM02-F238]

- 2. Keep Par Interest Rate Constant

It is assumed that the last available par interest rate in the yield curve, once converted into the continuous interest-bearing portrayal, is the same as the continuously interest-bearing forward interest rate in the entire extrapolation area. This achieves almost constant par interest rates for terms in the extrapolation area. However, using this option does not mean that the par interest rates in the extrapolation area are exactly the same as the par interest rate on the last grid point. The system performs the following calculations:

Calculation of the par interest rate for the last yield curve grid point based on the conditions set for the yield curve (for more information, see Calculate Interest Rates from the Yield Curve Generated).

Conversion of the par interest rate P into a continuously interest-bearing portrayal (m = number of interest payments per year) and calculation of the factor F, as portrayed in the following graphic:

[figure TRM02-F239]

Calculation of the discount factor d(T), as portrayed in the following graphic:

[figure TRM02-F240]

Calculation of the continuously interest-bearing zero interest rate, as portrayed in the following graphic:

[figure TRM02-F241]

- 3. Keep Continuously Interest-Bearing Forward Rate Constant


**Note:**

If you have selected the payment frequency Zero Interest Rate: One Interest Payment at End of Term in the Customizing settings for the yield curve, the system nevertheless assumes a payment frequency of one year for the par interest rate to remain constant.

The system assumes that the continuously interest-bearing forward rate on the last grid point of the yield curve is the same as the continuously interest-bearing forward interest rate in the entire extrapolation area. The system performs the following calculations:

Determination of the increase of the interpolation lines between the penultimate and last grid points of the yield curve, as portrayed in the following graphic:

[figure TRM02-F242 - Calculation of the continuously interest-bearing forward interest rate on the last grid point of the yield curve, as portrayed in the following graphic:]

Calculation of the continuously interest-bearing forward interest rate on the last grid point of the yield curve, as portrayed in the following graphic:

[figure TRM02-F243]

Calculation of the continuously interest-bearing zero rate, as portrayed in the following graphic:

[figure TRM02-F244 - Calculation of the continuously interest-bearing zero rate, as portrayed in the following graphic:]

###### Extrapolation

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Yield Curves > Creation of Yield Curves > Extrapolation | L8 | trm02 p.192 | loio `0a39ff507cc38028e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0a39ff507cc38028e10000000a44176d.html?locale=en-US)

Calculate Interest Rates from the Yield Curve Generated

Basis Spreads and Basis Spread Curves

Manual Entry of Basis Spread Values

Customizing for Credit Spreads

Credit Spreads and Credit Spread Curve Structures

Create Reference Entities for Business Partners

Maintain Reference Entities

Assign Reference Entities to Business Partners

Enter Credit Spread Values

Composite Curves

###### Calculate Interest Rates from the Yield Curve Generated

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Yield Curves > Creation of Yield Curves > Calculate Interest Rates from the Yield Curve Generated | L8 | loio `3539ff507cc38028e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3539ff507cc38028e10000000a44176d.html?locale=en-US)

Once the yield curve has been created, it is used to calculate the interest rates on the basis of the interest conditions that are set in the yield curve. The interest rate R is noted at par level if the condition represented by the following graphic applies for R:

[figure TRM02-F245 - The quotients q from the difference in days and days in the year as well as the payment dates i are achieved from the conditions of the interest rate. To calculate R, the system activates the equation towards R, as portrayed in the following graphic:]

The quotients q from the difference in days and days in the year as well as the payment dates i are achieved from the conditions of the interest rate. To calculate R, the system activates the equation towards R, as portrayed in the following graphic:

i

[figure TRM02-F246 - Either the system has already calculated the discount factors d during the creation of the yield curve, or they are achieved by means of interpolation with the continuous compounding zero rates.]

Either the system has already calculated the discount factors d during the creation of the yield curve, or they are achieved by means of interpolation with the continuous compounding zero rates.

i

The prerequisite for this is that the last and not the first interest period is shortened if the term is not a whole-number multiple of the payment frequency.

Calculation of Zero Interest Rates with a Term Exceeding a Year

If a zero interest rate with a term exceeding a year needs to be calculated, the system uses a different equation to the method portrayed above. Instead, it uses the equation depicted below:

[figure TRM02-F247 - This means that, for zero interest rates with a term exceeding a year, the system assumes a compounding frequency of one year.]

This means that, for zero interest rates with a term exceeding a year, the system assumes a compounding frequency of one year.

###### Calculation Procedures

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Yield Curves > Creation of Yield Curves > Calculation Procedures | L8 | loio `e9d545738e6d4eeca4f9087cca258354` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e9d545738e6d4eeca4f9087cca258354.html?locale=en-US)

The system uses the options Linear Interpolation of Continuously Compounded Zero Rates and Linear Interpolation of Zero Rates (Also for Swap Gaps) to interpolate continuously compounded zero rates linearly between the grid points. The difference

between the two options lies in the different handling of swap gaps during bootstrapping. A swap gap exists if reference interest rates (such as for a term of 1, 2, 3, 4, 5, 7, and 10 years) are assigned to a yield curve. In this case, the grid points (swap gaps) are missing for 6, 8, and 9 years.

If you select Linear Interpolation of Continuously Compounded Zero Rates, the missing grid points are determined when the yield curve is generated using the linear interpolation of par interest rates of the neighboring grid points. This is noticeable by the fact that grid points without a reference interest rate occur in the swap gaps in the yield curve display in addition to the grid points with a reference interest rate.

If you select Linear Interpolation of Zero Rates (Also for Swap Gaps), no additional grid points are determined when the yield curve is generated as is the case for Linear Interpolation of Continuously Compounded Zero Rates. Instead, the system interpolates the zero rate of the previously calculated grid point and the as yet unknown zero rate for the grid point to be added linearly to calculate the net present values of interest payments for the swap gaps. Since this cannot be solved with an algebraic equation, the system uses Newton’s iteration method. No additional grid points then occur in the swap gaps in the yield curve display.

The system uses the options Spline Interpolation (Harmonic Mean) of Zero Rates and Spline Interpolation (Weighted Harmonic Mean) of Zero Rates to interpolate continuously compounded zero rates with cubic Hermite splines. For these, different methods can be selected for calculating the values of the first derivation at the grid points. These curves are continuously differentiable. With both options, the system handles swap gaps in the same way as with the option Linear Interpolation of Zero Rates (Also for Swap Gaps). Since the equations that occur when the yield curve is created cannot be solved algebraically, the system uses an iteration method. When it creates a yield curve, the system calculates the discount factors multiple times for all of the curve’s grid points until they no longer change in a further calculation run.

If you use the option Spline Interpolation (Harmonic Mean) of Zero Rates, the system calculates the values of the first derivation on the grid points as the unweighted harmonic mean of the slopes to the neighboring grid points. This method is monotonicity-preserving.

If you use the option Spline Interpolation (Weighted Harmonic Mean) of Zero Rates, the system calculates the values of the first derivation on the grid points as the weighted harmonic mean of the slopes to the neighboring grid points. This method is also monotonicity-preserving.

With the options Linear Interpolation of Log( Discount Factor), Spline Interpolation (Harmonic Mean) of Log( DF), and Spline Interpolation (Weighted Harmonic Mean) of Log( DF), the system interpolates the natural logarithm of the discount factors between the grid points. In these options, the system handles swap gaps in the same way as with the option Linear Interpolation of Zero Rates (Also for Swap Gaps). This means that the system interpolates only the natural logarithm of the discount factors,

not par interest rates. For these three options, the system uses an iterative method when it creates yield curves (as it does for the spline interpolation of zero interest rates). The system calculates the discount factors multiple times for all of the curve’s grid points until they no longer change in a further calculation run.

The option Linear Interpolation of Log( Discount Factor) means the system keeps instantaneous or differential forward rates constant between the grid points. This method is very robust and can also work in borderline cases where the other calculation methods lead to an error during yield curve creation.

If you use the option Spline Interpolation (Harmonic Mean) of Log(DF), the system calculates the values of the first derivation on the grid points in the same way as in the option Spline Interpolation (Harmonic Mean) of Zero Rates as the unweighted harmonic mean of the slopes to the neighboring grid points. The system interpolates the natural logarithm of the discount factors instead of zero rates. This method is monotonicity-preserving.

If you use the option Spline Interpolation (Weighted Harmonic Mean) of Log(DF ), the system calculates the values of the first derivation on the grid points in the same way as with the option Spline Interpolation (Weighted Harmonic Mean) of Zero Rates as the weighted harmonic mean of the slopes to the neighboring grid points. The system interpolates the natural logarithm of the discount factors instead of zero rates. This method is monotonicity-preserving.

**Dependencies**

The iterative method for creating yield curves used for spline interpolation or linear interpolation of logarithm (discount factor) is a fixed-point iteration of the discount factor for all grid points in the curve. If a negative discount factor occurs during fixed-point iteration, the system instead tries to calculate the discount factor using the algorithm known in numerical analysis as Brent’s method. In many cases, this results in a positive discount factor being calculated, and the iteration can be continued.

The iterative method differs from standard bootstrapping (as described in Creation of Yield Curves) in the following way: In this case, step 6 handles the special case in which the start of the interest period for a reference interest rate is after the end of the interest period for the previous grid point. Instead of continuing with a constant zero interest rate until the start of this yield curve (as is the case with standard bootstrapping), the iterative method does not use any special handling but applies only the interpolation method defined.

###### Day Count Convention for Interpolation

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Yield Curves > Creation of Yield Curves > Day Count Convention for Interpolation | L8 | loio `73a2072b37364445b0dc9b0dc4c3b976` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/73a2072b37364445b0dc9b0dc4c3b976.html?locale=en-US)

You can define how the portion of a year is determined between two Gregorian calendar dates. The following methods are available:

360E/360

360/360 (ISDA)

Act/360

Act/365

Act/ActY (ISDA)

The abbreviation ISDA stands for "International Swaps and Derivatives Association".

Act/ActE (AFB)

The abbreviation AFB stands for "L’Association Francaise des Banques" (French Bankers Association).

ActW/252

If you do not enter a day count convention for the interpolation, the system interpolates using day count convention Act/365.

**Dependencies**

The day count conventions 360E/360, 360/360 (ISDA) and actW/252 are problematic for interpolation if the yield curve contains a reference interest rate with a term of one day with a day count convention with a different days method, for example, Act.

If a yield curve like this is constructed, for example, for January 30, for a reference interest rate with day count convention Act/365 and with a term of one day, the system calculates a discount factor not equal to one for January 31. However, if interpolation with day count convention 360E/360 is defined for the yield curve, for example, the term between January 30 and January 31 is zero

days, and the discount factor for January 31 in the yield curve must be equal to one, then this produces a discrepancy. Therefore, an error occurs when a yield curve like this is constructed.

This problem does not occur if the day count convention for interpolation matches the day count convention for the reference interest rate, and, for ActW/252, if the two corresponding factory calendars are identical.

###### Manage Yield Curves

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Yield Curves > Manage Yield Curves | L7 | loio `0590f9aba35c49cdaa6020be44d5f1d6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0590f9aba35c49cdaa6020be44d5f1d6.html?locale=en-US)

With this app, you get an overview of the yield curve values and calculation bases and you can maintain the interest rate values for a specific yield curve.

**Use**

This app provides you with an overview of the calculability of the selected yield curves and also of the percentage shares of the interest rates entered for the curve or for the date. You can also display the interest rates and discounting factors for a certain yield curve, or you can display the yield curve as a graph. Further, you can enter missing reference interest rates directly for the selected combination of yield curve type, currency, and date.

**Integration**

When the yield curve is evaluated, the system reads the interest rates and zero-bond discounting factors from the interest rate tables.

**Prerequisites**

For the interest rates that you want to display, you need to have defined the yield curve type in Customizing and assigned it a currency. You can also create or edit the yield curve type directly from the overview screen or from the detail screen by choosing Environment Set Up Yield Curve .

**Features**

- 1. Call the Manage Yield Curves app on the SAP Fiori launchpad or in the back end from the area menu under Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Interest .
- 2. Enter the yield curve type, the currencies, and the date.
- 3. You can choose either Overview or Details.


If you choose Overview, you get a list of all selected yield curves.

The yield curve list contains the following information:

Information about the calculability of the yield curve. The yield curve can be calculated if at least one reference interest rate has been entered for the yield curve in accordance with the read procedure.

Percentage of the reference interest rates already maintained for the yield curve or for the date.

If you choose Details:

On the following screen, you see on the YC Values tab the interest rates used in the yield curve in the form of par and zero-coupon rates, plus the corresponding zero-bond discounting factors (ZBDF) for the interest rate date.

Calculation Base tab: On this tab, the reference interest rates are shown without the markup or markdown, and are sorted by the interest calculation method of the reference interest rates. Interpol. (interpolation) appears in the

Reference Interest Rate column if an annual grid value was interpolated. Choose Yield Curve Overview to display the overview screen again.

Graphic Display tab: All interest rates of the selected reference interest rate that exist in the selected period are displayed as a graph.

Choose Maintain Yield Curve Rates: On the following screen, you can enter or change the reference interest rate values at the grid points of the yield curve for the yield curve date.

**Supported Device Types**

Desktop

**Information for Key Users**

The SAP Fiori apps reference library has details about the content necessary for giving users access to an app on the SAP Fiori launchpad. To see this app’s Fiori content, go to the SAP Fiori apps reference library and search for the app. Then select the product. On the Implementation Information tab, select the correct release. The details are in the Configuration section.

**Related Information**

Yield Curve Framework Yield Curves

###### Basis Spreads and Basis Spread Curves

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Basis Spreads and Basis Spread Curves | L6 | loio `b7ba00518c19c557e10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b7ba00518c19c557e10000000a44176d.html?locale=en-US)

**Definition**

Basis spreads are premiums and discounts on one side of a basis swap that make the swap into a fair transaction. The spread relates to the first two reference interest rates assigned.

You can define tenor spreads and currency spreads. Basis spreads need to be defined before you can perform the following activities:

Upload Basis Spread Market Data to the System

Build Basis Spread Curves from Basis Spreads with Different Terms

**Structure**

To portray basis spreads, you need to create basis spread IDs in Customizing for Treasury and Risk Management under Basic Functions Market Data Management Master Data Basis Spreads Define Basis Spreads .

You assign to a basis spread ID two reference interest rates, the term, and the time unit.

**Note:**

If you want to portray a tenor spread, assign two reference interest rates with the same currency and different terms. The first reference interest rate is the one to which the spread is added. In this way, the properties of the first reference interest rate determine the quotation of the basis spread.

If you want to portray a currency spread, assign two reference interest rates with the same term and different currencies. The first reference interest rate is the one to which the spread is added. In this way, the properties of the first reference interest rate determine the quotation of the basis spread.

In the Extended Properties area, you can override some of the settings of the assigned reference interest rate by setting the Extended Properties indicator. When you set this indicator, the following fields are made visible:

Payment Frequency

Compounding Frequency

Fixing Period

Working Day Shift

Calendar

Interest Calculation Method

Maturity at Month End

You can override these settings.

Example

You want to portray a tenor spread that creates the surcharge on the three-month side of a term basis swap 3-Month EURIBOR versus 6-Month EURIBOR, with a term of five years.

You make the following settings:

|Basis Spread ID|Ref1|Ref2|Term|Time Unit|
|---|---|---|---|---|
|EUR3M6M|EURIBOR3M|EURIBOR6M|5|Year|


**Note:**

You can use the auxiliary program FTBBYC_BSPRD_CUST_HELP to create multiple similar basis spreads in parallel. For more information, see the documentation on this program in the system.

You manually enter the concrete values of the basis spreads for a specific date in the area menu of Treasury and Risk Management under Basic Functions Market Data Management Manual Market Data Entry Basis Spreads Enter Basis Spreads .

Instead of entering the basis spread values manually, you can also upload basis spread values in the same way as other market data, such as with Datafeed, the file interface, or by using Market Data Transfer from Spreadsheet.

See also:

Manual Entry of Basis Spread Values

Market Data Management

Basis Spread Curves

You can include basis spreads in the price calculator for the calculation of discount factors and forward interest rates. For this, you define basis spread curve types in Customizing for Treasury and Risk Management under Basic Functions Market Data

Management Master Data Basis Spreads Define Basis Spread Curve Types and use them as the basis for creating the basis spread curves that, together with the yield curve, form the composite curve used as the basis for the calculations.

In the definition of the basis spread curve types, no settings are made regarding the interest rates derived from the curve because basis spread curves are not created as independent curves; instead, they are only used in conjunction with the creation of a composite curve. For a concrete curve to be achieved from the curve type, a concrete pair of currency/tenor combinations (for example, currency 1/tenor 1 <-> currency 2/tenor 2) is required.

The quotation type stored at the level of the basis spread curve type is for information purposes only.

The maximum age stored is relevant for the market data uploaded for a concrete curve. The quotation stored at the level of the concrete curve influences what market data is selected.

See also:Composite Curves

###### Customizing for Credit Spreads

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Customizing for Credit Spreads | L6 | loio `ae5e3053833d6957e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ae5e3053833d6957e10000000a44538d.html?locale=en-US)

**Market Data**

For you to be able to enter market data in the system for credit spreads, you first need to make the following settings:

|Customizing/Function|Path|Comments|
|---|---|---|
|Define Credit Spread IDs (view V_FTBBYCCSPRD)|Customizing: Treasury and Risk Management Basic Functions Market Data Management Master Data|In this Customizing activity, you create credit spread IDs by specifying their characteristics. In the Market Data Quotation area, you can define how the yield curve framework interprets the market data. For this, you make entries in the following fields: Payment Frequency Compounding Frequency Fixing Period Working Day Shift Calendar Interest Calculation Method Maturity at Month End In the Expert Settings area, you need to select the default entry for the Usage field, unless you want to implement your own logic for converting the market data into spreads for use in the yield curve framework.|
|Maintain Reference Entities (transaction RMRE) Create Reference Entities for Business Partners (transaction RMREBP)|Area menu: Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Credit Spread Curves|You also need to create the reference entities that are referred to by your credit spreads. You can assign business partners, company codes, and security ID numbers to reference entities. However, you can also|


|Customizing/Function|Path|Comments|
|---|---|---|
| | |define more general reference entities for ratings or industries. To create reference entities for your business partners, you can use the program Create Reference Entities for Business Partners (transaction RMREBP). See also: Maintain Reference Entities Create Reference Entities for Business Partners |
|Settings for the Datafeed| | |
|Convert Credit Spread Quotation Types (view V_MDUDFCS)|Customizing: Treasury and Risk Management Basic Functions Market Data Management Master Data Datafeed Translation Table Define Datafeed Conversion Codes|In this activity, you define the conversion codes for credit spread quotation types. Define the external names for the required quotation types. Consult your datafeed provider to establish which names (instrument properties) are recognized by your external partner program.|
|Define Credit Spreads (view V_DFCU10)|Customizing: Treasury and Risk Management Basic Functions Market Data Management Master Data Datafeed Translation Table|In this activity, you define how to import credit spreads using the external partner program of your datafeed provider. Prerequisites You need to define the credit spread ID. You need to define the reference entities. The real-time price/rate provision function requires that your external partner program operates in real time. Ask your datafeed provider regarding whether your external partner program meets this **Example:** Notation: Reference entity: BP_DEUBA Credit spread ID: 5_YEAR Quotation type: 2 (bid) Relevant datafeed notation: Instrument name: DB5YEUAM=R Data origin: DDS Instrument property: BID|


|Customizing/Function|Path|Comments|
|---|---|---|
| | |requirement and whether one query from the system suffices for market data to be provided regularly. Activities 1. Specify how you want to import your interest rates using the external partner program and consequently using datafeed. 2. If you want to record an exchange rate history in the system, you need to set the Store Market Data Permanently in R/3 indicator. 3. Moreover, you can define whether the prices are only supplied from the system upon explicit request, or whether they are supplied in real time using the external partner program of your datafeed provider. 4. Save your entries. **Note:** To reduce effort considerably, first perform the following activities: 1. Define Credit Spread IDs 2. Convert Codes for Credit Spread Notation Types 3. Define Reference Entities 4. Import S/4HANA Master Data In this way, most settings in this activity are filled automatically and do not need to be filled manually.|
|Settings for the File Interface| | |
|Convert Codes for Quotation Types (view V_MDUCS)|Customizing: Treasury and Risk Management Basic Functions Market Data Management Master Data File Interface Credit Spreads|In this activity, assign the quotation types used by your data provider to the quotation types used in the sytem. To each quotation type used in the SAP system, assign the relevant external quotation type (= name used by the data provider). Ensure that a 1:1 assignment is guaranteed for the quotation types. The codes are not converted until you enter an external quotation type for the quotation type used in the system. **Example:** System notation:|


|Customizing/Function|Path|Comments|
|---|---|---|
| | |1 (Middle) 2 (Bid) 3 (Ask) Data provider notation: MID BID ASK|


**Applying Credit Spreads in the Calculation of Net Present Values**

For credit spreads to be applied in the calculation of net present values, the system must create a suitable credit spread curve during the calculation of net present values. To enable this, you first need to make the following settings:

|Customizing/Function|Path|Comments|
|---|---|---|
|Define Credit Spread Curve Structures (transaction RMCSC)|Customizing: Treasury and Risk Management Basic Functions Market Data Management Master Data|In this Customizing activity, you define credit spread curve structures and use attributes that influence the selection of market data. Further, you assign credit spread IDs to define the term structure of the curve. In combination with a reference entity, a credit spread curve structure describes a specific credit spread curve. For this reason, credit spread curve structures can be assigned to reference entities. Create new credit spread curve structures. 1. Enter a four-digit ID for the credit spread curve structure. 2. Choose Create. **Note:** When you create a new credit spread curve structure, you can use the Copy function. Enter the ID of an existing credit spread curve structure and choose Copy. In the next screen that appears, enter the ID for the new structure. The system creates the new structure with the same settings. Enter the new structure ID and choose Change to make the necessary changes to the new structure.|


|Customizing/Function|Path|Comments|
|---|---|---|
| | |3. Enter a descriptive text for the credit spread curve structure. 4. In the Market Data Properties area, specify the quotation type and the maximum age. These attributes influence which market data (credit spreads) is selected. 5. In the Credit Spread Curve Structure area, select the credit spread IDs using the New Credit Spread IDs pushbutton, which provides a list of available credit spread IDs. 6. Save your entries. Further, you can use the following functions for credit spread curve structures: Change or Display Credit Spread Curve Structures 1. Enter the ID for the credit spread curve structure. 2. Choose Edit or Display. 3. Make your changes and save your entries. Check Credit Spread Curve Structures 1. Enter an ID for the credit spread curve structure. 2. Choose Goto. 3. The system checks the consistency of the credit spread curve structures and the credit spread IDs assigned. The system displays any inconsistencies found and suggests how to resolve them. Before you use the credit spread curve structures, you need to resolve any inconsistencies. Delete Credit Spread Curve Structures 1. Enter the ID of the credit spread curve structure and choose Delete. 2. The system deletes all table entries that depend on the credit spread curve structure. Transport Credit Spread Curve Structures|


|Customizing/Function|Path|Comments|
|---|---|---|
| | |1. Enter the ID of the credit spread curve structure and choose Transport. 2. The system transports the credit spread curve structure. For reasons of consistency, the master data of the assigned credit spread IDs is included in the transport. Where-used list 1. Enter the ID for the credit spread curve structure. 2. Choose Where-Used List. 3. You obtain a list of all reference entities to which the selected credit spread curve structure is assigned. |
|Determining Reference Entities| | |
|Assign Reference Entities to Business Partners (transaction RMBPRE_ASSIGN)|Area menu: Treasury and Risk Management Market Risk Analyzer/Portfolio Analyzer/Accounting Analyzer/Analyzer for Commodities Evaluation Control Valuation Settings|For many business partners, there is no credit spread market data available, which means that these business partners cannot be created directly as reference entities in the system. It may nevertheless be necessary for valuation purposes to apply the most suitable credit spread curve as a substitute credit spread curve for these business partners. Depending on the semantics involved, there are many different approaches for finding a substitute curve (search by ratings, industries, countries/regions, similar companies, indexes, and so on). The system cannot automatically assign these alternative reference entities to the business partners, which means that you have to use this function to assign the relevant reference entity to the affected business partners.|
|Define Reference Entity Derivation IDs (view cluster VC_FTBB_YC_REF_ENTITY_DERI)|Customizing: Treasury and Risk Management Basic Analyzer Settings Valuation|In this Customizing activity, you define for all clients the derivation IDs for reference entities. A reference entity derivation ID controls how the system derives reference entities representing the business partner or your own company code that is involved in the financial transactions/positions. Based on the credit spread curve structures of these reference entities, the system creates credit spread curves that are added to yield curves at runtime to form composite curves. The ID is relevant for yield curve types that are entered in the|


|Customizing/Function|Path|Comments|
|---|---|---|
| | |evaluation type/valuation rule and are used, for example, for discounting. Notes: Your reference entity derivation IDs must start with the prefix X, Y, or Z (customer namespace). For each reference entity derivation ID for business partners and your own companies, you have to create a BAdI implementation with the reference entity derivation ID as the BAdI filter value. If the preconditions above are met, the corresponding credit spread curves added to the interest curves for valuation purposes (such as discount) are fetched from the reference unit. Here, the system orients itself by the BAdI implementation with the reference unit derivation ID as a filter value. Activities 1. Choose Derivation for Business Partners or Derivation for Your Own Companies. 2. Choose New Entries. 3. Enter the four-digit reference entity derivation ID and a short and a long text for the ID. 4. Enter all needed derivation IDs and save your entries. |
|BAdI: Derive Reference Entity for Your Own Companies (BADI_FTBBYC_REF_ENTITY_OWN)|Customizing: Treasury and Risk Management Basic Analyzer Settings Valuation Spread Curve Derivation|This Business Add-In (BAdI) is used in Treasury and Risk Management (FINFSCM-TRM) to derive reference entities for your own companies - and consequently credit spread curves for your own companies - for evaluation purposes such as discounting. The BAdI filter Reference Entity Derivation ID for Your Own Companies is the only procedure for deriving credit spread curves for your own companies (see also the Customizing activity Define Reference Entity Derivation IDs). Either you use the BAdI implementation delivered by SAP (see the standard implementation), or you can create your own coding corresponding to the reference entity derivation ID that you have created for your own companies.|


|Customizing/Function|Path|Comments|
|---|---|---|
| | |Prerequisites You have defined reference entities (using the function Maintain Reference Entities transaction RMRE) representing your own companies with the Use in Credit Spread Curve indicator set and specified for the the credit spread curve structures. Activities For more information about implementing BAdIs in the context of the enhancement concept, see the SAP Library for SAP NetWeaver. This BAdI uses the interface IF_EX_FTBBYC_REF_ENT_DER_OWN. For more information, display the interface in the class builder. **Example:** SAP delivers the standard BAdI implementation BADII_REF_ENTITY_DERI_BP_001 corresponding to the reference entity derivation ID for your own companies, STD. 1. Securities ID Number 2. Transaction/Position CoCode 3. Selection Type CoCode |
|BAdI: Derive Reference Entities for Business Partners (BADI_FTBBYC_REF_ENTITY_BP)|Customizing: Treasury and Risk Management Basic Analyzer Settings Valuation Spread Curve Derivation|This Business Add-In (BAdI) is used in Treasury and Risk Management ((FINFSCM-TRM) to derive reference entities for business partners - and consequently credit spread curves for business partners - for evaluation purposes such as discounting. The BAdI filter Reference Entity Derivation ID for Business Partners is the only procedure for deriving credit spread curves for business partners (see also the Customizing activity Create Reference Entity Derivation IDs). Either you use the BAdI implementation delivered by SAP (see the standard implementation), or you can create your own coding corresponding to the reference entity derivation ID that you have created for business partners. Prerequisites You have defined reference entities (using the function Maintain Reference Entities -|


|Customizing/Function|Path|Comments|
|---|---|---|
| | |transaction RMRE) representing business partners with the Use in Credit Spread Curve indicator set and and specified for the credit spread curve structures. Activities For more information about implementing BAdIs in the context of the enhancement concept, see the SAP Library for SAP NetWeaver. This BAdI uses the interface IF_EX_FTBBYC_REF_ENT_DER_BP. For more information, display the interface in the class builder. **Example:** SAP delivers the standard BAdI implementation BADII_REF_ENTITY_DERI_BP_001 corresponding to the reference entity derivation ID for business partners, STD. 1. Securities ID Number 2. BP Hierarchy 3. Assignment Table |
|Define and Set Up Evaluation Types (transaction CFMEVAL)|Customizing: Treasury and Risk Management Basic Analyzer Settings Valuation|In this Customizing activity, the settings for credit spreads have been added to the Evaluation Control tab has been added in the evaluation type as well as in the valuation rule. In the Credit Spread Curve Derivation area, you make the following settings to control how the reference entities are determined: Derivation ID for Business Partners This derivation ID controls how the system derives reference entities that represent the business partners involved in the transaction or in the position. Based on the credit spread curve structures of these reference entities, the system creates credit spread curves that are added to yield curves at runtime to form composite curves. In the Customizing activity Create Derivation IDs for Reference Entities, you can define your own derivation IDs.|


|Customizing/Function|Path|Comments|
|---|---|---|
| | |If you want to define rules for the derivation of reference entities, you need to create an implementation for BAdI: Derive Reference Entities for Business Partners using the derivation ID as a filter value. SAP delivers the standard derivation rule STD, which the system deploys as follows: In general, the system only considers reference entities for which the Use in Curve indicator is set. The following search steps are performed: 1. In the case of bond positions, the system uses the securities ID number to search for a reference entity. If the search finds a reference entity, the system applies it; otherwise, the system continues the search using the business partner. 2. The system searches for a reference entity using business partners (OTC counterparty or bond issuer) as follows: 3. If a business partner hierarchy type is specified, the system determines the company at the top of the hierarchy; otherwise, the system uses the business partner itself. 4. The system uses the business partner determined in this way to search for a reference entity. If the search returns a reference entity, the system applies it. 5. If the system does not find a reference entity that represents the business partner, it searches for a replacement reference entity (such as a reference entity for a rating) that is assigned to the partner in |


|Customizing/Function|Path|Comments|
|---|---|---|
| | |transaction RMBPRE_ASSIGN. BP Relationship Category If you enter a relationship category here, the system determines the reference entity for the business partner with which the business partner of the transaction is connected by means of this relationship category. You can use the relationship category, for example, to valuate all companies in a group using the credit spreads of the parent group. In the business partner master data of the subsidiary, you assign the parent group using the relationship category Is Subsidiary Of and you enter this relationship category in the evaluation type. Consequently, the system applies the reference entity of the parent group for all subsidiaries. Derivation ID for Your Own Companies Enter the derivation ID to determine the reference entity for your own companies. Default Company Code By entering a default company code, you can influence how the system derives the reference entity for your own companies. Dependencies How this setting works depends on the derivation ID selected for deriving the reference entity for your own companies. The implementation of the selected standard derivation ID STD for deriving the reference entity for your own companies considers the default company code as follows: 1. The system searches for a reference entity for the company code of the transaction/position. 2. If it does not find a reference entity, it looks for |


|Customizing/Function|Path|Comments|
|---|---|---|
| | |a reference entity for the default company code. Alternative Maximum Age Indicator The maximum age of the market data is entered in the definition of the credit spread curve structures. If you set this indicator, you can define a new age as the maximum age for evaluation purposes. Maximum Age **Example:** If only one credit spread curve exists for your company, irrespective of the company code, you can define a reference entity for a specific company code that you then specify as the default company code in your evaluation type/valuation rule.|

###### Credit Spreads and Credit Spread Curve Structures

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Credit Spreads and Credit Spread Curve Structures | L6 | loio `1caf0e53e7728b4ae10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1caf0e53e7728b4ae10000000a441470.html?locale=en-US)

**Use**

You can enter credit spreads manually using the app Enter Credit Spreads.

In addition, you can define credit spread curve structures from credit spreads with different terms.

In combination with the reference entity, a credit spread curve structure defines a concrete credit spread curve that can be combined with yield curves in the Yield Curve Framework. See also:Composite Curves

**Prerequisites**

To portray credit spreads, you need credit spread IDs. In a credit spread ID, the credit spread is described.

Besides the term the following Market Data Quotation are defined for a credit spread ID.

Payment Frequency

Compounding Frequency

Fixing Period

Working Day Shift

Calendar

Interest Calculation Method

Maturity at Month End

Credit Spread Value Structures

You can include credit spreads in the price calculator for the calculation of discount factors. For this, credit spread curve

structures are defined. On the basis of these credit spread curve structures, credit spread curves are then created using a reference entity. Together with the yield curve the credit spread curves generate a composite curve that is then applied in the calculations.

In the definition of the credit spread curve structures, no settings are made regarding the interest rates derived from the curve because credit spread curves are not created as independent curves; instead, they are only used in conjunction with the creation of a composite curve.

By means of the assignment of a credit spread curve structure to reference entities, a concrete curve is created for each of these reference entities (the reference entity is also a key field in the market data table).

The maximum age and quotation type specified influence which market data is selected.

Reference Entities

You create the required reference entities either with the app Manage Reference Entities or using the app Create Reference Entities, Business Partners

See also:Manage Reference Entities and Create Reference Entities for Business Partners

You manually enter the concrete values of the credit spreads for a specific date in the app Enter Credit Spreads

See also:Enter Credit Spread Values

###### Create Reference Entities for Business Partners

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Credit Spreads and Credit Spread Curve Structures > Create Reference Entities for Business Partners | L7 | loio `2bb70d5331f48a4ae10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2bb70d5331f48a4ae10000000a441470.html?locale=en-US)

**Use**

You use this program to create reference entities simultaneously for multiple business partners.

**Activities**

Selection

- 1. Call the function by choosing Treasury and Risk Management Basic Functions Market Data Management Manual Market Data Entry Credit Spread Curves Create Reference Entities for Business Partners (transaction RMREBP).
- 2. Enter the business partners for which you want to create reference entities.
- 3. Choose the business partner roles for which you want to create reference entities. The role Counterparty, Issuer, and House Bank are set by default.
- 4. Enter the prefix (maximum of 5 digits) for the reference entity ID of the new reference entities. The default setting is BP_.
- 5. Overwrite Existing Entries indicator: Specify whether reference entities with the same ID are overwritten. If you set this indicator, the system overwrites existing reference entities.


**Note:**

If you do not enter a business partner and you do not change the business partner role default settings, the system selects all existing business partners that have these roles assigned to them.

- 6. Avoid Duplicates indicator: Specify whether duplicate reference entities for a business partner are allowed. When you set this indicator and, in addition, you have not made the setting allowing existing reference entities to be overwritten, the system does not create a second reference entity with the same ID for a business partner, and existing reference entities remain unchanged.
- 7. If you want to use the reference entities in the Yield Curve Framework, set the Use in Credit Spread Curve indicator. Assign the credit spread curve structures to the credit spread curves "Bid", "Ask", and "Middle".
- 8. Execute the function.


Result

The system creates a reference entity for each business partner selected.

The ID of the reference entities consists of the prefix and the business partner name.

If you have set the Use in Credit Spread Curve indicator, the credit spread curves for the new reference entity are also defined.

You can use the function Maintain Reference Entities (transaction RMRE) to rework the reference entities.

**Example**

If you execute the report with the default values for the selection parameters, the system creates new reference entities for all business partners with the roles "Counterparty", "Issuer", and "House Bank" in your system.

The reference entities are named BP_PARTNER, where PARTNER stands for the name of the business partner. Existing entries are not overwritten, and duplicates are not allowed.

###### Maintain Reference Entities

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Credit Spreads and Credit Spread Curve Structures > Maintain Reference Entities | L7 | loio `afbb0d5331f48a4ae10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/afbb0d5331f48a4ae10000000a441470.html?locale=en-US)

**Use**

The reference entity is the reference factor for a credit spread.

**Example:**

Examples of reference entities:

Business partners ("reference debtor")

Company codes (for the storage of credit spreads belonging to your company)

Security ID numbers

Ratings

You need to define reference entities to enable you to do the following:

Enter credit spread values in the system

Use credit spread curves in the Yield Curve Framework

You can use this function to create and change reference entities. To create reference entities automatically for your business partners, you can use the program Create Reference Entities for Business Partners.

**Note:**

For many business partners, there is no credit spread market data available, which means that these business partners cannot be created directly as reference entities. It may nevertheless be necessary for valuation purposes to apply the most suitable credit spread curve as a substitute credit spread curve for these business partners. For this, you can use the function Assign Reference Entities to Business Partners (transaction RMREBP_ASSIGN).

**Activities**

- 1. Call the function in the area menu for Treasury and Risk Management by choosing Basic Functions Market Data Management Manual Market Data Entry Credit Spread Curves Edit Reference Entities (transaction RMRE).

An overview of all previously defined reference entities appears. You can display or change existing reference entities or create new reference entities.

- 2. Choose to switch from the display mode to the change mode. In the change mode, you can make changes to existing reference entities or create a new reference entity.
- 3. To create a new reference entity, choose New Entries.


- a. In the Reference Entity field, enter an ID with a maximum of nine digits or a short description for the reference entity as well as an additional description in the Name field.
- b. In the Definition area, under Standard Attributes for Spread Curve Definition, specify the business partner, company code, or ID number to which the reference entity relates.

For these standard attributes, the Yield Curve Framework can automatically derive the appropriate reference entity.

If you want to portray other types of reference entity, you can select combinations of the attributes in the Additional Attributes area. The following attributes are available:

Rating Procedure

Rating

Industry System

Industry

Country/Region

Currency

In this way, you can create more general credit spread market data, for example, in cases when no specific credit spread market data is available for one of your business partners. You then need to manually assign these reference entities to a business partner. This is because an automatic assignment by the system is not possible. See also: Assign Reference Entities to Business Partners

- c. In the Settings for Usage in Yield Curve Framework area, set the Use in Curve indicator when you want the related credit spread curves to be used in the composite curves of the Yield Curve Framework.

Further, you need to assign which credit spread curve structures are used for the credit spread curves "Bid", "Ask", and "Middle".

- d. Save your entries.


Example

|Reference Entity|Business Partner|Company Code|Security ID Number|
|---|---|---|---|
|BP_AA|AA| | |
|CC_1000| |1000| |
|SID_123456| | |DE123456|

###### Assign Reference Entities to Business Partners

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Credit Spreads and Credit Spread Curve Structures > Assign Reference Entities to Business Partners | L7 | loio `2b041c531e23fe07e10000000a423f68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2b041c531e23fe07e10000000a423f68.html?locale=en-US)

**Use**

For many business partners, there is no credit spread market data available, which means that these business partners cannot be created directly as reference entities in the system. It may nevertheless be necessary for valuation purposes to apply the most suitable credit spread curve as a substitute credit spread curve for these business partners. Depending on the semantics involved, there are many different approaches for finding a substitute curve (search by ratings, industries, countries/regions, similar companies, indexes, and so on).

The system cannot automatically assign these alternative reference entities to the business partners, which means that you have to use this function to assign the relevant reference entity to the affected business partners.

See also: Composite Curves

**Activities**

- 1. Call the function by choosing Treasury and Risk Management Market Risk Analyzer / Portfolio Analyzer / Accounting Analyzer Evaluation Control Valuation Settings Assign Reference Entities to Business Partners (transaction RMBPRE_ASSIGN).
- 2. Choose to switch from the display mode to the change mode. In the change mode, you can make changes to existing assignments or create new assignments.
- 3. To create a new assignment, select the business partner and assign the relevant reference entity to it.
- 4. Save your entries.


Example

|Business Partner|Reference Entity|
|---|---|
|CC|Rating_CC|
|DD_AG|ITRX_EUR_NONFIN|

###### Composite Curves

> **Path:** Treasury and Risk Management > Risk Management > Basics > Price Calculator for Financial Instruments > Yield Curve Framework > Composite Curves | L6 | loio `528c91511655fc53e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/528c91511655fc53e10000000a44538d.html?locale=en-US)

Each composite curve consists of exactly one yield curve and any number of basis spread curves. The properties of the yield curve determine the properties of the resulting composite curve.

The Yield Curve Framework allows you to define a set of basis spread curves that are added to the yield curve, both for forward yield curves and for yield curves that are assigned in the evaluation type/valuation rule. Further, it is possible to derive a credit

spread curve.

[figure TRM02-F248 - Creation of a Composite Curve]

Creation of a Composite Curve

- 1. Deriving Basis Spread Curves


Determining the Basis Spread Curve Type

First, the basis spread curve type is determined. This is either the basis spread curve type (bid/ask) that was assigned in the relevant evaluation type/valuation rule or, in the case of forward calculations, the basis spread curve type that was assigned to the yield curve type of the relevant yield curve for forward calculations.

Determination of the Basis Spread Curve for Concrete Use

SAP delivers different BAdIs for the purposes of forward calculations and evaluation processes. The BAdIs are used to select the basis spread curve to be used specifically for the relevant basis spread curve type.

The BAdIs belong to the enhancement spot ES_FTBBYC_SPREAD_CURVES_DER. You find these BAdIs in Customizing for Treasury and Risk Management under Basic Analyzer Settings Valuation Spread Curve Derivation .

BAdI BADI_FTBBYC_SPREAD_CURVES_EVALBAdI: Derive Basis Spread Curves for Evaluation Purposes

BAdI BADI_FTBBYC_SPREAD_CURVES_FORWBAdI: Derive Basis Spread Curves for Forward Calculations

SAP delivers standard implementations (such as BADII_BSPRD_DER_FWD_001 for determining basis spread curve(s) for forward calculations for BAdI BADI_FTBBYC_SPREAD_CURVES_FORW) and implementation example classes that they can use.

For example, for the determination of the basis spread curve(s) for evaluation purposes, SAP delivers two implementation example classes for the BAdI BADI_FTBBYC_SPREAD_CURVES_EVALBAdI: Derive Basis Spread Curves for Evaluation Purposes. Now you need to create your own implementations, which you can base on the implementation example classes:

- CL_FTBBYC_EX_BSPRD_DER_EVAL001Example: Derivation of Currency Spreads for Discounting

- CL_FTBBYC_EX_BSPRD_DER_EVAL002Example: Currency Combination of Risk-Free Discounting Currencies


In Customizing for Treasury and Risk Management under Basic Analyzer Settings Valuation Define Evaluation Type , you assign for each evaluation type/valuation rule on the Evaluation Control tab in the Basis Spread Curve Derivation area a four-character ID for each of the cases Forward Calculation (Spread Derivation ID (Forward) field) and Evaluation Purposes (Spread Derivation ID (Eval) field). You use this four-character ID as a filter value in the BAdI implementations.

