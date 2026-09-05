# Treasury Trade Request - Read, Create - SAP TRM Knowledge Base (branch split)

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

### Treasury Trade Request - Read, Create

> **Path:** APIs for Treasury and Risk Management > Treasury Trade Request - Read, Create | L2 | trm12 p.36 | loio `49e6afd88f92496da41e8b02464a62ee` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/49e6afd88f92496da41e8b02464a62ee.html?locale=en-US)

This inbound OData service enables you to read the existing treasury trade requests in your SAP S/4HANA system, such as hedge trade requests, B/S hedge trade requests, cash trade requests, or manual trade requests. The service also enables you to create manual trade requests for FX and MM instrument categories. You can create manual trade requests using the Process Trade Requests app (App ID: TPITRO) or via this service. Further processing of the manual trade requests created via this service is done in the Process Trade Requests app. The trade requests are then transferred to the SAP Trading Platform Integration application to trigger the conclusion of a financial transaction (trade) on an external trading platform.

For more information, see also Integration with External Trading Platforms.

This service is published on the SAP Business Accelerator Hub. For more information about APIs, see APIs on SAP Business Accelerator Hub.

This is an OData version 4 service. This version aims to improve processing time and resource consumption of clients and servers. This includes a lightweight JSON format that reduces the size of every response.

**Technical Details**

A service group contains services that belong to the same business object model and so it shares similar environment conditions. The configuration and administration of a service group apply to all services in a service group (for example, routing) so you only have to do them once.

In the OData version 4 (V4) runtime implementation of the SAP Gateway Foundation, framework services originate from repositories.

|Service Group (incl. Namespace if It Exists)|Repository ID|Service Name (incl. Namespace if it Exists)|Version|
|---|---|---|---|
|API_TREASURYTRADEREQUEST|srvd_a2x|API_TREASURYTRADEREQUEST|0001|


**Service Structure**

Service Header (optional)

The service header contains information about the service.

Entities

The entities contain the business data of the service.

|Entity|Description|Necessity|Link to Details|
|---|---|---|---|
|Treasury Trade Request (TreasuryTradeRequest|With a trade request, you trigger the conclusion of a financial transaction (trade) on an external trading platform.|Mandatory|Treasury Trade Request|


Service Response

|Entity|Description|
|---|---|
|Treasury Trade Request (TreasuryTradeRequest|The details included in the response vary according to the type of operation. **Note:** The response to a CREATE action contains the information sent for creation, but not the ID of the new trade request. A subsequently sent GET action provides the trade request ID.|


Authorization Details

The following authentication methods are supported:

x509

OAuth2

For security reasons, SAP recommends using certificate-based authentication rather than username/password.

SAP recommends creating technical users specifically for the respective business application with minimum required privileges.

Technical users must have authorization to display trade requests and create manual trade requests. Using the following authorization objects the required authorizations can be granted:

T_TPI_TR Authorization Object for Trade Request

T_TPI_MM Authorization Object for Trade Request Money Market (MM)

T_TPI_IG Authorization Object for Trade Request Instrument Group

**Service Group Publishing**

Service groups are published in transaction /IWFND/V4_ADMIN on the SAP Gateway Foundation hub. For more information, see Service Group Publishing.

**Error Handling**

The error log facilitates easy navigation to the affected source code where you can make the necessary corrections. For more information, see Error Log.

**Additional Information**

https://api.sap.com/api/sap-s4-OP_API_TREASURYTRADEREQUEST_0001-v1/overview

When you've opened an API on SAP Business Accelerator Hub, you can see the information about the API for a specific release. To switch between different releases, use the Select Release dropdown list.

#### Treasury Trade Request

> **Path:** APIs for Treasury and Risk Management > Treasury Trade Request - Read, Create > Treasury Trade Request | L3 | trm12 p.38 | loio `cedbcb4e84044fe0b06ab382a4a7b865` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/cedbcb4e84044fe0b06ab382a4a7b865.html?locale=en-US)

Technical name: TreasuryTradeRequest

**Properties**

|Property|Description|Necessity|
|---|---|---|
| | |**Note:**|
| | |The necessity of a field|
| | |varies depending on the|
| | |action and chosen|
| | |instrument category. In|
| | |general, the same rules|
| | |apply as for the creation of|
| | |a manual trade request in|
| | |the Process Trade Requests|
| | |app.|
|TrsyTrdReqInstrumentGroup|Instrument Group|Optional|
| |The trade request instrument group distinguishes| |
| |between the different kinds of financial instruments by| |
| |assigning them to different groups.| |
| |The following financial instrument groups are available:| |
| |Foreign Exchange| |
| |(TrsyTrdReqInstrumentGroup: FX)| |


|Property|Description|Necessity **Note:** The necessity of a field varies depending on the action and chosen instrument category. In general, the same rules apply as for the creation of a manual trade request in the Process Trade Requests app.|
|---|---|---|
| |Money Market (TrsyTrdReqInstrumentGroup: MM)| |
|TreasuryTradeRequestStatus|Trade Request Status Shows the processing status of the trade request. Automatically generated trade requests, meaning those based on hedge requests, cash requests or balance sheet hedge requests do not go through the Created, Submitted or Released statuses, since they go directly to In Transfer, meaning they are sent directly to the SAP Trading Platform Integration. The following statuses are available: C - Created: The trade equest was created and is waiting to be submitted. S - Submitted: The request was submitted and is waiting to be released. R - Released: The request was released and is waiting to be transferred to the SAP Trading Platform Integration. T - In Process: The trade request or parts thereof are still being processed. X -Canceled: The request was released and then canceled or declined. F - Completed: All trades belonging to this trade request have been received. I - In Transfer: The request was sent and is waiting to be received by the SAP Trading Platform Integration. U - Transfer Failed: There was an error while transferring the trade request. |Optional|
|CompanyCode|Company Code|Optional|
|TrsyTrdReqInstrumentCategory|Instrument Category The category of the financial instrument that is requested in the trade requests.|Optional|


|Property|Description|Necessity **Note:** The necessity of a field varies depending on the action and chosen instrument category. In general, the same rules apply as for the creation of a manual trade request in the Process Trade Requests app.|
|---|---|---|
| |Foreign Exchange (TrsyTrdReqInstrumentGroup: FX) FX Forward (TrsyTrdReqInstrumentCategory: FXFW) FX Spot (TrsyTrdReqInstrumentCategory: FXSP) FX Option (TrsyTrdReqInstrumentCategory: FXOP) FX Non-Deliverable Forward (TrsyTrdReqInstrumentCategory: NDF) FX Swap (TrsyTrdReqInstrumentCategory: FXSW) FX Non-Deliverable Swap (TrsyTrdReqInstrumentCategory: NDS) FX Collar (TrsyTrdReqInstrumentCategory: FXCO) Money Market (TrsyTrdReqInstrumentGroup: MM) Money Market: Fixed Term Deposit/Loan (TrsyTrdReqInstrumentCategory: FT)| |
|HedgingArea|Hedging Area|Optional|
|HedgeRequestIdentifier|Hedge Request ID|Optional|
|TrsyTradeReqCancellationReason|Trade Request Cancellation Reason|Optional|
|TreasuryTradeRequestNote|Trade Request Note|Optional|
|TrsyTradeRequestDescription|Trade Request Description|Optional|


|Property|Description|Necessity **Note:** The necessity of a field varies depending on the action and chosen instrument category. In general, the same rules apply as for the creation of a manual trade request in the Process Trade Requests app.|
|---|---|---|
|TrsyTrdReqRefObjectCategory|Reference Object Category|Optional|
|TrsyTrdReqRefObjectIdentifier|Reference Object ID|Optional|
|ForeignExchangeValueDate|FX Value Date|Optional|
|TrsyTrdReqRequestedAmount|Trade Request Requested Amount|Optional|
|TrsyTradeRequestTradedCurrency|Trade Request Traded Currency|Optional|
|TrsyTrdRequestOppositeCurrency|Trade Request Opposite Currency|Optional|
|TrsyTradedAmountBuySellCode|Traded Amount Buy Sell Code|Optional|
|FinTransFixingDate|Fixing Date|Optional|
|ForeignExchangeFixingReference|FX Fixing Reference|Optional|
|CashSettlementCurrency|Cash Settlement Currency|Optional|
|FXLeg2ValueDate|FX Leg 2 Value Date|Optional|
|FXLeg2TradedAmount|FX Leg 2 Traded Amount|Optional|
|FXLeg2TradedCurrency|FX Leg 2 Traded Currency|Optional|
|FXSwapLeg2FixingDate|FX Swap Leg 2 Fixing Date|Optional|
|FXSwapLeg2FixingReference|FX Swap Leg 2 Fixing Reference|Optional|
|FXSwapLeg2CashSettleCurrency|FX Swap Leg 2 Cash Settlement Currency|Optional|
|TrsyTradeReqInvestBorrow|Invest/Borrow You enter the direction of the request trade using the Invest or Borrow setting. Invest Since a certain amount of money is available for a certain period of time, the trader should invest this amount in the market. Borrow Since a certain amount of money is required for a certain period of time, the trader should borrow this amount in the market.|Optional|


|Property|Description|Necessity **Note:** The necessity of a field varies depending on the action and chosen instrument category. In general, the same rules apply as for the creation of a manual trade request in the Process Trade Requests app.|
|---|---|---|
|TrsyTradeReqInterestRateStruc|Interest Rate Structure|Optional|
|NominalAmountInNominalCurrency|Nominal Amount in Nominal Currency|Optional|
|NominalCurrency|Nominal Currency|Optional|
|TrsyTradeReqMinStartDate|Minimum Start Date|Optional|
|TrsyTradeReqMaxStartDate|Maximum Start Date|Optional|
|TrsyTradeReqMinEndDate|Minimum End Date|Optional|
|TrsyTradeReqMaxEndDate|Maximum End Date|Optional|
|Action History See when and by whom the trade request was created and processed further on. This also makes it possible to see which actions the trade request has gone through.| | |
|TreasuryTradeRequestUUID|Trade Request UUID|Optional|
|TreasuryTradeRequest|Trade Request|Optional|
|TrsyTrdReqActHistEntrDteTme|Entry Date/Time|Optional|
|TrsyTrdReqActHistActionCode|Action Code|Optional|
|TrsyTrdReqActHistLastChangedBy|Changed by|Optional|
|TrsyTrdReqActHistVersion|Version|Optional|
|TradeRequest|Trade Request|Optional|
|Additional Attributes If values are entered for the following fields, these values are also assigned to the financial transaction concluded for this trade request.| | |
|FinancialTransactionPortfolio|Portfolio|Optional|
|FinTransHedgingClassification|Hedging Classification|Optional|
|TrsyTrdReqExternalReference|External Reference|Optional|


|Property|Description|Necessity **Note:** The necessity of a field varies depending on the action and chosen instrument category. In general, the same rules apply as for the creation of a manual trade request in the Process Trade Requests app.|
|---|---|---|
|FinancialTransactionAssignment|Assignment|Optional|
|FinTransInternalReference|Internal Reference|Optional|
|FinTransactionCharacteristics|Characteristics|Optional|
|ProfitCenter|Profit Center|Optional|
|CostCenter|Cost Center|Optional|
|WBSElementInternalID|WBS Element|Optional|
|OnBehalfOfCompany|On Behalf of Company Code|Optional|
|Country|Country/Region|Optional|
|Segment|Segment|Optional|
|BusinessArea|Business Area|Optional|
|TreasuryTradeRequest|Trade Request|Optional|
|Financial Transaction Shows the concluded fiancial transactions to fulfill the trade request including some details for the financial transaction such as the active status of the financial transaction.| | |
|TreasuryTradeRequestUUID|Trade Request UUID|Optional|
|TreasuryTradeRequest|Trade Request|Optional|
|FinTransactionCompanyCode|Company Code|Optional|
|FinTransactionDealIdentifier|Financial Transaction ID|Optional|
|FinancialInstrumentStatus|Status|Optional|
|FinancialTransactionAmount|Financial Transaction Amount|Optional|
|TradedCurrency|Traded Currency|Optional|
|FinancialTransactionLeg|Leg|Optional|
|TrsyFinTransactionBuySellCode|Buy/Sell Code|Optional|


|Property|Description|Necessity **Note:** The necessity of a field varies depending on the action and chosen instrument category. In general, the same rules apply as for the creation of a manual trade request in the Process Trade Requests app.|
|---|---|---|
|OptionPutCallCode|Option Put/Call Code|Optional|
|TradeRequest|Trade Request|Optional|
|Total Amounts of the Trade Request| | |
|TrsyTradeRequestTradedCurrency|Traded Currency|Optional|
|TrsyTrdReqTradedCurrencyName|Traded Currency Name|Optional|
|TrsyTrdReqRequestedAmount|Requested Amount|Optional|
|TrsyTrdReqFulfilledAmount|Fulfilled Amount|Optional|
|TrsyTrdReqRejectedAmount|Rejected Amount|Optional|
|TrsyTrdReqOpenAmount|Open Amount|Optional|
|TrsyTrdReqAverageRate|Average Rate|Optional|
|TrsyTradeRequestLeg2Currency|Leg 2 Currency|Optional|
|TrsyTradeReqLeg2CurrencyName|Leg 2 Currency Name|Optional|
|TrsyTrdReqLeg2RequestedAmount|Leg 2 Requested Amount|Optional|
|TrsyTrdReqLeg2FulfilledAmount|Leg 2 Fulfilled Amount|Optional|
|TrsyTrdReqLeg2RejectedAmount|Leg 2 Rejected Amount|Optional|
|TrsyTrdReqLeg2OpenAmount|Leg 2 Open Amount|Optional|
|TrsyTrdReqLeg2AverageRate|Leg 2 Average Rate|Optional|


**Note:**

To display more information about the properties on the SAP Business Accelerator Hub, open one of the entity's operations and select Model or Schema.

**Supported Operations**

The following operations are supported:

|Operation|Technical Name|Example|
|---|---|---|
|Read|GET - Get all entities from TreasuryTradeRequest GET/TreasuryTradeRequest GET - Get specific entity from TreasuryTradeRequest by key GET/TreasuryTradeRequest/{TradeRequestUUID}|GET <host>/sap/opu/odata4/sap/api_treasurytradere|
|Create|POST/TreasuryTradeRequest - Add new entity to TreasuryTradeRequest|POST <host>/sap/opu/odata4/sap/api_treasurytrader { "TrsyTrdReqInstrumentGroup": "MM", "TreasuryTradeRequestStatus": "C", "CompanyCode": "0001", "TrsyTrdReqInstrumentCategory": "FT", "TrsyTradeRequestDescription": "API", "TrsyTradeReqInvestBorrow": "INVEST", "TrsyTradeReqInterestRateStruc": "0", "NominalAmountInNominalCurrency": 2300.90, "NominalCurrency": "USD", "TrsyTradeReqMinStartDate": "2025-09-13", "TrsyTradeReqMaxStartDate": "2025-09-13", "TrsyTradeReqMinEndDate": "2025-11-13", "TrsyTradeReqMaxEndDate": "2025-11-13", "_AdditionalAttributes": { "FinancialTransactionPortfolio": "1", "TrsyTrdReqExternalReference": "REF400", "FinancialTransactionAssignment": "ASS1", "FinTransInternalReference": "4711" } }|

#### Operations for Treasury Trade Request - Read, Create

> **Path:** APIs for Treasury and Risk Management > Treasury Trade Request - Read, Create > Operations for Treasury Trade Request - Read, Create | L3 | trm12 p.45 | loio `67a82ab8c1d14bbda1f3d78a0d55d6a5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/67a82ab8c1d14bbda1f3d78a0d55d6a5.html?locale=en-US)

|Operation|Technical Name|Example|
|---|---|---|
|Read|GET - Get all entities from TreasuryTradeRequest GET/TreasuryTradeRequest GET - Get specific entity from TreasuryTradeRequest by key GET/TreasuryTradeRequest/{TradeRequestUUID}|GET <host>/sap/opu/odata4/sap/api_treasurytradere|
|Create|POST/TreasuryTradeRequest - Add new entity to TreasuryTradeRequest|POST <host>/sap/opu/odata4/sap/api_treasurytrader { "TrsyTrdReqInstrumentGroup": "MM", "TreasuryTradeRequestStatus": "C", "CompanyCode": "0001", "TrsyTrdReqInstrumentCategory": "FT",|


|Operation|Technical Name|Example|
|---|---|---|
| | |"TrsyTradeRequestDescription": "API", "TrsyTradeReqInvestBorrow": "INVEST", "TrsyTradeReqInterestRateStruc": "0", "NominalAmountInNominalCurrency": 2300.90, "NominalCurrency": "USD", "TrsyTradeReqMinStartDate": "2025-09-13", "TrsyTradeReqMaxStartDate": "2025-09-13", "TrsyTradeReqMinEndDate": "2025-11-13", "TrsyTradeReqMaxEndDate": "2025-11-13", "_AdditionalAttributes": { "FinancialTransactionPortfolio": "1", "TrsyTrdReqExternalReference": "REF400", "FinancialTransactionAssignment": "ASS1", "FinTransInternalReference": "4711" } }|

