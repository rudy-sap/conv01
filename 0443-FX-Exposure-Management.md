# FX Exposure Management - SAP TRM Knowledge Base (branch split)

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

### FX Exposure Management

> **Path:** Treasury and Risk Management > FX Exposure Management | L2 | trm03 p.288 | loio `301f3455991c48d5a63cbd25712c60cb` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/301f3455991c48d5a63cbd25712c60cb.html?locale=en-US)

FX Exposure Management offers an easy way of entering FX exposures with the Manage FX Exposures app or using the Foreign Exchange Exposure (API_FXEM_FXEXPOSURE) API. The status concept and available functions for FX exposures that are relevant within the Manage FX Exposures app are also relevant for processing FX exposures using the API.

The Foreign Exchange Exposure Management (FX Exposure Management) is integrated in the Hedge Management and Accounting of Net Open Exposures (FX Risk) process. You can select the FX exposures as exposure items for a hedging area. To do so, you must set up a filter in the hedging area master data for the data source Foreign Exchange Exposure Management.

**Related Information**

Manage FX Exposures

#### Manage FX Exposures

> **Path:** Treasury and Risk Management > FX Exposure Management > Manage FX Exposures | L3 | trm03 p.288 | loio `fb0786b5051544ed9c0fe425af1b9830` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fb0786b5051544ed9c0fe425af1b9830.html?locale=en-US)

App ID: F7990

With this app, you can create and process foreign exchange exposures.

**Configuration**

Define FX Exposure Types

In this configuration activity, which is available in your configuration environment, you define the FX exposure types to differentiate the FX exposures. In the definition of the FX exposure type, you choose the relevant attributes for the FX exposures of this type by setting the indicator for each relevant field:

Portfolio

Cost Center

Profit Center

Country/Region

WBS Element

On Behalf of Company Code

Segment

In the Hedge Management Cockpit, the selected differentiation criteria of a hedging area together with the chosen reporting time pattern determine the analysis items. The analysis items determine the granularity with which you monitor and hedge your FX exposures in the Hedge Management Cockpit. Incoming and outgoing exposures and hedges with the same differentiation criteria and time period belong to the same analysis item. Therefore, if you have chosen a field in a hedging area as a differentiation criterion, this field must also be filled in the FX exposures for this hedging area.

If you select an indicator for the FX exposure type, the related field must be filled for each FX exposure of this FX exposure type.

If you do not set an indicator, you cannot assign a value for this field to the FX exposures of this FX exposure type.

**Key Features**

Create an FX exposure manually.

Create FX exposures by uploading the data from a spreadsheet.

- 1. Choose Upload Download Template to download the template.
- 2. Enter the FX exposure data in the spreadsheet.
- 3. Choose Upload Upload to upload the spreadsheet.


|Column|Explanation|
|---|---|
|(A) FX Exposure Type|The FX exposure type is an attribute of an FX exposure and is used to distinguish FX exposures from each other.|
|(B) Company Code|Organizational entity|
|(C) Portfolio (D) Cost Center (E) Profit Center (F) Country/Region (G) WBS Element (H) On Behalf of Company Code (I) Segment |Which of these columns are to be filled for an FX exposure depends on the settings in the FX exposure type.|
|(J) Valid From|Date as of which the FX exposure is valid.|
|(K) Due Date|Date at which the FX exposure is due.|
|(L) Amount (M) Risk Currency |Enter the amount and the currency of the FX exposure. **Note:** For an incoming exposure, the sign of the FX exposure amount must be positive and for an outgoing exposure it must be negative.|
|(N) FX Exposure Target Currency|Currency in which the amount of the FX exposure must be hedged.|
|(O) Direction|The direction specifies whether the exposure is an Incoming or an Outgoing cash flow.|
|(P) FX Exposure External ID|The external ID for the FX exposure is a free text field in which you can enter external references for the FX exposure, such as the invoice number or the customer/supplier item number.|


Edit an FX exposure with the status Created.

Set an FX exposure with the status Created to the status Obsolete.

Submit an FX exposure with the status Created for checking.

When the FX exposure data is entered completely, the user who created the FX exposure sends the FX exposure for checking.

Check an FX exposure.

FX exposures with the status Submitted need to be checked. A user who is authorized to check can release or reject the FX exposure. If the submitted FX exposure has an error and needs to be adjusted before release, the FX exposure can be sent for update. In this case, the status of the FX exposure is reset to Created.

If an already released FX exposure changes, you can set the status of the FX exposure back to Created and you can update the following fields:

Amount

Valid-From Date

External ID

List of FX Exposures

The app provides you with an overview of all FX exposures. You can use the search criteria to restrict the list to certain FX exposures.

From this list, you can jump to the details of an FX exposure to display or process the FX exposure.

From the list, you can choose the Create button to create a new FX exposure.

If you leave the entry process for an FX exposure without saving your data, you can keep your entries as a draft version or discard your entries. The editing status of the FX exposure reflects the state of the FX exposure in terms of the processing cycle. The following editing statuses are available:

All

Displays all FX exposures.

Own Draft

Displays your own FX exposures that you have started creating/changing but not finished.

Locked by Another User

Displays all FX exposures that another user has started creating/changing and is currently editing.

The FX exposures with this editing status are locked.

Unsaved Changes by Another User

Displays FX exposures that another user has started editing but not finished. The FX exposure can be opened for editing. (The lock has expired, somebody else's draft version is still available.)

Unchanged

Displays all FX exposures that do not have draft status.

On the Administrative Data tab, you get the following information:

Creation Mode

Created At

Created By

Status Change History

Status changes made to FX exposures are documented in the change documents for change document object FXEM_EXPOSURE Foreign Exchange Exposure.

For more information, see also Maintaining Exposures in Treasury and Risk Management.

**Data of FX Exposures**

| |Field|Explanation|
|---|---|---|
|Header|FX Exposure ID|The identifier of the FX exposure is set automatically by the system.|
|Header|FX Exposure Type|The FX exposure type is an attribute of an FX exposure and is used to distinguish FX exposures from each other. In the FX exposure type, you define which attributes need to be filled for an FX exposure of this FX exposure type. In the hedging areas of Hedge Management of Net Open Exposures, in addition to other criteria, you can use the FX exposure type to filter the foreign exchange exposures relevant for the hedging area.|
|Header|Company Code|Organizational entity|
|Header|Due Date|Date at which the FX exposure is due.|
|Header|FX Exposure Status|The status of the FX exposure is set by the system according to the actions performed by the user. The following status are possible: Created Submitted Released Rejected Obsolete|
|FX Exposure Details|Differentiation criteria: Portfolio Cost Center Profit Center Country/Region|Which of these fields are to be filled for an FX exposure depends on the settings in the FX exposure type.|


| |Field|Explanation|
|---|---|---|
| |WBS Element On Behalf of Company Code Segment| |
|FX Exposure Details|Direction|The direction specifies whether the exposure is an Incoming or an Outgoing cash flow.|
|FX Exposure Details|Amount|Enter the amount and the currency of the FX exposure. **Note:** For an incoming exposure, the sign of the FX exposure amount must be positive and for an outgoing exposure it must be negative.|
|FX Exposure Details|FX Exposure Target Currency|Currency in which the amount of the FX exposure must be hedged.|
|FX Exposure Details|Valid From|Date as of which the FX exposure is valid.|
|FX Exposure Details|FX Exposure External ID|The external ID for the FX exposure is a free text field in which you can enter external references for the FX exposure, such as the invoice number or the customer/supplier item number.|
|FX Exposure Details|Reason|Reason for the status change of the FX exposure When you reset a status, for example, when you manually set an already released FX exposure to Created or when you set an FX exposure to Obsolete, you can enter the reason for this status switch.|


**Statuses and Status Transitions of FX Exposures**

[figure TRM03-F379]

**An FX exposure always has a status. The status is set by the system according to the actions performed by the user. An FX exposure can have one of the following statuses:**

|Status of FX Exposure|Explanation|
|---|---|
|Created|The following actions are available for FX exposures with this status: Edit You can change the data of the FX exposure. Submit If all data for the FX exposure is entered, you can use the Submit button to submit the FX exposure for checking. The status of the FX exposure changes to Submitted. Set to Obsolete If the FX exposure is no longer relevant, you can set its status to Obsolete. You can enter the reason for this status switch.|
|Submitted|This status is reached when an FX exposure has been submitted. FX exposures with this status must be checked for correctness. The following actions are available for FX exposures with this status:|


|Status of FX Exposure|Explanation|
|---|---|
| |Release Reject Send for Update Use this function if you have accidentally sent an FX exposure for release and still need to make changes. If you perform this action, the status of the FX exposure changes from Submitted to Created. You can enter the reason for this status switch.|
|Released|If the already released FX exposure changes, you can change the status of the FX exposure back to Created. However, in this case, you can only edit the fields Amount, Valid From and External ID. You can enter the reason for this status switch.|
|Rejected|If the reviewer of the FX exposure rejects an FX exposure, the FX exposure can no longer be changed. The status Rejected is a final status.|
|Obsolete|The status Obsolete is a final status.|


**Authorization Object**

For this process, you must authorize users to enter and update the FX exposures and users responsible to check the FX exposures. The following authorization object is available:

FX Exposure Management (F_FXEM)

You can use this authorization object to control how FX exposures are processed in the Manage FX Exposures app of Treasury and Risk Management.

This authorization object contains the following fields and values:

BUKRS Company Code

FXEXPTYPE FX Exposure Type ID

ACTVT Activity

- 01 Add or Create

Enables users to create an FX exposure.

- 02 Change

Enables users to process FX exposures with the status Created (actions Edit, Submit, and Set to Obsolete).

- 03 Display


Enables users to display FX exposures.

43 Release

Enables users to release or reject FX exposures with the status Submitted.

RE Restart

Enables users to set already released FX exposures back to status Created using the Set to Created action.

RT Reset

Enables users to reset already submitted FX exposures back to status Created using the Send for Update action.

**Supported Device Types**

Desktop

Tablet

**Related Information**

FX Exposure Management Hedge Management and Accounting of Net Open Exposures (FX Risk)

