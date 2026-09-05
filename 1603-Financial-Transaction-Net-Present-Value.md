# Financial Transaction Net Present Value - SAP TRM Knowledge Base (branch split)

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

### Financial Transaction Net Present Value (1 of 2)

> **Path:** APIs for Treasury and Risk Management > Financial Transaction Net Present Value | L2 | trm12 p.30 | loio `523e246060fd449cba25a939f799b5a3` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/523e246060fd449cba25a939f799b5a3.html?locale=en-US)

Service name: API_FINTRANSACTIONNPV

This service enables you to create, read, update, and delete net present values of financial transactions in the net present values table in Treasury and Risk Management. By default, NPVs are calculated in Treasury and Risk Management with the Calculate Net

Present Values - With CVA and DVA app. You can enter externally calculated net present values using the Enter Net Present Values app or with this service.

This service is published on the SAP Business Accelerator Hub. For more information about APIs, see APIs on SAP Business Accelerator Hub.

This is an OData version 4 service. This version aims to improve processing time and resource consumption of clients and servers. This includes a lightweight JSON format that reduces the size of every response.

**Required Communication Scenario**

To be able to use this service, you must configure communication scenario SAP_COM_0923. For more information, see https://api.sap.com .


**Technical Details**

A service group contains services that belong to the same business object model and so it shares similar environment conditions. The configuration and administration of a service group apply to all services in a service group (for example, routing) so you only have to do them once.

In the OData version 4 (V4) runtime implementation of the SAP Gateway Foundation, framework services originate from repositories.

|Service Group (incl. Namespace if It Exists)|Repository ID|Service Name (incl. Namespace if It Exists)|Version|
|---|---|---|---|
|API_FINTRANSACTIONNPV|srvd_a2x|API_FINTRANSACTIONNPV|0001|


**Service Structure**

Service Header (optional)

The service header contains information about the service.

Entities

The entities contain the business data of the service.

|Entity|Description|Necessity|Link to Details|
|---|---|---|---|
|Financial Transaction Net Present Value (FinancialTransactionNPV)|The NPV of a financial transaction is the calculated value of a financial transaction on a specific date based on the market data available. The calculation method depends on the type of financial transaction. For most transactions, the NPV is determined by discounting the future cash flows. However, different calculation methods are used for options. The NPV calculation of financial transactions is a method of determining the fair value of a financial transaction on a specific date as required by accounting principles.|Mandatory|Financial Transaction Net Present Value |


**Authentication**

The following authentication methods are supported:

Basic

x509

OAuth2

For security reasons, SAP recommends using certificate-based authentication rather than username/password.

SAP recommends creating technical users specifically for the respective business application with minimum required privileges.

**Additional Information**

The link to the API on the SAP Business Accelerator Hub: Financial Transaction NPV

**Note:**

For more information about the API, choose the API Reference tab or Schema View tab on the SAP Business Accelerator Hub.

#### Financial Transaction Net Present Value (2 of 2)

> **Path:** APIs for Treasury and Risk Management > Financial Transaction Net Present Value > Financial Transaction Net Present Value | L3 | trm12 p.32 | loio `b67db82f262b415484a94ec6f0383753` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/b67db82f262b415484a94ec6f0383753.html?locale=en-US)

Technical name: FinancialTransactionNPV

Properties

|Property|Description|Necessity|
|---|---|---|
|CompanyCode|Company Code|Mandatory (Optional for GET and POST operation)|
|FinancialTransaction|Financial Transaction|Mandatory (Optional for GET and POST operation)|
|FinancialTransactionNPVType|Price/NPV Type for OTC Transactions|Mandatory (Optional for GET and POST operation)|
|NetPresentValueValidityDate|Effective From|Mandatory (Optional for GET and POST operation)|
|NetPresentValueAmountInNPVCrcy|Net Present Value|Optional|
|NetPresentValueCurrency|Currency of Net Present Value|Optional|
|IntrinsicValueAmountInNPVCrcy|Intrinsic Value of an Option in NPV Currency|Optional|
|TimeValueAmountInNPVCrcy|Time Value of an Option in NPV Currency|Optional|
|CleanPriceAmountInNPVCrcy|Clean Price in NPV Currency|Optional|
|IncomingNPVAmountInNPVCrcy|NPV of Incoming Side|Optional|
|OutgoingNPVAmountInNPVCrcy|NPV of Outgoing Side|Optional|
|RiskFreeNPVAmountInNPVCrcy|Risk-Free NPV|Optional|
|CreditValueAdjmtAmtInNPVCrcy|Credit Value Adjustment|Optional|
|DebitValueAdjmtAmtInNPVCrcy|Debit Value Adjustment|Optional|


**Note:**

To display more information about the properties on the SAP Business Accelerator Hub, open one of the entity's operations and select Model or Schema.

Supported Operations

The following operations are supported:

GET by Key

POST

PATCH

DELETE

#### Operations for Financial Transaction Net Present Value

> **Path:** APIs for Treasury and Risk Management > Financial Transaction Net Present Value > Operations for Financial Transaction Net Present Value | L3 | trm12 p.33 | loio `9461a3b60ded4bdfb11cb2548054e029` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/9461a3b60ded4bdfb11cb2548054e029.html?locale=en-US)

The API Financial Transaction Net Present Value offers these operations:

|Operation|HTTP Method|Sample URL|
|---|---|---|
|Get entities from FinancialTransactionNPV by Key|GET by Key |GET <host> /sap/opu/odata4/sap/api_fintransactionnpv/srvd_a2x/sap/financialtransactionnpv/0001/Financia|
|Get entities from FinancialTransactionNPV (top 50)|GET|GET <host> /sap/opu/odata4/sap/api_fintransactionnpv/srvd_a2x/sap/financialtransactionnpv/00|
|Add new entity to FinancialTransactionNPV|POST|POST <host> /sap/opu/odata4/sap/api_fintransactionnpv/srvd_a2x/sap/financialtransactionnpv/0001/Financia|
|Update entity in FinancialTransactionNPV|PATCH|PATCH <host> /sap/opu/odata4/sap/api_fintransactionnpv/srvd_a2x/sap/financialtransactionnpv/0001/Financia|
|Delete entity from FinancialTransactionNPV|DELETE|DELETE <host> /sap/opu/odata4/sap/api_fintransactionnpv/srvd_a2x/sap/financialtransactionnpv/0001/Financia|

##### GET by Key

> **Path:** APIs for Treasury and Risk Management > Financial Transaction Net Present Value > Operations for Financial Transaction Net Present Value > GET by Key | L4 | trm12 p.33 | loio `65a580ef7dbd405b9fb423b463cbaac5` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/65a580ef7dbd405b9fb423b463cbaac5.html?locale=en-US)

To get the net present value of a financial transaction from the net present value table, you use the HTTP method GET to call the FinancialTransactionNPV function import.

**Request**

You can include the following properties in the request's URL:

|Property|Necessity|
|---|---|
|CompanyCode|Optional|
|FinancialTransaction|Optional|
|FinancialTransactionNPVType|Optional|
|NetPresentValueValidityDate|Optional|


You can execute the GET operation to get only a specific net present value for a financial transaction.

To get a specific net present value fill all parameter field.

The operation returns the requested net present values.

**Examples**

Request

**Sample Code:**

GET <host> /sap/opu/odata4/sap/api_fintransactionnpv/srvd_a2x/sap/financialtransactionnpv/0001/F

Response

Response Body

Response Header

**Sample Code:**

{

}

"@odata.context": "$metadata#FinancialTransactionNPV", "@odata.metadataEtag": "W/\"20221026193132\"", "value": [

{

"CompanyCode": "1010", "FinancialTransaction": "4711", "FinancialTransactionNPVType": "001", "NetPresentValueValidityDate": "2022-04-13", "NetPresentValueAmountInNPVCrcy": 1234, "NetPresentValueCurrency": "EUR", "IntrinsicValueAmountInNPVCrcy": 0, "TimeValueAmountInNPVCrcy": 0, "CleanPriceAmountInNPVCrcy": 0, "IncomingNPVAmountInNPVCrcy": 0, "OutgoingNPVAmountInNPVCrcy": 0, "RiskFreeNPVAmountInNPVCrcy": 0, "CreditValueAdjmtAmtInNPVCrcy": 0, "DebitValueAdjmtAmtInNPVCrcy": 0, "SAP__Messages": []

} ]

##### POST

> **Path:** APIs for Treasury and Risk Management > Financial Transaction Net Present Value > Operations for Financial Transaction Net Present Value > POST | L4 | trm12 p.34 | loio `c983a93efd624d0d817443285198fcf0` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/c983a93efd624d0d817443285198fcf0.html?locale=en-US)

To add a new net present value in the net present value table, you use the HTTP method POST to call the FinancialTransactionNPV function import.

**Request**

You can include the following properties in the request's URL:

|Property|Necessity|
|---|---|
|CompanyCode|Optional|


|Property|Necessity|
|---|---|
|FinancialTransaction|Optional|
|FinancialTransactionNPVType|Optional|
|NetPresentValueValidityDate|Optional|
|IntrinsicValueAmountInNPVCrcy|Optional|
|TimeValueAmountInNPVCrcy|Optional|
|CleanPriceAmountInNPVCrcy|Optional|
|IncomingNPVAmountInNPVCrcy|Optional|
|OutgoingNPVAmountInNPVCrcy|Optional|
|RiskFreeNPVAmountInNPVCrcy|Optional|
|CreditValueAdjmtAmtInNPVCrcy|Optional|
|DebitValueAdjmtAmtInNPVCrcy|Optional|


**Response**

The operation returns success message.

##### PATCH

> **Path:** APIs for Treasury and Risk Management > Financial Transaction Net Present Value > Operations for Financial Transaction Net Present Value > PATCH | L4 | trm12 p.35 | loio `ce31454288064947a6134289528a5948` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/ce31454288064947a6134289528a5948.html?locale=en-US)

To change or update a net present value in the net present value table, you use the HTTP method PATCH to call the FinancialTransactionNPV function import.

|Property|Necessity|
|---|---|
|CompanyCode|Mandatory|
|FinancialTransaction|Mandatory|
|FinancialTransactionNPVType|Mandatory|
|NetPresentValueValidityDate|Mandatory|
|IntrinsicValueAmountInNPVCrcy|Optional|
|TimeValueAmountInNPVCrcy|Optional|
|CleanPriceAmountInNPVCrcy|Optional|
|IncomingNPVAmountInNPVCrcy|Optional|
|OutgoingNPVAmountInNPVCrcy|Optional|
|RiskFreeNPVAmountInNPVCrcy|Optional|
|CreditValueAdjmtAmtInNPVCrcy|Optional|
|DebitValueAdjmtAmtInNPVCrcy|Optional|


The operation returns success message.

##### DELETE

> **Path:** APIs for Treasury and Risk Management > Financial Transaction Net Present Value > Operations for Financial Transaction Net Present Value > DELETE | L4 | trm12 p.36 | loio `bac7adb6683c40cbb76b48abf5ab9c4e` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/d9c0dd5023e34f0d85ed30fc859496aa/bac7adb6683c40cbb76b48abf5ab9c4e.html?locale=en-US)

To delete a net present value from the net present value table, you use the HTTP method DELETE to call the FinancialTransactionNPV function import.

**Request**

You can include the following properties in the request's URL:

|Property|Necessity|
|---|---|
|CompanyCode|Optional|
|FinancialTransaction|Optional|
|FinancialTransactionNPVType|Optional|
|NetPresentValueValidityDate|Optional|


You can execute the DELETE operation to delete a specific net present value for a financial transaction.

**Response**

The operation returns success message.

