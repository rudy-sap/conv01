# Risk Management > Basics > Risk Hierarchy - SAP TRM Knowledge Base (branch split)

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

##### Risk Hierarchy

> **Path:** Treasury and Risk Management > Risk Management > Basics > Risk Hierarchy | L4 | trm02 p.31 | loio `9112da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9112da531198434de10000000a174cb4.html?locale=en-US)

The market risk of a credit institution results from a combination of many risk factors. Interest rate changes, exchange rate, and stock price fluctuations all influence the value of the assets of a credit institution. Market risk represents potential loss due to market price changes. You can use the key figures when reaching judgments about the necessary equity cover for an enterprise, the limiting of positions, or the desired minimum return on a portfolio.

**Definition**

To achieve a more comprehensive level of control, market risk has to be split up into its component parts. Market risk can be divided into the following risk categories:

Interest rate risk

Currency risk

Index risk

Volatility risk

Price risk

Every risk category can be further divided into specific partial risks. In the interest area, there are submarkets for swaps, bonds, money market transactions, and so forth, and each one has corresponding partial risks. Partial risks are generally different for every currency area.

In the risk hierarchy, you define how the market risk is split up into its components. Risk factors form the basis of risk hierarchies. By definition, a risk factor cannot be divided up into further components. At the same time, risk factors also represent the price factors for the instruments in the portfolio.

In the interest area, the key rates are defined as risk factors. The idea behind key rates is to define the temporal progression of a yield curve for several specific terms using interest rates. The key rates are depicted as zero coupon rates. The interest rates for the remaining terms are determined directly from the key rates. As key rates are implicitly selected when you choose a yield curve structure, it is not absolutely necessary for you to define the key rates of a yield curve structure in the risk hierarchy explicitly. Only do this in cases where you specifically want an evaluation for the key rates defined in the risk hierarchy.

With stocks, the stock price is represented on a market index. It is assumed that the stock price development is directly dependent on the market index.

[figure TRM02-F023]

**Use**

Using risk hierarchies in evaluations allows you to portray in detail the influence of different risk factors. The risks defined in the risk hierarchy are shown in the evaluations.

**Structure**

Every level of a risk hierarchy is a consolidation level. Market risk is the consolidation level at the very top of the risk hierarchy.

Risk hierarchies are built by starting with the market risk and working down to the individual risk factors. You determine the composition of the risk hierarchy by defining a structure.

At one of the higher levels, the risks are divided into risk categories. Risk aggregations, starting with the risk factors all the way up to the market risk, are not normally made using addition because of the interdependencies of real-world risks. Adding together individual risk factors represents a very simple way of estimating isolated risk-factor influences. If you enter aggregation categories, you define the aggregation of risks. The system only interprets the aggregation category when calculating the value-atrisk after variance/covariance evaluation. Therefore, you can find a list of all possible aggregation categories and their meaning in the documentation for variance/covariance evaluation.

###### Editing Risk Hierarchies

> **Path:** Treasury and Risk Management > Risk Management > Basics > Risk Hierarchy > Editing Risk Hierarchies | L5 | trm02 p.32 | loio `9412da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/9412da531198434de10000000a174cb4.html?locale=en-US)

Choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Master Data Risk Hierarchy .

The system now displays the initial screen for risk hierarchy maintenance.

Select or enter an ID for the risk hierarchy.

Choose a processing type (for example, Create or Change).

If you choose Create, the system displays the maintenance screen for the header data of the hierarchy:


Enter a short and a long name for the risk hierarchy. If you want to activate an additional authorization check, assign the hierarchy an authorization group. You create authorization groups in Customizing under Financial Supply Chain Management Treasury and Risk Management Basic Analyzer Settings Maintain Authorizations/Profiles/Users Maintain Authorization Groups .

In Control Interest Area, you can see how the risk factors are assigned for the interest area.

You can either freely define the risk factors in the interest area or allow the system to generate them automatically (in the form of reference interest rates) by choosing a yield curve type. We recommend that you let the system generate the reference interest rates automatically from the yield curve.

If you want to define the interest rates, choose Edit Control Interest Area Freely-Defined Terms .


Once you have specified that the risk factors are to be freely definable, you cannot change this setting.

Choose the aggregation category that is to be the default aggregation category for the risk hierarchy. You can still override this default setting on the individual hierarchy node level, if required.

To edit the structure of the hierarchy, choose Hierarchy Tree.


When you create a new hierarchy, the system automatically creates a node with the name ROOT. You cannot delete this root node. It represents the starting point for setting up your tree structure.

To add nodes, select the root node and choose Nodes.

In the right hand part of the screen you can specify the node by entering a short name and a long name. The risk category is not assigned by default. You can choose from the following risk categories:

|Risk Category|Further Entries Required|
|---|---|
|Yield curve|Currency, yield curve type The default setting designates all reference interest rates (grid points of the respective yield curve) as risk factors. You do have the option of deleting individual grid points from the risk hierarchy, however. For information on the effects of this, see Treatment of Shifts in the Risk Hierarchy. To regenerate all of the risk factor nodes that are situated under the one that represents a yield curve, in accordance with the most recent definition of the yield curve types, choose Edit Regenerate Yield Curve .|
|Yield curve (for freely definable terms in the interest area)|Currency, yield curve type, term|
|Interest rate volatility|Volatility type, term, reference interest rate|
|Exchange rate|Base currency, target currency You can also leave the target currency field blank. The display currency is then used as the target currency in the risk hierarchy in the later evaluation. See also: Currency Risk Factors in the Risk Hierarchy|
|Exchange rate volatility|Volatility type, term, base currency, target currency|


|Risk Category|Further Entries Required|
|---|---|
|Security price|Securities|
|Security volatility|Volatility type, term, security class|
|Stock index|Security index|
|Stock index volatility|Volatility type, term, security index|
|Abstract risk factor|Risk factor name|


If you choose Nodes on a node with risk category Not assigned, the system generates a subnode. If you choose Nodes on a node that has been assigned a risk category, the system generates a new node on the same level.



Nodes for which you have created subnodes are automatically recognized by the system as summarization nodes. In the righthand area of the screen you can assign an aggregation type to them.

You can choose from the following aggregation types:

Same as RH aggregation type

Totaled (according to +/- sign)

Totaled (absolute amounts)

Differentiated

Correlated

Aggregated (directly preceding nodes)

Below the area for specifying the aggregation type you are also able to se the indicator No value at risk below this node for the summarization node. If you have also set the indicator Consolidated VaR in the evaluation type, then for historical simulation and Monte Carlo simulation the system will not calculate the value at risk below this node. This enables run time and memory usage to be optimized for these evaluations.

If you have chosen Change or Display, the system will display to the maintenance interface for the selected hierarchy. Proceed as described above.



Choose Save.



Before you save, check the hierarchy to see whether risk categories were created for all end nodes. Choose Consistency Check.

Result

The risk hierarchy is ready for use in the evaluations. Due to the options for saving evaluation results in the Results Database, risk hierarchies are recorded historically. By choosing Display Historical Version and then entering a version date, you are able to display different versions.

###### Treatment of Shifts in the Risk Hierarchy

> **Path:** Treasury and Risk Management > Risk Management > Basics > Risk Hierarchy > Treatment of Shifts in the Risk Hierarchy | L5 | trm02 p.34 | loio `5f13da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/5f13da531198434de10000000a174cb4.html?locale=en-US)

If grid points of a yield curve are to be omitted as risk factors, those adjacent grid points included in the risk hierarchy share proportionally the risk of those grid points that were omitted. This is achieved by extrapolating the market data changes (shifts) in the gridpoints that remain in the risk hierarchy linear to the adjacent risk factors. Grid points that lie between these risk factors but which are not contained in the risk hierarchy are taken into account proportionally by the shift on one risk factor.

[figure TRM02-F033]

Outside the first defined grid point and the last defined grid point shifts are extrapolated with a partial derivation of zero.

[figure TRM02-F034 - Outside the first defined grid point and the last defined grid point shifts are extrapolated with a partial derivation of zero.]

###### Currency Risk Factors in the Risk Hierarchy

> **Path:** Treasury and Risk Management > Risk Management > Basics > Risk Hierarchy > Currency Risk Factors in the Risk Hierarchy | L5 | trm02 p.35 | loio `7c11da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7c11da531198434de10000000a174cb4.html?locale=en-US)

As indirectly-quoted exchange rates are permitted as of Basis release 4.6, the corresponding adaptations for the management of these rates in value-at-risk have been carried out.

The currency valuation of items is a linear function. Thus at the start of delta-gamma formulation you expect a gamma position of

0. Internally, indirectly quoted rates are always converted to price-quoted rates using the quotation ration of 1:1. This maintains the

linearity of the valuation function. When defining risk factors, ensure that you use the generic generation of currency risk factors.

Only store the from-currency as the risk factor. The system automatically replaces the to-currency with the evaluation currency. In this way you ensure that relative currency shifts resulting from the internal conversion to price-quoted representation are always multiplied for the creation of currency simulation scenarios. In this way, linearity of the valuation function is retained.

If you do not use this generic for creating currency risk factors, gamma items can arise that do not equal zero since you have to divide by shifts.

