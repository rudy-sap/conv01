# APIs for Treasury and Risk Management - SAP TRM Knowledge Base (branch split)

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

## APIs for Treasury and Risk Management

> **Path:** APIs for Treasury and Risk Management | L1 | trm12 p.1 | loio `325f953a5fb54319921538882b015b5a` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/325f953a5fb54319921538882b015b5a.html?locale=en-US)

**APIs for Treasury and Risk Management**

The following table contains all APIs available in Treasury and Risk Management. You can filter them according to various criteria.

Overview of APIs in Treasury and Risk Management

|Name|Technical Name|Type|Application Component|
|---|---|---|---|
|Treasury Position Flows Read |API_TRSYPOSFLOW_SRV|OData V2|Treasury and Risk Management|
|Line Item of Treasury Posting Journal Entry - Read |API_TRSYPOSTGJRNLENTRITM_SRV|OData V2|Treasury and Risk Management|
|Foreign Exchange Exposure|API_FXEM_FXEXPOSURE|OData V4|Treasury and Risk Management|
|Treasury Trade Request Read, Create |API_TREASURYTRADEREQUEST|OData V4|Treasury and Risk Management|
|Financial Transaction Net Present Value |API_FINTRANSACTIONNPV|OData V4|Treasury and Risk Management|

