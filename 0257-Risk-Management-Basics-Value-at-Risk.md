# Risk Management > Basics > Value at Risk - SAP TRM Knowledge Base (branch split)

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

##### Value at Risk

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk | L4 | trm02 p.232 | loio `d412da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d412da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

The value at risk (VaR) represents the potential loss in value of a position (expressed as a net present value) that could – with a certain probability – be realized before the position is hedged or liquidated. The VaR evaluation is thus an extension of NPV analysis, which has the benefit of allowing a standardized approach to risk quantification. The difference between the two types of evaluation is that VaR takes into account the uncertainty of future market developments.

**Use**

An NPV approach is used throughout the VaR evaluation, allowing the VaR to be consolidated across all sub-areas of the enterprise. You can freely aggregate the risk from products, currencies, and organizational units, and bring the results together to establish the total risk. Value-at-risk analysis is therefore of key significance for an enterprise’s global risk controlling activities.

Within the framework of risk management, VaR represents a target figure for controlling. The value at risk therefore forms the basis of the internal risk controlling models proposed by the Basle Committee on Banking Supervision . Keep in mind, however, that the final decision about which operative controlling measures are appropriate has to be made by the risk controlling department of your enterprise. As a key figure, VaR only has a warning function.

Risk/Return control represents a further use of VaR analysis. In modern portfolio management, expected yields are viewed in relation to the respective risks involved.

**Structure**

In principle, the value at risk is determined by the value of the position entered into and the volatility of market prices. The value at risk is also influenced by the average retention period of the position, that is, the time it takes for the position to be hedged or liquidated. The following calculation methods are used for VaR:

[figure TRM02-F251 - In principle, the value at risk is determined by the value of the position entered into and the volatility of market prices. The value at risk is also influenced by the average retention period of the position, that is, the time it takes for the position to be hedged or liquidated. The following calculation methods are used for VaR:]

###### Historical Simulation: Theoretical Background

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Historical Simulation: Theoretical Background | L5 | trm02 p.233 | loio `d712da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/d712da531198434de10000000a174cb4.html?locale=en-US)

The purpose of historical simulation is to determine what profits or losses would be incurred if a market price development from the past were to occur today. In the process, the correlations between the risk factors are implicitly taken into account . The calculation methods available can roughly be divided into the following procedures:

Full valuation:

In the case of full valuation within historical simulation, n comparative NPV calculations are made over the historical period. Hence market data changes ( MD) are determined for all time points in the historical period for a certain holding period.

[figure TRM02-F252 - First the NPV is calculated using current market data. Then the NPV is also calculated for each change to the current market data brought about by the historical market data changes ( MD).This is known as the simulated net present value. These simulated NPVs are compared with the NPV calculated from the current market data. This results in n potential profits/losses.]

First the NPV is calculated using current market data. Then the NPV is also calculated for each change to the current market data brought about by the historical market data changes ( MD).This is known as the simulated net present value. These simulated NPVs are compared with the NPV calculated from the current market data. This results in n potential profits/losses.

This calculation is done at each risk factor level in the risk hierarchy, taking into account the respective historical changes. Every time a new node in the risk hierarchy is reached, a new calculation is carried out, which takes into account all the historical changes to the risk factors below that particular node.

The correlations of the individual market prices and the relationships between positions are implicitly taken into account since the NPVs at each time point in the historical period are calculated based on all the market data valid for that time point.

Profits and losses are sorted by amount.

[figure TRM02-F253 - The relative frequency of the profits and losses is calculated. If there is a large enough sample (n), this is an unbiased estimator for predicting the actual probability distribution of profits and losses.]

The relative frequency of the profits and losses is calculated. If there is a large enough sample (n), this is an unbiased estimator for predicting the actual probability distribution of profits and losses.

[figure TRM02-F254 - When you enter a confidence level, the system calculates the value at risk from the distribution of profits and losses. This value at risk amount represents a floor based on the specified probability.]

When you enter a confidence level, the system calculates the value at risk from the distribution of profits and losses. This value at risk amount represents a floor based on the specified probability.

**Example:**

With a sample of 200 values and a confidence level of 99%, the third largest loss represents the value at risk.

[figure TRM02-F255]

Delta valuation:

With the delta approach, the NPV is not calculated for every point in time in the historical period. Instead, the elasticity of the price function is estimated for the different price parameters, independent of historical market prices ( delta positions ). The NPV differences result from weighting this reactivity with the price differences from the historical market data. As with full valuation, this results in n potential profits/losses, whose relative frequency distribution can be displayed.

This approach is based on the assumption that the NPV function is linear.

Delta-Gamma approach:

Here, in contrast to the delta valuation, non-linear terms of the second order (gamma positions) are additionally taken into account at the risk factor level.

The process used for both delta valuation and the delta-gamma approach is known as risk factor mapping .

###### Historical Simulation

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Historical Simulation: Theoretical Background > Historical Simulation | L6 | trm02 p.235 | loio `dd12da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/dd12da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Here the historical market price changes are stored in simulation scenarios. A simulation scenario is created for each day in the time series for every risk consolidation level. In this scenario, only those market prices for which the risk is to be determined at that particular risk consolidation level are changed.

**Example:**

To determine the interest rate risk, scenarios are created in which only the zero bond yields are changed.

The position is valued using these simulation scenarios, and the value at risk is determined on the basis of the resulting gains and losses.

When simulation scenarios are created, all price changes are taken into account with the probability of their common, simultaneous occurrence. In the historical simulation, therefore, all price changes for a day flow into the historical simulation at the

same time. As a consequence, the correlations between the individual risk factors are already taken into account.

With this procedure, you can also display complex price changes that cannot be modeled using the variance/covariance approach.

**Integration**

The value-at-risk amounts are displayed using the risk and portfolio hierarchies.

With the full valuation approach, the profit and loss is calculated for every position on every risk hierarchy level by revaluing every position using the historical market data for each respective relevant risk factor.

With the delta approach, aggregation across the risk hierarchy is based on the assumption that you can add together the NPV differences according to the +/- sign. For each portfolio on a risk factor level, the system calculates the reactivity of the NPV to the risk factors, independent of the historical market prices.

With the delta-gamma approach, non-linear terms of the second order (gamma positions) are additionally taken into account at the risk factor level.

The three methods can also be combined with one another (combination procedure). In this case, the selection of the respective method takes place depending on the value in the differentiation rule stored in the evaluation type and specific to the valuation rule. These settings specific to the valuation rule are only interpreted, however, once the combination procedure has been stored in the Customizing settings for the value at risk type.

**Scope of Functions**

The fictitious profits and losses resulting from the valuations form the basis for determining the value at risk. In the SAP system, value at risk can be calculated in the following ways based on the distribution of profits and losses:

From simulated profits and losses

The simulated profits and losses determined for each day in the historical period are sorted by size taking into account the

+/- sign.

The value at risk for a confidence level is the nth smallest profit/loss, where:

n = ((1 - confidence level) x No. of simulation days) +1.

The value at risk is displayed as a positive or negative value.

**Example:**

th

With 200 days, VaR is the 11 smallest profit/loss, since

95%

n = ((1-0.95) x 200) + 1 = 11

From absolute profits and losses

The simulated profits and losses determined for each day in the historical period are transformed into absolute amounts and sorted by size without taking into account the +/- sign.

The value at risk for a confidence level is the nth largest profit/loss, where:

n = ((1 - confidence level) x No. of simulation days) *2+ 1

The value at risk is always displayed as a negative value. If n is larger than the number of simulation values (with a very low confidence level), the value at risk is displayed as zero.

**Example:**

95% st

With 200 days, VaR is the 21 largest profit/loss, since

n = [ (1-0.95)*200*2 ] +1 = 21

This method provides only odd values for the sample evaluation and the value at risk is overestimated. You can calculate more exact values with the same CPU time using the following methods:

From absolute profits and losses (double the number of values)

The simulated profits and losses determined for each day in the historical period are transformed into absolute amounts and sorted by size without taking into account the +/- sign. However, double the number of sample values is used.

The value at risk for a confidence level is the nth largest profit/loss, where:

n =((1 - confidence level) x 2 x No. of simulation days) +1.

The value at risk is always displayed as a negative value. If n is larger than the number of simulation values (with a very low confidence level), the value at risk is displayed as zero.

**Example:**

95% st

With 200 days, VaR is the 21 largest profit/loss, since

n = [ (1-0.95)x400 ] +1 = 21

Assuming normal distribution

The simulated profits and losses are assumed to be values in a sample having an expected value of zero with normal distribution. The standard deviation is determined using a statistical estimation. The value at risk then results from the multiplication of the standard deviation by the confidence level.

The value at risk is always displayed as a negative value.

###### Structured Monte Carlo

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Structured Monte Carlo | L5 | trm02 p.237 | loio `ce12da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/ce12da531198434de10000000a174cb4.html?locale=en-US)

Like the historical simulation, the Monte Carlo simulation is a simulation method using scenarios to describe potential changes to the values of risk factors. In contrast to the historical simulation, however, the scenarios are not determined using historical data but using a random process instead. A random number generator creates the random numbers required, and various methods can then be used to transform these numbers into the standard normal distribution.

With the Monte Carlo simulation, it is assumed that there is a normal distribution of risk factor changes with an expected value of zero and a positive variance. The parameters required for the random process can be calculated from historical values (structured Monte Carlo).

Monte Carlo simulation comprises the following steps:

[figure TRM02-F256 - Integration]

Integration

The value-at-risk amounts is displayed using the risk and portfolio hierarchies.

With the full valuation approach, profit and loss are calculated for every position on every risk hierarchy level by valuing every position anew using the simulated market data for each respective risk factor.

With the delta approach, the aggregation across the risk hierarchy is based on the assumption that you can add together the NPV differences according to the +/- sign. For each portfolio on a risk factor level, the system calculates the reactivity of the NPV to the risk factors, independently of the historical market prices (delta positions).

With the delta-gamma approach, non-linear terms of the second order (gamma positions) are relevant at the risk factor level.

The process used for both delta valuation and the delta-gamma approach is known as risk factor mapping.

The three methods can also be combined with one another (combination procedure). In this case, the respective method is selected depending on the value in the differentiation rule stored in the evaluation type and specific to the valuation rule. However, these settings specific to the valuation rule are first interpreted after the combination procedure has been stored in the Customizing for the value at risk type.

###### Generation of Random Numbers

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Structured Monte Carlo > Generation of Random Numbers | L6 | trm02 p.238 | loio `4f11da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4f11da531198434de10000000a174cb4.html?locale=en-US)

[figure TRM02-F257]

The correlated, standard normally-distributed random numbers required for the stochastic model are generated using Cholesky decomposition from independent -distributed random numbers .


[figure TRM02-F259]

[figure TRM02-F260]


In turn, these numbers can be generated from independent -equally distributed random numbers (standard random numbers ) by means of transformation methods.

Standard random numbers are required for the generation of independent, standard normally-distributed random numbers and can be generated using random number generators. Generators that describe the random number sequence by means of an algorithm have proved particularly useful here. These random numbers are then known as pseudo random numbers .

[figure TRM02-F262]

In the case of Monte Carlo simulation, the pseudo standard random numbers are generated by the linear congruence method:

[figure TRM02-F263]


[figure TRM02-F265 - With these values, the resulting pseudo random number sequence from the interval has the maximum period .]

[figure TRM02-F266]

[figure TRM02-F267]

with the values , , and any start value .





With these values, the resulting pseudo random number sequence from the interval has the maximum period .

If the same start value is chosen again, the same random numbers are generated. This function helps to make the simulation results comprehensible.

###### Strata-Gems Procedure

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Structured Monte Carlo > Generation of Random Numbers > Strata-Gems Procedure | L7 | trm02 p.239 | loio `6e13da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6e13da531198434de10000000a174cb4.html?locale=en-US)

[figure TRM02-F273]




In this procedure for generating random numbers with the distribution , the interval is divided into


[figure TRM02-F278]



[figure TRM02-F281]

equally long partial intervals of the length . The mid-point of the interval is the value

[figure TRM02-F282 - If we assume that is the inverse function of the standard normal distribution, then the equation for generates standard normally-distributed numbers sorted according to size.]

for .

[figure TRM02-F283]


If we assume that is the inverse function of the standard normal distribution, then the equation for generates standard normally-distributed numbers sorted according to size.

[figure TRM02-F285 - A property of these numbers is that they divide the density function of the -distribution into equally-large areas of the size]


A property of these numbers is that they divide the density function of the -distribution into equally-large areas of the size

[figure TRM02-F287]


[figure TRM02-F289]


, that is , where is the density function of the

standard normal distribution.

[figure TRM02-F291]

[figure TRM02-F292]


With a permutation , which can be simulated by drawing -times from the number set without laying back, appropriate random numbers can be generated.

[figure TRM02-F294 - The advantage of this procedure is that even with a small sample size, the generated sample comes very close to the normal distribution, although this is paid for with longer computation times on account of the inverse function calculation.]

The advantage of this procedure is that even with a small sample size, the generated sample comes very close to the normal distribution, although this is paid for with longer computation times on account of the inverse function calculation.

[figure TRM02-F295 - distribution only has be calculated -times using an approximation procedure. The remaining values can be specified using the]

Because of the symmetry of the normal distribution , the inverse function of the standard normal


distribution only has be calculated -times using an approximation procedure. The remaining values can be specified using the

[figure TRM02-F297]

relationship .

###### Tree Procedure

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Structured Monte Carlo > Generation of Random Numbers > Tree Procedure | L7 | trm02 p.239 | loio `6b13da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6b13da531198434de10000000a174cb4.html?locale=en-US)

This transformation method, also known as Direct transformation , creates a standard, normally-distributed random number from standard random numbers using the following formula:

[figure TRM02-F298]

[figure TRM02-F299]

.

The distribution of for converges after the central axiom rate against the standard normal distribution.

[figure TRM02-F300 - Experience shows that a satisfactory result can in fact be achieved with . The formula for calculating can be simplified to:]

[figure TRM02-F301]

Experience shows that a satisfactory result can in fact be achieved with . The formula for calculating can be simplified to:

[figure TRM02-F302 - Hence to approximate M-independent standard normally distributed random numbers with this procedure, you need standard random numbers.]

.

[figure TRM02-F303]

Hence to approximate M-independent standard normally distributed random numbers with this procedure, you need standard random numbers.

###### Box-Muller Procedure

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Structured Monte Carlo > Generation of Random Numbers > Box-Muller Procedure | L7 | trm02 p.240 | loio `6813da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6813da531198434de10000000a174cb4.html?locale=en-US)

This transformation method from Box and Muller, known as the Polar method, is based on the following procedure:

[figure TRM02-F305]



[figure TRM02-F308]

[figure TRM02-F309]

Assuming and are two standard random numbers. Set , and .

[figure TRM02-F310]

[figure TRM02-F311]


If applies, the random numbers and are independent standard normally

distributed random numbers.




If the condition does not apply, two new standard random numbers and are generated, which are independent of and . The algorithm is then executed again with these figures.




With this procedure, you require two standard random numbers to generate two -distributed random numbers if the


[figure TRM02-F320]


condition is met. The probability of this condition being met is , so that on average standard random numbers

are needed.

###### User-Defined Procedures

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Structured Monte Carlo > Generation of Random Numbers > User-Defined Procedures | L7 | trm02 p.240 | loio `3011da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/3011da531198434de10000000a174cb4.html?locale=en-US)

You can use simulation categories 50-53 to integrate user-defined functions into the structured Monte Carlo simulation via an RFC interface. The simulation categories are assigned to the following functions:

|Simulation Category|Features|
|---|---|
|50: Structurized Monte Carlo with user-defined algorithm for generating normally-distributed random numbers|Generates standard, normally-distributed random numbers|
|51: Structurized Monte Carlo, completely user-defined|Generates correlated time series of the risk factors Transfers the covariance matrix|
|52: Monte Carlo bootstrapping, user-defined|Generates correlated time series of the risk factors Transfers the historic time series of the risk factors|
|53: Structurized bootstrapping, user-defined|Generates correlated time series of the risk factors Transfers the covariance matrix and the historic time series of the risk factors|


There are two example functions for the interface. You can access these via the function modules MONTE_CARLO_USEREXIT_STEP_1 and MONTE_CARLO_USEREXIT_STEP_2:

###### Cholesky Decomposition

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Structured Monte Carlo > Cholesky Decomposition | L6 | trm02 p.241 | loio `6513da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/6513da531198434de10000000a174cb4.html?locale=en-US)

When calculating the value at risk, you want to be able to do more than just simulate individual prices. To manage the risk in a portfolio, you have to be able to simulate all the prices of the securities involved. Since these prices are usually interdependent, the question is how to build such correlations into the simulation.

[figure TRM02-F322]

The correlated, standard normally-distributed random numbers can be generated using linear transformation

[figure TRM02-F323]

[figure TRM02-F324]


[figure TRM02-F326]

, where is a matrix and a vector of uncorrelated, standard normally-distributed random

[figure TRM02-F327 - The matrix must be set up in such a way, that the following criteria are fulfilled when is multiplied by a vector :]

numbers, that is .



The matrix must be set up in such a way, that the following criteria are fulfilled when is multiplied by a vector :

[figure TRM02-F330 - You get the required matrix by solving the equation according to the elements of .]

[figure TRM02-F331]



You get the required matrix by solving the equation according to the elements of .


One procedure for calculating this matrix is the Cholesky decomposition, where the Cholesky matrix is a lower, triangular matrix, provided you are assuming that the correlation matrix is a symmetrical matrix with a consistently positive sign. A correlation matrix or covariance matrix meets these criteria when the risk factors are different pair-wise and linearly independent.


[figure TRM02-F336]



Using the matrix , you then get the following recursive calculation rule for the elements in the matrix :

[figure TRM02-F339 - With the resulting matrix , the following then applies:]


With the resulting matrix , the following then applies:

[figure TRM02-F341 - and]

and

[figure TRM02-F342 - The advantage of the Cholesky decomposition is that the multiplication requires few operations due to the lower triangular matrix.]


The advantage of the Cholesky decomposition is that the multiplication requires few operations due to the lower triangular matrix.

###### Variance/Covariance Approach: Theoretical Background

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Variance/Covariance Approach: Theoretical Background | L5 | trm02 p.242 | loio `da12da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/da12da531198434de10000000a174cb4.html?locale=en-US)

The variance/covariance approach is an analytical procedure for determining the value at risk. It is based on the assumption of the distribution of price changes. In the variance/covariance approach, potential loss is calculated from the volatility of the risk factors. The volatility of the risk factors and their correlations can be estimated from the historical market data for the respective risk factors (with a statistics calculator), or imported from external sources (using a datafeed, or a market data file).

The resulting individual risks are aggregated using correlation matrices, taking any interdependencies into account.

Delta valuation:

In the delta approach, normal distribution of price factors is assumed and the elasticity of the price function is used to estimate the NPV change based on the various price-determining parameters ( delta positions ). The portfolio changes are also normally distributed. The required quantile is determined by taking the inverses of the cumulated normal distribution function. The VAR arises as the product between the quantile and the variance of the NPV changes.

[figure TRM02-F344 - Delta-Gamma approach:]

Delta-Gamma approach:

The assumption of normal distribution does not apply. Here, in contrast to the delta valuation, non-linear terms of the second order (gamma positions) are additionally taken into account at the risk factor level so that skewed distributions are also interpreted. The VAR is calculated from the four moments of the distribution (expected value, variance, skewness and kurtosis)

using Cornish/Fisher approximation. It calculates the percentile of a normal distribution for a specified confidence level and for the first four moments of a distribution. The calculation of the VAR then occurs in the same way as for the delta procedure.

[figure TRM02-F345 - The process used for both delta valuation and the delta-gamma approach is known as risk factor mapping .]

The process used for both delta valuation and the delta-gamma approach is known as risk factor mapping .

###### Variance/Covariance Approach

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Variance/Covariance Approach: Theoretical Background > Variance/Covariance Approach | L6 | trm02 p.243 | loio `e012da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/e012da531198434de10000000a174cb4.html?locale=en-US)

**Prerequisites**

To calculate VAR using the variance/covariance approach, you need the volatilities and correlations of the risk factors. These can be determined from historical price changes or imported to the system from third-party vendors. In addition to calculation by the system using the statistics calculator, the RiskMetrics data record from JP Morgan can be imported using a file interface or a datafeed.

During the calculation, the variances and correlations for a certain holding period are estimated using the statistics calculator.

If you want to calculate value at risk for a holding period that differs from the holding period of estimated variances, you can perform a conversion to the holding period of the value at risk. For relative or absolute changes, this is done in a linear way. For logarithmic changes, the conversion is performed in accordance with the root-t method.

**Example:**

You can, for example, transform a one-day standard deviation into a ten-day standard deviation by multiplying it by the root of 10.

**Integration**

The value-at-risk amounts are displayed using the risk and portfolio hierarchies.

In the delta approach, the aggregation across the risk hierarchy is based on the assumption that you can add together the NPV differences according to the +/- sign. For each portfolio on a risk factor level, the system calculates the reactivity of the NPV to the risk factors, independent of the historical market prices.

In the delta-gamma approach, non-linear terms of the second order (gamma positions) are additionally taken into account at the risk factor level.

**Scope of Functions**

Value at risk in a risk factor

The system determines the value at risk for a risk factor by calculating the value change of the position that occurs with an isolated price change of this risk factor.

The value change of the position is calculated by determining the delta position in the risk factor and multiplying it by the standard deviation of the risk factor. The delta position is calculated by the price calculators.

The sign (+/-) of the value at risk for risk factors is the same as the sign of the delta.

Value at risk for risk hierarchy levels

The aggregation of VAR along the risk hierarchy is controlled by the aggregation type of the risk hierarchy. The following aggregation types are available:

|Aggregation type|Meaning|
|---|---|
|Totaled (according to +/- sign)|For each consolidation level of the risk hierarchy, providing the same aggregation type is set on the nodes under the consolidation node, the value at risk is determined from individual risk factors using the total. If this is not the case, then the value at risk is determined from the lowest level of the risk hierarchy ⇒ positive and negative values.|
|Totaled (absolute amounts)|For each consolidation level in the risk hierarchy, the value at risk is determined from the individual risk factors using the total of their absolute amounts ⇒ positive value.|
|Differentiated|The values at risk of the underlying risk factors are totaled separately according to whether they are positive or negative amounts. The larger of the two values represents the value at risk ⇒ positive value.|
|Correlated|For each consolidation level in the risk hierarchy, the value at risk is determined from the individual risk factors by means of their correlation ⇒ positive value.|
|Aggregated (directly preceding nodes)|For each consolidation level of the risk hierarchy, the value at risk is calculated from the nodes of the preceding risk hierarchy nodes by totaling, without taking into account which aggregation types exist in the preceding node ⇒ positive and negative values.|

###### Risk Factor Mapping

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Risk Factor Mapping | L5 | trm02 p.244 | loio `bb12da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/bb12da531198434de10000000a174cb4.html?locale=en-US)

The system maps the portfolios to the risk factors by determining the deltas and gammas of the portfolio in regard to the respective risk factors. It uses a difference quotient to approximate the first (delta) and second (gamma) derivative per risk factor. This derivative is then assigned to the respective risk factors as the delta or gamma position of the portfolio.

###### Delta Positions

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Delta Positions | L5 | trm02 p.245 | loio `7413da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/7413da531198434de10000000a174cb4.html?locale=en-US)

[figure TRM02-F346]

is the first partial derivative of the NPV function after the i-nth risk factor at the point


[figure TRM02-F348]


. is the current market value of the i-nth risk factor. In the shown procedure, is approximated using the right-sided difference quotient ("Delta position"):

[figure TRM02-F350 - (Alternatively, the first partial derivative can be expressed as a central difference quotient:]

(Alternatively, the first partial derivative can be expressed as a central difference quotient:

[figure TRM02-F351]

)

###### Detail Log

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Detail Log | L5 | trm02 p.245 | loio `c213da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/c213da531198434de10000000a174cb4.html?locale=en-US)

**Definition**

Detailed information about the valuations in Market Risk Analysis or in the price calculator.

**Use**

You can use the detail log to see how the system calculated figures in the valuations in Market Risk Analysis and in the price calculator. During the valuation process, the system writes the most important information about the processing steps to the detail log. When the valuation has finished, you can call the detail log from within the reporting function, such as that for the valueat-risk analysis.

You can then print the detail log for documentation purposes, and save the log as a file outside of the SAP system.

**Structure**

The detail log is a list in which the system records data relating to a valuation. Each section has a title.

The following tables explain each section of the detail log. Some sections can appear in the log more than once, whereas others may not be shown at all.

Market Data

This section contains the yield curve type, the exchange rate, and the security used in the valuation.

Summary of Results from the Price Calculator: NPV

This area contains the results from each price calculator process. The results are the same as the detailed results that are usually shown higher up in the detail log.

Historical Simulation

The system calculates NPVs using the delta procedure; there is no complete evaluation.

Covariance Method using Deltas:

The system calls the price calculator with shift rules. The shift rules define which market data the price calculator is to use during the valuation process. The shift rules are interpreted on the basis of the shift rule category. The shift rules themselves contain the following parameters:

|Parameter|Comment|
|---|---|
|Shift rule category|The shift rule category can have the following values: No shift rules (00) Sensitivity rules (01) Grid rules (02) Rules for historical simulation - complete evaluation (03) Rules for historical simulation - delta approach (04) Rules for variance/covariance – delta positions (05) Rules for historical simulation – delta-gamma approach (06) Rules for variance/covariance – delta-gamma (07) Combination method (generic rule) (09) External rules (99)|
|Risk factor|The system displays the ID of the risk factor from the risk hierarchy. The system reads the short name from the risk hierarchy for the relevant node.|
|Shift index|The meaning of the shift index depends upon the shift rule category: Covariance method : Upshift (00000) or downshift (99999) Historical simulation : Number of the simulation|


Value-at-Risk Calculation: Delta-Gamma Positions

In this section, the system displays the delta-gamma positions, and the parameters that it used to calculate them.

In the historical simulation, this area is used to display the sensitivities only.

|Parameter|Comment|
|---|---|
|PV (upshift)|NPV with upward shift|
|PV (downshift)|NPV with downward shift|
|Delta|Delta position normed to a shift of 1 (sensitivity): [figure TRM02-F352 - Delta position normed to a shift of 1 (sensitivity):]|


|Parameter|Comment|
|---|---|
|Gamma|Gamma position normed to a shift of 1|
|Shift|Absolute shift that results when the standard shift of 0.01 is applied to the current rate.|


Value-at-Risk Calculation: Calculation of Delta Positions for Each Transaction

In this section, the system displays the changes in the NPV, and the parameters that it used to calculate them.

|Parameter|Comment|
|---|---|
|Normed delta position|Sensitivity for a shift of 1 (see the Delta parameter in the Valueat-Risk Calculation: Delta-Gamma Positions section).|
|Shift|The shift reflects the volatility values from the market data, which were adjusted accordingly: Adjustment to the number of business days: [figure TRM02-F353 - Adjustment to the scaling factor:] Adjustment to the scaling factor: [figure TRM02-F354] Norming for absolute shifts: [figure TRM02-F355 - Norming for absolute shifts:] Calculation of the additive shift: [figure TRM02-F356 - Calculation of the additive shift:] The shift represents the shift in the generated market data.|
|Change in the NPV|[figure TRM02-F357]|


Value-at-Risk Calculation: Aggregation for the Value-at-Risk Value using the Correlated Method

In this section the system displays the aggregation of the results for the value-at-risk value. The risk hierarchy describes how the values are calculated.

Value-at-Risk Calculation: Adjustment of Delta-Gamma Positions

In this section, the log shows how the delta and gamma positions were normalized to an absolute shift. This step takes place for relative and logarithmic shifts only. The system uses the following formula:

[figure TRM02-F358 - In this section, the log shows how the delta and gamma positions were normalized to an absolute shift. This step takes place for relative and logarithmic shifts only. The system uses the following formula:]

[figure TRM02-F359 - Correlations: Correlations Used]

Correlations: Correlations Used

In this area the system displays the risk factors and correlations for all the transactions that were valued.

Value-at-Risk Calculation: Distribution Moments

In this area the system displays the values of the four moments for each risk factor and risk hierarchy. The system uses the correlations between the risk factors to calculate the moments.

Value-at-Risk Calculation: Value-at-Risk Values

In this section the system displays the value-at-risk value for each transaction and risk factor. The system uses the CornishFischer formula to calculate these values.

Below this, the log contains the value-at-risk values for each hierarchy node. In the individual analysis, the original value-atrisk values are retained, but in the portfolio approach, they are changed when they are aggregated.

Value-at-Risk Calculation: Historical Simulation using the Method in which the Value at Risk is Calculated from Absolute Profits and Losses

In the historical simulation, the system calculates the value at risk by finding the relevant part of the change in the NPV. To show how this was done, the log contains the length of the history, and the entry from the list of losses (sorted in descending order) that it took as the value at risk.

###### Mean Excess Loss (MEL)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Mean Excess Loss (MEL) | L5 | trm02 p.248 | loio `fccfe4bff65d4407a3e26c0f975d83f4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/fccfe4bff65d4407a3e26c0f975d83f4.html?locale=en-US)

**Use**

Mean excess loss (MEL) is defined as the mean loss that can be incurred in the scenarios in which the VaR confidence level is exceeded, also taking into account the VaR amount.

**Note:**

Mean excess loss is sometimes also called expected shortfall or tail VaR or conditional VaR.

The VaR provides an estimate for the maximum loss that will not be exceeded with a certain probability, but this result does not provide any information about scenarios in which the VaR is exceeded. Furthermore, whereas certain VaR methods are based on a normal distribution for the profits and losses of a portfolio, the actual probability for high profits and high losses is often much higher than that of the normal distribution.

The mean excess loss (MEL) sheds light on this topic.

MEL is supported by the Full Evaluation calculation method available for VaR by Historical Simulation and VaR by Monte Carlo Simulation.

Mean excess loss is defined as the mean loss that can be incurred in the scenarios in which the VaR confidence level is exceeded, also taking into account the VaR amount.

Historical Simulation Approach

MEL is supported by all calculation methods available for historical simulation:

Full Evaluation

Delta/Gamma Evaluation

Delta Evaluation

**Example:**

Given a profit loss distribution of 200 observations, VaR with a 99% confidence level will be the third-highest loss and MEL will be the mean of three highest losses.

Formula for MEL as implemented in system is:

[figure TRM02-F360 - Formula for MEL as implemented in system is:]

The mean excess loss key figure provides answers to the following questions (linked to several business scenarios) that may arise in the practice of risk management:

Beyond VaR, how much loss do we have to expect on average in the worst 5% (1%, 10%) of cases?

Are there significant deviations from normal distribution that need to be taken into account?

**Integration**

Usage of the MEL key figure is similar to the calculation of the VaR by the historical simulation key figure. In the key figure hierarchy, MEL is listed under the VaR by the historical simulation key figure to enable easy comparison. Consequently, the MEL key figure uses the attributes of its parent VaR key figure. The MEL key figure is not available for the variance-covariance approach.

**Note:**

The MEL key figure is also available in VaR online reporting (transaction RMV0).

**Features**

The MEL amounts are displayed using the risk and portfolio hierarchies.

With the full valuation approach, the profit and loss is calculated for every position on every risk hierarchy level by revaluating every position using the historical market data for each respective relevant risk factor.

With the delta approach, the aggregation across the risk hierarchy is based on the assumption that you can add together the NPV differences according to the +/- sign. For each portfolio on a risk factor level, the system calculates the reactivity of the NPV to the risk factors, independently of the historical market prices.

With the delta-gamma approach, non-linear terms of the second order (gamma positions) are additionally taken into account at the risk factor level.

The three methods can also be combined with one another (combination procedure). In this case, the respective method is selected depending on the value in the differentiation rule stored in the evaluation type and specific to the valuation rule. However,

the settings specific to the valuation rule are not interpreted until the combination procedure has been selected in Customizing for the value-at-risk type.

The fictitious profits and losses resulting from the valuations form the basis for determining the mean excess loss. In the system, mean excess loss can be calculated in the following ways, based on the distribution of profits and losses:

From simulated profits and losses

The simulated profits and losses determined for each day in the historical period are sorted by size taking into account the

+/- sign.

The value at risk for a confidence level is the nth smallest profit/loss, where:

n = ((1 - confidence level) x No. of simulation days) +1.

Hence, with 200 days, MEL95% is the mean of 11 smallest profits/losses, since

n = ((1-0.95) x 200) + 1 = 11

From absolute profits and losses

The simulated profits and losses determined for each day in the historical period are transformed into absolute amounts and sorted by size without taking into account the +/- sign.

The mean excess loss for a confidence level is the mean of n largest profits/losses, where:

n = ((1 - confidence level) x No. of simulation days) *2+ 1

The mean excess loss is always displayed as a negative value. If n is larger than the number of simulation values (with a very low confidence level), the mean excess loss is displayed as zero. With 200 days, MEL95% is the mean of 21 largest profits/losses, since

n = [(1-0.95)*200*2] +1 = 21

This method provides only odd values for the sample evaluation, and the value at risk is overestimated. You can calculate more exact values with the same CPU time using the following methods:

From absolute profits and losses (double the number of values)

The simulated profits and losses determined for each day in the historical period are transformed into absolute amounts and sorted by size without taking into account the +/- sign. However, twice the number of sample values are used.

The mean excess loss for a confidence level is the mean of n largest profits/losses, where:

n = ((1 - confidence level) x 2 x No. of simulation days) +1.

The mean excess loss is always displayed as a negative value. If n is larger than the number of simulation values (with a very low confidence level), the mean excess loss is displayed as zero.

With 200 days, MEL95% is the mean of 21 largest profits/losses, since

n = [(1-0.95)*200*2] +1 = 21

Assuming normal distribution

The simulated profits and losses are assumed to be values in a sample having an expected value of zero with normal distribution. The standard deviation is determined using a statistical estimation.

When the normal distribution is enforced, the long tails of the distribution are then ignored. Hence mean excess loss values do not have much relevance when normal distributions are assumed.

In the system, the mean excess loss then has the following formula:

MEL = VaR * exp(-z_alpha^2/2)/((1-alpha)*z_alpha*SQRT(2*pi))

Where, VaR is the value at risk with the same confidence level calculated using historical simulation

Z_alpha is the z factor of normal distribution,

Alpha is the confidence level.

###### VaR Contribution (VaRC) and Marginal VaR (MVaR)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > VaR Contribution (VaRC) and Marginal VaR (MVaR) | L5 | trm02 p.251 | loio `16a2840c23f84e4189b6d910df366caa` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/16a2840c23f84e4189b6d910df366caa.html?locale=en-US)

**Use**

To measure the effect that changing positions have on portfolio risk, individual VaRs are not sufficient.

Volatility measures the uncertainty of the return of an asset when it is considered in isolation. When this asset belongs to a portfolio, however, what matters is its contribution to the portfolio risk. The effect of the small changes to a part of the portfolio on the portfolio VaR is measured by marginal value at risk (MVaR). The contribution of a position or a subportfolio to the total VaR is measured by value-at-risk contribution (VaRC). VaRC is the additive decomposition of the total portfolio VaR and is calculated and reported both at portfolio level as well as single-deal level.

The above key figures provide answers to the following questions, which are linked to several business scenarios and which may arise in the practice of risk management:

What are the most significant sources of risk, that is, what are the portfolio's 'hot spots'?

VaRC on portfolio hierarchy levels and on instrument level

What can be done to reduce the VaR? Which new trades will improve VaR and which will degrade it?

MVaR, VaRC on portfolio hierarchy levels and on instrument level

How will we implement trading limits based upon VaR?

VaRC on portfolio hierarchy levels

What is the contribution of an asset category or of an asset manager to the risk of the whole portfolio or enterprise? How can hedging costs be allocated to the risk sources?

VaRC on portfolio hierarchy levels

**Integration**

The VaRC and the MVaR key figure calculations are available only through the variance-covariance delta approach.

The VaRC and MVaR amounts are displayed using portfolio hierarchies. In the key figure hierarchy, the VaRC key figure has been listed under the VaR by the variance-covariance approach to enable the calculation of both key figures simultaneously and to enable easy comparison. Since VaRC uses the attributes of its parent VaR key figure, it is essential for the comparison that the Position Category attribute of the key figure is set to Delta Positions. If the category is not Delta Position, results of VaR and VaRC may differ.

MVaR key figure is listed below VaRC as it requires the results of VaRC for its calculation.

Unlike the classical VaR key figures, the VaRC and MVaR key figures are available in the Single Records area of the Analyzer Information System display but not in the Risk Hierarchy area.

The key figures are unavailable in VaR online reporting (transaction RMV0).

**Features**

The calculation method used to calculate value-at-risk contribution (VaRC) can be encapsulated as follows:

The approach is based on the assumption of normal distribution of price factors. The potential loss is calculated from the volatility of risk factors. The volatilities of the risk factors and the correlations between them can be estimated by the statistics calculator or imported from external sources (datafeed).

- 1. The NPV is calculated for each instrument using the current market data.
- 2. The delta positions are calculated for each transaction for each relevant risk factor.
- 3. The correlations between the risk factors are returned and are then used to calculate the VaRC for each financial transaction. The VaRC at a portfolio node level is the total of the VaRCs of all the underlying financial transactions.


The total portfolio VaRC is always equal to the portfolio VaR calculated using the variance-covariance delta approach, provided that the aggregation category of the risk hierarchy used is Correlated. The formula for VaRC as implemented in the system is:

[figure TRM02-F361 - The calculation method used to calculate marginal value at risk (MVaR) can be encapsulated as follows:]

The calculation method used to calculate marginal value at risk (MVaR) can be encapsulated as follows:

Like VaRC, MVaR is also calculated and reported both at single financial transaction level and at portfolio node level. MVaR in the system is implemented as the VaRC per unit of NPV and is represented as a percentage key figure.

MVAR = VaRC / NPV

###### Backtesting

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Backtesting | L5 | trm02 p.253 | loio `4011da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/4011da531198434de10000000a174cb4.html?locale=en-US)

**Use**

Backtesting is the process in which value-at-risk values are checked ex post against actual changes in the value of the portfolio. Backtesting checks how accurately the value-at-risk calculation predicted the actual risk.

The Basel Committee on Banking Supervision requires banks to perform an ex post comparison for the in-house models that they use to calculate the capital requirement. In this process, the exceptions (realized gain or loss > VaR) from the last 250 trading days (holding period of 1 day, 99% confidence level) are added together and compared with the forecasts.

The Basel backtesting procedure enables you to assess in-house models using a traffic light display that is based on the number of outliers:

|Traffic Light Display|Description|
|---|---|
||The number outliers is less than or equal to 4. The model is considered accurate by the banking supervisory body.|
||The number of outliers is less than or equal to 9. The bank can continue to use the model if they use a higher scaling factor.|
||The number of outliers is greater than 10. The scaling factor is 4 in this instance and the banking supervisory body can refuse the use of the bank's in-house model for the calculation of the capital requirement.|


Other methods, such as Q-Q plots and P-P plots, check the distribution of the forecasts.

**Integration**

Displaying Backtesting Results (Results Database)

You can use the system to perform backtesting for results data as per the Basel Committee's requirements. It also contains additional functions in the results database, such as Q-Q plots and P-P plots.

Calculation of the NPV for saved datasets

**Prerequisites**

Backtesting requires that the ex post check accesses the same transaction data as that used for the value-at-risk forecast. This means that any changes to the portfolio that have taken place in the meantime must not be included in backtesting.

The system contains a function for saving, at any point in time, the data that is used in an analysis. This data is referred to as a saved dataset and is stored in the database. In order that the backtesting functions can be used, a saved dataset must exist.

To generate saved datasets, in the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Tools Back Testing Generate New Dataset .

The system saves the transaction data as risk objects for the selection date specified and on the basis of a view and a portfolio hierarchy. It assigns the dataset an identification number, which is used in the backtesting function to access this dataset.

Future-style transactions are saved and analyzed differently from other types of transaction. When the NPV is being calculated, futures have, by definition, an NPV of zero. However, during backtesting, they may well have an NPV risk. For these reasons, when futures are saved at time point t0, the system saves the current price at the same time. When the transaction is analyzed at time point t1, the price valid at that time is determined, and the future (or option on the future) is valued using the price difference.

You can also archive datasets. When datasets are archived, they are stored both on the database and in the SAP Archive until they can be deleted explicitly from the database.

###### Displaying Backtesting Results (Results Database)

> **Path:** Treasury and Risk Management > Risk Management > Basics > Value at Risk > Backtesting > Displaying Backtesting Results (Results Database) | L6 | trm02 p.254 | loio `b812da531198434de10000000a174cb4` | [portal](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/848f8ce21bcd4f67bce77494799e2257/b812da531198434de10000000a174cb4.html?locale=en-US)

**Use**

The Analyzer Information System contains functions for reporting backtesting results using the results database.

The following analyses are available:

Traffic light display for the requirements from the Basel Committee

Tables containing the results of calculations

Graphs showing the value at risk, and the values of the profit and loss key figures required for purposes of comparison

Q-Q plot for generating graphs to show the extent to which key figures deviate from their average values

- P-P plot to check to what extent a profit and loss key figure is evenly distributed


In the analysis functions, you can navigate in the portfolio hierarchy and risk hierarchy, which enables you to display the results at different aggregation levels, and for different risk factors.

**Prerequisites**

In Customizing for market risk analysis, which is under Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Results Database Define Initial Layout , you need to have stored the following information:


One value-at-risk key figure, and at least one profit and loss key figure that you want the system to display.

A profit and loss key figure that you want the system to compare with the value at risk.

Size of the sample for backtesting

You also need to have carried out the relevant valuation runs for value at risk and the profit and loss key figures.

**Procedure**

In the SAP Easy Access screen, choose Accounting Financial Supply Chain Management Treasury and Risk Management Market Risk Analyzer Information System Analyzer Information System .

The system displays a selection screen.

Specify the view, portfolio hierarchy, and the key dates for the data that you want to display, and choose an initial layout for the display of the results.

Choose Execute.

The portfolio hierarchy is shown in the top part of the screen, and risk hierarchy is shown in the lower part of the screen.

To analyze the backtesting results, you first select a node in the portfolio hierarchy, and then a node in the risk hierarchy.

Choosing a Node in the Portfolio Hierarchy

There are two ways in which you can choose a node in the portfolio hierarchy:

Choose Determine Outliers.

The system opens a dialog box that shows the section of the portfolio hierarchy that contains the outlier. Any portfolio hierarchy nodes that contain outliers are shown by a red indicator.

To analyze an outlier, highlight the respective portfolio hierarchy node by choosing the relevant field in the Outliers column, and then choose Display Details.

Open the portfolio hierarchy down to the level of the required node. Then choose the node by double clicking the field containing the key figure.

The system highlights the portfolio hierarchy node in the upper part of the screen, and selects its backtesting data.

Choosing a Node in the Risk Hierarchy

Choose the Backtesting tab page.

On the left, the system displays a navigation structure containing the risk hierarchy.

To display the backtesting results, double click the node in the risk hierarchy.

The system highlights the risk hierarchy node, and displays the associate backtesting results in the right-hand part of the screen next to the navigation structure.

Reporting

The system displays the backtesting results on the Backtesting tab page. This tab page is divided into the following areas:

Table Containing Backtesting Results

For each maturity band, the system compares the value-at-risk key figures with the profit or loss that was realized. In the righthand column, the system displays the difference from backtesting, which is the difference between the estimated loss from the value-at-risk analysis, and the key figure defined in Customizing for comparison with the actual profit or loss.

If the actual loss is larger than the value at risk, the backtesting different is negative. Negative differences from backtesting are shown in red.

Summary of Backtesting Results

|Field|Description|
|---|---|
|Number of Outliers|Number of key dates on which the backtesting key figure is negative The system shows the number of outliers in green, yellow, or red, depending on the number of outliers and as per the Basel|


|Field|Description|
|---|---|
| |Committee regulations.|
|Number of times limit was exceeded positively|Number of key dates on which the profit is larger than the value at risk|
|Number of Losses|Number of key dates on which the key figure for the comparison for profits and losses is negative|
|Size of Sample|Number of key dates that have been included in the analysis|
|Holding Period|The holding period specified in the value-at-risk calculation|
|Confidence Level (Plan) in Percentage|Range for the confidence level, which is stored in the value-at-risk key figure|
|Confidence Level (Actual) in Percentage|Confidence level P calculated from the set of values that were determined: [figure TRM02-F366 - where x is the number of outliers, and N the scope of the sample.] where x is the number of outliers, and N the scope of the sample.|
|Value at Risk on key date| |
|Green, yellow, and red traffic lights|Number of outliers in the green, yellow or red areas, as defined by the Basel Committee. In a sample of 250, the ranges are defined as follows: Green: up to 4 outliers Yellow: 5 to 9 outliers Red: more than 9 outliers If the sample is not 250, the system calculates the ranges for the traffic lights as per the Basel regulations.|


**Distribution of Value at Risk and Profits and Losses**

[figure TRM02-F367 - The system shows the profits and losses as bars on the time axis. This graph is based on the the key figure that you defined for comparing the profit and loss. The outliers are shown in red. In order to make it easier to compare the profit and loss with the value at risk, the system also shows the data for the value at risk.]

The system shows the profits and losses as bars on the time axis. This graph is based on the the key figure that you defined for comparing the profit and loss. The outliers are shown in red. In order to make it easier to compare the profit and loss with the value at risk, the system also shows the data for the value at risk.

To display the value at risk and the profit and loss key figure for a key date, double click a bar in the diagram. In the status bar, the system displays the relevant key date with the values for the value at risk and the profit and loss key figure.

- Q-Q Plot


[figure TRM02-F368 - For each key date, the system calculates the extent to which the value-at-risk key figure deviates from its average, and the extent to which the profit and loss key figure deviates from its average. It then sorts the values of the key figures by size (separately for the profit and loss key figure, and for the value-at-risk key figure). The system enters the values in the sorted lists accordingly, so that they can be compared.]

For each key date, the system calculates the extent to which the value-at-risk key figure deviates from its average, and the extent to which the profit and loss key figure deviates from its average. It then sorts the values of the key figures by size (separately for the profit and loss key figure, and for the value-at-risk key figure). The system enters the values in the sorted lists accordingly, so that they can be compared.

The deviations are measured as follows:

[figure TRM02-F369]

,

[figure TRM02-F370]

where n is the scope of the sample, and σ is the standard deviation.

The graph shows how close the distribution of the forecast VaR values is to the distribution of the actual profit and loss values.To make the analysis easier, the system displays a line from the origin with a slope of 1. The actual distribution is equal to this line if the deviations of the value at risk and the profit and loss key figure are identical.

To display the value at risk and the profit and loss key figure for a key date, double click a bar in the diagram. In the status bar, the system displays the relevant key date with the values for the value at risk and the profit and loss key figure.

P-P Plot

[figure TRM02-F371 - The system places the values of the profit and loss key figure in 100 equal quantiles.In the graph, the system shows how frequently the values for the profit and loss key figures occur in the respective quantiles. It also shows the respective cumulative frequency across the quantiles.]

The system places the values of the profit and loss key figure in 100 equal quantiles.In the graph, the system shows how frequently the values for the profit and loss key figures occur in the respective quantiles. It also shows the respective cumulative frequency across the quantiles.

To make the analysis easier, the system displays a line from the origin with a slope of 1. If the profit and loss key figure is equally distributed, the graph of the actual distribution has this form.

To display a pair of values of the actual distribution, double click on a point in the graph. In the status bar, the system displays the relevant quantile and cumulated frequency.


You can change the size of the areas in the tab page by using Drag&Drop to move the gray borders.

