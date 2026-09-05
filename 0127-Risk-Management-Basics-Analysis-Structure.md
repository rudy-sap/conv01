# Risk Management > Basics > Analysis Structure - SAP TRM Knowledge Base (branch split)

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

##### Analysis Structure

> **Path:** Treasury and Risk Management > Risk Management > Basics > Analysis Structure | L4 | trm02 p.3 | loio `ec01c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ec01c55368511d4be10000000a174cb4.html?locale=en-US)

**Definition**

In risk management, the analysis structure is the organizational unit used to analyze and control risks in businesses. The analysis structure is the highest-level organizational and evaluation unit in risk analysis. The analysis structure contains the analysis characteristics. These characteristics are your evaluation criteria. Your portfolio hierarchies are based on the characteristics belonging to the analysis structure. A portfolio hierarchy organizes the characteristics into a hierarchy and defines the aggregation levels at which the valuations are carried out.

The following kinds of analysis structures exist in the system:

Static Analysis Structure

For the static analysis structure, SAP delivers the analysis characteristics. These characteristics are your evaluation criteria. The following characteristics are predefined:

Business Partner Number

Trader

Contract Type

Product Category

Product Type

Security Class

Securities Account

Futures Account

Currency

Portfolio

Country/Region Key

Financial Transaction

Loans Contract Number

Exposure Position ID

Characteristics

Your portfolio hierarchies must be based on the characteristics belonging to the static analysis structure.

Generated Analysis Structure

For the generated analysis structure, you must define the analysis characteristics. In addition to using the characteristics that are predefined in the standard system, you can define characteristics of your own.

The characteristics predefined in the system are listed in a field catalog. The analysis structure comprises all characteristics.

In the same way, you can also define structures for the characteristic values. These structures are known as characteristic hierarchies and affect the layout of reports.

For VaR analysis, a standard risk hierarchy is assigned to every hierarchy node in a portfolio hierarchy. The valuation results for a portfolio hierarchy node are displayed according to the risk factors in the risk hierarchy.

**Note:**

The analysis structure and the segment-level characteristics are defined in Customizing, whereas portfolio hierarchies and characteristics hierarchies are all defined within the application.

**Analysis Structure Selection**

In the Customizing activity Select Analysis Structure Category, you can choose to use the generated analysis structure, the static analysis structure, or both together.

If you choose the the static analysis structure, the system switches from the generated to the static analysis structure.

The static analysis structure is now relevant for the functions available in the Market Risk Analyzer.

If a generated analysis structure was previously active, the existing financial objects and results database data can no longer be used after you have switched to the static structure. For this reason, execute the following steps after you have switched to the static analysis structure:

- 1. Regenerate the financial objects for the different kinds of financial instrument.

Use the regeneration functions available in the area menu under Market Risk Analyzer Tools Reorganization Tools Financial Object Financial Object Integration .

- 2. In addition, you can delete the obsolete single record data stored in the results database using the Delete/Reorganize Single Record Procedures (Market Risk) function (transaction RASRPDEL).
- 3. Under Edit Segment-Level Characteristics, you specify for the static analysis structure which characteristics are used to form segments. You specify these characteristics for an analysis structure and a certain client. Segments are internal keys that describe combinations of characteristic values. In many


**Note:**

SAP recommends that you delete the data to free up memory space.

functions, they are used instead of the original characteristic values. Key figures in the results database are stored by segment, for example.

Make the settings for the static analysis structure.

4. Define your portfolio hierarchies in the area menu under Market Risk Analyzer Evaluation Control Portfolio Hierarchy Define using the transaction Define Portfolio Hierarchy (transaction AFWPH) if you want to use the apps for online calculation or the Analyzer Information System using the results database.

If you haven't used financial object integration so far and you now start with the static analysis structure in Risk Management, you must do the following:

- 1. You must set up financial object integration.
- 2. Under Edit Segment-Level Characteristics, you specify for the static analysis structure which characteristics are used to form segments. You specify these characteristics for an analysis structure and a certain client. Segments are internal keys that describe combinations of characteristic values. In many functions, they are used instead of the original characteristic values. Key figures in the results database are stored by segment, for example.

Make the settings for the static analysis structure.

- 3. Define your portfolio hierarchies in the area menu under Market Risk Analyzer Evaluation Control Portfolio Hierarchy Define using the transaction Define Portfolio Hierarchy (transaction AFWPH) if you want to use the apps for online calculation or the Analyzer Information System using the results database.
- 4. If you have existing financial instruments in the system, you must generate the financial objects for the different kinds of financial instrument.


Use the generation functions available in the area menu under Market Risk Analyzer Tools Reorganization Tools Financial Object Financial Object Integration .

The Generated Analysis Structure is the default setting. If you want to keep the generated analysis structure, do not change this setting.

**Note:**

If you choose this setting, you can't use the functions that are only available for the static analysis structure:

Manage Market Risk Key Figure Sets (transaction AFWKF_SET)

Calculate Market Risk Key Figures report (transaction RAEP1_KFSET)

CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery)

Reorganization Tools Financial Object Financial Object Integration .

If you choose the setting Generated and Static Analysis Structure, the generated analysis structure is still active. This means that the generated analysis structure is still relevant for the functions that calculate key figures online and for the results database functions.

However, you can also use functions that are only available for the static analysis structure, which exists in addition to the generated analysis structure:

Manage Market Risk Key Figure Sets (transaction AFWKF_SET)

Calculate Market Risk Key Figures report (transaction RAEP1_KFSET)

CDS query views Treasury Market Risk Key Figure Value Query (C_TrsyMktRskKeyFigValueQry) and Treasury Value at Risk Query (C_TrsyValueAtRiskQuery)

If you have already used Risk Management with the generated analysis structure, perform the following step after you have switched to using the generated and the static analysis structure:

Regenerate the financial objects for the different kinds of financial instrument. Use the generation functions available in the area menu under Market Risk Analyzer Tools Reorganization Tools Financial Object Financial Object Integration

.


As a result, for each financial instrument, the financial object now also contains the characterictics of the static analysis structure. If you use functions for displaying or processing financial objects, you can now switch between displaying the financial object data for the generated analysis structure and displaying it for the static analysis structure.

Reorganization Tools Financial Object Financial Object Integration .

As a result, for each financial instrument, the financial object contains the characteristics of the static analysis structure and also the charateristics of the generated analysis structure. If you use functions for displaying or processing financial objects, you now can switch between displaying the financial object characteristics for the generated analysis structure and displaying them for the static analysis structure in the Analysis Characteristics data group on the Analysis (RM) tab.

###### Editing Characteristic Values

> **Path:** Treasury and Risk Management > Risk Management > Basics > Analysis Structure > Editing Characteristic Values | L6 | trm02 p.7 | loio `ef01c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ef01c55368511d4be10000000a174cb4.html?locale=en-US)

**Caution:**

When you edit the characteristic values of a characteristic that is verified against a check table. Bear in mind that by changing the characteristic values, you are changing entries in the central SAP tables (for example, the characteristic Country/Region is checked against table T005).

- 1. Choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Master Data Characteristic Values Edit .

The system now displays a list of all characteristics in the active analysis structure.

- 2. Select a characteristic and choose Change.


The system displays the table for maintaining the values of the characteristic you have chosen.

- 3. Edit the values (for example, change the description, delete, copy, or add characteristic values) and choose Save.



Result

You have edited the characteristic values for the characteristic you selected.

###### Characteristics Hierarchy

> **Path:** Treasury and Risk Management > Risk Management > Basics > Analysis Structure > Characteristics Hierarchy | L6 | trm02 p.7 | loio `f201c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f201c55368511d4be10000000a174cb4.html?locale=en-US)

Definition

A characteristics hierarchy organizes the characteristic values into a hierarchy. By defining a characteristics hierarchy you are able to have a better overview of characteristics with many values.

**Use**

Characteristics hierarchies are used in the following instances:

In portfolio hierarchies (structured evaluations) .

Characteristics hierarchies can be combined with a portfolio hierarchy. Structured evaluations using portfolio hierarchies form the basis of the pre-defined report types NPV analysis, value at risk analysis, gap analysis, and P + L analysis.

In evaluations covering all characteristics in an analysis structure (generic or multi-dimensional evaluations) .

Characteristics hierarchies can be integrated into a report. The generic evaluations are based on the report types generated per analysis structure. They allow you to navigate freely through the data cube constructed by the characteristics and characteristic values. In this multi-dimensional data cube, you can integrate the characteristics hierarchies as structure items.

**Examples**

[figure TRM02-F004]

[figure TRM02-F005]

###### Editing Characteristic Hierarchies

> **Path:** Treasury and Risk Management > Risk Management > Basics > Analysis Structure > Characteristics Hierarchy > Editing Characteristic Hierarchies | L7 | trm02 p.9 | loio `f501c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f501c55368511d4be10000000a174cb4.html?locale=en-US)

- 1. Choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Master Data Characteristics Hierarchy Edit .

The system displays the Specify Report Type dialog box . Choose a report type. Using the report type, you access only a selection of the characteristics. The characteristics hierarchies are, however, valid for report types other than the report type chosen here.

- 2. In the left part of the screen, choose a characteristic for which you would like to edit a hierarchy, and enter an ID for the hierarchy variant.
- 3. Choosing or takes you directly to the maintenance screen for the hierarchy structure. If you want to create a new hierarchy, you first have to maintain the following hierarchy attributes:




- a. Enter a short description for the characteristics hierarchy.
- b. If required, indicate that the characteristics hierarchy is visible system-wide. Setting the Visible System-Wide indicator allows you to use the characteristics hierarchy in other components of the SAP system as well.
- c. Choose Hierarchy.
- d. Define the nodes of the characteristics hierarchy by entering a short and long description.
- e. Choose Save.


**Note:**

Occasionally, when the Visible System-Wide indicator is selected, errors occur when the analysis structure is transported.

Recommendation: Do not set the indicator.

**Note:**

Because end nodes are at the lowest level of the characteristics hierarchy, they have to be characteristic values.


**Result**

The characteristics hierarchy is ready for use in the evaluations. If, after you have defined the characteristics hierarchy, you create new characteristic values for the characteristics used there, you must not enter these manually. These additional values are automatically displayed as individual nodes in the characteristics hierarchy during evaluations.

###### Translating Characteristic Hierarchies

> **Path:** Treasury and Risk Management > Risk Management > Basics > Analysis Structure > Characteristics Hierarchy > Translating Characteristic Hierarchies | L7 | trm02 p.10 | loio `f801c55368511d4be10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f801c55368511d4be10000000a174cb4.html?locale=en-US)

Using this function, you can translate all language-dependent texts in a characteristics hierarchy. The source language is the original language.

**Procedure**

- 1. Call the Translate Risk Hierarchies function (transaction JBHTL).

The system displays the Choose Languages dialog box.

- 2. Select a source language and a target language.
- 3. Choose Continue.

A list showing all characteristics is displayed.

- 4. You can select individual characteristics by marking them.
- 5. Choose Choose.

You reach a list screen displaying all of the texts for the selected characteristics available for translation. You will see the following information:

Object type

Text in the source language

Text in the target language

Object name

- 6. Select the texts and choose Translate.

You reach the SAP translation tool with which you can enter the texts in the target language next to the texts in the source language.

- 7. Choose Save.


**Result**

If you open a session in the target language, the translated text elements are displayed.

###### Editing Characteristic Derivations

> **Path:** Treasury and Risk Management > Risk Management > Basics > Analysis Structure > Editing Characteristic Derivations | L6 | trm02 p.10 | loio `e7006b5365665d0ee10000000a44176d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e7006b5365665d0ee10000000a44176d.html?locale=en-US)

**Use**

With the characteristic derivation, the system can automatically derive characteristic values from other characteristic values.

You must first specify the logical connections between the characteristic values in the derivation strategies.

If you define a derivation rule in the derivation strategy, you must maintain the rule values in Customizing. You can change the rule values later in the area menu under Market Risk Analyzer Master Data Derive Rule Values .

An analysis structure has one derivation strategy per client.

**Prerequisites**

First define the general derivation strategy in Customizing under Basic Analyzer Settings Automatic Integration of Financial Objects Maintain General Derivation Strategy and the derivation strategies for the various kinds of financial transaction under Basic Analyzer Settings Automatic Integration of Financial Objects Money Market / Foreign Exchange ... Define Derivation Strategy .

**Activities**

- 1. If you would like to change the rule values, choose Market Risk Analyzer Master Data Derive Rule Values .
- 2. Make your changes and then choose Save.

###### Multi-Client Capability of Analysis Structures + Characteristics

> **Path:** Treasury and Risk Management > Risk Management > Basics > Analysis Structure > Multi-Client Capability of Analysis Structures + Characteristics | L6 | trm02 p.11 | loio `be12da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/be12da531198434de10000000a174cb4.html?locale=en-US)

The applications TRM Market Risk Analyzer and TRM Portfolio Analyzer use analysis structures, to which analysis characteristics are assigned. These are cross-client objects. From a technical viewpoint, these objects are data elements, domains, tables, structures, views or entries in cross-client tables (field catalog).

The system can handle multiple requests from different clients at the same time for the following reasons:

One system can contain multiple analysis structures. Characteristics can be assigned to these structures in any combination (without overlaps).

Analysis structures can be activated specific to a particular client. The application functions use only the analysis structure that is active in the respective client. This means that you can use different analysis structures in different clients. The use of characteristics is also client-dependent, as they are assigned to the analysis structure.

The system assigns identifiers for both characteristics and analysis structures. By using suitable naming conventions, conflicts between the different clients can therefore be avoided.

When you maintain characteristics and analysis structures, the system displays the cross-client effects of the maintenance in a dialog box and checks authorization. Once you have created a characteristic, you can change only its name. This prevents any critical cross-client changes being made here.

