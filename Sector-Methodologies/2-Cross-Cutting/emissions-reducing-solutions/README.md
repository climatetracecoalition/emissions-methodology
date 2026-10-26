<img src="figures/logo.png" width="246" />

### Emissions-Reducing Solutions Framework for Climate TRACE

**Krsna Raniga<sup>1,2</sup>, Lauren Betz<sup>1,2</sup>, Zoheyr Doctor<sup>1,2</sup>, Amy Kouch<sup>1,2</sup>, Christy Lewis<sup>1,2</sup>, Dan Moore<sup>1,2</sup>, Amy Piscopo<sup>1,2</sup>, Anthony Russo<sup>1,2</sup>, Ishan Saraswat<sup>1,2</sup>, Ting So<sup>1,2</sup>, Lekha Sridhar<sup>1,2</sup>, Peter Thomas<sup>1,2</sup>, and Gavin McCormick<sup>1,2</sup>**

*1) WattTime, 2) Climate TRACE*

#### 1 Introduction

The ultimate goal of Climate TRACE is to empower climate action to reach net-zero anthropogenic greenhouse gas emissions. The detailed asset-level emissions estimates synthesized by Climate TRACE thus far have provided a baseline from which to assess impacts of specific emissions-mitigating actions. Here we describe a crucial addition to the Climate TRACE data set: a catalog of emissions-reduction solutions (ERSs) and corresponding estimates of emissions reduction potential if these solutions were applied to any asset, in any sector, globally. The ERS framework accounts for both direct effects on activity and emissions factors at the target asset as well as consequential induced effects on other dependent sectors (e.g., electricity).

#### 2 Methods

#### 2.1 Framework

Climate TRACE’s ERSs are based on two essential lists: the assets tracked by Climate TRACE and the candidate strategies for emissions reduction (Section 2.2). In our framework, each asset is matched (“crosswalked”) to one or more strategies that could be applied to it. We model the effect of a candidate strategy on an asset’s emissions by considering the strategy’s changes to the asset’s emissions factor, activity, and/or capacity (see Equation 1 in [*<span class="underline">Completeness of Bottom-up Emissions Estimates and Associated Metadata</span>*](https://github.com/climatetracecoalition/methodology-documents/tree/main/2025/Post%20Processing%20for%20Global%20Emissions%20and%20Metadata%20Completeness) (Moore et al, 2025)). Furthermore, we account for the fact that applying a strategy to a target asset may “induce” changes in activity at *other* assets, therefore yielding additional changes in emissions. We catalog the parameters of this “new” reality if the solution were applied, including both the direct and induced emissions changes (holding all else equal), and then propagate these parameters to calculate the resultant global emissions reduction. This yields a list of asset and strategy pairs and their expected emissions reductions per year compared to business as usual. We describe these inputs and steps in the following sections.

#### 2.2 Strategy Completeness

Climate TRACE prioritizes domain-specific, research-backed ERS developed with sector expertise. However, to ensure comprehensive coverage across all assets and sectors, the dataset includes supplementary strategy generation methods that guarantee at least one applicable ERS with non-negligible emissions reductions for every asset. ERS are collated using the following hierarchical approach:

-   **Domain-specific solutions**: ERS compiled by Climate TRACE member teams that provide asset- or sector-specific actions and associated metadata. See individual sector methodologies in the [<span class="underline">Climate TRACE GitHub methodology repository</span>](https://github.com/climatetracecoalition/methodology-documents/tree/main/2025) and [<span class="underline">version 5.0 Changelogs</span>](https://github.com/climatetracecoalition/methodology-documents/tree/main/2025/CHANGELOG).

-   **Auxiliary domain-specific solutions**: Additional domain-specific ERS compiled by WattTime.

-   **Benchmark-based ERS**: Automatically generated strategies that benchmark assets to the 10th-percentile emissions intensity in each sector, grouped by facility output type. Benchmark-based ERS aims to reduce asset-level emissions by aligning the emissions intensity of a given facility with that of the 10th percentile of facilities within the same sector. The potential reduction for any individual facility can range from 0% to 100%, depending on its current efficiency relative to the sector benchmark. Adoption of this strategy varies by industry, geography, ownership structure, and technology sub-types, as these factors influence the feasibility of implementing retrofits. In some sectors, such as iron and steel, switching from blast furnaces to electric arc furnaces represents a well-established retrofit pathway. In other sectors, identifying clear benchmarks is more challenging due to complex production processes or insufficient comparative data, which can limit the ability to apply this solution broadly.

-   **Unspecified improvements**: Universal 10% reduction (internal definition) in emissions factor applied as a fallback option. Provided as a guide of what is possible from e.g. minor reductions in consumption and/or increases in efficiency. The unspecified improvements aim to reduce emissions by approximately 10% at individual assets through generalized improvements in operational efficiency. While the specific technologies or practices are not defined, the mechanism relies on applying efficiency gains that may already exist at other assets within the same sector. Adoption of this solution is potentially universal across sectors, as the approach can be tailored to the unique conditions of each facility. However, the exact improvements necessary will vary by sector and by facility, and the solution remains "unspecified" because it aggregates diverse efficiency measures rather than prescribing a single intervention.

-   **Do Nothing/Do not reopen:** This approach maintains current operations for assets that are already operating at the most efficient levels with available technology or have been permanently shut down. This strategy does not actively reduce emissions but preserves the assets’ performance that have already been optimized or closed. Adoption of this approach is inherently limited to facilities that meet these criteria, ensuring that no further operational changes are required. The main caveat is that no additional emission reductions are achieved beyond the existing efficiency or closure status of the asset. Where this occurs, induced emissions are not estimated.

Each ERS is ascribed subjective confidence values assessing real-world practicality covering “very low”, “low”, “medium”, “high”, “very high”. Note, while this scheme ensures completeness, it does not guarantee that every asset is paired with at least one domain-specific solution: Some assets are paired only with benchmark-based ERS or unspecified improvement ERS, which are provisional best-available estimates. When multiple strategies are crosswalked to the same asset, each is evaluated independently as a mutually exclusive alternative; the current framework does not compound multiple interventions on a single asset.

#### 2.3 Core Reduction Calculation

For each greenhouse gas - carbon dioxide (CO<sub>2</sub>), methane (CH<sub>4</sub>), and nitrous oxide (N<sub>2</sub>O) - the annual emissions reduction rate (*R*) relative to the baseline emissions, defined as the total emissions from the previous full calendar year, is calculated as:

$`R\  = \ A_{\text{affected}}(\epsilon_{\text{old}} - \lbrack\epsilon_{\text{new}} + \alpha_{1}\text{ME}R_{1} + \ \alpha_{2}\text{ME}R_{2} + \alpha_{3}\text{ME}R_{3}\rbrack)`$ (1)

Below we list the definition of each of these quantities and their corresponding field in the ERS data set in parentheses.

-   $`R`$ (total\_emissions\_reduced\_per\_year): Rate of total emissions reduced per year, against the baseline emissions

-   $`A_{\text{affected}}`$ (max\_activity\_affected): Amount of the asset’s activity affected by the ERS, ranging from 0-100% of the annualized previous full calendar year activity. For example, if the ERS only applies to half of the activity at an asset, this would be 50% of the asset’s baseline activity

-   $`\epsilon_{\text{new}}`$ (\[GAS\]\_emissions*\_*factor\_new\_absolute) Emissions factor (tonnes of gas per unit activity) after the ERS intervention

-   $`\epsilon_{\text{old}}`$: Annualized baseline emissions factor pre-intervention

-   $`\alpha_{i}`$ (induced\_sector\_i\_conversion\_rate): Target sector to induced sector activity conversion factor, for each sector *i* in which emissions are induced by the ERS (e.g., MWh/tonne steel produced if an action in the steel sector induces electricity generation)

-   $`\text{ME}R_{i}`$: Marginal emissions rate for induced sector *i* (tonnes gas per unit induced activity)

Each strategy in our portfolio specifies $`A_{\text{affected}}`$, $`\epsilon_{\text{new}}`$, and $`\alpha_{i}`$, with the other quantities being derived from existing emissions estimates (or CMERs for electricity-generation, see “Power sector-Emissions from Electricity Generation” in the [<span class="underline">Climate TRACE GitHub methodology repository</span>](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Power/Power%20sector-Emissions%20from%20Electricity%20Generation.docx.pdf)). In some cases, $`A_{\text{affected}}`$ and $`\epsilon_{\text{new}}`$ are specified using ratios relative to the baseline activity and $`\epsilon_{\text{old}}`$ respectively, via parameters with the “\_new\_to\_old\_ratio” suffix. These ratios are converted to their absolute values when calculating the reduction potential in Equation 1. $`R`$, as well as other intermediate quantities, are computed for all three of CO<sub>2</sub>, CH<sub>4</sub>, and N<sub>2</sub>O following Equation 1, and the results are used to derive expected reductions for 20-year and 100-year global-warming-potential (GWP) CO<sub>2</sub> equivalents, as defined by the IPCC.

#### 2.3.1 Induced emissions

Induced emissions represent the emissions consequences of implementing an ERS to an asset that are not accounted for in changes to the direct emissions of that asset. For example, this would apply to electric vehicles replacing fossil-fuel vehicles, leading to induced emissions from electricity generation.

These induced emissions are calculated by converting the facility's affected activity into induced activity in other sectors, then employing marginal emissions rates to quantify the emissions impact, captured by the $`A_{\text{affected}}\alpha_{i}\text{ME}R_{i}`$ terms of Equation 1.

At present, we account for the asset's influence on up to three induced sectors where the ERS causes emissions changes (typically increases) due to additional energy, transportation, materials, or general process requirements. In principle, we can account for an arbitrary number of induced sectors, but have found thus far that three is sufficient to handle all ERS. Electricity generation is the most common induced sector as many ERS rely on electrification, but self-induced emissions are also common especially for shutdown strategies, where demand is diverted back to the regional network of assets in the sector.

#### 2.3.2 Activity conversion

Activity conversion factors $`\alpha_{i}`$ translate the target asset’s affected activity into induced activity in upstream or downstream sectors. For example, an electrification strategy applied to a steel facility might require 0.00081 MWh of electricity per tonne of steel produced. This conversion factor is multiplied by the facility's affected activity (i.e. the amount of steel produced using electricity) to determine the induced electricity generation activity.

#### 2.3.3 Marginal Emissions Rates (MER)

For electricity generation, we use the combined marginal emissions rate (CMER), taken as the average of the marginal operating emissions rate (MOER) and marginal build emissions rate (MBER). These vary by renewable energy type, and are described in detail in our power sector methodology (Freeman et al. 2025; see “Power sector-Emissions from Electricity Generation” in the [<span class="underline">Climate TRACE GitHub methodology repository</span>](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Power/Power%20sector-Emissions%20from%20Electricity%20Generation.docx.pdf)).

The month-averaged CMER values for the previous full calendar year are applied at the balancing authority (BA) level for induced electricity cases. For cases where the facility of interest does not belong to an existing BA, the country-level average of power plant emissions factors defines the CMER. The global average serves as the final fallback.

For non-electricity induced sectors, MERs are approximated as the average emissions factor at:

-   Country-level where one or more assets of the induced sector exist in the same country

-   Global level where no other assets of the induced sector are available in the same country

-   Default emissions factors derived from the Intergovernmental Panel on Climate Change (IPCC) guidelines where no spatially certain asset-level information is available in Climate TRACE

Future work may improve on this approximation since the MER is not equal to the average emissions factor in general. MERs and induced activity conversion rates are applied against the facility's monthly activity profile, with monthly induced emissions summed to calculate the annual offset against facility-level reductions. When applicable, the MER is calculated based on the asset output type. This is used for cases where activity is shut down at an asset, inducing more demand for the same output as the closed facility.

#### 2.4 ERS Selection per Asset

While there are multiple possible ERS for each asset, we provide a single one at this time. Future upgrades will include more ERS options per asset. To select a single ERS for each asset, we first rely on the initial strategy\_rank for asset-strategy pairs, if it was provided in the initial data compiled for each sub-sector. However, in cases where the reductions are less than 3% (including negative reductions) or an initial strategy\_rank is unavailable, we re-rank the asset-strategy pairs. Our re-ranking proceeds by prioritizing reductions &gt; 3% (an effective threshold), then reductions between 0 and 3%. We exclude any cases where emissions reductions are negative. If further tie breaking is necessary, we follow each of the bullets below to break any ties, in order:

-   Domain-specific strategy &gt; Auxiliary domain-specific strategy &gt; Benchmark strategy &gt; Unspecified efficiency improvement

-   strategy\_id (this is a final deterministic tie breaker)

#### 2.5 ERS for spatially uncertain sources

Not all emissions within a country can be confidently attributed to individual assets. Instead, these spatially uncertain emissions are attributed to GADM regional boundaries and GHS Functional Urban Areas (ghs-fua) city boundaries, described in further detail in our methodology on spatially uncertain emissions (Collins et. al. 2025, see methodology in “[<span class="underline">Post Processing for Global Emissions and Metadata Completeness</span>](https://github.com/climatetracecoalition/methodology-documents/tree/main/2025/Post%20Processing%20for%20Global%20Emissions%20and%20Metadata%20Completeness)” directory in the Climate TRACE GitHub repository).

Despite the lack of attribution to specific sites or operations, these sources still require quantified reduction pathways to ensure comprehensive coverage of global mitigation potential. The ERS for these spatially uncertain sources are derived using three approaches:

1.  The rank=1 asset-level strategies within each boundary are used to calculate an effective emissions reduction for each greenhouse gas, by taking the mean reduction ratio for all *n* assets in the boundary and applying to the boundary baseline emissions:

$`R_{boundary,\ gas}{\  = E_{\text{boundary}} \cdot \ {{(1/n_{\text{assets}}) \cdot \sum_}_{i}}{(R}_{i,\ gas}/E_{i,\ gas})\ }`$

The mean boundary-level emissions factor ratio is then applied to spatially uncertain emissions by gas. If no localized assets exist in the boundary, the country-level mean is used as a fallback, and if no localized assets exist in the country, the global mean is used as the final fallback.

1.  Auxiliary domain-specific solutions from Climate TRACE member teams for any sectors without asset-level coverage, applied globally with no regional differentiation at this time.

2.  Unspecified efficiency improvements through a universal 10% reduction in emissions factor applied as a fallback option, analogous to the approach for standard assets described in Section 2.2.

No induced emissions are explicitly accounted for in spatially uncertain reductions, but rather are integrated into the effective reduction ratios implicitly.

#### 2.6 Difficulty Score

With a defined strategy for each asset, we next seek to prioritize assets across sectors with ERS that are both easy to implement and yield high emissions reductions. Three qualitative metrics that weigh in the ease or difficulty of ERS implementation are the *effectiveness*, *practicality*, and *cost*. We capture these metrics quantitatively with a simple scoring system, and then combine the scores into a final “difficulty score” that is easily reproducible and comparable across sectors. We define the intermediate scores as:

-   Cost Score: Categorical integer ranging from 1 to 5 assessed through expert judgement and research, representing capital and operational intensity spanning from less costly (1) to more resource-intensive (5)

-   Practicality Score: Categorical integer ranging from 1 to 5 following the guide below, assessed through expert judgement and research:

-   Practical (1): real-world solutions that can be implemented nearly everywhere with ease

-   Reasonable (3): commonly implemented solutions with noted considerations

-   Exploratory (5): solutions with implementation challenges

-   Effectiveness Score: Numerical value spanning \[-2,2\] calculated as the z-score of an asset’s reductions per unit of its baseline activity within that asset’s subsector. In the event of a tie, the total reduction potential of the asset is used to determine the rank, independent of the sector

These scores are then combined into a raw difficulty score, which is simply the average of the practicality and cost scores plus the effectiveness score. The final difficulty score re-normalizes the raw difficulty scores over all assets so that the maximum difficulty is 10 and the minimum is 1.

We note that these metrics do not capture every subtlety of implementing an ERS, but they do provide an initial guide that, when examined alongside the assumptions, can be used to prioritize asset-strategy pairs. Future releases will expand on this framework to continuously improve the decision-making information we provide via Climate TRACE.

#### 3 Conclusion

The Climate TRACE ERS calculation framework is a systematic, modular pathway that both defines strategies and quantifies their expected net emissions reductions. Valid strategies are based on domain expertise and are drawn, as much as is feasible, from evidence-driven, real-world deployments of emissions reducing technologies/practices. Reductions calculated from these strategies account for changes in both emissions at the facility and downstream induced effects while safeguarding against implausible outcomes. Finally, the 100-year GWP aggregation enables comparison across interventions affecting different greenhouse gases in different sectors, accommodating both highly local and accumulated, globally aggregated reductions estimates.

Crucial next steps remain after the initial rollout of TRACE ERS. First, continued engagement with sector experts, technology developers, and downstream users is needed to meaningfully expand and refine the strategy library, including developing compound strategies that combine complementary interventions currently treated as mutually exclusive alternatives. Second, integrating more detailed cost and practicality data will enable stronger prioritization by accounting for additional implementation barriers. Third, validating expected reductions against observed emissions changes from real-world deployments can refine strategy parameters and improve confidence bounds. Altogether, these next steps can transition the framework from a static assessment to a dynamic, user-driven system, enabling consideration of multiple strategies per facility, either in isolation or as realistic hybrid strategies to maximize reduction potential.
