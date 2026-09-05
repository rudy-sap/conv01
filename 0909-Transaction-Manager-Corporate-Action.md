# Transaction Manager > Corporate Action - SAP TRM Knowledge Base (branch split)

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

#### Corporate Action

> **Path:** Treasury and Risk Management > Transaction Manager > Corporate Action | L3 | trm06 p.307 | loio `4b522c0089472827e10000000a42189c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4b522c0089472827e10000000a42189c.html?locale=en-US)

**Use**

Corporate actions are part of position management in the securities area. They can also influence transaction management deals such as Forward Securities Transactions (FST) and Total Return Swaps (TRS). You can use this function to display changes made by the issuer to the capital structure for classes in your position. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities Accounting Corporate Actions (transaction FWK0).

**Prerequisites**

You have made the following settings for Securities in Customizing for the Transaction Manager.

You have determined number ranges by choosing Position Management Corporate Actions Define Number Ranges for Corporate Actions .

In addition to the default corporate action categories, you have created individual corporate action types and assigned them number ranges by choosing Position Management Corporate Actions Define Types of Corporate Actions .

You have created three update types for the corporate action and assigned them to usage 0004 Corporate Action by choosing Transaction Management Update Types Define Update Types and Assign Usages .

**Note:**

SAP provides the following default update types for corporate actions:

- CA0001 Corporate action: Position increase – units/nominal

- CA0002 Corporate action: Position decrease – units/nominal

- CA0003 Corporate action: Issue currency changeover


You have made your settings by choosing Position Management Corporate Actions Update Types Assign Update Types to Corporate Action Categories .

**Note:**

For the issue currency changeover, you assign only the update type CA0003 Corporate Action: Issue Currency Changeover.

**Features**

Standard functions are available for the following capital changes:

Stock split

When a stock is very expensive the issuer can decide to split the stock e.g. in the ratio 4:1. By this the number of stocks in each securities account is multiplied by 4, i.e. for each stock a stock holder gets 3 stocks for free (the value of a position is not changed as the market price usually is split by the inverse ratio.)

Stock Swap

Capital reduction

If a company is in a bad financial situation it can decide to reduce its capital and to reduce its number of issued stocks. In this case a stock position of 100 stocks is reduced to a new number of e.g. 10 stocks, i.e. the capital reduction is reflected by position decrease flow of 90 stocks.

Capital increases from retained earnings

If a company has a lot of free capital it can decide to make a capital increase, i.e. to issue new free stocks to the stock holders. As with a stock split each position will have a quantity increase in a given ratio.

Transfer new stock

Within the process of an ordinary capital increase new stocks are given to the stock holders. The new stocks have an own security ID which differentiates them from the existing “old” stocks. This is needed because in many cases the dividend for the new stocks is lower than the dividend for the old stocks. At a given date (decided by the issuer) the new stocks are

transferred into old stocks, i.e. we have a quantity decrease of the new stocks and a quantity increase in a specified ratio in the old stocks (like in the case of a stock swap).

Posting Subscription Rights

Issue Currency Changeover

You can use the manually-generated corporate actions function for capital changes that are not supported by the standard functions offered in the securities management area.

|Status|Description|Remarks|
|---|---|---|
|0|Planned|The corparte action has status 0 once you have created and saved it in the system. You can change, delete or activate the corporate action. You cannot post the corporate action.|
|1|Activated (No flows exist)|This status enables you to transfer a planned corporate action (status 0) or one you have just created by choosing Corporate action Activate. You can post the corporate action. Deactivate resets the corporate action to status 0.|
|2|Activated (Posted flows exist)|At least one company code contains posted flows.|
|3|Activated (Posted and reversed flows exist)|At least one company code contains posted flows. At least one company code contains reversed flows.|
|4|Activated (Reversed flows exist)|You can transfer the corporate action to status 5 using the deactivate function.|
|5|Reversed|The corporate action is deactivated and all flows are reversed. You can no longer post the corporate action.|


**Activities**

You must execute the following steps for a corporate action

- 1. Creating Corporate Actions

You create corporate actions for all company codes. When you create a corporate action, the system does not update any positions or generate general and sub ledger documents.

- 2. Activate

If you activate the corporate action (status 1), you can then post it in each company code. See also: Editing Corporate Actions

- 3. Position Indicator

You create securities account position indicators for new positions.

- 4. Posting a Corporate Action

You post corporate actions for each company code. This updates the company code positions and generates the FI documents (posting log), where applicable. If the corporate action is within the term of a FST/TRS the deal is updated. The corporate action is automatically assigned status 2 and 3.

After you have carried out a corporate action, you cannot change position-changing business transactions to the positions of the relevant securities before the corporate action key date, because the function sets a lock. If, however, you have to subsequently make a change, you must first reverse the corporate action.

If you have carried out a stock split, you must change the nominal value of the stock in the class data. On the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Securities Master Data Class ( transaction FWZZ).

- 5. Reversing a Corporate Action


**More Information**

For more information, see also Corporate Actions for Total Return Swap.

##### Editing Corporate Actions

> **Path:** Treasury and Risk Management > Transaction Manager > Corporate Action > Editing Corporate Actions | L4 | trm06 p.310 | loio `b818da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b818da531198434de10000000a174cb4.html?locale=en-US)

Procedure

- 1. Choose Back Office Corporate Actions.

This brings you to the screen Edit Corporate Action: Initial Screen .

- 2. Here you can either create a new corporate action or edit or display an existing one.


|Function|Entries|Comments|
|---|---|---|
|Create| |See: Creating a Corporate Action See: Issue Currency Changeover See: Generating a Corporate Action Manually |
|Change|1. Corporate Action number 2. Change |Changes to a corporate action are only possible in status 0 (planned).|


| |3. Enter the changes . 4. Save or activate the corporate action. |If you save the corporate action, it retains status 0 (planned). If you activate the corporate action, it attains status 1 (activated, no flows exist). It can now be posted.|
|---|---|---|
|Delete|1. Go to change mode. 2. Choose the delete function. |You can only delete a corporate action that is in status 0 (planned).|
|Display|1. Corporate Action number 2. Display | |
|Deactivate|1. Go to display mode. 2. Choose Deactivate corporate action. |Using the deactivate function, you can reset a corporate action from status 1 to status 0, and change one from status 4 to status 5.|
|Additional Functions| |These functions are in the Accounting area.|
|Post| |See: Posting a Corporate Action |
|Reverse| |See: Reversal of Corporate Actions |

##### Creating Corporate Actions

> **Path:** Treasury and Risk Management > Transaction Manager > Corporate Action > Creating Corporate Actions | L4 | trm06 p.311 | loio `1417da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/1417da531198434de10000000a174cb4.html?locale=en-US)

Procedure

To create a corporate action for all company codes, proceed as follows:

On the SAP Easy Access screen, choose transaction Corporate Actions (FWK0).

Enter the Corporate Action (CA) number.


To determine whether the system should assign the corporate action numbers internally or whether they should be assigned externally, in Customizing for the Transaction Manager, choose Securities Position Management Corporate Actions

Define Number Ranges for Corporate Actions . With internal number assignment, you do not need to enter a CA number. The system assigns the number.

Choose the corporate action category and type.


If only one corporate action type is defined in Customizing for the selected corporate action category, the system transfers the type automatically.

Choose Create.


You use the Create with Reference function to copy an existing corporate action.

In the Basic Data area, enter the Key Date of the position change and a Description of the corporate action.

Enter the required data in the Detailed Data area.

To display the security class data, choose Display Class Data. When you have several securities, select the respective security ID number.

To display how the flow types are assigned to the flow categories delivered with the system, choose Extras Flow Types . You must define any individual flow types you wish to use here.


The system posts a corporate action by default with the flow types that have already been determined for the relevant flow categories in Customizing.

Save or Activate the corporate action.


If you save the corporate action, it is assigned status 0 (Planned). You can then still change it or delete it. You can only post the corporate action after it has been activated (see Posting a Corporate Action).

##### Posting a Corporate Action

> **Path:** Treasury and Risk Management > Transaction Manager > Corporate Action > Posting a Corporate Action | L4 | trm06 p.312 | loio `6a19da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6a19da531198434de10000000a174cb4.html?locale=en-US)

**Prerequisites**

The corporate action must be activated (status 1/2/3/4).

Do not carry out valuation after this key date for any security positions affected by the corporate action.

You must have created a position indicator for any new positions.

**Procedure**

- 1. Choose Accounting Corporate Action Post .
- 2. Enter the Corporate action number and the Company code in which you want to post your corporate action.
- 3. Enter the Calculation date, Posting date (FI) and Document date (FI). The Posting date field defaults to the current date. You can, however, overwrite this date.

In the Assignment Text field, you can enter a text which will appear on the FI document.

- 4. Choose Execute. This posts the corporate action.


**Note:**

An issue currency translation is executed for all company codes.

**Note:**

If you set the Simulation indicator, the system performs a test posting run.

**Result**

When you post the corporate action, the company code positions are updated and the related FI documents are generated, where required.

##### Reversing a Corporate Action

> **Path:** Treasury and Risk Management > Transaction Manager > Corporate Action > Reversing a Corporate Action | L4 | trm06 p.313 | loio `3318da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3318da531198434de10000000a174cb4.html?locale=en-US)

**Use**

This function enables you to reverse a corporate action that has already been posted.

**Note:**

You have to use this function if you were posting a corporate action and the activity was terminated.

**Integration**

From the various reversal functions available in the securities area, you choose the one that corresponds to the flows you want to reverse.

For more information, see Overview: Reversals in Securities .

**Prerequisite**

Make sure that no flows have been closed after the key date.

**Procedure**

- 1. Choose Accounting Corporate action Reverse.
- 2. This takes you to the Reverse Corporate Action screen. Enter the following data:


Corporate action number

Company code

Posting date

Document date

FI reversal reason ( required entry )

TR reversal reason

- 1. You can perform the reversal first as a Test run. To do this, select the relevant field.
- 2. Execute Reversal only inTR.


**Caution:**

You should only do this if the corporate action cannot be reversed in Financial Accounting (FI), for example, because the document in FI has already been reversed.

1. Choose Execute.

**Result**

The flows posted in the company code are reversed. The corporate action is transferred to status 3 or 4.

If the corporate action has status 4, you can transfer it to status 5 (reversed) using the Deactivate function.

See also:

Corporate Actions

Editing a Corporate Action

##### Stock Swap

> **Path:** Treasury and Risk Management > Transaction Manager > Corporate Action > Stock Swap | L4 | trm06 p.314 | loio `f117da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f117da531198434de10000000a174cb4.html?locale=en-US)

**Use**

When you perform a stock swap, you exchange the positions of a stock for the positions of another stock at a fixed swap ratio.

A stock swap can be performed for a class when the issuer insists upon it. Alternatively, a stockholder has the right/offer to swap a stock and can choose whether or not to exercise this right.

This is why there are two ways of representing stock swaps in the system:

Stock swap as a corporate action

When you choose this option, the swap is executed for all the positions of the class in each company code.

Stock swap as a security right

When you choose this option, you can exercise the right for individual positions.

Integration

|Stock swap as a corporate action|1. You create and activate the stock swap as a corporate action in the system. 2. You post the corporate action for each company code. |
|---|---|
|Stock swap as a security right|1. You create the data for the stock swap in the class data ( Stock swap tab). 2. The stock swap appears as an executable right in the Exercise security right function. 3. Exercise the security right. |


Prerequisites

|Stock swap as a corporate action|You must have created the securities involved as classes. Positions must exist for the stock you want to swap.|
|---|---|
|Stock swap as a security right|You have created the stock swap data in the class data for the stock that vests the right. You must have created the class data for the stock you want to receive as a result of the swap. Positions must exist for the stock you want to swap.|


**Features**

For more information on processing corporate actions or on exercising rights, see:

Corporate Actions

##### Creating Manually-Generated Corporate Actions

> **Path:** Treasury and Risk Management > Transaction Manager > Corporate Action > Creating Manually-Generated Corporate Actions | L4 | trm06 p.315 | loio `2b19da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/2b19da531198434de10000000a174cb4.html?locale=en-US)

Procedure

To create a manually-generated corporate action for all company codes, on the SAP Easy Access screen, choose transaction Corporate Actions (FWK0) and execute the following steps:

Enter the Corporate Action (CA) number.


Choose Define Number Ranges for Corporate Actions in Customizing for Securities to define whether or not you want the system to assign corporate action numbers internally or whether you want to assign the numbers externally. If the number is assigned internally, the system automatically assigns a CA number.

Select the corporate action category Manually Generated.

Select the corporate action type.


If you have only defined one corporate action type in Customizing for the selected corporate action category, the system transfers this automatically.

Choose Create . You use the Create with Reference function to copy an existing corporate action.

In the Basic Data area , enter the Key Dateof the position change and aDescription of the corporate action.

Define the corporate action in the table below.


The system posts a corporate action by default with the flow types that have already been defined for the relevant flow categories in Customizing for the Transaction Manager . Choose Securities → Transaction Management → Flow Types (Transaction) →

Define Flow Types . You must define any individual flow types you wish to use with the Display Flow Types function.

Save the corporate action or activate it.


When you save the corporate action, it is assigned status 0 (planned) and you can still change or delete it. You can only post the corporate action after it has been activated.

See also Posting Corporate Actions

