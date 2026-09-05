# CDS Views for Treasury and Risk Management - SAP TRM Knowledge Base (branch split)

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

### CDS Views for Treasury and Risk Management (2 of 2)

> **Path:** Treasury and Risk Management > CDS Views for Treasury and Risk Management | L2 | trm01 p.191 | loio `f71f1f5c39374159bb9f07cbc0e05aa2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f71f1f5c39374159bb9f07cbc0e05aa2.html?locale=en-US)

The following table shows the CDS views available for Treasury and Risk Management. Based on the CDS views released, you can create your own query views.

The CDS query views can be used by any tool that supports CDS views, such as SAP Analysis for Microsoft Office, Design Studio, SAP Lumira, or SAP Analytics Cloud. For more information about CDS views, see also CDS Views.

**Note:**

You will find the Treasury Executive Dashboard story as example content in the SAP Analytics Cloud application. The story is based on the available CDS query views for Treasury Management in the back-end system. The following two packages for Treasury and Management are available in SAP Analytics Cloud:

Treasury Management for SAP S/4HANA 2022 and Cloud

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2022 and subsequent releases and SAP S/4HANA Cloud Public Edition.

Treasury Management for SAP S/4HANA 2020

You can use this package in SAP Analytics Cloud based on the back-end systems SAP S/4HANA 2020 and subsequent releases.

The two packages both contain a story for the Treasury Executive Dashboard. The difference is that two CDS views have been replaced with a new version with some technical improvement. The exchange of some CDS views in the package Treasury Management for SAP S/4HANA 2022 and Cloud has improved the performance of the Treasury Executive Dashboard.

For more information, see also Treasury Executive Dashboard Available in SAP Analytics Cloud.

Overview of CDS Views in Treasury and Risk Management

|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|System Data|Treasury Counterparty Limit Utilization Base |I_TrsyCtptyLmtUtilznBase| | |
|System Data|Product Category|I_FinancialInstrProdCat| | |
|System Data|Transaction Category |I_FinInstrTransCat| | |
|System Data|Option Settlement Type |I_OptionSettlementType| |I_OptionSettlementType|
|System Data|Option Exercise Type|I_OptionExerciseType| |I_OptionExerciseTypeTe|
|System Data|Trade Finance Category |I_TradeFinanceCategory| |I_TradeFinanceCategory|
|Transactional Data|Financial Transaction |I_FinancialTransactionDEX|Only for data extraction| |
|System Data|Securities Account Category |I_SecurityAccountCategory| | |
|System Data|Security Class Stock Category |I_SecurityClassStockCategory| | |
|System Data|Security Class Quotation |I_SecurityClassQuotation| | |
|System Data|Listed Derivative Quotation |I_ListedDerivativeQuotation| | |
|System Data|Listed Derivative Category |I_ListedDerivativeCategory| | |
|System Data|Option Put/Call Code |I_OptionPutCallCode| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|System Data|Debt Investment Indicator |I_TrsyCshFlowDebtInvmtCode| | |
|System Data|Fixed Variable Interest Category |I_FixedVariableInterestCat| | |
|Configuration Data|Geographical Center of a Country/Region |I_TrsyFinStsCountryGeoPoint| | |
|System Data|Financial Transaction Processing Category |I_FinTransProcgCategory| |I_FinTransProcgCatego|
|System Data|Financial Instrument Activity Category |I_FinInstrActivityCategory| |I_FinInstrActivityCate|
|System Data|Financial Transaction Flow Category |I_FinTransFlowCategory| |I_FinTransFlowCategory|
|System Data|Financial Condition Condition Category |I_FinCndnConditionCategory| |I_FinCndnConditionCate|
|System Data|Treasury Contract Type |I_TreasuryContractType| |I_TreasuryContractType|
|System Data|Financial Instrument Status |I_FinInstrumentStatus| |I_FinInstrumentStatusT|
|System Data|Financial Transaction Release Status |I_FinTransReleaseStatus| |I_FinTransReleaseStat|
|System Data|Financial Transaction Central Clearing Option |I_FinTransCntrlClrgOption| |I_FinTransCntrlClrgOpt|
|System Data|Financial Transaction Central Clearing Status |I_FinTransCntrlClrgStatus| |I_FinTransCntrlClrgSta|
|System Data|Financial Transaction Confirmation Status |I_FinTransConfStatus| |I_FinTransConfStatusTe|


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|System Data|Financial Transaction Counterconfirmation Status |I_FinTransCntrconfStatus| |I_FinTransCntrconfStat|
|System Data|Financial Transaction Flow Posting Status |I_FinTransFlowPostgStatus| |I_FinTransFlowPostgSta|
|System Data|Status of Interest Rate Adjustment |I_FinIntrstRateAdjmtStatus| |I_FinIntrstRateAdjmtSt|
|System Data|Treasury Payment Request Grouping |I_TreasuryPaytReqGrouping| |I_TreasuryPaytReqGrou|
|System Data|Financial Transaction Direction |I_FinTransactionDirection| |I_FinTransactionDirect|
|System Data|Financial Condition Interest Category |I_FinCndnInterestCategory| |I_FinCndnInterestCateg|
|System Data|Financial Transaction Notice Period Unit |I_FinTransNoticePeriodUnit| |I_FinTransNoticePeriod|
|System Data|Hedging Relationship Scenario |I_TrsyHedgingRelshpScenario| |I_TrsyHedgingRelshpSce|
|Configuration Data|Treasury Valuation Area |I_TreasuryValuationArea| | |
|Configuration Data|Treasury Valuation Class |I_TreasuryValuationClass| | |
|Configuration Data|Security Account Type |I_SecurityAccountType| | |
|Configuration Data|Product Type|I_FinancialinstrProductType| | |
|Configuration Data|Security Class General Classification |I_SecurityClassGenClassfctn| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Configuration Data|Bond Classification|I_BondClassification| | |
|Configuration Data|Security Class Fund Type |I_SecurityClassFundType| | |
|Configuration Data|Transaction Type|I_FinancialInstrTransType| | |
|Configuration Data|Portfolio|I_TreasuryPortfolio| | |
|Configuration Data|Treasury Hedging Classification |I_TreasuryHedgingClassfctn| | |
|Configuration Data|Treasury Account Assignment Reference |I_TreasuryGLAccountAssignRef| | |
|Configuration Data|Treasury Position Management Procedure |I_TrsyPosManagementProcedure| | |
|Configuration Data|Securities Account Group |I_SecurityAccountGroup| | |
|Configuration Data|Market Data: Basis Spread ID |I_MktDataBasisSpreadID| | |
|Configuration Data|Credit Spread ID|I_CreditSpreadID| | |
|Configuration Data|Reference Entity Attribute |I_ReferenceEntity| | |
|Configuration Data|Volatility Name Definition |I_VolatilityName| | |
|Configuration Data|Volatility Profile Information |I_VolatilityProfile| | |
|Configuration Data|Volatility Type|I_VolatilityType| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Configuration Data|Treasury Company Code Additional Data |I_TreasuryCompanyCodeSetting| | |
|Configuration Data|Treasury Counterparty Limit Type |I_TrsyCtptyLimitType| | |
|Configuration Data|Hedging Relationship Profile |I_TrsyHedgingRelshpProfile| |I_TrsyHedgingRelshpPr|
|Configuration Data|Treasury Reversal Reason |I_TreasuryReversalReason| |I_TreasuryReversalRea|
|Configuration Data|Financial Condition Condition Type |I_FinCndnConditionType| |I_FinCndnConditionType|
|System Data|Financial Transaction Flow Posting Blocking Reason |I_FinTransFlowPostgBlkgRsn| |I_FinTransFlowPostgBl|
|Master Data|Financial Status Financial Position |I_FinancialPosition| | |
|Master Data|Financial Status Financial Position Group |I_FinancialPositionGroup| | |
|Master Data|Treasury Security Account |I_SecurityAccount| | |
|Master Data|Security Class|I_SecurityClass| | |
|Master Data|Security Class Bond|I_SecurityClassBond| | |
|Master Data|Security Class Stock|I_SecurityClassStock| | |
|Master Data|Security Class Listed Derivative |I_SecurityClassLstdDerivative| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Master Data|Counterparty|I_Ftr_Counterparty| | |
|Master Data|Treasury Counterparty Limit Business Partner Rating Cube |I_TrsyCtptyLmtBPRatingCube| | |
|Master Data|Treasury Counterparty Limit Business Partner Rating Query |C_TrsyCtptyLmtBPRatingQry| | |
|Master Data|Treasury Market Risk Key Figure Set |I_TrsyMktRskKeyFigureSet| | |
|Master Data|Foreign Exchange Fixing Reference |I_FXFixingReference| |I_FXFixingReferenceTex|
|Transactional Data|Query for Bank Guarantee Overview |C_BankGuaranteeOverviewQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Cube View for Bank Guarantee Overview |I_BankGuaranteeOverview| | |
|Transactional Data|Cube View for Credit Line Utilization |I_CreditLineUtilCube| | |
|Transactional Data|Query for Credit Line Utilization |C_CreditLineUtilQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Financial Transaction |I_FinancialTransaction| | |
|Transactional Data|Treasury Facility Contract |I_FacilityContract| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Transactional Data|Fin. Trans.: Nominal Amount |I_FinTransNominal| | |
|Transactional Data|Fin. Trans.: Interest Information |I_FinTransInterest| | |
|Transactional Data|Fin. Trans.: Securities Information |I_FinTransSecurity| | |
|Transactional Data|Financial Transaction Condition |I_FinTransCondition| | |
|Transactional Data|Fin. Trans. Condition: Single Date |I_FinTransCndnSingleDate| | |
|Transactional Data|Fin. Trans. Condition: Scaled Interest |I_FinTransCndnScale| | |
|Transactional Data|Fin. Trans. Condition: Formula Variable |I_FinTransCndnFmlaVarbl| | |
|Transactional Data|Financial Transaction Flow |I_FinTransFlow| | |
|Transactional Data|Treasury Facility Utilization |I_FacilityUtilization| | |
|Transactional Data|Treasury Position Values Cube |I_TrsyPositionValueCube| | |
|Transactional Data|Hedging Relationship |I_HedgingRelationship| | |
|Transactional Data|Hedged Item|I_HedgedItem| | |
|Transactional Data|Hedging Instrument|I_HedgingInstrument| | |
|Transactional Data|Financial Position Query |C_FinancialPositionQuery|This query view only reports financial positions of financial position groups with| |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
| | | |asset/liability indicator Asset and Liability, defined in the Define Financial Positions app.| |
|Transactional Data|Financial Status Query |C_FinancialStatusQuery|This query view reports all financial positions, defined in the Define Financial Positions app. This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application. (Package Treasury Management for SAP S/4HANA 2020)| |
|Transactional Data|Query View for Maturity Profile |C_MaturityProfileQuery|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Financial Status 2|C_FinancialStatusQuery2|This CDS view provides the same information as the Financial | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
| | | |Status Query view, but uses only one filter for company code, which improves performance. This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application. (Package Treasury Management for SAP S/4HANA 2022 and Cloud)| |
|Transactional Data|Financial Status History 2 |C_HistFinancialStatusQry_2|This CDS view provides the same information as the Financial Status History Query view, but uses only one filter for company code, which improves performance. This query view is consumed in the Treasury Executive Dashboard| |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
| | | |story, which is predefined as example content in the SAP Analytics Cloud application. (Package Treasury Management for SAP S/4HANA 2022 and Cloud)| |
|Transactional Data|Maturity Profile Cash Flow Data Cube |I_MaturityProfileCashFlow| | |
|Configuration|Financial Instrument Product Type Supplement |I_FinInstrProdTypeSuplmnt| | |
|Transactional Data|Financial Transaction Situation |C_FinancialTransactionSitn| | |
|Transactional Data|Financial Transaction General Activity Category |I_FinTransGenActyCategory| |I_FinTransGenActyCateg|
|Transactional Data|Financial Status Cube |I_FinancialPositionCube| | |
|Transactional Data|Treasury Counterparty Limit Overview Cube |I_TrsyCtptyLimitOverviewCube| | |
|Transactional Data|Treasury Counterparty Limit Overview Query |C_TrsyCtptyLimitOverviewQ|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Master Data|Financial Transaction Counterparty (Value Help) |I_FinTransacCounterPartyStdVH| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Configuration Data|Financial Transaction Currency Pair (Value Help) |I_FinTransCurrencyPairVH| | |
|Transactional Data|Financial Transaction Activity |I_FinTransActivity| | |
|Transactional Data|Financial Transaction Current Activity |I_FinTransCurrentActivity| | |
|Transactional Data|Financial Transaction Contract Activity |I_FinTransContractActivity| | |
|Transactional Data|Financial Transaction Amount - Query|C_FinTransAmtQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud solution.| |
|Transactional Data|Fin. Trans. Amt on Single Date - Query |C_FinTransSingleDayAmtQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud solution.| |
|Transactional Data|Fin. Trans.: Histl/Fcstd Fee Amt - Query|C_FinTransFcstHistlFeeQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud solution.| |
|Transactional Data|Fin Trans Histl Fcst Fee - Cube |I_FinTransHistlFcstFeeCube| | |
|Transactional Data|Treasury Financial Object |I_TrsyFinancialObject| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Transactional Data|Treasury Market Risk Key Figure Value Cube |I_TrsyMktRskKeyFigValueCube| | |
|Transactional Data|Treasury Market Risk Key Figure Value Query |C_TrsyMktRskKeyFigValueQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Treasury Value at Risk Query |C_TrsyValueAtRiskQuery|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Transactional Data|Financial Status History - Query |C_HistFinancialStatusQuery|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application. (Package Treasury Management for SAP S/4HANA 2020)| |
|Transactional Data|Bank Guarantee Type |I_BankGuaranteeType| |I_BankGuaranteeTypeTex|
|Transactional Data|Fin. Trans. Amount by Bank Group Query |C_FinTransBusVolBankGrpQry| | |
|Market Data|Market Data Reporting Date Function |I_MKTDATADATEFUNCTION| | |
|Market Data|Market Data Query for FX Rate |C_MktDataFXRateQuery|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content| |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
| | | |in the SAP Analytics Cloud application.| |
|Market Data|Market Data: FX Rate Cube View |I_MktDataFXRateCube| | |
|Configuration Data|Market Data: Currency Pair |I_MktDataCurrencyPair| | |
|Market Data|Market Data Query for Basis Spread |C_MktDataBasisSpreadQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Basis Spread Value Cube View |I_MktDataBasisSpreadCube| | |
|Market Data|Market Data Query for Credit Spread |C_MktDataCreditSpreadQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Credit Spread Value Cube View |I_MktDataCreditSpreadCube| | |
|Market Data|Market Data Query for Reference Interest Rate |C_MktDataRefIntrstRateQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Market Data Cube View for Reference Interest Rate |I_MktDataRefIntrstRateCube| | |
|Market Data|Reference Interest Rate |I_ReferenceInterestRate| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Market Data|Market Data Query for Security Price |C_SecurityPriceQuery|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Market Data: Security Price Cube View |I_SecurityPriceCube| | |
|Market Data|Reference Interest Rate Value |I_ReferenceInterestRateVal| | |
|Configuration Data|Security Exchange|I_SecurityExchange| | |
|Configuration Data|Market Data: Security Price Type |I_SecurityPriceType| | |
|Market Data|Market Data Query for Implied Volatility |C_MktDataImpVolatilityQry|This query view is consumed in the Treasury Executive Dashboard story, which is predefined as example content in the SAP Analytics Cloud application.| |
|Market Data|Implied Volatility Cube View |I_MktDataImpliedVolatilityCube| | |
|Market Data|Historic Exchange Rate Volatility Query |C_HisExchRateVolatilityQry| | |
|Market Data|Historic Exchange Rate Volatility Cube |I_ExchangeRateVolatilityCube| | |
|Market Data|Historic Security Price Volatility Query |C_HisScrtyPrcVolatilityQry| | |
|Market Data|Historic Security Price Volatility Cube |I_ScrtyPrcVolatilityCube| | |


|Data Group|Name|Technical Name|Specific Usage Notes|Technical Name of the Relate|
|---|---|---|---|---|
|Market Data|Historic Interest Rate Volatility Query |C_HistIntRateVolatilityQry| | |
|Market Data|Historic Interest Rate Volatility Cube |I_InterestRateVolatilityCube| | |

