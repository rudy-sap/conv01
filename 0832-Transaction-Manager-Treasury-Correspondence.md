# Transaction Manager > Treasury Correspondence - SAP TRM Knowledge Base (branch split)

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

#### Treasury Correspondence

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence | L3 | trm06 p.189 | loio `001f59060464450eb9b0f02b3b1f5c00` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/001f59060464450eb9b0f02b3b1f5c00.html?locale=en-US)

**Use**

The Treasury correspondence functionality (also known as the Correspondence Framework) enables you to manage your correspondence, standardize your correspondence processes, and create consistent correspondence and results.

You can create correspondence relating to individual requests and mass requests to be sent to your business partners. You can generate correspondence objects both automatically and manually for financial transactions and securities accounts. You can do this with the correspondence monitor, which enables you to manage correspondence objects. As well as providing you with a status management function, the correspondence function provides you with an automatic matching process to automatically set the status of a financial transaction to be settled, based on the product type.

Integration

If you use the Treasury Correspondence Integration with SWIFT Network integration scenario, you can send and receive the following kinds of SWIFT message:

MT300 for FX transaction confirmation

MT320 for money market transaction confirmation

MT535 Statement of Holdings

For more information, see also Exchange Treasury Correspondence via SWIFT.

**Prerequisites**

You need to match the settings for the business attributes and the technical attributes. The technical attributes are found under Correspondence Messaging Interface and are settings relating to the recipient type, the correspondence format, and the channels of communication. The business attributes are found under General Settings and relate to the business partners, counterconfirmation, and roles.

You can make the required settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Correspondence .

Under Correspondence Messaging Interface:

Define the correspondence recipient type, for example, business partner, 3rd party, or internal recipient.

Define and assign the correspondence format. Each correspondence message has a specific format and attributes. When you have defined these, the format is then assigned to the profiles based on correspondence class, recipient type, and communication channel.

Define the channels of communication and the communication profiles, for example, fax, email, file system, or print. The profile contains all technical attributes that control the creation, sending, and receiving of messages.

Correspondence class and recipient/sender type

Under General Settings:

Define business partner groups. The business partner group enables the system to differentiate between business attributes and technical attributes.

Assign business attributes to the business partner groups. In this activity, you assign business attributes to the business partner, correspondence class, and recipient/sender type. You can specify the following:

Whether automatic correspondence is required

Whether counterconfirmation from the counter party is required

Whether the correspondence object is relevant for the transaction status

Whether the correspondence needs to be released before being sent. (You use the Release indicator to specify that the release tool has to be called before the correspondence object is sent.)

Whether reconciliation is required

Whether a correspondence can be automatically marked as completed

Whether the information about the external reference and contact person in the transaction has to be updated with the information received in a status-relevant incoming correspondence

Under Correspondence Activities:

Define the correspondence activities, for example, Money Market, Securities, Foreign Exchange, or Derivatives. You assign each correspondence function code to a product type for an activity as well as for a recipient type.

Under Match Correspondence Objects:

Define rules for matching correspondence objects. For example, you can specify which correspondence class of the incoming correspondence has to be matched with which correspondence class of the outgoing correspondence.

Under Release:

Define settings for the release of a particular release object. Since the release of release objects is regulated by the SAP Business Workflow, you need to specify in the Run Release Workflow group box whether and when the system places a release object in the release process.

Assign a rule to the release steps of the release procedure for a particular release object. The system uses the rule to find the processors responsible and forwards the release object as a work item to them for further processing with the SAP Business Workflow.

Correspondence classes are delivered by SAP, but they can be enhanced. You need to add new correspondence classes whenever you define a new transaction type (with a new format, partner settings, or status relevance, for example).

Master Data

Assign Business Partner Group and Profiles

Assign Correspondence Class for Inbound Process Dependent on Recipient (Transaction FTR_INB_FUNC)

Assign the correspondence classes for the MT300 and MT320 formats to your counterparties (recipient type) dependent on the business partner.

Assign the correspondence classes for the MT535 format to your depository banks (recipient type) dependent on the business partner.

You can assign business partner group and profiles in order to assign attributes to the following:

Business partner

Correspondence class

Recipient/sender type

For more information, see Assign Business Partner Group and Profiles.

Define Fixing References

Define Values for Expiry Time

For MT535 messages, you must enter the External Securities Account ID and the Depository Bank in the securities account master data using Manage Securities Accounts app.

For MT535 messages, you must enter the ISIN for all your security classes. You can either enter the ISIN as secondary index or use the ISIN as security class ID number.

Assign BIC to Business Partner

**Features**

The Correspondence solution now offers the following features:

The correspondence monitor enables you to perform the following functions:

Create new correspondence objects

Display correspondence object details

Attach documents to correspondence objects

View the underlying transactions

View correspondence object attachments

Create and view notes associated with the correspondence object

Show all related correspondences

Show matched and linked correspondence objects

Assign or unassign correspondence objects to or from a transaction

View and update correspondence object statuses

View the correspondence objects history log

View and send alerts for selected correspondence objects

For more information, see Correspondence Monitor.

Individual functions enable you to do the following:

Create correspondence objects

Send correspondence objects

Match correspondence objects

Import incoming messages

For more information, see Individual Functions.

You are able to monitor and send correspondence alerts:

The Alert Monitor collects correspondence alerts and enables you to send an alert notification for a pending transaction activity, such as a settlement, posting, or correspondence confirmation.

For more information, see Correspondence Alerts.

**Activities**

When you create a financial transaction with a business partner, the correspondence settings associated with the business partner will trigger any required outgoing correspondence.

The system will sort incoming correspondence by checking the following:

The channel by which it was received

The format, for example, MT300

The sender and type

The purpose of the correspondence

The system then calls the relevant BAdI to check the correspondence object and matches it with another correspondence object. The correspondence object can be assigned to a transaction.

**Related Information**

Terms in Treasury Correspondence

##### Exchange Treasury Correspondence via SWIFT

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Exchange Treasury Correspondence via SWIFT | L4 | trm06 p.193 | loio `0c0ef52522f04000a5044347081c06a5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0c0ef52522f04000a5044347081c06a5.html?locale=en-US)

**Use**

This process allows you to exchange Treasury correspondence with your counterparties using MT300 and MT320 SWIFT messages for your FX and money market transactions and to receive MT535 messages for external securities account statements from your depository banks. The process requires the Treasury Correspondence Integration via SWIFT Network integration scenario.

**Prerequisites**

Set up the Treasury Correspondence Integration via SWIFT Network integration scenario.

For more information, see Treasury Correspondence Integration with SWIFT Network.

Perform the following Customizing activities that are relevant for the SWIFT process:

Define Company Code Additional Data

For the communication via SWIFT, it is important to identify the receiver, the sender, and the kind of message explicitly:

Receiver ID

Outbound Process: Bank identifier code (BIC) of the counterparty

Inbound Process: BIC of your corporate

Sender ID

Outbound Process: BIC of your corporate

Inbound Process: Bank identifier code (BIC) of the counterparty

Message ID

Outbound Process: ID of Correspondence Object

You assign the bank identifier code (BIC) for your company codes in the Define Company Code Additional Data Customizing activity.

**Note:**

You assign the BIC of your counterparties in the Assign BIC to Business Partner function.

###### Define Your Own Format Mapping

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Exchange Treasury Correspondence via SWIFT > Define Your Own Format Mapping | L5 | trm06 p.196 | loio `fffbe23186174d18aee0784e60f24ff0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fffbe23186174d18aee0784e60f24ff0.html?locale=en-US)

If the predefined format mappings are not sufficient for you needs, for example because your bank needs more fields, you define your own format mappings.

**Note:**

This function is only available for your outgoing and incoming treasury correspondence for MT300 and MT320 SWIFT formats and incoming MT535 SWIFT message format.

Make the following settings in the Map Format Data for Treasury Correspondence configuration activity available in your configuration environment.

- 1. Open the Map Format Data for Treasury Correspondence configuration activity.
- 2. Create a treasury correspondence format mapping by copying a predefined format mapping and adapting it as required.

For more information about the SWIFT formats, see the information available at https://www2.swift.com/knowledgecentre/publications/usgf_20180720/3.0? topic=idx_msg.htm%233.

Not all fields of the correspondence object are in the delivered structure. If you need more fields with which to fill the SWIFT message, you can include your own custom reference fields based on the fields of the treasury correspondence object.

For more information, see Including Custom Reference Fields.

- 3. Assign the new format mapping to the corresponding treasury correspondence format in the configuration activities Assign Format Mappings for Outbound Process or Assign Format Mappings for Inbound Process.


**Note:**

There are some fields in the format mapping, for example: EXT_REF2, EXT_STMT_NAME, EXT_STMT_GROUP, and EXT_STMT_STATUS which are not filled in the delivered format mapping. However, in your own format mapping, you can use these fields to map the configuration settings of the external securities account statement so that these values are then automatically filled in the external securities account statement when the SWIFT message is imported. To do this, you define rules for how the field values of these fields are derived from values in the SWIFT message.

Examples:

EXT_REF2 -> External Reference 2

EXT_STMT_NAME -> External position name

EXT_STMT_GROUP -> Group external securities account statements

EXT_STMT_STATUS -> Status

**Information for Delivered Format Mapping for MT300 and MT320 Messages**

Specific Fields Mappings

|Format Mapping|Field in SWIFT Message|Fieldname in Format Mapping|
|---|---|---|
|General Information - Structure GENERAL| | |
|TRTM_MT300 and TRTM_MT320|20 Sender Reference|GENERAL-SENDER_REFERENCE|
|TRTM_MT300 and TRTM_MT320|21 Related Reference|GENERAL-RELATED_REFERENCE|
|TRTM_MT300 and TRTM_MT320|22A Type of Operation|GENERAL-OPERATION_TYPE|


|Format Mapping|Field in SWIFT Message|Fieldname in Format Mapping|
|---|---|---|
|TRTM_MT320|22B Type of event|MM-TYPE_OF_EVENT|
|TRTM_MT300 and TRTM_MT320|22C Common Reference|GENERAL-COMMON_REFERENCE|
|TRTM_MT300 and TRTM_MT320|82A Party A Type A*|PARTY_A-PARTY_BIC|
|TRTM_MT300 and TRTM_MT320|82J Party A Type J* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_A-PARTY_BIC PARTY_A-PARTY_ACCT PARTY_A-PARTY_ADD1 PARTY_A-PARTY_ADD2 PARTY_A-PARTY_CITY PARTY_A-PARTY_CLRC PARTY_A-PARTY_LEI PARTY_A-PARTY_NAME PARTY_A-PARTY_TXID|
|TRTM_MT300 and TRTM_MT320|87A Party B Type A*|PARTY_B-PARTY_BIC|
|TRTM_MT300 and TRTM_MT320|87J Party B Type J* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_B-PARTY_BIC PARTY_B-PARTY_ACCT PARTY_B-PARTY_ADD1 PARTY_B-PARTY_ADD2 PARTY_B-PARTY_CITY PARTY_B-PARTY_CLRC PARTY_B-PARTY_LEI PARTY_B-PARTY_NAME PARTY_B-PARTY_TXID|
|TRTM_MT300|17F Non-deliverable indicator|FX-NON_DELIVERABLE|
|TRTM_MT300|17O NDF open indicator|FX-NDF_OPEN|
|TRTM_MT300|32E Settlement currency|FX-SETTLEMENT_CURRENCY|
|TRTM_MT300|30U Valuation date|FX-VALUATION_DATE|
|TRTM_MT300|14S Settlement rate source|Rate source Either EMTA rate FXSETTLE_RATE_SOURCE_EMTA or Other rate FX-SETTLE_RATE_SOURCE|
|TRTM_MT300|21A Reference to opening confirmation|FX-OPENING_REFERENCE|
|TRTM_MT300|Transaction Details| |


|Format Mapping|Field in SWIFT Message|Fieldname in Format Mapping|
|---|---|---|
| |FX Part - Structure FX| |
|TRTM_MT300|21A Reference to Opening Confirmation|OPENING_REFERENCE|
|TRTM_MT300|30T Trade Date|TRADE_DATE|
|TRTM_MT300|30V Value Date|VALUE_DATE|
|TRTM_MT300|36 Exchange Rate|EXCHANGE_RATE|
|TRTM_MT300|32B Currency, Amount Bought|CURRENCY BOUGHT + AMOUNT_BOUGHT|
|TRTM_MT300|53A Delivery agent Type A*|PARTY_DEL_A-PARTY_BIC|
|TRTM_MT300|53J Delivery agent Type J* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_DEL -A-PARTY_BIC PARTY_DEL_A-PARTY_ACCT PARTY_DEL_A-PARTY_ADD1 PARTY_DEL_A-PARTY_ADD2 PARTY_DEL_A-PARTY_CITY PARTY_DEL_A-PARTY_CLRC PARTY_DEL_A-PARTY_NAME|
|TRTM_MT300|56A Intermediary agent Type A*|PARTY_INT_A-PARTY_BIC|
|TRTM_MT300|56J Intermediary agent Type J* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_INT -A-PARTY_BIC PARTY_INT_A-PARTY_ACCT PARTY_INT_A-PARTY_ADD1 PARTY_INT_A-PARTY_ADD2 PARTY_INT_A-PARTY_CITY PARTY_INT_A-PARTY_CLRC PARTY_INT_A-PARTY_NAME|
|TRTM_MT300|57A Receiving agent Type A*|PARTY_REC_A-PARTY_BIC|
|TRTM_MT300|57J Receiving agent Type J* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_REC-A-PARTY_BIC PARTY_REC_A-PARTY_ACCT PARTY_REC_A-PARTY_ADD1 PARTY_REC_A-PARTY_ADD2 PARTY_REC_A-PARTY_CITY PARTY_REC_A-PARTY_CLRC PARTY_REC_A-PARTY_NAME|
|TRTM_MT300|33B Currency, Amount Sold|CURRENCY_SOLD + AMOUNT_SOLD|
|TRTM_MT300|53A Delivery agent Type A*|PARTY_DEL_B-PARTY_BIC|
|TRTM_MT300|53J Delivery agent Type J*|PARTY_DEL -B-PARTY_BIC|


|Format Mapping|Field in SWIFT Message|Fieldname in Format Mapping|
|---|---|---|
| |/ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_DEL_B-PARTY_ACCT PARTY_DEL_B-PARTY_ADD1 PARTY_DEL_B-PARTY_ADD2 PARTY_DEL_B-PARTY_CITY PARTY_DEL_B-PARTY_CLRC PARTY_DEL_B-PARTY_NAME|
|TRTM_MT300|56A Intermediary agent Type A*|PARTY_INT_B-PARTY_BIC|
|TRTM_MT300|56J Intermediary agent Type J* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_INT_B-PARTY_BIC PARTY_INT_B-PARTY_ACCT PARTY_INT_B-PARTY_ADD1 PARTY_INT_B-PARTY_ADD2 PARTY_INT_B-PARTY_CITY PARTY_INT_B-PARTY_CLRC PARTY_INT_B-PARTY_NAME|
|TRTM_MT300|57A Receiving agent Type A*|PARTY_REC_B-PARTY_BIC|
|TRTM_MT300|57J Receiving agent Type J* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_REC-B-PARTY_BIC PARTY_REC_B-PARTY_ACCT PARTY_REC_B-PARTY_ADD1 PARTY_REC_B-PARTY_ADD2 PARTY_REC_B-PARTY_CITY PARTY_REC_B-PARTY_CLRC PARTY_REC_B-PARTY_NAME|
| |Transaction Details MM Part - Structure MM| |
|TRTM_MT320|17R Party A’s Role|PARTY_A_ROLE|
|TRTM_MT320|30T Trade Date|TRADE_DATE|
|TRTM_MT320|30V Value Date|VALUE_DATE|
|TRTM_MT320|30P Maturity Date|MATURITY_DATE|
|TRTM_MT320|32B Currency, principal amount|MM-PRINCIPAL_CURRENCY + MMPRINCIPAL_AMOUNT|
|TRTM_MT320|32H Amount to be Settled|MM-SETTLEMENT_CURRENCY + MMSETTLEMENT_AMOUNT|
|TRTM_MT320|30X Next Interest Due Date|MM-NEXT_INTEREST_DUE_DATE|


|Format Mapping|Field in SWIFT Message|Fieldname in Format Mapping|
|---|---|---|
|TRTM_MT320|34E Currency, Interest Amount|MM-INTEREST_CURRENCY + MMINTEREST_AMOUNT|
|TRTM_MT320|37G Interest Rate|MM-INTEREST_RATE|
|TRTM_MT320|14D Day Count Fraction|MM-DAY_COUNT_FRACTION|
|TRTM_MT320|30F Last Day of the First Interest Period|MMLAST_DAY_FIRST_INTEREST_PERIOD|
|TRTM_MT320|38J Number of Days|MM-NUMBER_OF_DAYS_CODE + MMNUMBER_OF_DAYS|
|TRTM_MT320|Transaction Details C Amounts party A| |
|TRTM_MT320|53A Delivery Agent(A)*|PARTY_DEL_A - PARTY_BIC|
|TRTM_MT320|53D Delivery Agent(D)*|PARTY_DEL_A - PARTY_NAME|
|TRTM_MT320|53J Delivery Agent(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_DEL -A-PARTY_BIC PARTY_DEL_A-PARTY_ACCT PARTY_DEL_A-PARTY_ADD1 PARTY_DEL_A-PARTY_ADD2 PARTY_DEL_A-PARTY_CITY PARTY_DEL_A-PARTY_CLRC PARTY_DEL_A-PARTY_NAME|
|TRTM_MT320|56A Intermediary(A)*|PARTY_INT_A - PARTY_BIC|
|TRTM_MT320|56D Intermediary(D)*|PARTY_INT_A - PARTY_NAME|
|TRTM_MT320|56J Intermediary(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_INT -A-PARTY_BIC PARTY_INT_A-PARTY_ACCT PARTY_INT_A-PARTY_ADD1 PARTY_INT_A-PARTY_ADD2 PARTY_INT_A-PARTY_CITY PARTY_INT_A-PARTY_CLRC PARTY_INT_A-PARTY_LEI PARTY_INT_A-PARTY_NAME|
|TRTM_MT320|57A Receiving Agent(A)*|PARTY_REC_A - PARTY_BIC|
|TRTM_MT320|57D Receiving Agent(D)*|PARTY_REC_A - PARTY_NAME|
|TRTM_MT320|57J Receiving Agent(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_REC-A-PARTY_BIC PARTY_REC_A-PARTY_ACCT PARTY_REC_A-PARTY_ADD1|


|Format Mapping|Field in SWIFT Message|Fieldname in Format Mapping|
|---|---|---|
| | |PARTY_REC_A-PARTY_ADD2 PARTY_REC_A-PARTY_CITY PARTY_REC_A-PARTY_CLRC PARTY_REC_A-PARTY_NAME|
|TRTM_MT320|Transaction Details D Amounts party B| |
|TRTM_MT320|53A Delivery Agent(A)*|PARTY_DEL_B - PARTY_BIC|
|TRTM_MT320|53D Delivery Agent(D)*|PARTY_DEL_B - PARTY_NAME|
|TRTM_MT320|53J Delivery Agent(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_DEL -B-PARTY_BIC PARTY_DEL_B-PARTY_ACCT PARTY_DEL_B-PARTY_ADD1 PARTY_DEL_B-PARTY_ADD2 PARTY_DEL_B-PARTY_CITY PARTY_DEL_B-PARTY_CLRC PARTY_DEL_B-PARTY_NAME|
|TRTM_MT320|56A Intermediary(A)*|PARTY_INT_B - PARTY_BIC|
|TRTM_MT320|56D Intermediary(D)*|PARTY_INT_B - PARTY_NAME|
|TRTM_MT320|56J Intermediary(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_INT -B-PARTY_BIC PARTY_INT_B-PARTY_ACCT PARTY_INT_B-PARTY_ADD1 PARTY_INT_B-PARTY_ADD2 PARTY_INT_B-PARTY_CITY PARTY_INT_B-PARTY_CLRC PARTY_INT_B-PARTY_NAME|
|TRTM_MT320|57A Receiving Agent(A)*|PARTY_REC_B - PARTY_BIC|
|TRTM_MT320|57D Receiving Agent(D)*|PARTY_REC_B - PARTY_NAME|
|TRTM_MT320|57J Receiving Agent(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_REC-B-PARTY_BIC PARTY_REC_B-PARTY_ACCT PARTY_REC_B-PARTY_ADD1 PARTY_REC_B-PARTY_ADD2 PARTY_REC_B-PARTY_CITY PARTY_REC_B-PARTY_CLRC PARTY_REC_B-PARTY_NAME|


|Format Mapping|Field in SWIFT Message|Fieldname in Format Mapping|
|---|---|---|
|TRTM_MT320|Transaction Details E Interests party A| |
|TRTM_MT320|53A Delivery Agent(A) *|PARTY_DEL_A_INT - PARTY_BIC|
|TRTM_MT320|53D Delivery Agent(D)*|PARTY_DEL_A_INT - PARTY_NAME|
|TRTM_MT320|53J Delivery Agent(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_DEL_A_INT-PARTY_BIC PARTY_DEL_A_INT-PARTY_ACCT PARTY_DEL_A_INT-PARTY_ADD1 PARTY_DEL_A_INT-PARTY_ADD2 PARTY_DEL_A_INT-PARTY_CITY PARTY_DEL_A_INT-PARTY_CLRC PARTY_DEL_A_INT-PARTY_NAME|
|TRTM_MT320|56A Intermediary(A)*|PARTY_INT_A_INT - PARTY_BIC|
|TRTM_MT320|56D Intermediary(D)*|PARTY_INT_A_INT - PARTY_NAME|
|TRTM_MT320|56J Intermediary(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_INT_A_INT-PARTY_BIC PARTY_INT_A_INT-PARTY_ACCT PARTY_INT__INTA-PARTY_ADD1 PARTY_INT_A_INT-PARTY_ADD2 PARTY_INT_A_INT-PARTY_CITY PARTY_INT_A_INT-PARTY_CLRC PARTY_INT_A_INT-PARTY_NAME|
|TRTM_MT320|57A Receiving Agent(A)*|PARTY_REC_A_INT - PARTY_BIC|
|TRTM_MT320|57D Receiving Agent(D)*|PARTY_REC_A_INT - PARTY_NAME|
|TRTM_MT320|57J Receiving Agent(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_REC-A_INT-PARTY_BIC PARTY_REC_A_INT-PARTY_ACCT PARTY_REC_A_INT-PARTY_ADD1 PARTY_REC_A_INT-PARTY_ADD2 PARTY_REC_A_INT-PARTY_CITY PARTY_REC_A_INT-PARTY_CLRC PARTY_REC_A_INT-PARTY_NAME|
|TRTM_MT320|Transaction Details F Interest party B| |
|TRTM_MT320|53A Delivery Agent(A)*|PARTY_DEL_B_INT - PARTY_BIC|
|TRTM_MT320|53D Delivery Agent(D)*|PARTY_DEL_B_INT - PARTY_NAME|


|Format Mapping|Field in SWIFT Message|Fieldname in Format Mapping|
|---|---|---|
|TRTM_MT320|53J Delivery Agent(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_DEL -B_INT-PARTY_BIC PARTY_DEL_B_INT-PARTY_ACCT PARTY_DEL_B_INT-PARTY_ADD1 PARTY_DEL_B_INT-PARTY_ADD2 PARTY_DEL_B_INT-PARTY_CITY PARTY_DEL_B_INT-PARTY_CLRC PARTY_DEL_B_INT-PARTY_NAME|
|TRTM_MT320|56A Intermediary(A)*|PARTY_INT_B_INT - PARTY_BIC|
|TRTM_MT320|56D Intermediary(D)*|PARTY_INT_B_INT - PARTY_NAME|
|TRTM_MT320|56J Intermediary(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_INT_B_INT-PARTY_BIC PARTY_INT_B_INT-PARTY_ACCT PARTY_INT_B_INT-PARTY_ADD1 PARTY_INT_B_INT-PARTY_ADD2 PARTY_INT_B_INT-PARTY_CITY PARTY_INT_B_INT-PARTY_CLRC PARTY_INT_B_INT-PARTY_NAME|
|TRTM_MT320|57A Receiving Agent(A)*|PARTY_REC_B_INT - PARTY_BIC|
|TRTM_MT320|57D Receiving Agent(D)*|PARTY_REC_B_INT - PARTY_NAME|
|TRTM_MT320|57J Receiving Agent(J)* /ABIC/ACCT/ADD1/ADD2/CITY/CLRC/LEIC/NAME/TXID/|PARTY_REC-B-PARTY_BIC PARTY_REC_B_INT-PARTY_ACCT PARTY_REC_B_INT-PARTY_ADD1 PARTY_REC_B_INT-PARTY_ADD2 PARTY_REC_B_INT-PARTY_CITY PARTY_REC_B_INT-PARTY_CLRC PARTY_REC_B_INT-PARTY_NAME|
|E Reporting information| | |
|TRTM_MT300|22L Reporting Jurisdiction|REPORT_JURISDICTION|
|TRTM_MT300|22M UTI Namespace/Issuer Code|UTI_NAMESPACE|
|TRTM_MT300|22N Transaction Identifier|TRANSACTION_ID|


**Note:**

In option J, party identification must be specified as a list of pairs (Code)(Value) and one or more of the following codes and formats must be used (Error code(s): T78). The codes must be placed between slashes ('/').

ABIC 4!a2!a2!c[3!c] Identifier Code

ACCT 34x Account number

- ADD1 34x First line of the address

- ADD2 34x Second line of the address


CITY 34x City, possibly followed by state and country/region

CLRC 2!a[32x] Clearing code

LEIC 18!c2!n Legal Entity Identifier

Must be filled with 20 characters in total.

Only used in MT300 and MT320 in fields 82J and 87J.

NAME 34x Party's name

TXID 34x Tax identification code

Only used in MT300 and MT320 in fields 82J and 87J.

* The following rules apply for filling the relevant fields for the party identification.

Decision Table for Option A or J

|BIC|Value|Value|Space|Space|
|---|---|---|---|---|
|PARTY_LEI PARTY_ACCT PARTY_CITY PARTY_ADD1 PARTY_ADD2 PARTY_CLRC PARTY_TXID|Value|Space|Value|Space|
|Result|Option J|Option A|Option J UKWN|Empty|


Decision Table for Option A or D or J

|PARTY_BIC|Value|Value|Value|Value|Space|Space|Space|Space|
|---|---|---|---|---|---|---|---|---|
|PARTY_NAME|Value|Value|Space|Space|Value|Space|Value|Space|
|Others: PARTY_LEI PARTY_ACCT PARTY_CITY PARTY_ADD1 PARTY_ADD2 PARTY_CLRC PARTY_TXID|Value|Space|Space|Value|Space|Value|Value|Space|


|Result|J|A|A|J|D|J UKWN|J UKWN|Empty|
|---|---|---|---|---|---|---|---|---|


**Note:**

Value = The field is filled with a value.

Space = The field is empty.

For the Others: Value = At least one Others field is filled with a value.

For the Others: Space = All Others fields are empty.

J UKWN = Option J is used with code /ABIC/ = UKWN.

No decision tables are needed for the incoming formats. Incoming formats always support options A or D or J.

**Information for Delivered Format Mapping for MT535 Messages**

Specific Fields Mapping

|Format Mapping|Field in SWIFT Message|Field in Format Mapping|
|---|---|---|
|A General Information| | |
|TRM_MT535|23G Message Function Value of function: 'NEWM' 'CANC' Value of subfunction: 'CODU' 'DUPL' 'COPY'|GENERAL-OPERATION_TYPE Values: 'NEW' 'CANC' 'DUPL' Defined rules: when subfunction!=null and subfunction == ('CODU' or 'DUPL' or 'COPY') then 'DUPL’ when function = 'NEWM' then 'NEW' when function = 'CANC' then 'CANC'|
|TRM_MT535|20C Reference: Sender's Message Reference in A|GENERAL-SENDER_REFERENCE (Sender Reference) SEC-SECURITIES_ACCOUNT-EXT_REF1 **Note:** EXT_REF1 will be copied to securities main data in correspondence object, and also copied to external securities account statement. |


|Format Mapping|Field in SWIFT Message|Field in Format Mapping|
|---|---|---|
|TRM_MT535|20C Reference: Sender's Message Reference in A1|GENERAL-RELATED_REFERENCE (Related Reference) **Note:** A1 is optional, but it is mandatory while message function is cancel (:23G:CANC)|
|TRM_MT535|28E Page Number in A This field provides the page number of the message (within a statement) and a continuation indicator to indicate that the statement is to continue or that the message is the last page of the statement. Continuation Indicator must contain one of the following codes (Error code(s): T97): 'LAST' Last page of a statement with more than one page. 'MORE' Intermediate page of a statement which contains additional pages. 'ONLY' Only page of the statement.|GENERAL-PAGE_INFORMATION (Page Number/Continuation Indicator) Technical value to identify the same external account statement when it is split across multiple messages due to length limitation. This means that several SWIFT MT553 messages are received for one external account statement. The message with several pages can be identified by the continuation indicator in GENERAL- PAGE_INFORMATION. If it is 'ONLY' the message is a one page message. If the value is 'MORE'/'LAST', the message is one of several pages.|
|TRM_MT535|13A Number Identification: Statement Number in A|GENERAL-STATEMENT_REFERENCE (Statement Reference)|


|Format Mapping|Field in SWIFT Message|Field in Format Mapping|
|---|---|---|
|TRM_MT535|98A Date/Time in A|SEC-SECURITIES_ACCOUNTDELIVERY_DATE (Securities Account Delivery Date) SEC-SECURITIES_ACCOUNTDELIVERY_TIME (Securities Account Delivery Time) SEC-SECURITIES_ACCOUNTSTATEMENT_DATE (Securities Account Statement Date) Defined rules: Copy date value from 98A/C:STAT > STATEMENT DATE Copy date value from 98A/C/E:PREP or copy date value from 98A/C:STAT -> DELIVERY DATE Copy time value from 98C/E:PREP or copy time value from 98C:STAT > DELIVERY TIME|
|TRM_MT535|20C Reference: Sender's Message Reference in A|GENERAL-SENDER_REFERENCE (Sender Reference)|
|TRM_MT535|97A Account: Safekeeping Account in A 97A Account: Safekeeping Account in B |SEC-SECURITIES_ACCOUNT-SA_DATAEXT_SEC_ACC_NO (Exernal Securities Account Number) Defined rule: Copy value of account number from 97A **Note:** If the message is consolidated (:17B::CONS//Y), then in every occurrence of sequence B field :97a::SAFE is mandatory Two options are provided,97A and 97B, could retrieve value from any one of them|
|B1 Optional Repetitive Subsequence Financial Instrument| | |
|TRM_MT535|35B Identification of the Financial Instrument in B1|SEC-SECURITIES_ACCOUNT-SA_DATAPOSITIONS-SECURITY_ID (External Securities ID - ISIN)|
|TRM_MT535|93B Balance AGGR in B1|SEC-SECURITIES_ACCOUNT-SA_DATAPOSITIONS-UNITS (Position Units) SEC-SECURITIES_ACCOUNT-SA_DATAPOSITIONS-AGGREGATE_BALANCE|


|Format Mapping|Field in SWIFT Message|Field in Format Mapping|
|---|---|---|
| | |(Aggregate Balance) Defined rules: Qualifier = AGGR and code = ʻUNIT’ in value -> UNITS Qualifier = AGGR and code = ʻFAMT’ (ʻAMOR’ if no ʻFAMT’) in value -> AGGREGATE_BALANCE **Note:** Format - (Qualifier)(Data Source Scheme)(Quantity Type Code)(Sign) (Balance)|
|TRM_MT535|19A Amount in B1|SEC-SECURITIES_ACCOUNT-SA_DATAPOSITIONS-HOLDING_AMOUNT (Amount Holding) SEC-SECURITIES_ACCOUNT-SA_DATAPOSITIONSHOLDING_AMOUNT_CURRENCY (Currency Holding) Defined rules: Qualifier = HOLD Amount -> HOLDING_AMOUNT Qualifier = HOLD Currency Code -> HOLDING_AMOUNT_CURRENCY **Note:** Format - (Qualifier)(Sign)(Currency Code)(Amount)|
|TRM_MT535|22F Indicator in A Qualifier 'CODE' Complete/Updates Indicator, specifies whether the statement is complete or contains changes only. 'COMP' = Complete 'DELT' = Delta|Only 'COMP' supported|
|TRM_MT535|22F Indicator in A Qualifier 'STBA' Statement Basis, specifies the type of balances on which the statement is prepared. 'CONT' Contractual Statement is based on contractual settlement date positions, irrespective of failed instructions. 'SETT' Settled Statement is based on actual settlement date positions.|Only statements with basis 'CONT' or 'SETT' supported.|


|Format Mapping|Field in SWIFT Message|Field in Format Mapping|
|---|---|---|
| |'TRAD' Traded Statement is based on trade date positions.| |
|TRM_MT535|22F Indicator in A Qualifier 'STTY' Statement Type, specifies the usage purpose of the statement of holding. 'ACCT' Accounting Statement is an accounting statement. 'CUST' Custody Statement is a custody statement.|Both statement types are supported|
|TRM_MT535|17B Flag Qualifier 'ACTI' = Activity flag, that indicates whether holdings are reported in this statement. Codes: 'Y' = Yes 'N' = No|Only qualifier 'ACTI' with code 'Y' is supported.|

###### Map Format Data for Treasury Correspondence

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Exchange Treasury Correspondence via SWIFT > Define Your Own Format Mapping > Map Format Data for Treasury Correspondence | L6 | trm06 p.193 | loio `48a77e65b1a24ecf8afa2c6fc5b317f8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/48a77e65b1a24ecf8afa2c6fc5b317f8.html?locale=en-US)

Define your own format mappings for the outbound and inbound process.

For more information, see Define Your Own Format Mapping.

Assign Format Mappings for Outbound Process

The Treasury Correspondence Objects are created automatically when you save a financial transaction. They carry the data of the financial transaction. Before you can create the MT300/MT320 file, a format mapping must first be

defined and assigned to the formats. Within the format mapping, the fields of the correspondence objects must be mapped to the fields of the SWIFT messages.

To define your own format mappings for the outbound process, you use the Map Format Data for Treasury Correspondence Customizing activity.

Assign Format Mappings for Inbound Process

To define your own format mappings for the inbound process, you use the Map Format Data for Treasury Correspondence Customizing activity.

**Note:**

The MT300 and MT320 formats should have the Normal in- or outbound message message type and should belong to the SWIFT MT message format group. They must be assigned to the MBC Multi-Bank Connectivity channel, for the Counterparty sender/recepient type, and PR_MBC profile (which is marked as relevant for the automatic creation of SWIFT messages). You can use them for the outbound as well as for the inbound process:

The MT300 format is used for FX transactions and FX options, so it should be assigned to the correspondence class DEAL_FX.

The MT320 format is used for MM transactions, so it should be assigned to the correspondence class DEAL_MM.

The MT535 format should have the Normal in- or outbound message message type and should belong to the SWIFT MT message format group. It should be assigned to the MBC Multi-Bank Connectivity channel, for the DEPOSITORYBANK sender/recepient type, and PR_MBC profile (which is marked as relevant for the automatic creation of SWIFT messages). You can use them for the inbound process:

The MT535 format is used for external securities account statements, so it should be assigned to the correspondence class SEC_STMNT_HOLD.

Define the following master data:

Assign BIC to Business Partner

Assign the bank identifier code (BIC) to your business partners (counterparties and depository banks).

Assign Correspondence Class for Inbound Process Dependent on Recipient

Assign the correspondence classes for the MT300 and MT320 formats to your counterparties (recipient type) dependent on the business partner group.

Assign the correspondence classes for the MT535 format to your depository banks (recipient type) dependent on the business partner group.

For MT535 messages, you must enter the External Securities Account ID and the Depository Bank in the securities account master data using Manage Securities Accounts app.

For MT535 messages, you must enter the ISIN for all your security classes. You can either enter the ISIN as secondary index or use the ISIN as security class ID number.

**Note:**

For the communication with SWIFT a general SWIFT Character Set (X Character Set) is defined:

"Computer-based terminals communicating with SWIFT use EBCDIC code. The character set is as follows:

a b c d e f g h i j k l m n o p q r s t u v w x y z

A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

0 1 2 3 4 5 6 7 8 9

/ - ? : ( ) . , ' +

CrLf Space

The characters Cr and Lf must never be used as single characters and must only be used together in the sequence CrLf, that is, LfCr is not allowed.

When the character sequence CrLf is used in a field format with several lines, it is used to indicate the end of one line of text and the start of the next line of text."

Make sure that the data send with the SWIFT messages do not contain other characters.

**Note:**

For example, do not enter 'ß' in the address data of your business partner.

**Processes**

Treasury Correspondence - Outbound Process (SWIFT)

[figure TRM06-F091 - Treasury Correspondence - Outbound Process (SWIFT)]

- 1. Create financial transaction (FX transaction, FX option, or money market transaction).
- 2. The correspondence object is created automatically.
- 3. Send the correspondence object using he Send Correspondence app, or the Process Correspondence - Monitor app.
- 4. The system automatically creates the MT300/MT320 file including the SWIFT parameters according to the format mapping assigned. The file name is Format + CO Key.
- 5. The system sends the MT300/MT320 file to SAP Multi-Bank Connectivity.
- 6. The correspondence object gets the status Acknowledgment Awaited.
- 7. SAP Multi-Bank Connectivity generates the SWIFT message by adding a SWIFT envelope around the files received for MT300 / MT320.


- 8. SAP Multi-Bank Connectivity sends the SWIFT message to the SWIFT infrastructure.
- 9. SAP Multi-Bank Connectivity gets a response from the SWIFT infrastructure and passes the response to the SAP S/4HANA system:


- a. If an error occurred and the counterparty did not receive the SWIFT message, the non-acknowledge (NACK) response is sent from SAP Multi-Bank Connectivity automatically to SAP S/4HANA system. The system matches the response to the correspondence object and updates the status to Error. Analyze the error and correct the financial transaction data or the correspondence object. Send the correspondence object again.
- b. When the counterparty received the SWIFT message, the acknowledge (ACK) response is sent from SAP Multi-Bank Connectivity automatically to the SAP S/4HANA system. The system matches the response to the correspondence object and updates the status to Delivery.


**Note:**

During the process, you can check the status of your correspondence objects using the Process Correspondence Objects Monitor app.

Treasury Correspondence - Inbound Process (SWIFT)

[figure TRM06-F092 - Treasury Correspondence - Inbound Process (SWIFT)]

- 1. If the SAP Multi-Bank Connectivity gets a SWIFT message from one of your counterparties and depository banks, it automatically sends the message to the SAP S/4HANA system.
- 2. The incoming MBC files are automatically analyzed and an incoming correspondence object is created.
- 3. For the incoming MT535 messages, system automatically creates the external securities account statements that you can display using Manage Statements - External Securities Account app and reconcile with your positions on internal securities accounts using Reconcile Statements - External Securities Accounts app. For more information, see also External Securities Account Statements.

- 4. If the correspondence objects for MT300 and MT320 messages are matched correctly, the status of the outgoing and incoming correspondence objects needs to be changed to Matched or Completed depending on the system setting.


**Note:**

For an incoming message of MT535 referring to multiple external securities accounts (:17B::CONS//Y) the system creates a correspondence object for each external securities account.

###### Including Custom Reference Fields

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Exchange Treasury Correspondence via SWIFT > Define Your Own Format Mapping > Including Custom Reference Fields | L6 | trm06 p.210 | loio `4117c92120224f1b92f36b54a49174ca` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4117c92120224f1b92f36b54a49174ca.html?locale=en-US)

This topic describes how to include your own custom reference fields when you define your own format mapping for your treasury correspondence.

You use the Business Add-In (BAdI) Treasury Correspondence: Format-Dependent Customer Data. Based on the fields of the treasury correspondence object (adminstrative data and main data), you can define additional custom reference fields. You can use these fields later within your own format mapping.

- 1. Launch the Custom Fields and Logic app from the Extensibility business group on your launchpad.
- 2. Switch to the Custom Logic tab.
- 3. Choose + (Create) to add an enhancement implementation.
- 4. Fill out the dialog box as explained in the following table and then choose Create.


**Note:**

For you to be able to access this app, your user must be assigned a role that has the authorization as defined in the business catalog Extensibility (SAP_CORE_BC_EXT).

|Field|Explanation|
|---|---|
|Business Context|Select Treasury Correspondence Object.|


|Field|Explanation|
|---|---|
|BAdI Description|Select Treasury Correspondence: Format-Dependent Customer Data.|
|Implementation Description|Enter a description, for example TRM_Correspondence.|
|Implementation ID|The field is filled out automatically as you enter the implementation description. You can change the ID if you like.|


- 5. Switch to the Filter tab.
- 6. Choose + (Add) to add a filter condition.
- 7. Choose + (Add) to add an entry.
- 8. Fill out the dialog box as explained in the following table and then choose Save.
- 9. Adapt the code in the Draft Logic section to your business needs.
- 10. Choose Publish in the bottom-right corner.
- 11. Assign the field values to target fields within the definition of your own treasury Correspondence format mapping.


|Field|Explanation|
|---|---|
|Filter Parameter|Select format.|
|Comparator|Select =.|
|Value|Enter the treasury correspondence format to which you want to add custom reference fields.|


For more information, see Define Your Own Format Mapping

**Related Information**

Exchange Treasury Correspondence via SWIFT Define Your Own Format Mapping

##### Terms in Treasury Correspondence

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Terms in Treasury Correspondence | L4 | trm06 p.211 | loio `0bc6a1508d459d04e10000000a441470` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/0bc6a1508d459d04e10000000a441470.html?locale=en-US)

Here you get more details about terms used in correspondence function.

|Term|Definition|
|---|---|
|Correspondence|Correspondence refers to all written forms of communication between business partners. Correspondence can be sent via various communication channels in different formats.|
|Correspondence Monitor|You can use the correspondence monitor to obtain an overview of the existing correspondence objects. From the monitor, you can edit existing correspondence objects and create new (incoming/outgoing) correspondence objects manually.|


|Term|Definition|
|---|---|
|Correspondence Object (CO)|A correspondence object contains the administration and Customizing data necessary for creating correspondence. It is created automatically in accordance with the settings defined in Customizing; however, it can also be created manually in the correspondence monitor. The data of the correspondence object and the corresponding data of the corresponding business transaction form the payload from which the correspondence is created and sent via the correspondence interface (Messaging).|
|Assigning Correspondence Objects|A correspondence object is assigned to just one financial transaction or securities account. Any number of correspondence objects (their number being designated here as "n") can be assigned to a financial transaction/securities account.|
|Matching Correspondence Objects|When matching two or more correspondence objects of a financial transaction/securities account (in accordance with the settings defined in Customizing), their match rate is checked in n fields. If the fields match, the status of the correspondence objects is set to Matched.|
|Status of Correspondence Objects|A correspondence object can have the following statuses: Created Awaiting Approval Returned Rejected Released Sent Reversed Matched Closed Received ACK Missing Error when sending Removed Channel answer received The status of the CO is visible in the corresponding financial transaction or securities account.|
|Payload|Contains the data of the correspondence object and the data of the corresponding business transaction. The payload consists not only of a single structure but also contains tables, table categories, and structures that can be used in the communication between the correspondence monitor and correspondence interface (messaging).|


|Term|Definition|
|---|---|
|Correspondence Class|A correspondence class defines how correspondence is used. Different correspondence classes are delivered. Examples: Purchase/Sales order Transfer order In Customizing, you can define your own correspondence classes.|
|Correspondence Recipient Type|Each type of business partner or involved party that could receive correspondence during the processing of the financial transactions or transfers. Examples: Internal Business partner|
|Correspondence Messaging Interface|The Correspondence Messaging Interface between the correspondence monitor and the middleware of TRM creates and sends outgoing correspondence for correspondence objects as well as correspondence objects for incoming correspondence.|
|Communication Channel|Defines the fixed rules according to which messages are dealt with during incoming/outgoing processing. In the communication channel, you define, for example, the type of adapter used for incoming/outgoing processing and how the adapter is configured.|
|File Adapter|Implementation of the Correspondence Messaging Interface for the communication channel FILE.|
|SWIFT Implementations|You define the implementation for SWIFT messages for all supported SWIFT formats.|
|Document Management (CA-DMS)|Document management uses the correspondence messaging interface to save all incoming/outgoing correspondence as well as just parts of it or temporary data.|

##### Correspondence Monitor

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Correspondence Monitor | L4 | trm06 p.213 | loio `6d0cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6d0cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

The correspondence monitor (transaction FTR_COMONI) provides an overview of all the correspondence objects available. You can edit these and also create new correspondence objects. You can use the correspondence monitor to conduct the entire trade process without the need for re-keying or manual intervention. Straight through-processing exists throughout the entire trade lifecycle.

**Prerequisites**

You can make the required settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Correspondence.

**Features**

The following functions are available:

Create Manually (incoming and outgoing correspondence objects)

Change

Display Correspondence Object

Display Correspondence

Cancel

Assign

Send

##### Individual Functions

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Individual Functions | L4 | trm06 p.214 | loio `700cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/700cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

With the function Create Correspondence Object (FTR_COCREATE), you can c reate and a ssign the relevant entities that contain runtime information to a correspondence. These entities are determined by you and can include the name of an employee, type of product or service being provided, and other details that are relevant to the requisite transaction.

With the function Send Correspondence (FTR_COSEND), you can execute correspondence on the basis of the planned records and assigned entities for the transactions selected. A correspondence tool creates a correspondence container for each recipient from a correspondence request. Each correspondence container saves references to correspondence data in an abstract form and the records the control parameters for creating correspondence.

With the function Match Correspondence (FTR_COMATCH), you can automatically match correspondence objects. This means that incoming and outgoing correspondence can be matched with each other through their respective deal number and company code, thereby creating a link between various correspondence. Also, w ith a user exit you can matchoutgoing confirmations with the original incoming correspondence. For example, the correspondence class for a money market deal of incoming correspondence can be matched with a correspondence class for a money market deal of outgoing correspondence based on the deal number of the correspondence object table as the parameter.

The function Import Incoming Messages (FTR_IMPORT) is also available.

**Prerequisites**

You can make the required settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Correspondence.

###### Create Correspondence Objects

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Individual Functions > Create Correspondence Objects | L5 | trm06 p.214 | loio `9f4df452349b0375e10000000a44538d` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9f4df452349b0375e10000000a44538d.html?locale=en-US)

Use

With this function, you can enter correspondence objects manually. This is sometimes necessary, such as when you have received a counterconfirmation by fax.

**Activities**

- 1. Call the function by choosing Transaction Manager Money Market/Foreign Exchange/Derivatives/Securities/Debt Management Back Office Correspondence Individual Functions Create Correspondence Objects (transaction FTR_COCREATE).
- 2. Choose a correspondence category.

01Transaction Activities

If you choose this correspondence category, you need to choose the company code and the product type in the next step.

02Securities account transfer

If you choose this correspondence category, you need to choose the company code and the securities account in the next step.

- 3. Specify whether the correspondence is incoming or outgoing.


If you want to enter an incoming correspondence, you need to choose the appropriate entry option:

01Fast Entry

This option provides a very fast method for manually entering incoming correspondence data with minimal transaction details and correspondence administration details. This method is only available for correspondences related to money market and foreign exchange transactions.

02No Template

This method takes the user to a detailed entry screen for incoming and outgoing correspondences. The entry screen is almost empty and requires the user to enter all correspondence details, both administrative data and transaction-specific data.

03Transaction as Template

This method takes the user to a detailed entry screen for incoming and outgoing correspondences. This entry option is only available for correspondences relating to specific transactions. The system fetches the transaction data and enters it into the correspondence entry screen on the basis of the transaction details specified by the user as a template. The administrative details, however, remain empty and have to be filled by the user.

04Securities Account as Template

This method takes the user to a detailed entry screen for incoming and outgoing correspondences. This entry option is only available for correspondences relating to securities account transfers. The system fetches the securities account transfer data and enters it into the correspondence entry screen on the basis of the securities account transfer details specified by the user as a template. The administrative details, however, remain empty and have to be filled by the user.

05Correspondence Object as Template

This method takes the user to a detailed entry screen for incoming and outgoing correspondences. With this entry method, the system fetches all template details provided by another correspondence. Both the administrative details as well as the transaction and securities account transfer details are copied from the correspondence specified as the template. The data can then be modified where necessary.

- 4. You can choose a display variant.
- 5. Choose .


- 6. Depending on the entry option that you have chosen, the related entry screen appears for the correspondence object data.

Fast Entry

If you want to enter an incoming correspondence using the Fast Entry option, you need to fill the following fields:

Administrative Data

Recipient/Sender Type

Send

BP Group

Profile

Correspondence Class

Entering Confirmation Data

Which fields are available here depends on the product type that you have chosen.

Assigned Transaction

In this area, you see the assigned transaction that has been determined using the data entered above (transaction number, product type, transaction type, contract date, and activity type).

In addition, entries can be made for financial transactions in the following fields:

External Reference

Business Partner

Trade Repository Reporting

This area is visible in the case of financial transactions that are relevant for trade repository reporting.

In this area, entries can be made in the following fields:

Legal Basis

External Trade ID

- 7. Save your entries.

##### Correspondence Alerts

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Correspondence Alerts | L4 | trm06 p.216 | loio `adacd9d3cc474502b00841a69112a191` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/adacd9d3cc474502b00841a69112a191.html?locale=en-US)

**Use**

You can use Send Correspondence Alerts (FTR_ALRT_BTCH) to send an alert notification for a pending transaction activity such as a settlement, posting, correspondence confirmation etc.

You use the Alert Monitor (FTR_ALERT) to monitor the processing status of alerts inbound and outbound, and to process alerts manually.

**Prerequisites**

You need to define and assign alert categories. You can make the required settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Correspondence Alert .

Define alert categories to maintain the recipients of the alert, text for the alert message, and other properties of the alert message.

Assign the alert categories defined to the product types, transaction types, and the activity of the contract type. Whenever an alert notification has to be sent for a transaction, you use the alert category assigned to the product type of that transaction. Example product types are:

**Money Market**

Foreign Exchange

Derivatives

Securities

You can use BAdI: Alert Attributes to define your own alerts. These alerts can be used in:

Financial Transaction Manager: Alert Monitor

Correspondence Alert in Batch Job

Correspondence Monitor

See the relevant BAdI documentation in Customizing for more details.

**Activities**

There are two ways to process alerts. You can use:

Financial Transaction Manager: Alert Monitor (FTR_ALERT)

Correspondence Alert in Batch Job (FTR_ALRT_BTCH)

Both screens contain the same selection criteria. Correspondence Alert in Batch Job contains the general and alert selection criteria on one screen.

The Financial Transaction Manager: Alert Monitor screen has a Correspondence tab on which you can make alert selections in addition to the General Selection criteria. All correspondence objects that are not matched within the selected time frame are selected for alert on the results page. You can choose your selection criteria from:

Issue no messages – tick the check box if you do not want to send any alert messages.

Selections for Securities Account Transfer – enables you to make selections for securities account transfers. See Securities Account Transfers.

Report Open Counter Confirmation – Set the time frame within which the confirmation must be sent before an alert is opened. All correspondence objects which are in status Delivered but with no match Id whose confirmation status and counter confirmation required status are set are selected for alert. In addition, all correspondence objects which are Delivered and Matched but the matching incoming correspondence object does not have counter confirmation status as set, then the incoming correspondence object is a status message and this outgoing correspondence object is still open for counter confirmation. Therefore it is also selected for alert.

Report Open Outgoing Confirmation Time – Set the time frame within which the confirmation must be sent before an alert is opened. All outgoing correspondence objects which do not have the status Delivered with no match Id and with creation date and time exceeding the selection date and time for outgoing confirmation, are selected for alert.

Report Open Incoming Confirmation – Set the time frame within which the confirmation must be received before an alert is opened. All incoming correspondence objects which have the status Received with no match Id and its counter confirmation status being set indicating that it's an incoming confirmation message, are selected for alert.

When the selection criteria has been entered, Execute the transaction to view all alerts matching the criteria. You can then save the alert in various formats (word processing, spreadsheet etc.) and send the alert.

**More Information**

For more information, see also Alert Monitor.

###### Define Fixing References

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Correspondence Alerts > Define Fixing References | L5 | trm06 p.218 | loio `056e5c63cbc44ebf846d0600d3818e49` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/056e5c63cbc44ebf846d0600d3818e49.html?locale=en-US)

Define fixing references needed for the confirmation of Non-Deliverable Forwards using SWIFT MT300.

**Prerequisites**

In the Customizing Define Locations available in the Customizing of the Transaction Manager under General Settings Correspondence General Settings you define locations and financial centers where fixing of FX rates takes place .

**Use**

Fixing references specify how a FX rate fixing takes place. In the fixing reference for a specific currency pair (leading and following currency) the fixing reference source (published by e.g. EMTA or ISDA), the location code (e.g. for London) and the fixing time (e.g. 16:00) is defined. The following fixing reference categories are available:

Fixing Reference Categories

|Category|Explanation|
|---|---|
|1 General Fixing Reference|You need to define source, location and time as agreed with your counterparties and needed for SWIFT MT300 For example: ID: WM/REFINITIV USD/EUR 4 pm Desc.: WM/REFINITIV USD/EUR 4 pm LCrcy: EUR FCrcy: USD Cat.: 1 Source: EUR2 Location: GBLO Time: 16:00|
|2 EMTA Fixing Reference|If the terms for the specific currency pair are governed by an EMTA template, you choose this fixing reference category. You do not need to enter the source, location and time. For example: ID: BRL09|


|Category|Explanation|
|---|---|
| |Desc.: BRL PTAX (BRL09) LCrcy: USD FCrcy: BRL Cat.: 2 This fixing reference will be confirmed as EMT00 (see SWIFT MT300 documentation for field 14S).|
|3 Compound Fixing Reference|If you set up e.g. a cross-currency fixing reference where two fixing steps are necessary, you need to choose the category compound fixing reference. You define a compound fixing reference BRL09WM/REFINITIV USD/EUR with a description like BRL PTAX (BRL09)-WM/REFINITIV USD/EUR 4pm and in the table Specify Compound Fixing Reference Details you assign the two (noncompound) fixing references in the sequence of reference currency followed by the settlement currency. For example, for the compound fixing reference for EUR/BRL you must assign a non-compound fixing reference for fixing USD/BRL (e.g. BRL09) and the non-compound fixing reference for fixing USD/EUR (e.g. WM/REFINITIV USD/EUR 4 pm).|


If the locations and fixing references are defined, you enter the fixing reference ID on the structure tab in the financial transaction data of Non-Deliverable Forwards. From the entered fixing reference ID the system can derive the fixing details needed to fill the specific fields in SWIFT MT300 messages.

###### Define Values for Expiry Time

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Correspondence Alerts > Define Values for Expiry Time | L5 | trm06 p.219 | loio `11c2f9a7e5de4db193dd30b27ec7d5c5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/11c2f9a7e5de4db193dd30b27ec7d5c5.html?locale=en-US)

Assign location codes to times to define values for the expiry time of an FX option.

**Prerequisites**

You have defined location codes for locations and financial centers in the Customizing activity Define Location Codes under Transaction Manager General Settings Correspondence General Settings Define Location Codes

**Process**

You use the Define Values for Expiry Time (transaction FTR_EXPIRY_TIME_DEF) function to specify expiry times for FX options by assigning location codes to times.

- 1. Choose New Entries.
- 2. Select a 4-digit Location Code and a description.
- 3. Enter the relevant expiry time.
- 4. Save your entries.


**Result**

Now that the times are assigned to the location codes, you can enter the expiry time for FX options on the Structure tab of the Create Financial Transaction function.

**Related Information**

Creating an FX Option Create Collar FX Option

###### Assign BIC to Business Partner

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Correspondence Alerts > Assign BIC to Business Partner | L5 | trm06 p.220 | loio `670cda531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/670cda531198434de10000000a174cb4.html?locale=en-US)

**Use**

With Assign BIC to Business Partner (transaction FTR_BP_BIC), you can assign a Bank Identifier Code (BIC) and an external security account ID to your business partner.

**Prerequisites**

You can make the required settings in Customizing under Financial Supply Chain Management Treasury and Risk Management Transaction Manager General Settings Correspondence .

###### Assign Business Partner Group and Profiles

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Correspondence Alerts > Assign Business Partner Group and Profiles | L5 | trm06 p.220 | loio `a6ea32ba287c4a18a6d5090e326283d6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/a6ea32ba287c4a18a6d5090e326283d6.html?locale=en-US)

**Use**

Each business partner acting as a recipient or sender has to be assigned a business partner group and communication profile in order to derive the business attributes and technical attributes. However, if no assignment is found for a business partner, the system will try to find the assignment based on wildcard entries.

With the functions:

Maintain Profile and BP Group Assignments to External Recipients (FTR_EXT_ASSIGN)

Maintain Profile and BP Group Assignments to Internal Recipients (FTR_INT_ASSIGN)

You make an assignment between Business Partner / Company Code / Recipient Type for possible Contract Category / Product Category / Product Type / Activity Category with Profile / Business Partner Group.

**Prerequisites**

Ensure that the business and technical settings have been made in Customizing. In particular:

Business Partner Groups

Sender/Recipient Types

Communication Profiles

See Correspondence Framework.

**Activities**

To make a new business partner group and profile assignment:

- 1. Open SAP menu: Accounting Financial Supply Chain Management Treasury and Risk Management Transaction Manager Money Market/Foreign Exchange/Derivatives/Securities Back Office Correspondence Master Data

Maintain Profile and BP Group Assignments to External/Internal Recipients

- 2. Choose Insert Row and enter business partner or internal recipient, company code and sender/recipient type.

A new tree structure for the combination is displayed to the right. You can open the tree structure and view the markets and financial transactions available to this business partner.

- 3. Select the market or financial transaction to assign the business partner group and profile.

Any existing assignments are displayed in the assignments area below the tree structure.

- 4. Choose Insert Row in the assignments area.
- 5. Enter a profile and business partner group.
- 6. You can also add more details, such as:

User name (internal recipient only)

Country/Region (internal recipient only)

Fax number (internal recipient only)

Email address (internal recipient only)

Alternative address (external recipient only)

- 7. Choose Save.

###### Assign Correspondence Class for Inbound Process Dependent on Recipient

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Correspondence Alerts > Assign Correspondence Class for Inbound Process Dependent on Recipient | L5 | trm06 p.221 | loio `f99cfc4cb36a4bc98c4592a0b0f8ac16` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/f99cfc4cb36a4bc98c4592a0b0f8ac16.html?locale=en-US)

Transaction Code: FTR_INB_FUNC

With this function, you assign for each format, business partner, and recipient type the correspondence class for the inbound process, to enable the SWIFT inbound process for the MT300 and MT320 formats.

**Activities**

- 1. Choose New Entries.
- 2. Choose the Format (either MT300 or MT320).
- 3. Enter the business partner ID in BPartner field.
- 4. Choose in the Recipient/SendType field the COUNTERPARTY value.
- 5. Assign the Correspondence Class. The correspondence classes are predefined. You can either choose DEAL_FX, DEAL_DER, or DEAL_MM.


**Supported Device Types**

Desktop

Tablet

**Related Information**

Exchange Treasury Correspondence via SWIFT

##### Migration of Correspondence Data

> **Path:** Treasury and Risk Management > Transaction Manager > Treasury Correspondence > Migration of Correspondence Data | L4 | trm06 p.222 | loio `4b29fcd9e16b4cb9e10000000a42189b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4b29fcd9e16b4cb9e10000000a42189b.html?locale=en-US)

**Use**

If you used the old correspondence function in your predecessor SAP ERP system before the upgrade to SAP S/4HANA and the correspondence framework was not technically available in this older SAP ERP release, you can migrate your system settings and application data related to your correspondence from the old tables to the new tables.

Specific conversion programs are available for the migration of correspondence data in Customizing for the Transaction Manager under General Settings Tools Conversion Programs (transaction TPM_MIGRATION).

**Note:**

We recommend that you rebuild the correspondence framework Customizing and not migrate from the existing correspondence settings. Only use the migration of correspondence data if you must display the old correspondence data in SAP S/4HANA for auditing purposes.

**Prerequisites**

The upgrade to SAP S/4HANA is finished.

You used the old correspondence function in your predecessor SAP ERP system before the upgrade to SAP S/4HANA and the correspondence framework was not technically available in this older SAP ERP release.

Together with your external auditor, you have determined that the old correspondence data needs to be available for display in your SAP S/4HANA system.

You set the appropriate conversion type in Customizing for the Transaction Manager under General Settings Tools

Conversion Conversion Customizing Set Migration Type and Assign to Customizing Request . All conversion programs to be executed after the upgrade are displayed in the Conversion Programs (transaction TPM_MIGRATION) Customizing activity in accordance with the conversion type selected.

**Process**

To convert the correspondence data, you must carry out the following conversion steps in the sequence listed below. We recommend that you perform the conversion in your quality system first. If the conversion was successful in the quality system, perform the conversion in the production system as well.

**Note:**

These steps could have different step numbers depending on the conversion type selected.

1. Convert Customizing for Correspondence (I03)

This company code-independent step converts the Customizing settings for correspondence types, correspondence activities, printer options, and so on.

- 2. Convert Business Partner Standing Instructions for Correspondence (K14)

This company code-specific step converts any standing instructions defined for a business partner.

- 3. Convert Correspondence Data (K15)


This company code-specific step converts correspondence into the new format of the new correspondence framework.

**Result**

The Customizing settings correspond to your previous settings. However, you may have to make some small adjustments.

You can now process the migrated correspondence objects using the new correspondence monitor (transaction FTR_COMONI).

