### Manufacturing and Industrial Processes sector: Cement Manufacturing Emissions

**Verity Crane and George Ebri**

*Authors are affiliated with TransitionZero and Climate TRACE*

V5.11.0, Sept. 2026

#### 1. Introduction

The cement industry plays a critical role in both global infrastructure and global emissions. It accounts for roughly 7% of industrial energy use and an equal share of global carbon dioxide emissions, making it the second-largest source of direct industrial CO2 emissions after steel (IEA, 2018). Cement is the principal ingredient used to make concrete, the most widely used manufactured material in the world, owing to its versatility across housing, sanitation, transportation, and energy infrastructure. Meeting future cement demand while cutting CO2 emissions poses a major challenge: although China's construction sector has cooled in recent years, rising demand in other regions is set to drive global consumption upward.

A clear picture of where cement-sector emissions originate and how they are distributed is typically difficult to obtain. Commercial confidentiality and international competition limit public reporting of plant-level production data. Most official statistics are aggregated at the national level, with reporting delays of up to several years (USGS, 2026a; NBSC, 2026). Only a few jurisdictions, such as the EU and the United States, publish facility-level emissions data (E-PRTR, 2024; US EPA, 2025). This dataset aims to close these spatial and temporal gaps by providing global, asset-level estimates of cement-related emissions on a monthly basis. Using satellite-derived thermal anomaly data, we infer activity levels at clinker-producing facilities identified in Global Energy Monitor's Global Cement and Concrete Tracker (GEM, 2026). This approach allows for consistent, near-real-time monitoring of cement production and associated emissions across regions where traditional data sources are limited or unavailable.

Unlike steel and other carbon-intensive sectors, the majority of cement emissions are process-related, stemming from limestone calcination rather than fuel combustion for heat generation. The cement industry therefore requires unique, targeted emissions reduction strategies. In this work, we propose a set of emission reduction solutions (ERSs) and provide a minimum of one suitable strategy out of nine suggested strategies for each asset in the dataset based on known production technology and process characteristics. We take into account conventional wet- or dry-kiln operations, use of alternative fuels, and clinker substitution practices. Based on these, the strategies considered include switching to alternative fuels, implementing carbon capture and storage (CCS), substituting clinker with supplementary materials such as slag or calcined clay, and decommissioning high-emission wet-kiln plants. Each strategy represents a pathway to reduce emissions, either by lowering process emissions from clinker production, reducing fuel-related emissions, or phasing out high-emission technologies.

#### 2. Materials and methods

Cement production emits CO2 from two main sources: process emissions from limestone calcination and combustion emissions from fossil fuels used to heat rotary kilns. Clinker production is by far the most emissions-intensive stage in the cement value chain and accounts for the majority of the sector's total CO2 output. A more detailed overview is provided in Section 9.1 and Figure 9.

Given the lack of asset-level emission data publicly available, a standardized 'bottom-up' approach is used to quantify the emissions. This process is characterized by first estimating production levels for each plant before applying an emission factor to generate emissions estimates. Emission factors are asset-specific, determined as a function of final product characteristics (clinker-to-cement ratio, cement color, type), plant production route (wet, dry, semi-dry), and the use of emissions-reduction technologies (alternative fuels, supplementary cementitious materials, CCS/CCUS).

<img src="figures/figure1.png" width="610" />

**Figure 1** Flowchart of the methodology to calculate plant level emissions for global cement assets.

#### 2.1. Materials

#### 2.1.1. Asset inventory dataset

Cement production consists of three steps: first limestone is mixed with other materials, then the mixture is heated to produce clinker, and finally this clinker is ground together with other ingredients to produce cement. The final grinding process can happen in integrated facilities where clinker is also produced, or in independent grinding facilities closer to the end market. Global Energy Monitor provides facility-level information such as GPS coordinates, owner, capacity, age, product, and technology type for integrated, clinker-only, and grinding plant types. In this work, we estimate emissions for clinker-producing assets only. In total there are 2,494 integrated cement plants across 142 countries. We manually validated the locations of all the plants using geolocation data from Google Maps API (2025) and OpenStreetMap (2025).

Figure 2 shows the global distribution of integrated cement plants. China accounts for around half of global production, followed by India at 10% (USGS, 2026a).

<img src="figures/figure2.png" width="610" />

**Figure 2** Global map showing integrated cement facilities. Countries included in cement emissions monitoring are shaded. Assets that are monitored with satellites are shown in blue. The circle size represents plant production capacity, with reference scales shown at the top of the figure for 1,200 and 6,000 thousand tonnes per annum (ktpa).

#### 2.1.2. Remote sensing datasets

Satellite-derived production estimates make use of multispectral imagery from two different collections:

-   The European Space Agency (ESA) Copernicus Sentinel mission with a resolution of 20 m and a combined 5-day equator revisit with two satellites:

-   Sentinel 2A: with imagery available since 2015 (ESA, 2025).

-   Sentinel 2B: with imagery available since 2017 (ESA, 2025).

Both Sentinel-2 satellites have a MultiSpectral Instrument (MSI) that can measure wavelengths from \~443 - \~2190 nm (blue to shortwave infrared (SWIR)) at 10-60 m spatial resolutions.

-   The U.S. Geological Survey (USGS) and National Aeronautics and Space Administration (NASA) Landsat program with a resolution of 30 m and a combined 8-day revisit:

-   Landsat-8: with imagery available since 2013 (NASA and USGS 2025a).

-   Landsat-9: with historical images available from 2021 (NASA and USGS 2025b).

Both Landsat-8 and Landsat-9 have an Operational Land Imager (OLI) that can measure wavelengths from \~435 to \~2,294 nm (blue to shortwave infrared) at 30 m spatial resolution.

All satellite datasets were sourced and processed using Google Earth Engine (Google Earth Engine 2025a, 2025b, 2025c). From each satellite dataset, we relied on the surface reflectance products and computed the ratio of the difference between two SWIR bands and NIR bands of each satellite. This is based on the study to detect high-temperature anomalies from Sentinel-2 MSI images where a tri-spectral thermal anomaly index (TAI) that jointly uses the two high-temperature sensitive SWIR bands and the high-temperature-insensitive NIR band to enhance High Temperature Anomalies (Liu et al., 2021). For the respective satellite collections, we infer the TAI through the following equations:

-   Sentinel-2A/B: $`TAI\  = \ \frac{(B12\  - \ B11)}{(B8a)}`$

-   Landsat-8/9: $`TAI\  = \ \frac{(B7\  - \ B6)}{(B5)}`$

<img src="figures/figure3.png" width="610" />

**Figure 3** Left: high resolution image of Lafarge’s cement plant in Port-la-nouvelle, France with a manually labeled rotary kiln (yellow shaded rectangle). Right: Sentinel-2 image showing the thermal anomaly over the rotary kiln and surrounding features (red for hot pixel) during 2023. Source: Modified Copernicus data and GEM GCCT.

Where B\# refers to the band number for the specific satellite. This ratio was used to identify thermal anomalies within the temperature range of industrial processes, while eliminating most of the noise from reflectance interference. Pixel values between the Sentinel 2A/B MSI and Landsat OLI were harmonized using NASA’s band pass adjustments allowing the two image collections to be used as if they were a single collection (NASA, 2023). The harmonized dataset ensured higher revisit for time-series surface applications. Partial images (coverage of the plant’s boundaries less than 80%) and cloudy images (more than 20% clouds) were excluded. <span class="underline">Figure</span> 3 shows an example of a cement plant with identified hotspots over a rotary kiln.

#### 2.1.3. Production datasets

Aggregated national cement production used in our models is primarily sourced from USGS (2026a) on an annual basis. These are used to form country-level totals (Section 2.2.4).

#### 2.1.4. Emissions factors dataset

Emissions factors are combined from multiple sources. See Section 2.2.3 for more details.

#### 2.2. Methods

#### 2.2.1. Emissions scope

Emissions were estimated for the direct and indirect CO<sub>2</sub> released during the manufacture of cement. Direct emissions comprise process emissions from the calcination of limestone in the kiln, and emissions from the combustion of fuels used to reach the temperatures required in the kiln. Indirect emissions arise from electricity consumed by the plant. Emissions vary by production route (wet, semi-dry, dry), by product characteristics such as cement type and color, and by the emissions-reduction technologies in place at the asset. Emissions are estimated for clinker-producing assets only.

#### 2.2.2. Production methodology

Two approaches were used to estimate asset-level production. As a priority, satellite-derived production estimates are used whenever a facility releases enough heat to be captured by satellite imagery (Zhou et al., 2018; Marchese et al., 2019; Liangrocapart, Khetkeeree and Petchthaweetham, 2020). This is the case for clinker-producing plants, as clinkerization occurs at high temperatures of around 1,400 °C.

Our methodology scours satellite imagery for heat signatures from operating cement plants. Each clinker-producing kiln, once identified, is outlined with a hand-drawn polygon, as shown in Figure 4.

<img src="figures/figure4.png" width="320" />

**Figure 4** Zooming in on an integrated cement plant in Kota Padang, Sumatera Barat, Indonesia. The 5 kilns have been hand labeled (yellow shaded rectangles).

Each month, the mean TAI across all usable images of a plant is converted to a utilization rate using a piecewise-linear curve. The curve rises steeply from zero for TAI below 0.02, flattens between 0.05 and 0.45, and is capped at a utilization of 0.91. Production is the utilization rate multiplied by monthly plant capacity. The breakpoints and slopes were fitted by matching aggregated plant production to reported monthly clinker production by district in the United States (USGS, 2026b) and cement production by province in China (NBSC, 2026). A month with only one cloud-free image showing no heat is not treated as idle. Where a plant has no usable image in a month, its most recent TAI is carried forward. For plants without usable hotspot signals, we estimate production using a regional or global average of satellite-derived utilization rates.

The satellite-based approach is useful for detecting fluctuations in plant activity, such as capturing whether a plant has been switched off. However, assets may be excluded from satellite monitoring due to a small signal-to-noise ratio, which makes it difficult to distinguish production from background fluctuations. Other sources of complication can be the occasional presence of strong reflections from a priori cold elements, or the fact that kilns may be placed inside a building and hidden by a roof. A representative example is shown in Section 9.2, Figure 10.

#### 2.2.3. Emissions methodology

In line with IPCC guidelines, clinker data is our primary source for estimating process emissions from cement production. This is because CO<sub>2</sub> is released during the calcination process that outputs clinker - not during the blending or grinding stages of cement production. The proportion of clinker contained in each tonne of cement varies according to a number of product and plant characteristics provided by GEM (2026). Where GEM reports a clinker substitution band for a grey-cement plant, the clinker-to-cement ratio is taken as one minus the band midpoint, giving 0.87, 0.72, 0.57, and 0.45 for the 6–20%, 21–35%, 36–50%, and &gt;50% bands respectively; otherwise the ratios in Table 1, sourced from IEA (2022) and Cembureau (2025), are applied according to cement type and color. A global clinker emission factor of 0.507 tCO₂/t-clinker (IPCC, 2006a) is then applied to the estimated clinker required by each plant, and reduced where carbon capture or clay calcination is present.

Fuel emissions vary by production route and, within the dry route, by kiln configuration: plants with both a precalciner and a preheater are assigned a lower thermal energy requirement than those with a preheater only or with neither, with the corresponding emission factors derived from reported thermal energy intensities (Worrell, Galitsky and Price, 2008) and IPCC fuel carbon contents (IPCC, 2006a). Where GEM does not confirm both kiln characteristics, the route-level factor is applied. White cement is treated as 70% more energy-intensive than grey (Cembureau, 2025), and alternative fuel use reduces fuel emissions (MPP, 2023).

Indirect emissions are estimated from an electricity use factor of 0.091 MWh/t-cement (IEA, 2018), reduced by 20% where waste heat recovery is reported (Sahoo, Kumar and Samsher, 2022), multiplied by the national or regional grid intensity (Ember, 2025). The full set of factors and adjustments is given in Tables 2 and 3.

| **Table 1** Factors impacting the clinker-to-cement ratio |                    |                                               |                  |
|-----------------------------------------------------------|--------------------|-----------------------------------------------|------------------|
| **Characteristic**                                        | **Category**       | **Clinker percentage**                        | **Source**       |
| White                                                     | Cement color       | 97                                            | Cembureau (2025) |
| Ordinary Portland Cement                                  | Cement type        | 95                                            | Cembureau (2025) |
| Blended                                                   | Cement type        | 71                                            | IEA (2022)       |
| Blast-furnace slag                                        | Cement type        | 50                                            | Cembureau (2025) |
| China                                                     | Regional variation | Reduced by up to 15% depending on cement type | IEA (2018)       |

| **Table 2** Product and plant characteristics impacting the direct and indirect emissions factor |                                |                     |                            |                                     |                                        |
|--------------------------------------------------------------------------------------------------|--------------------------------|---------------------|----------------------------|-------------------------------------|----------------------------------------|
| **Product/Plant characteristics**                                                                | **Emissions factors**          | **Source**          |                            |                                     |                                        |
| **Characteristic**                                                                               | **Category**                   | **Fuel or process** | **Absolute or adjustment** | **Value**                           |                                        |
| White                                                                                            | Cement color                   | Fuel                | Adjustment                 | 70% more energy intensive than grey | Cembureau (2025)                       |
| Dry - unconfirmed configuration                                                                  | Production route               | Fuel                | Absolute                   | 0.32 tCO2/t-clinker                 | IEA (2022), IPCC 2006 Vol. 2 Ch. 2     |
| Dry - Precalciner + preheater                                                                    | Production route               | Fuel                | Absolute                   | 0.31 tCO2/t-clinker                 | IPCC 2006 Vol. 2 Ch. 2, Worrell (2008) |
| Dry - Preheater                                                                                  | Production route               | Fuel                | Absolute                   | 0.33 tCO2/t-clinker                 | IPCC 2006 Vol. 2 Ch. 2, Worrell (2008) |
| Dry - Neither                                                                                    | Production route               | Fuel                | Absolute                   | 0.49 tCO2/t-clinker                 | IPCC 2006 Vol. 2 Ch. 2, Worrell (2008) |
| Semidry                                                                                          | Production route               | Fuel                | Absolute                   | 0.39 tCO2/t-clinker                 | ECRA (2016)                            |
| Wet                                                                                              | Production route               | Fuel                | Absolute                   | 0.59 tCO2/t-clinker                 | Gao H, Wang D, Zhao Z, Dang P. (2024)  |
| Carbon Capture and Storage (CCS)                                                                 | Emissions-reduction technology | Process             | Adjustment                 | 70% capture rate                    | CaptureMap (2022)                      |
| Alternative fuels                                                                                | Emissions-reduction technology | Fuel                | Adjustment                 | 35% emissions reduction             | MPP (2023)                             |
| Clay calcination                                                                                 | Emissions-reduction technology | Process             | Adjustment                 | 40% emissions reduction             | MPP (2023)                             |
| Waste heat recovery                                                                              | Emissions-reduction technology | Electricity         | Adjustment                 | 20% reduction in electricity use    | Sahoo, Kumar and Samsher (2022)        |

<table><thead><tr class="header"><th><strong>Table 3</strong> Emission types and associated emissions factors</th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr class="odd"><td><strong>Type of emissions</strong></td><td><strong>Direct emissions</strong></td><td><strong>Indirect emissions</strong></td><td></td><td></td></tr><tr class="even"><td></td><td><em><strong>Process emissions</strong></em></td><td><em><strong>Fuel emissions</strong></em></td><td>External power consumption from the national grid</td><td></td></tr><tr class="odd"><td></td><td><p>Limestone calcination</p><p>CaCO<sub>3</sub> → CaO + CO<sub>2</sub></p><p>Cement kiln dust</p></td><td>Kiln fuel emissions</td><td>Non-kiln fuel emissions</td><td></td></tr><tr class="even"><td></td><td></td><td><p>Heat consumption of kilns</p><p>Drying of fuels</p><p>Drying of raw materials</p></td><td>On-site power generation</td><td></td></tr><tr class="odd"><td></td><td>0.091 tCO2/t-clinker (with CCS and clay calcination)-0.507 tCO2/t-clinker (unabated)</td><td>0.20-1.0 tCO2/t-clinker (see Table 2)</td><td>0.091 MWh/t-cement (or 0.073 MWh/t-cement where waste heat recovery is present) multiplied by national or regional grid intensity</td><td></td></tr><tr class="even"><td><em><strong>Sources</strong></em></td><td><em>IPCC (clinker emission factor)<br />
CaptureMap 2022 (CCS adjustment)</em></td><td><em>MPP 2023 (alternative fuels adjustment), McKinsey (2020), Ecofys (2009) and Worrell (2008) (direct fuel emissions), Cembureau 2025 (white cement color adjustment)</em></td><td><em>IEA 2018 (electricity use factor), Ember 2025 (grid intensities) and Sahoo, Kumar and Samsher (2022).</em></td><td></td></tr></tbody></table>

#### 2.2.4. Country-level emissions

Country-level emissions are reported monthly from January 2015 and are not a sum of asset-level emissions. For each country, annual cement production is taken from USGS (2026a), using the most recent edition for each year. Missing years are filled with the nearest reported year, and production is split across months in proportion to the number of days. Where a country has no USGS production at all, the sum of our asset-level production estimates is used instead; the two sources are never added together.

Production is multiplied by a country emissions factor, calculated each month as total asset-level emissions divided by total asset-level production for that country (Section 2.2.3). Months without an asset-derived factor take the nearest available month for that country. Countries with no monitored assets take the global production-weighted factor for that month.

In 2024, 141 countries used USGS production with their own asset-derived emissions factor (2,493 MtCO₂), 19 countries without monitored assets used USGS production with the global factor (7 MtCO₂), and one country (Somalia) used the asset sum (&lt;0.1 MtCO₂). The remaining 90 territories have no reported production and are reported as zero. Asset-level emissions account for 83% of the published national total (2.07 of 2.50 GtCO₂). Because the national total uses USGS production for every month, monthly country totals do not vary with satellite-observed activity, and in some country-months the asset sum exceeds the national total.

###

#### 2.3. Emissions reduction solutions

To integrate each emissions reduction solutions (ERSs) strategy into facility-level emissions estimates, eligible assets were identified based on their production technology, alternative fuel use, clinker composition, and CCS application using Global Energy Monitor's Global Cement and Concrete Tracker (GEM, 2026). Emissions were then adjusted according to either literature-based emission factors or assumed percentage reductions, and facility-level CO<sub>2</sub> emissions were recalculated under each strategy scenario, as shown in Table 9. The full set of strategies is defined below.

#### 2.3.1. Strategy definitions

**Strategy 0: Continue current operation (near-zero baseline)** - A theoretical baseline in which both fuel-related and calcination emissions are fully eliminated through complete decarbonization of the production process. In practice, however, no cement asset in the database has yet achieved this condition.

**Strategy 1: Alternative fuel** - Applied to assets currently using conventional fossil fuels. We assumed that alternative fuels (e.g. biomass, industrial by-products, or waste-derived fuels) could fully replace fossil fuels, thereby reducing fuel-related CO₂ emissions, which account for \~40% of total plant emissions (World Economic Forum, 2024; IEA Greenhouse Gas R&D Programme, 2008). Emissions reductions were applied proportionally, reflecting real-world examples of European cement plants operating near 100% on alternative fuels, such as the Allmendingen plant in Germany and the Rugby plant in the UK (Cembureau, 2018; Lloyd-Perks, 2024). Applied as a secondary approach where a combined mitigation strategy (e.g. CCS + alternative fuels) was prioritized, and as a primary approach for assets where one of these measures had already been implemented.

**Strategy 2: Carbon capture and storage (CCS)** - Applied to assets capable of retrofitting CCS. CCS can capture almost the entire CO₂ output of a cement plant, including both process and fuel-related emissions (Emanuelsson, 2025). While the technology holds significant mitigation potential, it has not yet been widely deployed. The Norcem plant in Brevik, Norway provides an example of large-scale implementation (Cavalett, 2021), with further projects under development, including Ketton in the UK and Lengfurt in Germany (Linde Engineering, 2024; Global Cement, 2024a). Applied as a secondary approach in combined-mitigation cases, and as a primary approach where one of these measures had already been implemented.

**Strategy 3: Clinker substitution with GGBS** - Applied to assets capable of partially replacing clinker with ground granulated blast-furnace slag (GGBS) during grinding. The resulting reduction in both process and fuel-related emissions was applied proportionally to the share of clinker substituted, up to \~70% depending on substitution rate and plant technology (Yue and Zhu, 2025). A well-established practice - for example, the Heidelberg Speed Slag cement plant in the US (Heidelberg Materials, 2024; Global Cement, 2024b) - and particularly applicable in countries with high steel production, such as China, where GGBS is readily available as a by-product.

**Strategy 4: Clinker substitution with calcined clay (LC3)** - Applied to assets that can partially replace clinker with calcined clay during grinding. Reductions in emission factors were applied based on the substitution rate, up to \~30% (MPP, 2023; Lacina, 2024). Adoption is growing in regions with abundant clay resources (LC3, 2022) but remains limited by local clay availability and calcination infrastructure.

**Strategy 5: Shut down wet-process plants** - Applied to older, highly energy-intensive wet-kiln assets (IEA, 2018). Emissions from these plants were set to zero to reflect a theoretical retirement scenario, aligned with the efficiency gap between wet kilns and more efficient kilns, and with the ongoing transition of cement production toward efficient dry-kiln technologies (Miller, 2021).

**Strategy 6: Alternative fuel + CCS** - Applied to eligible assets capable of both substituting fossil fuels with alternative fuels and retrofitting CCS. The resulting emission-factor reductions reflect near-complete elimination of both fuel- and process-related CO₂ emissions. Projects combining the two approaches are under development at several cement plants, such as Ketton in the UK and Lengfurt in Germany (GEM, 2026). Applied as a high-priority option for high-production assets, where the potential for absolute emissions reductions is greatest.

**Strategy 7: Clinker substitution with GGBS + alternative fuel** - Applied to assets capable of both GGBS substitution and alternative fuel use. CO₂ emissions were reduced proportionally based on substitution rate and fuel replacement, with total reductions up to \~80%. Primarily applied to lower-production facilities and in countries where GGBS is readily available as a by-product of steel production.

**Strategy 8: Clinker substitution with calcined clay + alternative fuel** - Applied to assets that can implement both calcined-clay substitution and alternative fuel use. Emissions reductions were applied proportionally, with typical reductions of 50–60%, reflecting both emerging adoption and technical feasibility. Targeted at lower-production facilities where suitable clay resources are accessible.

#### 2.3.2. Verifying modeled emissions reductions

Verification of the modeled reductions varies depending on the strategy and the type of change assumed. For alternative fuel strategies (Strategy 1), implementation could in principle be monitored through company reports, trade statistics, and updates to facility fuel-usage data in the Global Cement and Concrete Tracker (GEM, 2026), although these sources may not provide real-time confirmation. CCS retrofits (Strategy 2) are not directly observable from satellite data, but can be tracked through company disclosures, pilot-project announcements, and regulatory filings. Clinker substitution strategies (Strategy 3 – GGBS; Strategy 4 – calcined clay) could be partially verified through satellite monitoring of lower clinker production, combined with company reports on feedstock use. In contrast, the shutdown of wet-process plants (Strategy 5) can be verified more robustly through satellite-based activity monitoring, which allows direct observation of whether a facility has ceased operation. Finally, combined strategies (Strategies 6–8) could be partially confirmed by combining the approaches above.

#### 2.4. Coverage

Based on 2024 data, asset-level emissions estimates accounted for approximately 86% (2.07 Gt-CO<sub>2</sub>) of estimated global direct sector emissions of 2.4 Gt-CO<sub>2</sub>, comprising \~1.5 Gt-CO<sub>2</sub> from limestone calcination and \~0.9 Gt-CO<sub>2</sub> from kiln fuel combustion (Andrew, 2025). Asset-level production estimates of 3.19 Gt of cement represent around 82% of the USGS world total of 3.9 Gt for the same year (USGS, 2026a). Across the full monitoring period, 85% of assets (2,109 of 2,494) were satellite-derived, either monitored directly or extrapolated from their own satellite-derived utilization rates; these assets contributed 88% of total asset-level emissions and 89% of estimated production. The remainder was estimated using national or global average utilization rates.

#### 3. Validation

#### 3.1. Thermal Anomaly Index and activity

Figure 5 illustrates the relationship between satellite-derived Thermal Anomaly Index (TAI) and the corresponding emissions for a cement plant in Spain. The data demonstrates that estimated emissions (based on production levels) align closely with fluctuations in TAI. Months in which few or no hotspots are detected translate directly into low estimated production and correspondingly low emissions. The clearest examples are March and September 2024, where TAI falls and estimated emissions drop to roughly a quarter and a half of the plant's typical monthly output. Figure 5 illustrates how the model responds to observed activity, and Figure 6 shows the hotspots detected at the same plant in August 2024.

<img src="figures/figure5.png" width="610" alt="Chart" />

**Figure 5** Satellite-based Thermal Anomaly Index (TAI; blue solid line) and estimated emissions (red solid line) at Valderrivas cement plant in Cantabria, Spain during January 2021 - September 2024.

<img src="figures/figure6.png" width="376" />

**Figure 6** Satellite-detected hotspots over Valderrivas cement plant in Cantabria, Spain during August 2024.

#### 3.2. Emission factor benchmarking

Modeled emission factors were benchmarked against two independent sources. At the global level, our production-weighted total direct emission factor of 0.65 tCO₂ per tonne of cement for 2024 compares with 0.62 tCO₂/t implied by dividing the Global Carbon Project's cement emissions estimate by USGS world cement production for the same year, a difference of 5% (Andrew, 2025; USGS, 2026a).

At the country level, modeled direct emissions were compared with verified emissions reported under activity code 29 (production of cement clinker) of the EU Emissions Trading System, which covers both process and combustion emissions at clinker-producing installations and therefore matches our emissions boundary (EEA, 2026). The comparison was restricted to the fourteen European countries with four or more monitored assets, since in countries served by one or two plants a single facility determines national output and small errors in plant-level activity produce large proportional differences. Across these countries, modeled and verified emissions are closely correlated (r = 0.957; Figure 7). Residual differences reflect country-specific variation in cement composition and product mix.

<img src="figures/figure7.png" width="455" />

**Figure 7** Modeled direct CO₂ emissions against verified emissions reported under EU ETS activity code 29 (production of cement clinker) for 2024, for the fourteen European countries with four or more monitored assets. The dashed line indicates exact agreement and the shaded band ±20% of verified emissions.

#### 4. Results

#### 4.1. Top emitters

Country totals in Table 4 are national totals as described in Section 2.2.4, not sums of the plants in Table 5. Tables 4 and 5 show the biggest producers and emitters in the cement industry at country and plant level, respectively. China accounts for almost half of the global cement emissions.

| **Table 4** Top 10 emitters in the cement sector in 2025 - by country (direct emissions only, national total; see Section 2.2.4) |                                                 |
|----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| **Country**                                                                                                                      | **CO<sub>2</sub> emissions (MtCO<sub>2</sub>)** |
| China                                                                                                                            | 1,087                                           |
| India                                                                                                                            | 298                                             |
| Turkey                                                                                                                           | 63                                              |
| Vietnam                                                                                                                          | 59                                              |
| Iran                                                                                                                             | 53                                              |
| Russia                                                                                                                           | 50                                              |
| USA                                                                                                                              | 49                                              |
| Egypt                                                                                                                            | 46                                              |
| Brazil                                                                                                                           | 40                                              |
| Saudi Arabia                                                                                                                     | 40                                              |

<table><thead><tr class="header"><th><strong>Table 5</strong> Top 10 emitting cement plants in 2025 (direct emissions only).</th><th></th><th></th><th></th></tr></thead><tbody><tr class="odd"><td><strong>Plant name</strong></td><td><strong>Country</strong></td><td><strong>Plant capacity (Mt)</strong></td><td><p><strong>CO<sub>2</sub> emissions</strong></p><p><strong>(MtCO<sub>2</sub>)</strong></p></td></tr><tr class="even"><td>Jinfeng Cement Changzhou Cement Plant</td><td>China</td><td>20.0</td><td>11.4</td></tr><tr class="odd"><td>Wonder Cement Phachar Aheeran Cement Plant</td><td>India</td><td>21.5</td><td>10.3</td></tr><tr class="even"><td>National Company for Cement in Beni Suef New Beni Suef Cement Plant</td><td>Egypt</td><td>13.3</td><td>8.4</td></tr><tr class="odd"><td>UltraTech Cement Maihar Cement Plant</td><td>India</td><td>12.0</td><td>6.7</td></tr><tr class="even"><td>Sichuan Esheng Cement Group Leshan Cement Plant</td><td>China</td><td>12.0</td><td>6.6</td></tr><tr class="odd"><td>Sungshin Cement Danyang Cement Plant</td><td>S Korea</td><td>11.3</td><td>6.4</td></tr><tr class="even"><td>Fujian Yong’an Jianfu Yongan Cement Plant</td><td>China</td><td>12.4</td><td>6.4</td></tr><tr class="odd"><td>China Resources Cement (Fengkai) Zhaoqing Cement Plant</td><td>China</td><td>12.0</td><td>6.0</td></tr><tr class="even"><td>Sampyo Cement Samcheok Cement Plant</td><td>S Korea</td><td>10.0</td><td>5.5</td></tr><tr class="odd"><td>Sichuan Xingchuancheng Cement Neijiang Cement Plant</td><td>China</td><td>12.0</td><td>5.4</td></tr></tbody></table>

#### 4.2. Emissions reduction solutions results

Applying these strategies to the cement assets demonstrates the significant mitigation potential of technological and operational shifts. Figure 8 presents the change in direct emission factors, separated by source - emissions from clinker calcination and emissions from fuel combustion - before and after strategy implementation.

For current assets mostly using conventional fossil fuels and standard clinker production, total CO<sub>2</sub> emission factors averaged around 0.42 tCO₂/t-cement from the calcination process and contributed an additional \~0.25 tCO₂/t-cement from fuel combustion. Application of alternative fuels (Strategy 1) reduces fuel-related emissions close to zero, while carbon capture and storage (CCS, Strategy 2) can reduce nearly all calcination emissions, bringing the overall emission factor down to \~0.03 tCO₂/t-cement for eligible facilities (Emanuelsson, 2025).

Strategies focused on clinker substitution further complement these reductions. Partial replacement of clinker with granulated blast-furnace slag (GGBS, Strategy 3) or calcined clay (LC3, Strategy 4) can reduce total plant emissions by up to \~70% and \~30% respectively, depending on substitution rates and local material availability (Yue and Zhu, 2025).

Shutdown of wet-process plants that are emission intensive (Strategy 5) immediately stops all emissions. While not necessarily practical due to shifting production to other assets, along with other economic and labor impacts, we provide it as a possibility to consider.

Lastly, combined strategies, such as GGBS or calcined-clay substitution paired with alternative fuels (Strategies 7 and 8), allow reductions of 50–80%, highlighting the synergistic effect of targeting both process- and fuel-related emissions.

Overall, these results show that near-zero emissions in cement production is potentially possible when high-producing assets adopt CCS alongside alternative fuels, while widespread adoption of clinker substitution and fuel switching across smaller facilities can contribute substantially to global decarbonization.

<img src="figures/figure8.png" width="316" />

**Figure 8** Average direct emission factors (tCO₂ per tonne of cement) from calcination and fuel combustion before (yellow bars) and after (blue bars) the application of emission reduction strategies across cement assets worldwide.

#### 5. Discussion

#### 5.1. Emissions estimates

The satellite-derived Thermal Anomaly Index (TAI) offers a promising approach for estimating cement production at the asset level on a monthly basis. By calibrating TAI against plant production data and combining it with clinker-based process parameters, it is possible to estimate direct CO<sub>2</sub> emissions from both calcination and fuel combustion. This approach enables temporally resolved, asset-specific emission estimates that go beyond traditional annual reporting, particularly for regions or facilities with limited disclosure.

The accuracy of these estimates depends on asset-specific characteristics, including production route (wet, semi-dry, dry), clinker-to-cement ratios, fuel type, and the use of emissions-reduction technologies such as CCS or alternative fuels. For example, conventional clinker production without mitigation results in \~0.42 tCO₂/t-cement from calcination and \~0.25 tCO₂/t-cement from fuel combustion, while the adoption of CCS or alternative fuels can greatly reduce asset emissions. Differences in cement type, production technology, and regional energy intensity further influence direct emission factors, highlighting the importance of integrating plant-level characteristics with TAI-based monitoring. Overall, combining satellite observations with process-based emission modeling provides a scalable framework for tracking cement-sector emissions and evaluating the potential of mitigation strategies across global assets.

#### 5.2. Applying the reduction strategies

Cement emissions are primarily driven by the chemical process of clinker production and the fuel used to heat kilns to high temperatures. Process emissions from calcination are largely unavoidable without technological intervention, while fuel emissions can be reduced through substitution or decarbonization. Applying these strategies to cement production routes demonstrates significant mitigation potential. The most promising strategies fall into three themes: reducing fuel-related emissions and capturing CO<sub>2</sub>, substituting clinker and improving process efficiency, and integrating multiple strategies.

#### 5.2.1. Fuel-related emissions and CO<sub>2</sub> capture

Strategy 1 (alternative fuel) shows substantial potential, eliminating fuel-related emissions, which account for \~40% of total plant emissions (World Economic Forum, 2024; IEA Greenhouse Gas R&D Programme, 2008). Many European plants already operate near 100% on alternative fuels (Allmendingen, Germany; Rugby, UK), demonstrating technical feasibility. This strategy is particularly effective as a primary pathway for assets that have already implemented decarbonization measures targeting calcination emissions. Limitations include variability in fuel quality, availability, and retrofitting costs, which require supportive policy and incentives to accelerate adoption.

Strategy 2 (carbon capture and storage, CCS) has the potential to capture almost the entire CO2 output of a cement plant, including both process and fuel-related emissions (Emanuelsson, 2025). While full deployment could theoretically reduce plant emissions close to zero, the technology remains in the early stages of commercial application. High capital and operational costs, infrastructure requirements, and technical complexity constrain broader deployment. Demonstration projects such as the Norcem plant in Brevik, Norway provide examples of large-scale implementation, but policy support, carbon pricing, and net-zero commitments will be critical for scaling CCS in the sector. This strategy is most relevant for high-production assets, where mitigation impact is maximized.

#### 5.2.2. Clinker substitution and process optimization

Strategies 3 and 4 (clinker substitution with GGBS or calcined clay) target process emissions by replacing a fraction of clinker with industrial by-products or low-carbon materials. GGBS substitution can reduce emissions by up to \~70% (Yue and Zhu, 2025) and is already widely adopted in regions with high steel production where slag is readily available (Heidelberg Speed Slag cement plant, US). Calcined-clay substitution offers reductions of up to \~30%, particularly suitable for regions with abundant clay resources. Both strategies are effective but are constrained by material availability, regional resource distribution, and potential quality considerations in cement performance.

Strategy 5 (shutdown of wet-process plants) immediately eliminates emissions from highly energy-intensive older facilities. While technically effective, its practical implementation depends on regulatory enforcement and on ensuring production is shifted to lower-emission assets rather than offset elsewhere. Economic and workforce impacts are additional considerations for policy planning.

#### 5.2.3. Combined strategies

Combined strategies (6–8) demonstrate the synergistic potential of integrating multiple approaches. Pairing alternative fuels with CCS (Strategy 6) can nearly eliminate both process- and fuel-related emissions, representing a high-priority option for high-production facilities. Similarly, combining clinker substitution with alternative fuels (Strategies 7 and 8) achieves reductions of 50–80%, depending on material availability and substitution rates. These combinations highlight pathways to substantial decarbonization, though scaling requires coordinated supply chains for low-carbon materials, reliable alternative fuels, and policy frameworks that support investment in CCS infrastructure.

Overall, this analysis indicates that near-zero emissions in cement production are potentially achievable through a combination of CCS, alternative fuels, and clinker substitution. However, sector-wide decarbonization is constrained by material availability, technological maturity, high costs, and the need for supportive regulatory and policy environments. Strategic deployment targeting high-production assets, alongside broader adoption of clinker substitution and fuel-switching technologies, will be essential to meet global net-zero ambitions.

#### 6. Conclusions

This work has shown that timely facility-level production and emissions can be obtained without the need to rely upon systematic and exhaustive company-published figures. Where possible, satellite data is directly used to estimate cement production, to which a facility-specific emission factor is applied to estimate emissions. Where satellite data is unavailable, regional utilization rates derived from our satellite estimates are used. In December 2024, 88% of total direct emissions were derived directly from satellite data.

Electricity-related emissions estimated in this work include emissions originating from the grinding process, which may or may not occur in the same facility where the clinker was produced. The GEM GCCT database contains grinding assets (where no clinker is produced) that contribute around a quarter of global cement capacity but are not included in the present work. Power-related grinding emissions are treated as if they were occurring in the facility that produced the clinker. This assumption allows us to cover a broader scope of emissions but does not create a large bias in the asset-level estimates, since grinding emissions contribute less than 5% of total cement production emissions (Shen et al., 2014). We intend to investigate the inclusion of grinding plants in future to more accurately distribute grinding emissions. However, this requires knowledge of clinker flows between plants, which has so far fallen outside the scope of this work.

Building on our production and emissions estimates, we have systematically applied a set of emissions reduction strategies to evaluate each asset's potential for decarbonization. Alternative fuels can nearly eliminate fuel-related emissions, while CCS offers the deepest overall reductions by targeting both process and combustion emissions, yet deployment is constrained by high costs, infrastructure, and policy uncertainty. Clinker substitution with slag or calcined clay provides significant near-term reductions but depends on regional material availability. Plant shutdowns and modernization to efficient dry processes can also deliver immediate cuts but raise socio-economic challenges. Overall, this analysis highlights that no single strategy can deliver full decarbonization of cement on its own. Instead, a portfolio of complementary measures - alternative fuels, clinker substitution, CCS, and targeted asset retirements - will be required, with the optimal mix depending on regional material availability, technology readiness, and policy support. Strong policy incentives and infrastructure investment will be critical to scale CCS and enable the sector to move toward net-zero emissions.

#### 7. Supplementary metadata section

Cement sector CO<sub>2</sub> emissions are reported for individual assets from January 2021. The emissions described here represent a subset of specific country-level emissions estimates from the Climate TRACE manufacturing sector. All data is freely available on the Climate TRACE website ([<span class="underline">https://climatetrace.org/</span>](https://climatetrace.org/)). A detailed description of what is available is described in Tables 6 - 8.

| **Table 6** Details on the asset metadata                                   |                                                                                                                                                                                                                              |
|-----------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **General Description**                                                     | **Definition**                                                                                                                                                                                                               |
| **Sector definition**                                                       | *Emissions from cement production*                                                                                                                                                                                           |
| **UNFCCC sector equivalent**                                                | *2.A.1 Cement production*                                                                                                                                                                                                    |
| **Temporal Coverage**                                                       | *2021 - present*                                                                                                                                                                                                             |
| **Temporal Resolution**                                                     | *Monthly*                                                                                                                                                                                                                    |
| **Data format**                                                             | *CSV*                                                                                                                                                                                                                        |
| **Coordinate Reference System**                                             | *None. ISO3 country code provided*                                                                                                                                                                                           |
| **Number of emitters available for download**                               | *2,241 integrated cement plants covering 138 countries*                                                                                                                                                                      |
| **What emission factors were used?**                                        | *Process- and plant- specific emission factors*                                                                                                                                                                              |
| **What is the difference between a “0” versus “NULL/none/nan” data field?** | *“0” values are for true non-existent emissions. If we know that the sector has emissions for that specific gas, but the gas was not modeled, this is represented by “NULL/none/nan”*                                        |
| **total\_CO2e\_100yrGWP and total\_CO2e\_20yrGWP conversions**              | *Climate TRACE uses IPCC AR6 CO<sub>2</sub>e GWPs. CO<sub>2</sub>e conversion guidelines are here: <span class="underline">https://www.ipcc.ch/report/ar6/wg1/downloads/report/IPCC\_AR6\_WGI\_FullReport\_small.pdf</span>* |

| **Table 7** Definition of the fields in asset dataset |                                                                                                                        |
|-------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| **Data attribute**                                    | **Definition**                                                                                                         |
| **sector**                                            | manufacturing                                                                                                          |
| **source\_sub-sector\_name**                          | cement                                                                                                                 |
| **source definition**                                 | emissions from cement production                                                                                       |
| **start\_date**                                       | start date for time period of emissions estimation (YYYY-MM-DD format)                                                 |
| **end\_date**                                         | end date for time period of emissions estimation (YYYY-MM-DD format)                                                   |
| **asset\_identifier**                                 | internal identifier                                                                                                    |
| **asset\_name**                                       | name of the facility                                                                                                   |
| **iso3\_country**                                     | ISO 3166-1 alpha-3 country code                                                                                        |
| **location**                                          | well-known text (WKT) point location                                                                                   |
| **type**                                              | manufacturing method                                                                                                   |
| **capacity**                                          | monthly plant capacity                                                                                                 |
| **capacity\_factor**                                  | utilization rate of cement plants                                                                                      |
| **activity**                                          | production estimates                                                                                                   |
| **CO2\_emissions\_factor**                            | direct emissions factor (t-CO<sub>2</sub>/t-cement)                                                                    |
| **CH4\_emissions\_factor**                            | not used; N/A                                                                                                          |
| **N2O\_emissions\_factor**                            | not used; N/A                                                                                                          |
| **CO2\_emissions**                                    | direct emissions estimates (t-CO<sub>2</sub>)                                                                          |
| **CH4\_emissions**                                    | not used; N/A                                                                                                          |
| **N2O\_emissions**                                    | not used; N/A                                                                                                          |
| **total\_CO2e\_100yrGWP**                             | 100 years global warming potential (t-CO<sub>2</sub>e)                                                                 |
| **total\_CO2e\_20yrGWP**                              | 20 years global warming potential (t-CO<sub>2</sub>e)                                                                  |
| **other1**                                            | direct and indirect emissions factor, includes - calcination, fuel use and electricity use (t-CO<sub>2</sub>/t-cement) |
| **other2**                                            | calcination emissions factor (t-CO<sub>2</sub>/t-cement)                                                               |
| **other3**                                            | fuel emissions factor (t-CO<sub>2</sub>/t-cement)                                                                      |
| **other4**                                            | electricity use factor (MWh/t-cement)                                                                                  |
| **other5**                                            | electricity use (MWh)                                                                                                  |
| **other6**                                            | grid emissions intensity (t-CO<sub>2</sub>/MWh)                                                                        |
| **other7**                                            | cement type                                                                                                            |
| **other8**                                            | emissions reduction technologies                                                                                       |
| **other9**                                            | clinker-to-cement ratio                                                                                                |
| **other10**                                           | model methodology (e.g. satellite\_monitored or extrapolation)                                                         |
| **model\_number**                                     | version of the model (e.g. 1, 2, …)                                                                                    |

<table><thead><tr class="header"><th><strong>Table 8</strong> Definition for confidence and uncertainty in asset data.</th><th></th><th></th></tr></thead><tbody><tr class="odd"><td><strong>Data attribute</strong></td><td><strong>Confidence Definition</strong></td><td><strong>Uncertainty Definition</strong></td></tr><tr class="even"><td><strong>type</strong></td><td><ul><li><blockquote><p><em>Very low:</em> Based on highly speculative or obsolete information. Very low level of confidence in the accuracy of asset classification.</p></blockquote></li><li><blockquote><p><em>Low:</em> Limited or somewhat outdated data. Low level of confidence in the classification's correctness.</p></blockquote></li><li><blockquote><p><em>Medium:</em> A mix of historical and more recent data. A medium level of confidence in its accuracy.</p></blockquote></li><li><blockquote><p><em>High:</em> Grounded in comprehensive and recent data. A high level of confidence in the precise classification of the asset.</p></blockquote></li><li><blockquote><p><em>Very high:</em> Extensive, up-to-date, and verified data. A very high level of confidence in the accurate and detailed identification of the asset.</p></blockquote></li></ul></td><td>Not used; N/A</td></tr><tr class="odd"><td><strong>capacity</strong></td><td><ul><li><blockquote><p><em>Very low:</em> Limited or outdated data, and significant uncertainties exist.</p></blockquote></li><li><blockquote><p><em>Low:</em> Outdated and/or incomplete data.</p></blockquote></li><li><blockquote><p><em>Medium:</em> A mix of historical and recent data.</p></blockquote></li><li><blockquote><p><em>High:</em> Comprehensive and recent data updates. High level of certainty.</p></blockquote></li><li><blockquote><p><em>Very high:</em> Extensive, up-to-date, and verified data. A very high level of certainty.</p></blockquote></li></ul></td><td>Not used; N/A</td></tr><tr class="even"><td><strong>capacity_factor</strong></td><td><ul><li><blockquote><p><em>Very low:</em> Data is sparse or highly unreliable. Considerable uncertainty in capacity factor estimations.</p></blockquote></li><li><blockquote><p><em>Low:</em> Moderate uncertainty in capacity factor calculations.</p></blockquote></li><li><blockquote><p><em>Medium:</em> Data is sufficiently available, though not comprehensive. No absolute accuracy in capacity factor estimations.</p></blockquote></li><li><blockquote><p><em>High:</em> High confidence in the accuracy of capacity factor calculations.</p></blockquote></li><li><blockquote><p><em>Very high:</em> Derived from thorough and validated data sources. Very high precision of capacity factor estimations.</p></blockquote></li></ul></td><td>Not used; N/A</td></tr><tr class="odd"><td><strong>activity</strong></td><td><ul><li><blockquote><p><em>Very low:</em> Largely speculative or based on outdated information. A very low level of confidence in activity assessments.</p></blockquote></li><li><blockquote><p><em>Low:</em> Limited or somewhat outdated sources. A low level of confidence in the activity assessments.</p></blockquote></li><li><blockquote><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in activity insights.</p></blockquote></li><li><blockquote><p><em>High:</em> Detailed and current operational data ensures a high level of confidence in the accuracy of activity assessments.</p></blockquote></li><li><blockquote><p><em>Very high:</em> Extensive, verified, and up-to-date data. A very high level of confidence in their accuracy.</p></blockquote></li></ul></td><td>±8 to 15 % of asset production</td></tr><tr class="even"><td><strong>CO2_emissions_factor</strong></td><td><ul><li><blockquote><p><em>Very low:</em> Highly uncertain due to insufficient or unreliable data.</p></blockquote></li><li><blockquote><p><em>Low:</em> Estimated from incomplete data. Low confidence level in its precision.</p></blockquote></li><li><blockquote><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in their accuracy.</p></blockquote></li><li><blockquote><p><em>High:</em> Derived from comprehensive and recent data. A high level of confidence in their precision.</p></blockquote></li><li><blockquote><p><em>Very high:</em> Based on extensive and validated data, providing a very high level of confidence in their precision.</p></blockquote></li></ul></td><td>±10% of asset (based on IPCC)</td></tr><tr class="odd"><td><strong>CH4_emissions_factor</strong></td><td>Not used; N/A</td><td>Not used; N/A</td></tr><tr class="even"><td><strong>N2O_emissions_factor</strong></td><td>Not used; N/A</td><td>Not used; N/A</td></tr><tr class="odd"><td><strong>CO2_emissions</strong></td><td><ul><li><blockquote><p><em>Very low:</em> Based on very rough estimations or outdated information. A very low level of confidence in its accuracy.</p></blockquote></li><li><blockquote><p><em>Low:</em> Estimated from incomplete data. Low confidence level in its precision.</p></blockquote></li><li><blockquote><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in their accuracy.</p></blockquote></li><li><blockquote><p><em>High:</em> Derived from comprehensive and recent data. A high level of confidence in their precision.</p></blockquote></li><li><blockquote><p><em>Very high:</em> Based on extensive and validated data, providing a very high level of confidence in their precision.</p></blockquote></li></ul></td><td>±13 to 20 % of asset emissions</td></tr><tr class="even"><td><strong>CH4_emissions</strong></td><td>Not used; N/A</td><td>Not used; N/A</td></tr><tr class="odd"><td><strong>N2O_emissions</strong></td><td>Not used; N/A</td><td>Not used; N/A</td></tr><tr class="even"><td><strong>total_CO2e_100yrGWP</strong></td><td><ul><li><blockquote><p><em>Very low:</em> Based on very rough estimations or outdated information. A very low level of confidence in its accuracy.</p></blockquote></li><li><blockquote><p><em>Low:</em> Estimated from incomplete data. Low confidence level in its precision.</p></blockquote></li><li><blockquote><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in their accuracy.</p></blockquote></li><li><blockquote><p><em>High:</em> Derived from comprehensive and recent data. A high level of confidence in their precision.</p></blockquote></li><li><blockquote><p><em>Very high:</em> Based on extensive and validated data, providing a very high level of confidence in their precision.</p></blockquote></li></ul></td><td>±13 to 20% of asset emissions</td></tr><tr class="odd"><td><strong>total_CO2e_20yrGWP</strong></td><td><ul><li><blockquote><p><em>Very low:</em> Based on very rough estimations or outdated information. A very low level of confidence in its accuracy.</p></blockquote></li><li><blockquote><p><em>Low:</em> Estimated from incomplete data. Low confidence level in its precision.</p></blockquote></li><li><blockquote><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in their accuracy.</p></blockquote></li><li><blockquote><p><em>High:</em> Derived from comprehensive and recent data. A high level of confidence in their precision.</p></blockquote></li><li><blockquote><p><em>Very high:</em> Based on extensive and validated data, providing a very high level of confidence in their precision.</p></blockquote></li></ul></td><td>±13 to 20% of asset emissions</td></tr></tbody></table>

| **Table 9** Emissions reduction solutions for the cement sector. |                                                       |                                                                                                                                       |               |                                       |                                           |
|------------------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|---------------|---------------------------------------|-------------------------------------------|
| **Strategy ID**                                                  | **strategy name**                                     | **strategy description**                                                                                                              | **mechanism** | **CO2 emissions factor new absolute** | **CO2 emissions factor new to old ratio** |
| 0                                                                | Continue current operation                            | plants with very low CO2 emission or without production can continue with their current operation                                     |               |                                       | 1                                         |
| 1                                                                | Alternative fuel                                      | Substitute fossil fuels for biomass, waste, electricity, or H₂ in kiln operations                                                     | resourcing    |                                       | 0.6                                       |
| 2                                                                | CCS                                                   | Install carbon capture and storage (CCS) system for process and/or fuel combustion emissions                                          | retrofit      | 0                                     |                                           |
| 3                                                                | Clinker substitution GGBS                             | Replace clinker with ground granulated blast furnace slag (GGBFS) as supplementary cementitious material (SCM)                        | resourcing    |                                       | 0.3                                       |
| 4                                                                | Clinker substitution calcined clay                    | Replace clinker with calcined clay (e.g., LC3) as SCM                                                                                 | resourcing    |                                       | 0.7                                       |
| 5                                                                | Shut down plant                                       | Shut down a plant and re-route production to another facility. Applied for wet plants with lower efficiency and high emission factor. | subtract      | 0                                     |                                           |
| 6                                                                | Alternative Fuel + CCS                                | This combines strategies 1 and 2                                                                                                      | retrofit      | 0                                     |                                           |
| 7                                                                | Clinker substitution GGBS + Alternative Fuel          | This combines strategies 1 and 3                                                                                                      | resourcing    |                                       | 0.18                                      |
| 8                                                                | Clinker substitution calcined clay + alternative fuel | This combines strategies 1 and 4                                                                                                      | resourcing    |                                       | 0.42                                      |

**Permissions and Use:** All Climate TRACE data is freely available under the Creative Commons Attribution 4.0 International Public License, unless otherwise noted below.

> **Data citation format:** Crane, V. and Ebri, G. (2026). Manufacturing and Industrial Processes sector – Cement Manufacturing Emissions. TransitionZero, UK, Climate TRACE Emissions Inventory. [<span class="underline">https://climatetrace.org</span>](https://climatetrace.org)

The above usage is not warranted to be error free and does not imply the expression of any opinion whatsoever on the part of Climate TRACE Coalition and its partner concerning the legal status of any country, area or territory or of its authorities, or concerning the delimitation of its borders.

**Disclaimer:** The emissions provided for this sector are our current best estimates of emissions, and we are committed to continually increasing the accuracy of the models on all levels. Please review our terms of use and the sector-specific methodology documentation before using the data. If you identify an error or would like to participate in our data validation process, please [<span class="underline">contact us</span>](mailto:coalition@climatetrace.org).

#### 8. References

1.  Construction Cost (2016) Cement Production Process, Cement Production Process. Available at: [<span class="underline">https://www.constructioncost.co/cement-production-process.html</span>](https://www.constructioncost.co/cement-production-process.html)

2.  Ember (2025) ‘Regional grid intensity retrieved from: Monthly Electricity Data’, Ember. Available at: [<span class="underline">https://ember-energy.org/data/monthly-electricity-data/</span>](https://ember-energy.org/data/monthly-electricity-data/)

3.  E-PRTR (2024) ‘Cement emissions data retrieved from: E-PRTR’, European Pollutant Release and Transfer Register. Available at: [<span class="underline">http://prtr.ec.europa.eu/</span>](http://prtr.ec.europa.eu/)

4.  ESA (2025) ‘Satellite images data retrieved from: Copernicus Sentinel-2 ESA’, European Space Agency Available at: [<span class="underline">https://www.esa.int/Applications/Observing\_the\_Earth/Copernicus/Sentinel-2</span>](https://www.esa.int/Applications/Observing_the_Earth/Copernicus/Sentinel-2)

5.  Google Earth Engine (2025a) Landsat 8 Datasets in Earth Engine, Google Developers. Available at: [<span class="underline">https://developers.google.com/earth-engine/datasets/catalog/landsat-8</span>](https://developers.google.com/earth-engine/datasets/catalog/landsat-8) .

6.  Google Earth Engine (2025b) Landsat 9 Datasets in Earth Engine, Google Developers. Available at: [<span class="underline">https://developers.google.com/earth-engine/datasets/catalog/landsat-9</span>](https://developers.google.com/earth-engine/datasets/catalog/landsat-9).

7.  Google Earth Engine (2025c) Sentinel-2 Datasets in Earth Engine, Google Developers. Available at: [<span class="underline">https://developers.google.com/earth-engine/datasets/catalog/sentinel-2</span>](https://developers.google.com/earth-engine/datasets/catalog/sentinel-2).

8.  Google Maps (2025) ‘Cement inventory data retrieved from: Google Maps’, Google. Available at: [<span class="underline">https://www.google.co.uk/maps</span>](https://www.google.co.uk/maps).

9.  IEA (2018) ‘Technology Roadmap - Low-Carbon Transition in the Cement Industry’, International Energy Agency, p. 66.

10. IEA (2022) Cement, International Energy Agency. Available at: [<span class="underline">https://www.iea.org/energy-system/industry/cement</span>](https://www.iea.org/energy-system/industry/cement) (Accessed: 1 September 2026).

11. Liangrocapart, S., Khetkeeree, S. and Petchthaweetham, B. (2020) ‘Thermal Anomaly Level Algorithm for Active Fire Mapping by Means of Sentinel-2 Data’, in 17th International Conference on Electrical Engineering/Electronics, Computer, Telecommunications and Information Technology (ECTI-CON), pp. 687–690. Available at: [<span class="underline">https://doi.org/10.1109/ECTI-CON49241.2020.9158262</span>](https://doi.org/10.1109/ECTI-CON49241.2020.9158262) .

12. Marchese, F. et al. (2019) ‘A Multi-Channel Algorithm for Mapping Volcanic Thermal Anomalies by Means of Sentinel-2 MSI and Landsat-8 OLI Data’, Remote Sensing, 11(23), p. 2876. Available at: [<span class="underline">https://doi.org/10.3390/rs11232876</span>](https://doi.org/10.3390/rs11232876).

13. NASA (2023) ‘Band Pass Adjustment’, National Aeronautics and Space Administration Available at: [<span class="underline">https://hls.gsfc.nasa.gov/algorithms/bandpass-adjustment/</span>](https://hls.gsfc.nasa.gov/algorithms/bandpass-adjustment/).

14. NASA and USGS (2025a) ‘Satellite images data retrieved from: Landsat-8 NASA/USGS’, National Aeronautics and Space Administration and United States Geological Survey. Available at: [<span class="underline">https://www.usgs.gov/landsat-missions/landsat-8</span>](https://www.usgs.gov/landsat-missions/landsat-8).

15. NASA and USGS (2025b) ‘Satellite images data retrieved from: Landsat-9 NASA/USGS’, National Aeronautics and Space Administration and United States Geological Survey. Available at: [<span class="underline">https://www.usgs.gov/landsat-missions/landsat-9</span>](https://www.usgs.gov/landsat-missions/landsat-9).

16. NBSC (2026) 'Chinese provincial monthly cement production retrieved from: NBSC', National Bureau of Statistics of China. Available at: [<span class="underline">https://data.stats.gov.cn/english/</span>](https://data.stats.gov.cn/english/) (Accessed: 1 September 2026).

17. OpenStreetMap (2025) ‘Cement inventory data retrieved from: OpenStreetMap’. OpenStreetMap. Available at: [<span class="underline">https://www.openstreetmap.org</span>](https://www.openstreetmap.org/) .

18. Global Energy Monitor (GEM), Global Cement and Concrete Tracker, July 2026 release. Available at: [<span class="underline">https://globalenergymonitor.org/projects/global-cement-and-concrete-tracker/</span>](https://globalenergymonitor.org/projects/global-cement-and-concrete-tracker/)

19. Shen, L. et al. (2014) ‘Factory-level measurements on CO2 emission factors of cement production in China’, Renewable and Sustainable Energy Reviews, 34, pp. 337–349. Available at: [<span class="underline">https://doi.org/10.1016/j.rser.2014.03.025</span>](https://doi.org/10.1016/j.rser.2014.03.025).

20. US EPA (2025) ‘Cement emissions data retrieved from: US EPA’, United States Environmental Protection Agency. Available at: [<span class="underline">https://www.epa.gov/</span>](https://www.epa.gov/).

21. USGS (2026a) Cement, in Mineral Commodity Summaries 2026, and Minerals Yearbook: Cement. United States Geological Survey. Used for reported annual national and world cement production. Available at: [<span class="underline">https://pubs.usgs.gov/periodicals/mcs2026/mcs2026-cement.pdf</span>](https://pubs.usgs.gov/periodicals/mcs2026/mcs2026-cement.pdf) (Accessed: 1 September 2026).

22. USGS (2026b) Mineral Industry Surveys: Cement, monthly. Table 4, clinker production by district. United States Geological Survey. Available at: [<span class="underline">https://www.usgs.gov/centers/national-minerals-information-center/cement-statistics-and-information</span>](https://www.usgs.gov/centers/national-minerals-information-center/cement-statistics-and-information) (Accessed: 1 September 2026).

23. Liu, Y., Zhi, W., Xu, B., Xu, W. and Wu, W. (2021) ‘Detecting high-temperature anomalies from Sentinel-2 MSI images’, [<span class="underline">ISPRS Journal of Photogrammetry and Remote Sensing</span>](https://www.sciencedirect.com/journal/isprs-journal-of-photogrammetry-and-remote-sensing), [<span class="underline">177</span>](https://www.sciencedirect.com/journal/isprs-journal-of-photogrammetry-and-remote-sensing/vol/177/suppl/C), p. 174-193, Available at: [<span class="underline">https://doi.org/10.1016/j.isprsjprs.2021.05.008</span>](https://doi.org/10.1016/j.isprsjprs.2021.05.008)

24. Zhou, Y. et al. (2018) ‘A Method for Monitoring Iron and Steel Factory Economic Activity Based on Satellites’, Sustainability, 10(6), p. 1935. Available at: [<span class="underline">https://doi.org/10.3390/su10061935</span>](https://doi.org/10.3390/su10061935).

25. MPP (2023) ‘Report: Making Net-Zero Concrete and Cement Possible,’ p. 12, Mission Possible partnership. Available at: [<span class="underline">https://www.missionpossiblepartnership.org/making-net-zero-concrete-and-cement-possible-report/</span>](https://www.missionpossiblepartnership.org/making-net-zero-concrete-and-cement-possible-report/)

26. Ecofys (2009) ‘Methodology for the free allocation of emission allowances in the EU ETS post 2012. Report on the project approach and general issues’. Available at: [<span class="underline">https://climate.ec.europa.eu/system/files/2016-11/bm\_study-project\_approach\_and\_general\_issues\_en.pdf</span>](https://climate.ec.europa.eu/system/files/2016-11/bm_study-project_approach_and_general_issues_en.pdf)

27. Cembureau (2025) ‘Product Standards’. Available at: [<span class="underline">https://cembureau.eu/about-our-industry/cement/\#:\~:text=CEM%20I%20Portland%20cement%20(%3E95,(20%2D64%25%20clinker)</span>](https://cembureau.eu/about-our-industry/cement/#:~:text=CEM%20I%20Portland%20cement%20(%3E95,(20%2D64%25%20clinker))

28. European Cement Research Academy (2016) [<span class="underline">https://cembureau.eu/media/oyahklgk/12042-ecra-energy-performance-cement-kilns-2017-10-15.pdf</span>](https://cembureau.eu/media/oyahklgk/12042-ecra-energy-performance-cement-kilns-2017-10-15.pdf)

29. Gao H, Wang D, Zhao Z, Dang P. (2024) Reducing carbon emissions in the cement industry using effective measures based on countries' characteristics. PLoS One. 2024 Nov 21;19(11):e0311859. doi: 10.1371/journal.pone.0311859. PMID: 39570832; PMCID: PMC11581325.

30. IPCC ‘CO2 Emissions From Cement Production’, Task Force on National Greenhouse Inventories. Available at: [<span class="underline">https://www.ipcc-nggip.iges.or.jp/public/gp/bgp/3\_1\_Cement\_Production.pdf</span>](https://www.ipcc-nggip.iges.or.jp/public/gp/bgp/3_1_Cement_Production.pdf)

31. McKinsey (2020) ‘Laying the foundation for zero-carbon cement’. Available at: [<span class="underline">https://www.mckinsey.com/industries/chemicals/our-insights/laying-the-foundation-for-zero-carbon-cement</span>](https://www.mckinsey.com/industries/chemicals/our-insights/laying-the-foundation-for-zero-carbon-cement)

32. CaptureMap (2022) ‘The Cement industry needs carbon capture for reducing emissions’. Available at: [<span class="underline">https://www.capturemap.no/carbon-capture-cement-industry/</span>](https://www.capturemap.no/carbon-capture-cement-industry/)

33. CEMBUREAU (2018) Cementing the European Green Deal: Reaching Climate Neutrality Along the Cement and Concrete Value Chain by 2050. CEMBUREAU, The European Cement Association. Available at: [<span class="underline">https://cembureau.eu/media/kuxd32gi/cembureau-2050-roadmap\_final-version\_web.pdf</span>](https://cembureau.eu/media/kuxd32gi/cembureau-2050-roadmap_final-version_web.pdf) (Accessed: 26 September 2025).

34. Lloyd-Perks, A. (2024) Cemex celebrates 1 million t of alternative fuel used at its Rugby Cement Plant. World Cement, 12 December 2024. Available at: [<span class="underline">https://www.worldcement.com/europe-cis/12122024/cemex-celebrates-1-million-t-of-alternative-fuel-used-at-its-rugby-cement-plant/</span>](https://www.worldcement.com/europe-cis/12122024/cemex-celebrates-1-million-t-of-alternative-fuel-used-at-its-rugby-cement-plant/) (Accessed: 26 September 2025).

35. Linde Engineering (2024) Groundbreaking Ceremony for one of the World's First Large-Scale Carbon Capture Projects in the Cement Industry. Press Release, 19 June. Available at: [<span class="underline">https://www.linde-engineering.com/news-and-events/press-releases/2024/groundbreaking-ceremony-for-one-of-the-world-s-first-large-scale-carbon-capture-projects-in-the-cement-industry</span>](https://www.linde-engineering.com/news-and-events/press-releases/2024/groundbreaking-ceremony-for-one-of-the-world-s-first-large-scale-carbon-capture-projects-in-the-cement-industry) (Accessed: 26 September 2025).

36. Global Cement (2024a) C-Capture launches new carbon capture trial at Heidelberg Materials' Ketton plant. Global Cement, 9 May. Available at: [<span class="underline">https://www.globalcement.com/news/item/17347-c-capture-launches-new-carbon-capture-trial-at-heidelberg-materials-ketton-plant</span>](https://www.globalcement.com/news/item/17347-c-capture-launches-new-carbon-capture-trial-at-heidelberg-materials-ketton-plant) (Accessed: 26 September 2025).

37. World Economic Forum (2024) Net-Zero Industry Tracker: 2024 Edition – Cement Industry. World Economic Forum. Available at: [<span class="underline">https://reports.weforum.org/docs/WEF\_Net\_Zero\_Industry\_Tracker\_2024\_Cement.pdf</span>](https://reports.weforum.org/docs/WEF_Net_Zero_Industry_Tracker_2024_Cement.pdf) (Accessed: 26 September 2025).

38. IEA Greenhouse Gas R&D Programme (2008) CO₂ Capture in the Cement Industry (Report No. 2008/3). IEA Greenhouse Gas R&D Programme. Available at: [<span class="underline">https://publications.ieaghg.org/technicalreports/2008-03%20CO2%20Capture%20in%20the%20Cement%20Industry.pdf</span>](https://publications.ieaghg.org/technicalreports/2008-03%20CO2%20Capture%20in%20the%20Cement%20Industry.pdf) (Accessed: 26 September 2025).

39. Cavalett, O., Cherubini, F. & Olsson, O. (2021) Deployment of bio-CCS in the cement sector: an overview of technology options and policy tools. IEA Bioenergy Technology Collaboration Programme. Available at: [<span class="underline">https://www.ieabioenergy.com/wp-content/uploads/2022/03/bio-CCS-in-the-cement-sector.pdf</span>](https://www.ieabioenergy.com/wp-content/uploads/2022/03/bio-CCS-in-the-cement-sector.pdf) (Accessed: 26 September 2025).

40. Emanuelsson, A.H., Rootzén, J. and Johnsson, F., 2025. Deployment of carbon capture and storage in the cement industry–Is the European Union up to shape?. International Journal of Greenhouse Gas Control, 146, p.104442.

41. Yue, Z. and Zhu, X. (2025) Microstructural insights and technical challenges of effectively adopting high-volume GGBS in blended cements for low-carbon construction. npj Materials Sustainability, 3, 25. Available at: [<span class="underline">https://doi.org/10.1038/s44296-025-00070-y</span>](https://doi.org/10.1038/s44296-025-00070-y) (Accessed: 26 September 2025).

42. Heidelberg Materials (2024) Advancing sustainable products: Heidelberg Materials converts cement plant to a slag grinding facility in Indiana. Press Release, 24 June. Available at: [<span class="underline">https://www.heidelbergmaterials.com/en/pr-2024-06-24</span>](https://www.heidelbergmaterials.com/en/pr-2024-06-24) (Accessed: 26 September 2025).

43. Global Cement (2024b) Heidelberg Materials converts Indiana cement plant to slag grinding facility. Global Cement, 25 June. Available at: [<span class="underline">https://www.globalcement.com/news/item/17527-heidelberg-materials-converts-indiana-cement-plant-to-slag-grinding-facility</span>](https://www.globalcement.com/news/item/17527-heidelberg-materials-converts-indiana-cement-plant-to-slag-grinding-facility) (Accessed: 26 September 2025).

44. Lacina, L. L. P. (2024) Cement production accounts for 7% of global CO2 emissions. Here's how to make it more sustainable. World Economic Forum, 16 September. Available at: [<span class="underline">https://www.weforum.org/stories/2024/09/cement-production-sustainable-concrete-co2-emissions/</span>](https://www.weforum.org/stories/2024/09/cement-production-sustainable-concrete-co2-emissions/) (Accessed: 26 September 2025).

45. LC3 (2022) LC3: A sustainable alternative for the cement industry. LC³. Available at: [<span class="underline">https://lc3.ch/wp-content/uploads/2022/11/LC3-A-sustainable-alternative-FINAL-WEB.pdf</span>](https://lc3.ch/wp-content/uploads/2022/11/LC3-A-sustainable-alternative-FINAL-WEB.pdf) (Accessed: 26 September 2025).

46. Miller, S.A., Habert, G., Myers, R.J. & Harvey, J.T. (2021) Achieving net zero greenhouse gas emissions in the cement industry via value chain mitigation strategies. One Earth, 4, pp. 1398–1411. Available at: [<span class="underline">https://doi.org/10.1016/j.oneear.2021.09.011</span>](https://doi.org/10.1016/j.oneear.2021.09.011)

47. Andrew, R.M. (2025) Global CO₂ emissions from cement production (GCP-CEM, version 251007) \[Data set\]. CICERO Center for International Climate Research. Zenodo. Available at: [<span class="underline">https://doi.org/10.5281/zenodo.17287474</span>](https://doi.org/10.5281/zenodo.17287474) (Accessed: 26 August 2026).

48. EEA (2026) EU Emissions Trading System (ETS) data viewer, European Environment Agency. Verified emissions for main activity code 29 (production of cement clinker), extracted from the European Union Transaction Log (EUTL). Available at: [<span class="underline">https://www.eea.europa.eu/data-and-maps/dashboards/emissions-trading-viewer-1</span>](https://www.eea.europa.eu/data-and-maps/dashboards/emissions-trading-viewer-1) (Accessed: 1 September 2026).

49. Worrell, E., Galitsky, C. and Price, L. (2008) Energy Efficiency Improvement and Cost Saving Opportunities for Cement Making: An ENERGY STAR Guide for Energy and Plant Managers, LBNL-54036-Revision. Lawrence Berkeley National Laboratory. Available at: [<span class="underline">https://www.osti.gov/servlets/purl/927882</span>](https://www.osti.gov/servlets/purl/927882) (Accessed: 1 September 2026).

50. IPCC (2006a) Chapter 2: Stationary Combustion, in 2006 IPCC Guidelines for National Greenhouse Gas Inventories, Volume 2: Energy. Available at: [<span class="underline">https://www.ipcc-nggip.iges.or.jp/public/2006gl/pdf/2\_Volume2/V2\_2\_Ch2\_Stationary\_Combustion.pdf</span>](https://www.ipcc-nggip.iges.or.jp/public/2006gl/pdf/2_Volume2/V2_2_Ch2_Stationary_Combustion.pdf) (Accessed: 1 September 2026).

51. Sahoo, N., Kumar, A. and Samsher (2022) 'Review on energy conservation and emission reduction approaches for cement industry', Environmental Development, 44, 100767. Available at: [<span class="underline">https://doi.org/10.1016/j.envdev.2022.100767</span>](https://doi.org/10.1016/j.envdev.2022.100767) (Accessed: 1 September 2026).

#### 9. Appendix

#### 9.1. Overview of the cement production process

The cement production process starts with mining and quarrying, where raw materials are extracted from the environment. Then, three main operations are performed. First, raw meals made of an appropriate mix of crushed limestone, calcium, silicon, aluminum and iron oxides are prepared. Second, raw meals are placed into a kiln where a large flame elevates the temperature greatly to allow for formation of clinker by chemical reaction and thereby releasing CO<sub>2</sub>. The thermal energy provided by the kiln originates from the combustion of various types of fuels ranging from traditional fossil fuels like coal and oil to alternative waste fuels and biomass. Third, cooled clinkers are ground and mixed with gypsum to create cement. An overview of this process is highlighted in Figure 9.

<img src="figures/figure9.png" width="435" />

**Figure 9** Overview of the cement production process (Construction Cost, 2016).

#### 9.2. Limits to hotspot mapping

Figure 10 depicts an example of a cement plant that is not monitored with satellite due to small signal-to-noise ratio limitations. Not only the heat signal is much more diluted around the kiln in comparison to the plant of Figure 3, but we also observe undesired signals originating from reflections on the coal stack.

<img src="figures/figure10.png" width="584" />

**Figure 10** Left - High resolution image of the Stockertown cement plant in Pennsylvania, United States. Right - composite Sentinel-2 image of the same plant. Heat signals (red areas) are not situated over kiln areas but on the coal stack (dashed circles). Sources: modified Copernicus and USGS data.
