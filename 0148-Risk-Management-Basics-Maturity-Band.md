# Risk Management > Basics > Maturity Band - SAP TRM Knowledge Base (branch split)

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

##### Maturity Band

> **Path:** Treasury and Risk Management > Risk Management > Basics > Maturity Band | L4 | trm02 p.36 | loio `0402c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0402c55368511d4be10000000a174cb4.html?locale=en-US)

**Definition**

A maturity band defines the sequence of time periods and governs in which time periods the results of evaluations are shown.

**Use**

Maturity bands play an important role in NPV analysis and particularly in gap analysis. In NPV analysis, the cash flows for which NPVs have been calculated are distributed over time using maturity bands. In gap analysis, maturity bands are used to distribute positions and outflows.

The payments are displayed in a table and according to the generated maturity band dates. For each maturity band date, the system displays the payments that belong to this date and to the period between the last maturity band date and this maturity band date.

You distinguish between the following maturity bands according to the creation mode:

[figure TRM02-F035 - Absolute maturity bands have a fixed start date. If the evaluation date is after the end of the time interval determined by the maturity band, then the system displays only the entry for the evaluation date.]

Absolute maturity bands have a fixed start date. If the evaluation date is after the end of the time interval determined by the maturity band, then the system displays only the entry for the evaluation date.

Relative maturity bands do not have a start date. Instead, the period pattern defined by the maturity band is generated with reference to another date.

In net present value evaluations , the maturity band is generated relative to the evaluation date .

In gap and ALM evaluations , the maturity band is generated relative to the horizon .

**Note:**

Starting on May 10, 1999 you want to analyze your data on the following key dates:

Daily evaluations up to May 31, 1999

Monthly evaluations up to December 31, 1999

Annual evaluations up to December 31, 2002

###### Editing the Maturity Band

> **Path:** Treasury and Risk Management > Risk Management > Basics > Maturity Band > Editing the Maturity Band | L5 | trm02 p.37 | loio `0702c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0702c55368511d4be10000000a174cb4.html?locale=en-US)

- 1. Choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Asset/Liability Management Evaluation Control Define and Set Up Maturity Band .
- 2. Choose the activity Maturity Band.


- 3. To create a new maturity band choose Create Maturity Band.

In the Maturity Band field enter a four-character abbreviation, in the Maturity Band Start Date field enter the start of the maturity band, enter the Generation Mode and a Short Name and a Long Name for the new maturity band.

- 4. The generation mode you selected governs whether the fields for the maturity band parameters are displayed when you choose enter, or whether the maturity band entries are displayed directly.

For relative maturity bands define the maturity band parameters:

Time unit and increment

In doing so you define the time periods of the required evaluation for the respective part of the maturity band.

Number

By entering the number, you define the time range for this part of the maturity band.

Fill

Here you define whether the unit valid for this part of the maturity band should be filled up to a particular date.


Either specify the Number or choose Fill.

For absolute maturity bands you provide the maturity band entries.

- 5. Choose Save.



Result

The maturity band has been created. You can display the date entries in the maturity band by choosing Calculate Maturity Band. Once you have saved the maturity band you cannot change its generation mode.

