# Risk Management > Basics > Parallel Processing Control - SAP TRM Knowledge Base (branch split)

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

##### Parallel Processing Control

> **Path:** Treasury and Risk Management > Risk Management > Basics > Parallel Processing Control | L4 | trm02 p.41 | loio `2202c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2202c55368511d4be10000000a174cb4.html?locale=en-US)

**Use**

This function allows you, as you require, to distribute to several different servers the evaluations in Market Risk Analysis, the simulations of the Strategic Analyzer, and all reports on utilizations (in end-of-day processing) in the Default Risk and Limit System. This increases the efficiency of your system.

**Note:**

When parallel processing control is active, no detail log is generated for those single value analyses that generate logs.

Prerequisites

You need to have already activated one or more servers for your SAP system. You can display a list of servers under Tools

Administration Administration Network RFC Destinationsunder Internal connections Choose RFC RFC groups to be able to bundle the servers into groups.

**Activities**

- 1. Enter your user name and the evaluation type (field ET).
- 2. Set the indicator Multi-tasking to active.
- 3. Specify the Package size.
- 4. In the field Max no. tasks , you can restrict the burden for each server group.
- 5. In the Server group field, enter a group of servers that you want to use to process the tasks of the evaluation in parallel.
- 6. Choose Save .



**Note:**

You can display the active servers of your SAP system and the tasks that are currently running on them under Tools

Administration Monitor System Monitoring Servers. For further information see also: Displaying the Status of the Application Server .

**Recommendation:**

If you use the Default Risk and Limit System, read the section Parallel Processing in the Default Risk and Limit System .

