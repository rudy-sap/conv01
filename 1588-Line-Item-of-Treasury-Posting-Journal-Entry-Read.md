# Line Item of Treasury Posting Journal Entry - Read - SAP TRM Knowledge Base (branch split)

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

### Line Item of Treasury Posting Journal Entry - Read

> **Path:** APIs for Treasury and Risk Management > Line Item of Treasury Posting Journal Entry - Read | L2 | trm12 p.9 | loio `a5c19312428b4fa7a956fbbf88440f44` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/a5c19312428b4fa7a956fbbf88440f44.html?locale=en-US)

Technical name: API_TRSYPOSTGJRNLENTRITM_SRV

This synchronous inbound service enables you to read line items of treasury posting journal entries to get detailed accounting information on the posted and reversed flows of financial transactions and treasury positions.

It is based on the OData protocol and can be consumed in Fiori apps and on other user interfaces.

This service is published on the SAP Business Accelerator Hub. For more information about APIs, see APIs on SAP Business Accelerator Hub.

**Service Structure**

The service contains header, item, and account assignment data.

Service Message Header

The service message header contains information on the service, the sender and receiver involved, and the date and time.

Entities

The entities contain the business data of the service.

|Entity|Description|Link to details|
|---|---|---|
|Treasury Posting Journal Entry (A_TrsyPostgJrnlEntrItm)|Line Item of Treasury Posting Journal Entry|Treasury Posting Journal Entry|


**Service Response**

The details of an API response are according to the operation types that are supported. For more information, see Operations for Treasury Posting Journal Entry - Read.

**Authorization Details**

The following authorization objects are required for this service:

T_DEAL_PD

Authentication Method

Basic authentication: X.509 certificate (X509 Token)

**Activate and Maintain Service**

The transaction for activating and maintaining services is used to maintain all registered services on the SAP Gateway server (hub system) and to register and activate services. For more information, see Activate and Maintain Services.

**Error Handling**

The error log facilitates easy navigation to the affected source code where you can make the necessary corrections. For more information, see Error Log.

**Additional Information**

On the SAP Business Accelerator Hub, on the Schema View tab for this API, you can see generated examples for creating and updating line items of treasury posting journal entries, please note that these operations are not available for this API.

#### Treasury Posting Journal Entry

> **Path:** APIs for Treasury and Risk Management > Line Item of Treasury Posting Journal Entry - Read > Treasury Posting Journal Entry | L3 | trm12 p.10 | loio `3b253b54e5a34d9d9775dc75cbdfa88e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/3b253b54e5a34d9d9775dc75cbdfa88e.html?locale=en-US)

Lists all fields available for the Line Item of Treasury Posting Jounal Entry - Read inbound service (API_TRSYPOSTGJRNLENTRITM_SRV)

Technical name: A_TrsyPostgJrnlEntrItm

Field List of Entitiy A_TrsyPostgJrnlEntrItm of API_TRSYPOSTGJRNLENTRITM_SRV Inbound Service

|Property|Description|Necessity|
|---|---|---|
|TrsyAccountingDocumentUUID|Treasury accounting document identifier|Optional|
|AccountingDocumentItemRef|Accounting document line item number|Optional|
|TrsyPositionContextUUID|Treasury position context identifier|Optional|
|TreasuryBusinessTransStatus|Status of a Treasury business transaction|Optional|
|TreasuryBusTransStatusName|Name of the status of a business transaction|Optional|
|TreasuryUpdateType|Treasury update type|Optional|
|TreasuryUpdateTypeName|Name of an update type|Optional|
|IsUsedInPaymentTransaction|Indicator: Is posting key used in a payment transaction?|Optional|
|TreasuryGLAccountAssignmentRef|Account assignment reference of the Treasury position management|Optional|
|TreasuryGLAccountAssignRefName|Name of an account assignment reference of the Treasury position management|Optional|
|TreasuryPostingCategory|The Treasury posting category defines the type and currency of a posting|Optional|
|TreasuryPostingCategoryName|Name of a posting category|Optional|
|TreasuryGLAccountSymbol|G/L account symbol for G/L account assignment reference|Optional|


|Property|Description|Necessity|
|---|---|---|
|TreasuryGLAccountSymbolName|Name of G/L account symbol for G/L account assignment reference|Optional|
|PostingKey|Posting key|Optional|
|PostingKeyName|Name of posting key|Optional|
|GLAccount|G/L account number. A G/L account stores changes in value relating to assets, payables, stockholders' equity, revenues, or expenses of a company.|Optional|
|PositionCurrency|Currency of a Treasury position|Optional|
|AmountInPositionCurrency|Amount in position currency|Optional|
|CompanyCodeCurrency|Local currency|Optional|
|AmountInCompanyCodeCurrency|Amount in company code currency with +/signs|Optional|
|TreasuryTransactionFlow|Treasury: Number of a distributor flow|Optional|
|AccountingDocument|Accounting document number|Optional|
|ReverseDocument|Reverse document number|Optional|
|JournalEntryType|Journal entry type|Optional|
|AccountingDocumentTypeName|Accounting document type name|Optional|
|PaymentDate|Payment date|Optional|
|Customer|Customer|Optional|
|PaymentTerms|Payment terms|Optional|
|PaymentMethod|Method of payment|Optional|
|PaymentMethodName|Payment method name|Optional|
|PaymentMethodSupplement|Payment method supplement|Optional|
|PaymentMethodSupplementName|Name of payment method supplement|Optional|
|PaymentBlockingReason|Payment block key|Optional|
|PaymentBlockingReasonName|Reason for payment block|Optional|
|PayerPayeeFullName|Full name of a payer / payee|Optional|
|HouseBank|House bank - The main bank used for dayto-day transactions|Optional|
|StateCentralBankPaymentReason|Payment reason code for state central bank reporting|Optional|
|SupplyingCountry|Supplying country/region|Optional|
|CountryName|Country/region name|Optional|


|Property|Description|Necessity|
|---|---|---|
|AssignmentReference|The assignment number is an additional information reference field in the line item. You can either enter the field contents manually, or have the system define them automatically in the master record via the sort key field.|Optional|
|JournalEntryItemText|Journal entry item text|Optional|
|BusinessArea|Business area|Optional|
|BusinessAreaName|Business area description|Optional|
|CostCenter|Cost center|Optional|
|FinancialTransactionType|Entry for a transaction type|Optional|
|FinancialTransactionTypeName|Financial transaction type name|Optional|
|PartnerCompany|Partner company ID|Optional|
|CompanyName|Company name|Optional|
|Counterparty|Counterparty number|Optional|
|CounterpartyFullName|Name of a counterparty|Optional|
|Issuer|Issuer identity key|Optional|
|IssuerFullName|Name of an issuer|Optional|
|SpecialGLCode|Special G/L indicator|Optional|
|SpecialGLCodeName|Short text for special G/L indicator|Optional|
|TreasuryBusinessTransaction|Identifier of a business transaction in parallel valuation areas|Optional|
|TreasuryValuationArea|Treasury subledger to value financial transactions according to a specific accounting regulation|Optional|
|TreasuryValuationAreaName|Name of valuation area|Optional|
|ReferenceDocument|Document No. of a reference document|Optional|
|ReferenceDocumentContext|Reference document organizational units|Optional|
|PostingDate|Posting date|Optional|
|FiscalPeriod|Fiscal period (synonyms are: Posting period, Accounting period)|Optional|
|FiscalYear|Fiscal year|Optional|
|ReversalReferenceDocument|Reversal: Reverse document reference document number|Optional|
|ReversalReferenceDocumentCntxt|Reversal: Reverse document reference organization|Optional|


|Property|Description|Necessity|
|---|---|---|
|ReverseDocumentPostingDate|Posting date of reverse document|Optional|
|ReverseDocumentFiscalPeriod|Fiscal period of reverse document|Optional|
|ReverseDocumentFiscalYear|Fiscal year of reverse document|Optional|
|Ledger|Ledger|Optional|
|DocumentDate|Document date|Optional|
|AccountingPrinciple|Accounting principle|Optional|
|TreasuryAcctgPostingCategory|Update to financial accounting category|Optional|
|TreasuryBusinessTransCategory|Category of a business transaction in parallel valuation areas|Optional|
|TreasuryBusTransCategoryName|Name of business transaction category|Optional|
|DocumentHeaderText|Document header text|Optional|
|DocumentReferenceID|Reference document number. Alternative number of a document for search and alternative identification. Use ExternalAcountingDocReference instead|Optional|
|FinancialInstrValuationClass|Financial instrument valuation class|Optional|
|FinancialInstrValClassName|Name of a financial instrument valuation class|Optional|
|TreasuryValuationClass|Valuation area according to a specific accounting regulation used in a Treasury financial subledger|Optional|
|TreasuryValuationClassName|Name of a valuation area|Optional|
|CompanyCode|Company code|Optional|
|FinancialInstrumentProductType|Product type of a financial instrument (e.g. Fixed-Term Deposit)|Optional|
|FinancialInstrProdTypeName|Name of a product type of a financial instrument|Optional|
|SecurityAccount|The securities account ID is related to a securities account kept at a bank|Optional|
|SecurityAccountName|Name of a securities account which is related to a securities account kept at a bank|Optional|
|SecurityClass|Security or listed derivative. It can, for example, correspond to an official security ID number.|Optional|
|SecurityClassName|Name of a security or listed derivative|Optional|
|SecurityClassDescription|Description of a security or listed derivative|Optional|


|Property|Description|Necessity|
|---|---|---|
|DifferentiationPortfolio|Portfolio acting as differentiation criterion of the position|Optional|
|DifferentiationPortfolioName|Name of the portfolio acting as differentiation criterion|Optional|
|SecurityAccountGroup|Group of securities accounts which are related to a securities account kept at banks|Optional|
|SecurityAccountGroupName|Name of a group of securities accounts|Optional|
|LoanContract|Unique number that identifies a contract (loan, lease-out, ...).|Optional|
|LoanContractName|Name of a loan contract|Optional|
|TreasuryPositionAccount|Account for listed options and futures at a bank|Optional|
|TreasuryPositionAccountName|Name of an account for listed options and futures|Optional|
|TreasuryPositionLongShortCode|Code indicating if position is Long or Short|Optional|
|Fund|Funds represent financial resources that are provided for a specific purpose by a sponsor and managed separately. This enables the exact source of the funds to be determined.|Optional|
|GrantID|Grant|Optional|
|CentralClearingAccount|Central clearing account|Optional|
|CentralClearingAccountName|Name of a central clearing account|Optional|
|ActivityFinancialTransaction|Financial transaction which triggers an activity|Optional|
|FinancialTransaction|Financial transaction|Optional|
|TreasuryAccountingCode|Accounting code, it has a 1:1 relation to a company code. It is needed in Treasury because it is the basis for the authority concept.|Optional|
|CreatedByUser|User ID of the creator of an SAP object (node)|Optional|
|CreationDate|Creation date|Optional|
|LastChangedByUser|Identifier of user who changed/updated the data entry last time|Optional|
|LastChangeDate|Last change date|Optional|
|GLAccountLongName|G/L account long name|Optional|
|CostCenterName|Cost center name|Optional|


|Property|Description|Necessity|
|---|---|---|
|FinancialInstrTransactionType|Type of transaction which can be carried out on a financial instrument of a certain financial instrument product type|Optional|
|FinancialInstrTransTypeName|Name of a financial instrument transaction type|Optional|
|FinancialInstrCharacteristic|Financial instrument free characteristic|Optional|
|FinancialInstrumentReference|Financial instrument free reference|Optional|
|FinancialInstrumentAssignment|Financial instrument: Generic customer defined assignment|Optional|
|Portfolio|A collection or a sample of assets, documents, samples or responsibilities|Optional|
|LetterOfCredit|Letter of credit|Optional|
|HedgingClassification|Hedging classification of a financial instrument|Optional|
|HedgingClassificationName|Name of the hedging classification|Optional|
|FinancialExposureItem|The financial exposure items represent the exposures of an analysis item and are saved on the database. Financial exposure items are created using a snapshot functionality.|Optional|
|FinancialExposureItemName|Name of a financial exposure item|Optional|
|FinancialExposureSubItem|The financial exposure subitem is a position which is needed when you use the automated exposure item hedging process for hedge accounting. It represents a valuation area specific hedged portion of the financial exposure item.|Optional|
|FinancialExposureSubItemName|Name of a financial exposure subitem|Optional|
|TrsyPosCustomDiffntnTerm1|Custom differentiation term 1 (value)|Optional|
|TrsyPosCustomDiffntnTerm1Name|Name of custom differentiation term 1 for Treasury positions|Optional|
|TrsyPosCustomDiffntnTerm2|Custom differentiation term 2 (value)|Optional|
|TrsyPosCustomDiffntnTerm2Name|Name of custom differentiation term 2 for Treasury positions|Optional|
|TrsyPosCustomDiffntnTerm3|Custom differentiation term 3 (value)|Optional|
|TrsyPosCustomDiffntnTerm3Name|Name of custom differentiation term 3 for Treasury positions|Optional|
|TrsyPosCustomDiffntnTerm4|Custom differentiation term 4 (value)|Optional|
|TrsyPosCustomDiffntnTerm4Name|Name of custom differentiation term 4 for Treasury positions|Optional|


|Property|Description|Necessity|
|---|---|---|
|TrsyPosCustomDiffntnTerm5|Custom differentiation term 5 (value)|Optional|
|TrsyPosCustomDiffntnTerm5Name|Name of custom differentiation term 5 for Treasury positions|Optional|
|DifferentiationCostCenter|Cost center acting as differentiation criterion of the position|Optional|
|WBSElementExternalID|WBS element|Optional|
|WBSDescription|Description of the WBS element|Optional|
|ProfitCenter|Profit center|Optional|
|FunctionalArea|Functional area|Optional|

#### Operations for Treasury Posting Journal Entry - Read

> **Path:** APIs for Treasury and Risk Management > Line Item of Treasury Posting Journal Entry - Read > Operations for Treasury Posting Journal Entry - Read | L3 | trm12 p.16 | loio `fc619e10ef45404d951f69efeb2d0bfd` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/fc619e10ef45404d951f69efeb2d0bfd.html?locale=en-US)

The Line Item of Treasury Posting Journal Entry - Read API offers these operations:

|Operation|HTTP Method|Sample URL|
|---|---|---|
|Get|GET|GET <host>/sap/opu/odata/sap/API_TRSYPOSTGJRNLENTRITM_SRV/A_TrsyPostgJrnlEntrItm|

