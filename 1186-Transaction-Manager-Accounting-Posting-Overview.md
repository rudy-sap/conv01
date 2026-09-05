# Transaction Manager > Accounting > Posting Overview - SAP TRM Knowledge Base (branch split)

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

##### Posting Overview

> **Path:** Treasury and Risk Management > Transaction Manager > Accounting > Posting Overview | L4 | trm08 p.190 | loio `7015da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7015da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Using the posting overview function, you can generate a list of all the flows posted for selected transactions.

A list is displayed that contains information on the underlying financial transactions and the related flow data, as well as the document numbers of the postings, where appropriate.

By making the appropriate selections, you can sort the list according to business partners.

You can also double-click to go to the basic data screen of a financial transaction.

In the Transaction Data area , you branch to the display screen for the individual transaction.

In the Posting Data area, you can branch directly to the display screen for the individual posting document, provided that the FI document number is displayed.

**Activities**

- 1. Choose Posting Overview.
- 2. If you select the Sort by Counterparty field in the Further Selections area, the system sorts the list by business partner.
- 3. Enter your criteria to select the transactions you require and their related flows.
- 4. Choose Program Execute.
- 5. The system displays a list of the transactions you selected.


From here, you can branch to the basic data. By making selections in the Transaction Data area, the transaction concerned is displayed. Via Posting Data, you can display a single posting document provided the selected flow has already been posted. You can see if a flow has already been posted when the corresponding FI document number is displayed in the list. The posting key and posting release will also provide you with more information on the transaction:

**Example:**

Posting status and posting release:

|Posting status (PS)|Description|Posting release(Re)|Description|
|---|---|---|---|
|1|Flagged for posting|X|Yes|


|Posting status (PS)|Description|Posting release(Re)|Description|
|---|---|---|---|
|2|Posted| | |
|3|Posting flagged for reversal| | |
|4|Posting reversed| | |

