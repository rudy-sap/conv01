# Foreign Exchange Exposure - SAP TRM Knowledge Base (branch split)

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

### Foreign Exchange Exposure (1 of 2)

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure | L2 | trm12 p.16 | loio `c3e11b2bf49f4baa8ca18650c418df4c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/c3e11b2bf49f4baa8ca18650c418df4c.html?locale=en-US)

You can use this inbound OData service to create, read, and process foreign exchange exposures. FX exposures are planned incoming or outgoing foreign currency cash flows that bear the risk of financial losses due to exchange rate fluctuations. They can be entered and processed manually using the Manage FX Exposures app or with this service.

The status concept and available functions for FX exposures that are relevant within the Manage FX Exposures app are also relevant for processing FX exposures using the API. For more information, see also Manage FX Exposures.

This service is published on the SAP Business Accelerator Hub. For more information about APIs, see APIs on SAP Business Accelerator Hub.

This is an OData version 4 service. This version aims to improve processing time and resource consumption of clients and servers. This includes a lightweight JSON format that reduces the size of every response.

**Technical Details**

A service group contains services that belong to the same business object model and so it shares similar environment conditions. The configuration and administration of a service group apply to all services in a service group (for example, routing) so you only have to do them once.

In the OData version 4 (V4) runtime implementation of the SAP Gateway Foundation, framework services originate from repositories.

|Service Group|Repository ID|Service Name|Version|
|---|---|---|---|
|API_FXEM_FXEXPOSURE|srvd_a2x|ForeignExchangeExposure|1.0.0|


**Service Structure**

Entities

The entities contain the business data of the service.

|Entity|Description|Necessity|Link to Details|
|---|---|---|---|
|Foreign Exchange Exposure (ForeignExchangeExposure)|A foreign exchange exposure is a planned incoming or outgoing foreign currency cash flow that bears the risk of financial losses due to exchange rate fluctuations. A foreign exchange exposure always has an amount (in a foreign currency) and a due date and contains the information for the target currency in which the amount is to be hedged.|Mandatory|Foreign Exchange Exposure|


**Authentication**

The following authentication methods are supported:

x509

OAuth2

For security reasons, SAP recommends using certificate-based authentication rather than username/password.

SAP recommends creating technical users specifically for the respective business application with minimum required privileges.

**Note:**

Authorization Concept in FX Exposure Management

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

**Additional Information**

The link to the API on the SAP Business Accelerator Hub: https://api.sap.com/api/sap-s4OP_FOREIGNEXCHANGEEXPOSURE_0001-v1/overview

**Note:**

For more information about the API, choose the API Reference tab or Schema View tab on the SAP Business Accelerator Hub.

**Related Information**

Foreign Exchange Exposure Operations for Foreign Exchange Exposures

#### Foreign Exchange Exposure (2 of 2)

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Foreign Exchange Exposure | L3 | trm12 p.18 | loio `cd852ad48e1c43498da252b068c40c92` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/cd852ad48e1c43498da252b068c40c92.html?locale=en-US)

Technical name: ForeignExchangeExposure

Properties

|Property|Description|Necessity|
|---|---|---|
|FXExposureUUID|FX Exposure Technical ID The FX exposure UUID of the FX exposure is set automatically by the system.|Mandatory Exception: If you create an FX exposure, do not enter a value in this field.|
|ForeignExchangeExposure|FX Exposure ID|Mandatory|


|Property|Description|Necessity|
|---|---|---|
| |The identifier of the FX exposure is set automatically by the system.|Exception: If you create an FX exposure, do not enter a value in this field.|
|FXExposureType|FX Exposure Type|Mandatory|
|FXExposureTypeName|FX Exposure Name|Optional|
|CompanyCode|Company Code|Mandatory|
|CompanyCodeName|Company Code Name|Optional|
|Portfolio|Portfolio|Whether this field must be filled for an FX exposure depends on the settings in the FX exposure type.|
|PortfolioName|Portfolio Name|Optional Whether this field could be filled for an FX exposure depends on the settings in the FX exposure type.|
|CostCenter|Cost Center|Whether this field must be filled for an FX exposure depends on the settings in the FX exposure type.|
|CostCenterName|Cost Center Name|Optional Whether this field could be filled for an FX exposure depends on the settings in the FX exposure type.|
|ProfitCenter|Profit Center|Whether this field must be filled for an FX exposure depends on the settings in the FX exposure type.|
|ProfitCenterName|Profit Center Name|Optional|
|Country|Country/Region|Whether this field must be filled for an FX exposure depends on the settings in the FX exposure type.|
|CountryName|Country/Region Name|Optional|
|WBSElementExternalID|WBS Element|Whether this field must be filled for an FX exposure depends on the settings in the FX exposure type.|
|WBSElementName|WBS Element Name|Optional Whether this field could be filled for an FX exposure depends on the settings in the FX exposure type.|
|OnBehalfOfCompany|On Behalf of Company Code|Whether this field must be filled for an FX exposure depends on the settings in the FX exposure type.|
|OnBehalfOfCompanyName|On Behalf of Company Code Name|Optional|


|Property|Description|Necessity|
|---|---|---|
| | |Whether this field could be filled for an FX exposure depends on the settings in the FX exposure type.|
|Segment|Segment|Whether this field must be filled for an FX exposure depends on the settings in the FX exposure type.|
|SegmentName|Segment Name|Optional Whether this field could be filled for an FX exposure depends on the settings in the FX exposure type.|
|FXExposureValidFromDate|Valid From Date|Mandatory|
|FXExposureDueDate|Due Date|Mandatory|
|FXExposureAmountInRiskCurrency|Amount in Risk Currency|Mandatory|
|FXExposureRiskCurrency|Risk Currency|Mandatory|
|FXExposureRiskCurrencyName|Risk Currency Name|Optional|
|FXExposureTargetCurrency|Target Currency|Mandatory|
|FXExposureDirection|Direction|Mandatory|
|FXExposureDirectionName|Direction Name|Optional|
|FXExposureExternalID|External ID|Mandatory|
|FXExposureStatus|Status|Set by the system, not editable|
|FXExposureStatusName|Status Name|Set by the system, not editable|


**Note:**

To display more information about the properties on the SAP Business Accelerator Hub, open one of the entity's operations and select Model or Schema.

**Supported Operations**

Manage FX Exposures

|Operation|Technical Name|Example|
|---|---|---|
|Create|POST/ForeignExchangeExposure - Add new entity to ForeignExchangeExposure|Example: Create Foreign Exchange Exposure |


|Operation|Technical Name|Example|
|---|---|---|
|Change|PATCH/ForeignExchangeExposure/{FXExposureUUID} - Update entity in ForeignExchangeExposure|Example: Change Foreign Exchange Exposure |
|Submit|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToSubmitted - Invoke action SetStatusToSubmitted|Example: Submit Foreign Exchange Exposure for Approval |
|Set to Obsolete|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToObsolete Invoke action SetStatusToObsolete|Example: Set Foreign Exchange Exposure to Obsolete |
|Send for Update (for submitted FX exposures)|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToCreated Invoke action SetStatusFromSubmittedToCreated|Example: Set Status of Foreign Exchange Exposure from Submitted to Created |
|Release|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToReleased Invoke action SetStatusToReleased|Example: Release Foreign Exchange Exposure |
|Reject|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToRejected Invoke action SetStatusToRejected|Example: Reject Foreign Exchange Exposure |
|Set to Created (for released FX exposures)|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToCreated Invoke action SetStatusToCreated|Example: Set Status of Foreign Exchange Exposure from Released to Created |
|Display|GET GET/ForeignExchangeExposure Get entities from ForeignExchangeExposure GET/ForeignExchangeExposure/{FXExposureUUID}Get entity from ForeignExchangeExposure by key|Example: Display Foreign Exchange Exposure |

#### Operations for Foreign Exchange Exposures

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures | L3 | trm12 p.22 | loio `2ea56e0b7442418cb1ebb74c9474168c` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/2ea56e0b7442418cb1ebb74c9474168c.html?locale=en-US)

The following operations are supported for foreign exchange exposures:

Manage FX Exposures

|Operation|Technical Name|Example|
|---|---|---|
|Create|POST/ForeignExchangeExposure - Add new entity to ForeignExchangeExposure|Example: Create Foreign Exchange Exposure |
|Change|PATCH/ForeignExchangeExposure/{FXExposureUUID} - Update entity in ForeignExchangeExposure|Example: Change Foreign Exchange Exposure |
|Submit|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToSubmitted - Invoke action SetStatusToSubmitted|Example: Submit Foreign Exchange Exposure for Approval |
|Set to Obsolete|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToObsolete Invoke action SetStatusToObsolete|Example: Set Foreign Exchange Exposure to Obsolete |
|Send for Update (for submitted FX exposures)|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToCreated Invoke action SetStatusFromSubmittedToCreated|Example: Set Status of Foreign Exchange Exposure from Submitted to Created |
|Release|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToReleased Invoke action SetStatusToReleased|Example: Release Foreign Exchange Exposure |
|Reject|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToRejected Invoke action SetStatusToRejected|Example: Reject Foreign Exchange Exposure |
|Set to Created (for released FX exposures)|POST/ForeignExchangeExposure/{FXExposureUUID}/SAP_self.SetStatusToCreated Invoke action SetStatusToCreated|Example: Set Status of Foreign Exchange Exposure from |


|Operation|Technical Name|Example|
|---|---|---|
| | |Released to Created |
|Display|GET GET/ForeignExchangeExposure Get entities from ForeignExchangeExposure GET/ForeignExchangeExposure/{FXExposureUUID}Get entity from ForeignExchangeExposure by key|Example: Display Foreign Exchange Exposure |

##### Example: Create Foreign Exchange Exposure

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures > Example: Create Foreign Exchange Exposure | L4 | trm12 p.23 | loio `4398ac260e234f0492bf47238fc8438f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/4398ac260e234f0492bf47238fc8438f.html?locale=en-US)

Request

POST <host>/sap/opu/odata4/sap/api_fxem_fxexposure/srvd_a2x/sap/foreignexchangeexposure/0001/Forei Content-Type: application/json Request Body {

"FXExposureType": "SFX", "FXExposureTypeName": "", "CompanyCode": "1010", "CompanyCodeName": "", "Portfolio": "", "PortfolioName": "", "CostCenter": "", "CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 20000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "", "FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "", "FXExposureStatusName": ""

}

Response

{

"@odata.context": "$metadata#ForeignExchangeExposure/$entity", "@odata.metadataEtag": "W/\"20250318205652\"", "FXExposureUUID": "513c7804-9970-1fd0-81ae-a0a520423070", "ForeignExchangeExposure": "118", "FXExposureType": "SFX", "FXExposureTypeName": "FX Exposure", "CompanyCode": "1010", "CompanyCodeName": "Company Code 1010", "Portfolio": "", "PortfolioName": "", "CostCenter": "",

"CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 20000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "United States Dollar", "FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "Incoming", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "C", "FXExposureStatusName": "Created", "SAP__Messages": []

}

##### Example: Change Foreign Exchange Exposure

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures > Example: Change Foreign Exchange Exposure | L4 | trm12 p.24 | loio `dc81d33eccef47f49f25a4bd7e0fc09b` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/dc81d33eccef47f49f25a4bd7e0fc09b.html?locale=en-US)

Request

PATCH <host>/sap/opu/odata4/sap/api_fxem_fxexposure/srvd_a2x/sap/foreignexchangeexposure/0001/Forei Content-Type: application/json Request Body: {

"FXExposureRiskCurrency": "USD", "FXExposureAmountInRiskCurrency": 50000000

}

Response

{

"@odata.context": "../$metadata#ForeignExchangeExposure/$entity", "@odata.metadataEtag": "W/\"20250318205652\"", "FXExposureUUID": "513c7804-9970-1fd0-81ae-a0a520423070", "ForeignExchangeExposure": "118", "FXExposureType": "SFX", "FXExposureTypeName": "FX Exposure", "CompanyCode": "1010", "CompanyCodeName": "Company Code 1010", "Portfolio": "", "PortfolioName": "", "CostCenter": "", "CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 50000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "United States Dollar",

"FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "Incoming", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "C", "FXExposureStatusName": "Created", "SAP__Messages": []

}

##### Example: Submit Foreign Exchange Exposure for Approval

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures > Example: Submit Foreign Exchange Exposure for Approval | L4 | trm12 p.25 | loio `47e243ca1fa34121a26e2ec00e4436a8` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/47e243ca1fa34121a26e2ec00e4436a8.html?locale=en-US)

Request

POST <host>/sap/opu/odata4/sap/api_fxem_fxexposure/srvd_a2x/sap/foreignexchangeexposure/0001/Foreig Content-Type: application/json

Response

{

"@odata.context": "../../$metadata#ForeignExchangeExposure/$entity", "@odata.metadataEtag": "W/\"20250318205652\"", "FXExposureUUID": "513c7804-9970-1fd0-81ae-a0a520423070", "ForeignExchangeExposure": "118", "FXExposureType": "SFX", "FXExposureTypeName": "FX Exposure", "CompanyCode": "1010", "CompanyCodeName": "Company Code 1010", "Portfolio": "", "PortfolioName": "", "CostCenter": "", "CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 50000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "United States Dollar", "FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "Incoming", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "S", "FXExposureStatusName": "Submitted",

"SAP__Messages": [] }

##### Example: Set Foreign Exchange Exposure to Obsolete

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures > Example: Set Foreign Exchange Exposure to Obsolete | L4 | trm12 p.25 | loio `61f28a57151841b397064a6931bd7b68` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/61f28a57151841b397064a6931bd7b68.html?locale=en-US)

Request

POST <host>/sap/opu/odata4/sap/api_fxem_fxexposure/srvd_a2x/sap/foreignexchangeexposure/0001/Foreig Content-Type: application/json

Response

{

"@odata.context": "../../$metadata#ForeignExchangeExposure/$entity", "@odata.metadataEtag": "W/\"20250318205652\"", "FXExposureUUID": "513c7804-9970-1fd0-81ae-a0a520423070", "ForeignExchangeExposure": "118", "FXExposureType": "SFX", "FXExposureTypeName": "FX Exposure", "CompanyCode": "1010", "CompanyCodeName": "Company Code 1010", "Portfolio": "", "PortfolioName": "", "CostCenter": "", "CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 50000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "United States Dollar", "FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "Incoming", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "O", "FXExposureStatusName": "Obsolete",

"SAP__Messages": [] }

##### Example: Set Status of Foreign Exchange Exposure from Submitted to Created

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures > Example: Set Status of Foreign Exchange Exposure from Submitted to Created | L4 | trm12 p.26 | loio `e15d23ee8aa845fcae3f4902518f72a6` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/e15d23ee8aa845fcae3f4902518f72a6.html?locale=en-US)

Request

POST <host>/sap/opu/odata4/sap/api_fxem_fxexposure/srvd_a2x/sap/foreignexchangeexposure/0001/Foreig Content-Type: application/json Action Parameter {

"FXExposureStsChgReasonText": "Amount is reduced" }

Response

{

"@odata.context": "../../$metadata#ForeignExchangeExposure/$entity", "@odata.metadataEtag": "W/\"20250318205652\"", "FXExposureUUID": "513c7804-9970-1fd0-81ae-a0a520423070", "ForeignExchangeExposure": "118", "FXExposureType": "SFX", "FXExposureTypeName": "FX Exposure", "CompanyCode": "1010", "CompanyCodeName": "Company Code 1010", "Portfolio": "", "PortfolioName": "", "CostCenter": "",

"CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 50000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "United States Dollar", "FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "Incoming", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "C", "FXExposureStatusName": "Created",

"SAP__Messages": [] }

##### Example: Release Foreign Exchange Exposure

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures > Example: Release Foreign Exchange Exposure | L4 | trm12 p.27 | loio `aab17653aa574b7caca78ca0262bef2f` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/aab17653aa574b7caca78ca0262bef2f.html?locale=en-US)

Request

POST <host>/sap/opu/odata4/sap/api_fxem_fxexposure/srvd_a2x/sap/foreignexchangeexposure/0001/Foreig Content-Type: application/json

Response

{

"@odata.context": "../../$metadata#ForeignExchangeExposure/$entity", "@odata.metadataEtag": "W/\"20250318205652\"", "FXExposureUUID": "513c7804-9970-1fd0-81ae-a0a520423070", "ForeignExchangeExposure": "118", "FXExposureType": "SFX", "FXExposureTypeName": "FX Exposure", "CompanyCode": "1010", "CompanyCodeName": "Company Code 1010", "Portfolio": "", "PortfolioName": "", "CostCenter": "", "CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 50000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "United States Dollar", "FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "Incoming", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "R",

"FXExposureStatusName": "Released", "SAP__Messages": []

}

##### Example: Reject Foreign Exchange Exposure

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures > Example: Reject Foreign Exchange Exposure | L4 | trm12 p.28 | loio `f6f820ff6d5947388065e52bb4f7ff76` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/f6f820ff6d5947388065e52bb4f7ff76.html?locale=en-US)

Request

POST <host>/sap/opu/odata4/sap/api_fxem_fxexposure/srvd_a2x/sap/foreignexchangeexposure/0001/Foreig Content-Type: application/json Action Parameter {

"FXExposureStsChgReasonText": "Exposure not relevant" }

Response

{

"@odata.context": "../../$metadata#ForeignExchangeExposure/$entity", "@odata.metadataEtag": "W/\"20250318205652\"", "FXExposureUUID": "6fd22f33-b793-1fe0-81b2-2865aa5f3c7a", "ForeignExchangeExposure": "119", "FXExposureType": "SFX", "FXExposureTypeName": "FX Exposure", "CompanyCode": "1010", "CompanyCodeName": "Company Code 1010", "Portfolio": "", "PortfolioName": "", "CostCenter": "", "CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 20000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "United States Dollar", "FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "Incoming", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "X", "FXExposureStatusName": "Rejected",

"SAP__Messages": [] }

##### Example: Set Status of Foreign Exchange Exposure from Released to Created

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures > Example: Set Status of Foreign Exchange Exposure from Released to Created | L4 | trm12 p.28 | loio `73000695d9da436c8b2d27ffb8f03212` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/73000695d9da436c8b2d27ffb8f03212.html?locale=en-US)

Request

POST <host>/sap/opu/odata4/sap/api_fxem_fxexposure/srvd_a2x/sap/foreignexchangeexposure/0001/Foreig Content-Type: application/json Action Parameter {

"FXExposureStsChgReasonText": "Amount is reduced" }

Response

{

}

"@odata.context": "../../$metadata#ForeignExchangeExposure/$entity", "@odata.metadataEtag": "W/\"20250318205652\"", "FXExposureUUID": "513c7804-9970-1fd0-81ae-a0a520423070", "ForeignExchangeExposure": "118", "FXExposureType": "SFX", "FXExposureTypeName": "FX Exposure", "CompanyCode": "1010", "CompanyCodeName": "Company Code 1010", "Portfolio": "", "PortfolioName": "", "CostCenter": "", "CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 50000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "United States Dollar", "FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "Incoming", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "C", "FXExposureStatusName": "Created", "SAP__Messages": []

##### Example: Display Foreign Exchange Exposure

> **Path:** APIs for Treasury and Risk Management > Foreign Exchange Exposure > Operations for Foreign Exchange Exposures > Example: Display Foreign Exchange Exposure | L4 | trm12 p.29 | loio `f9ed840c1be3499395eeee55c91d9dc2` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/f9ed840c1be3499395eeee55c91d9dc2.html?locale=en-US)

Request

GET <host>/sap/opu/odata4/sap/api_fxem_fxexposure/srvd_a2x/sap/foreignexchangeexposure/0001/Foreign Content-Type: application/json

Response

{

"@odata.context": "$metadata#ForeignExchangeExposure/$entity", "@odata.metadataEtag": "W/\"20250318205652\"", "FXExposureUUID": "513c7804-9970-1fd0-81ae-a0a520423070", "ForeignExchangeExposure": "118", "FXExposureType": "SFX", "FXExposureTypeName": "FX Exposure", "CompanyCode": "1010", "CompanyCodeName": "Company Code 1010", "Portfolio": "",

"PortfolioName": "", "CostCenter": "", "CostCenterName": "", "ProfitCenter": "", "ProfitCenterName": "", "Country": "", "CountryName": "", "WBSElementExternalID": "", "WBSElementName": "", "OnBehalfOfCompany": "", "OnBehalfOfCompanyName": "", "Segment": "", "SegmentName": "", "FXExposureValidFromDate": "2025-03-20", "FXExposureDueDate": "2025-12-31", "FXExposureAmountInRiskCurrency": 20000000, "FXExposureRiskCurrency": "USD", "FXExposureRiskCurrencyName": "United States Dollar", "FXExposureTargetCurrency": "EUR", "FXExposureDirection": "I", "FXExposureDirectionName": "Incoming", "FXExposureExternalID": "EXT000001", "FXExposureStatus": "C", "FXExposureStatusName": "Created", "SAP__Messages": []

}

