# Transaction Manager > BAPIs for the Transaction Manager - SAP TRM Knowledge Base (branch split)

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

#### BAPIs for the Transaction Manager

> **Path:** Treasury and Risk Management > Transaction Manager > BAPIs for the Transaction Manager | L3 | trm09 p.323 | loio `4ebbac42e50c657fe10000000a42189b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4ebbac42e50c657fe10000000a42189b.html?locale=en-US)

**Use**

The standardized interfaces known as Business Application Programming Interfaces (BAPIs) turn SAP applications into open systems that let you exchange data across system boundaries.

For more information about using and setting up BAPIs, see Cross-Application Components Business Framework Architecture (CA-BFA) .

Choose Tools Business Framework Business Explorer (transaction BAPI). The BAPI Explorer appears. The navigation area appears on the left. On the Hierarchical tab, choose Financials Financial Supply Chain Management . Here you find all business objects for Treasury and Risk Management as well as the documentation on the business objects and methods.

When you double-click a business object, it opens on the right of the screen.

**Features**

In the Transaction Manager, you can use the following business objects:

In the Area of Transaction Management

You can use the following specific business objects to enter financial transactions:

BUS5510 FixedTermDeposit (Fixed-Term Deposit)

BUS5520 DepositAtNotice (Deposit at Notice)

BUS5530 CommercialPaper (Commercial Paper)

BUS5540 CashFlowTransaction (Cash Flow Transaction)

BUS5550 InterestRateInstrument (Interest Rate Instrument)

BUS5600 ForeignExchange (Foreign Exchange Transaction)

BUS5610 OTCInterestCapFloor (OTC Option CAP or FLOOR)

BUS5620 OTCInterestSwap (Interest Rate Swap)

BUS5630 OTCInterestFRA (Forward Rate Agreement)

BUS5760 FXOption (Currency Option)

BUS5700 Future (Future)

BUS5200 SecurityTransaction (Security Transaction)

BUS5580 CurAcctStyleInstr (Current Account-Style Instrument)

BUS5850 LetterOfCredit (Letter of Credit)

BUS5860 BankGuarantee (Bank Guarantee)

There are also some general business objects that can be used for all financial transactions:

BUS2042 FinancialTransaction (Financial Transaction)

General business object with which you can run the following methods for all financial transactions:

Counterconfirm Financial Transaction

List of Financial Transactions

Determine Changed Fields for General Contract Data

Settle Financial Transaction

- BUS5101 FTRAdditionalFlow (Additional Flows)


For entering, changing, deleting, and displaying additional flows for financial transactions.

- BUS5102 FTRCondition (Conditions)

For entering, changing, deleting, and displaying conditions for financial transactions.

- BUS5103 FTRPaymentDetail (Payment Details)


For entering, changing, deleting, and displaying payment details.

Using BAPI_FTR_CREATE_FXCOLLAR you can create FX collar options.

In the Area of Master Data

BAPIs for creating, changing, and displaying class data. These BAPIs enable you to manage securities class data more easily and efficiently and to keep them up to date:

BUS1076 FinancialProduct

BUS1074 RedemptionSchedSet

BUS1064 RedemptionFactors

BUS1062 ExtSecurityAccStmnt (External Securities Account Statement)

See also:BAPIs for Hedge Accounting for Exposures

