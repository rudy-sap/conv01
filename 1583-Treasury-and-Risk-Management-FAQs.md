# Treasury and Risk Management: FAQs - SAP TRM Knowledge Base (branch split)

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

### Treasury and Risk Management: FAQs

> **Path:** Treasury and Risk Management > Treasury and Risk Management: FAQs | L2 | trm11 p.143 | loio `e96fd5b8ff7d41fba32bfb74473640a6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e96fd5b8ff7d41fba32bfb74473640a6.html?locale=en-US)

Here you can find answers to some frequently asked questions about Treasury and Risk Management.

**When does the system derive the account assignment reference for a treasury position?**

Account assignment references (AAR) are assigned to each treasury position in the position indicator. You use the account assignment reference to determine the G/L account in which the position is managed. You make the assignments of the G/L accounts dependent on the account assignment reference for the relevant account symbols (position and interest revenue) for posting the positions, dividend payments, interest payments, accruals and deferrals, incoming payments, and repayments in the general ledger.

The account assignment reference for a treasury position is determined once according to the rules defined in the Customizing when the treasury position is created.

The treasury positions for OTC transactions are created with the creation of the OTC transaction. The treasury positions of the different valuation areas for an OTC transaction are generated automatically when the financial transaction is saved as a contract. At this point, the position indicator including the account assignment references is also generated for the treasury positions.

In the securities area, the positions in the valuation areas are created in accordance with the respective differentiation as soon as a security is purchased in a securities account. Later purchases of the same security with the same differentiation values increase the existing positions. If you buy the same security with different differentiation values, such as a different securities account or valuation class, new positions are created. The general rule for securities positions is that all security purchases with the same differentiation values are managed as one position in the valuation areas.

If the derivation process failed and no account assignment reference could be derived by the system, you can manually enter the account assignment reference in the position indicator.

Using the Manage Position Indicator app, you can display, create manually, change, or delete the allocation of an account assignment reference to a treasury position. You can also reach the position indicator from the financial transaction data using the path in the menu More Environment Position Indicator .

You can change or delete the account assignment reference of a treasury position only if no posting has yet been made for that position. If a posting has already been made for a position, then the account assignment reference can be changed only by executing an account assignment reference transfer using the Transfer Account Assignment Reference app (App ID: TPM28).

**Note:**

The derivation of account assignment references for exposure subitems starts during the automated designation process (within the Hedge Management and Accounting of Net Open Exposures (FX Risk) process) when a exposure subitem is created.

For more information, see also:

Treasury Position

Differentiation Terms

Position Indicator

Account Assignment References

**What is the difference between Hedge Management for Net Open Exposures (FX Risk) and Hedge Management of Balance Sheet FX Risk?**

For more information, see also: Comparison of Hedge Management and Accounting of Net Open Exposures (FX Risk) and Hedge Management of Balance Sheet FX Risk

What are the prerequisites for an FX Hedge Request with prefilled 'Hedge Request Amount' in Hedge Management Cockpit?

General prerequisites that must be fulfilled to create a manual FX hedge request in the Hedge Management Cockpit:

Choose the current date as key date.

Choose a snapshot of the current date with day reference indicator.

Place the cursor in a cell of the analysis item for which you want to create the hedge request. This is relevant to prefill the hedge request with the correct values of the analysis item and the currency.

Additional prerequisites that must be fulfilled to automatically fill the sign and hedge request amount fields of an FX hedge request:

You defined net target quotas in the hedging area using the Define Hedging Areas app.

Choose a layout in the Hedge Management Cockpit that contains the relevant target quota type and the relevant target quota related key figures.

If you made settings on the FX Hedge Request tab for the automated generation of FX hedge requests function, these settings are also considered during the automatic determination of the hedge amount during the manual creation of an FX hedge request.

How to Define Target Quotas in the Hedging Area?

- 1. On the Main Data tab in the Target Quota area, make the following settings:

- a. Select the Target Quota radio button.
- b. Insert a new row by choosing Insert Row.
- c. Specify the target quota type.

The target quota types are defined in the Define Target Quota Types configuration activity. Each target quota type has a target quota category that specifies the kind of the target quota.

- d. Specify the time pattern for the relevant target quota. Time patterns are defined in the Define Time Pattern app. Choose a time pattern that fits the reporting time pattern of the hedging area. When the reporting time pattern is absolute, the time pattern for the target quota also needs to be an absolute time pattern. In addition, the period length of the target quota time pattern needs to be the same or longer than the period length of the reporting time pattern.


- 2. On the General Settings tab in the Differentiation Criteria area, you define which differentiation criteria are also relevant for the target quota definition. The following rules apply:

You can mark a differentiation criterion as relevant for target quotas only when the differentiation criterion is marked as relevant for the hedging area.

The currency is the only required differentiation criterion for the target quota definition.

We recommend that you choose as few differentiation criteria as possible as relevant for target quotas to reduce the volume of the target quota table.

- 3. On the Currencies tab, you must enter currency groups in the right-hand column. This setting is relevant for the target quota entry because the target quotas are entered for the currency groups. You define the groups by entering a name. If you enter the same group name for different currencies, they are within the same currency group. You can enter the currency groups manually or you can use the Prefill Currency Groups function. When you use the function, the system enters for each currency the currency name in the Currency Group column. In this way, you have then defined a currency group for each currency. Now you can change the entries. For example, you can assign all currencies for which the same target quotas should apply to the same group.
- 4. On the Target Quotas tab, you maintain the target quotas according to the time pattern and currency groups.


On this tab, you enter the target quotas in the target quota tables for each target quota type relevant for the hedging area.

You can enter the target quotas manually by using the insert target quota function.

You can upload the target quotas from a spreadsheet.

Manual Entry of Target Quotas

- a. Choose the target quota type. You can choose only a target quota type that is assigned to the hedging area on the Main Data tab.

If you have assigned only one target quota type to the hedging area, the target quota type is already entered.

- b. Choose Insert Quota.


On the popup that appears, you can enter the following:

- i. Specify the kind of target quota that you want to enter (either Net or Gross) in the Net/Gross field.
- ii. In the following fields, you can enter the specific combination of differentiation criteria (that are relevant for target quotas) for which you want to enter target quotas.

If you do not make entries here, the target quotas entered are relevant for all combinations of the differentiation criteria values.

If you set the Insert Target Quota indicator, only new entries in the target quota table that result from these entries are inserted into the target quota table.

If you set the Update Target Quota indicator, only existing entries in the target quota table are changed according to these entries.

By default, both indicators are set. Only deselect one of them if you want to have the special effect of the other.

- iii. Once you have entered all relevant values, press the Enter key on your keyboard and then choose the Enter pushbutton.


**Note:**

You can enter gross target quotas in the hedging area master data, but the Hedge Management Cockpit does not display gross target quotas. Therefore, it is recommended to enter net target quotas.

The system creates the target quota lines resulting from your entries. Each line represents a specific combination of the differentiation criteria values.

Enter the target quotas for the defined periods.

Limit

You enter one target quota for each period.

Target Quota Band

You enter the lower and the upper limit for all periods.

Example: If you want to enter a limit of 70%, you enter 70 in the cell.

Target Limit Within Band

You enter a target limit (target quota) within a target quota band:

Lower Quota [%]

Upper Quota [%]

Target Quota [%]

This value must lie between the lower and the upper limit.

The quotas are entered in percent.

- iv. Continue until you have entered all target quota values.
- v. You can change the target quota value in the lines manually.


Upload from Spreadsheet

- i. If you want to upload the target quotas from a spreadsheet, we recommend that you first download the target quota table as a spreadsheet using the export function.
- ii. Enter the values in the downloaded spreadsheet.
- iii. Upload the spreadsheet using the import function.
- iv. Save the entries.


**Note:**

You have two options for doing this:

You can download the empty table. In this case, you must enter all values of the table manually in the spreadsheet.

You can use the insert target quota function to generate all relevant lines of the target quota table before the download. In this case, you enter only the target quota values in the spreadsheet.

Which Target Quota-Related Key Figures Must be Chosen in the Layout for the Hedge Management Cockpit?

In the Hedge Management Cockpit, you must choose a layout that contains the target quota-related key figures. Otherwise, the target quotas are not shown in the analysis items and the target quota-related key figures are not calculated.

You create the layout in the Hedge Management Cockpit app, where you choose the Manage Layout button.

In the layout, you must select a target quota type (for which you have entered net target quotas) and the target quotarelated key figures. Which key figures you need to select depends on the target quota category of the selected target quota type:

Target quota-related key figures relevant for target quotas based on target quota category Limit

Target Quota [%]

Target Hedge Amount = Net Exposure * Target Quota (Single Limit) %

Sign of the amount has the opposite direction to that of the exposure.

Amount to Hedge = Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Target quota-related key figures relevant for target quotas based on target quota category Band

Lower Target Quota [%]

Upper Target Quota [%]

Target Hedge Amount = Net Exposure * Upper Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Lower Target Hedge Amount = Net Exposure * Lower Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Upper Target Hedge Amount = Net Exposure * Upper Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Min. Amount to Hedge = Lower Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Max. Amount to Hedge = Upper Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

Target quota-related key figures relevant for target quotas based on target quota category Target Limit within Band:

Lower Target Quota [%]

Upper Target Quota [%]

Target Quota [%]

Min. Amount to Hedge

Max. Amount to Hedge

Target Hedge Amount = Net Exposure * Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Lower Target Hedge Amount = Net Exposure * Lower Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Upper Target Hedge Amount = Net Exposure * Upper Target Quota %

Sign of the amount has the opposite direction to that of the exposure.

Amount to Hedge = Target Hedge Amount – (Hedges + Open Amount of Hedge Requests)

For more information, see also Target Quotas

