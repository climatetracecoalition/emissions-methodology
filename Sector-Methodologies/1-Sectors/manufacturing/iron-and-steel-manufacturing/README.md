**Manufacturing and Industrial Processes sector: Iron & Steel Manufacturing Emissions**

***Verity Crane and George Ebri***

*Authors affiliated with TransitionZero and Climate TRACE*

**1. Introduction**
===================

Steel production is a major industrial source of energy demand and carbon emissions, accounting for roughly 8% of global energy use and 7% of energy-sector CO₂ emissions (IEA, 2020). These emissions stem largely from the sector’s reliance on coal, particularly in primary steelmaking. Global demand for steel is expected to grow beyond two billion tonnes per year by 2030 (GEM, 2025), with production concentrated in a few countries: China (over 50%), India (7.4%), Japan (4.6%), and the U.S. (4.3%) (WSA, 2024).

Steelmaking relies on two primary metallic inputs: iron ore and recycled scrap. Around 70% of global steel production uses iron ore, with the remainder coming from scrap. Primary steel, produced in blast furnaces, dominates sectoral emissions, while secondary steel produced in electric arc furnaces (EAFs) is roughly one-eighth as energy-intensive, using electricity instead of coal (IEA, 2020).

Accurate facility-level steel production data is important for estimating sector emissions, yet such data are rarely publicly available due to competitive pressures. Most reported figures are at the national level, often with multi-month delays (WSA, 2024; NBSC, 2025). Plant-level emissions data exist for the EU and U.S. (EEA, 2025; US EPA, 2025), but these account for only \~10% of global output.

This work addresses both temporal and spatial gaps in traditional steel production and emissions reporting by generating monthly, facility-level estimates for all assets identified in Global Energy Monitor’s Global Iron and Steel Tracker (GIST) database (GEM, 2025). Facility activity is primarily inferred from satellite-derived hotspot data, which capture fluctuations in operational intensity at certain steel plants. These satellite-based estimates are then calibrated against regional and national production statistics to derive final production values. Production estimates are subsequently combined with route- and process-specific emissions factors to calculate asset-level CO<sub>2</sub> emissions.

Given its contribution to global emissions, steel production requires targeted emissions reduction solutions (ERS). In this study, ERS are applied to assets based on the production technology in use, including blast furnace–basic oxygen furnace (BF/BOF), electric arc furnace (EAF), and direct reduced iron–EAF (DRI–EAF) routes. The solutions include strategies such as maximizing scrap use in EAF facilities, substituting natural gas with green hydrogen in DRI–EAF plants, integrating carbon capture and storage (CCUS) into BF/BOF operations, and phasing out or replacing high-emission blast furnaces with hydrogen-based DRI–EAF routes. Each strategy represents a pathway to reduce emissions, either by lowering direct process emissions, substituting carbon-intensive inputs, or phasing out high-emission technologies. Together, these strategies reflect both incremental and transformative options for emission reduction in the steel sector, capturing the diversity of regional conditions and technological readiness levels.

**2. Materials and Methods**
============================

This section provides a high-level overview of the datasets and associated pipelines used to derive emission estimates for a steel plant.

Direct emissions are released during the manufacturing of crude steel, with estimates varying by different production routes, namely blast furnace-basic oxygenation furnace (BF-BOF), direct reduced iron-electric arc furnace (DRI-EAF) and electric arc furnaces (EAF). A simplified overview of the steel production value chain from raw materials to final steel products is available in Appendix 1, section 7.1.

Given the lack of source-level emission data available publicly, a standardized “bottom-up” approach is used to quantify the emissions. This process is characterized by first estimating production levels at each plant, then subsequently applying a production-specific emissions factor to estimate emissions. Two approaches were used to estimate source level emissions as shown in Figure 1 below.

<img src="figures/figure1.png" style="width:7.70206in;height:2.32576in" />

**Figure 1** Flowchart of the methodology to calculate plant-level emissions for global steel assets.

**2.1. Materials**
------------------

### **2.1.1. Steel inventory dataset**

GEM provides facility-level information such as location, owner, capacity, age, product type and technology type via the GIST that includes every iron and steel plant currently operating with a capacity of more than 500 thousand tonnes. The GIST also includes all plants meeting that capacity threshold that have been proposed or under construction since 2017 and retired or mothballed since 2020. In total there are 1,205 unique steel facilities with an annual production capacity of 3.5 billion tonnes across 89 countries. We manually validated the position of all the plants using geolocation data from Google Maps API (Google Maps, 2025) and OpenStreetMap (OpenStreetMap, 2025).

[Figure](#bookmark=id.ihv636) 2 shows how steel mills are distributed globally with high concentration of sources in China. The map also highlights countries with little to no steel production, mainly concentrated in Sub-Saharan Africa, Latin America and Southeast Asia.

<img src="figures/figure2.png" style="width:6.67188in;height:3.93164in" />**  
Figure 2** Global map showing operating steel plants as of 2025. Satellite monitored facilities (shown in dark blue) and other facilities (shown in orange). The circle size represents plant production capacity, with reference scales shown at the top of the figure for 1,000 and 20,000 thousand tonnes per annum (ktpa).

### **2.1.2. Remote sensing datasets**

Satellite-derived production estimates make use of multispectral imagery from two different collections:

-   The European Space Agency (ESA) Copernicus Sentinel mission with a resolution of 20 m and a combined 5-day equator revisit with two satellites:

    -   Sentinel 2A: with imagery available since 2015 (ESA, 2025).

    -   Sentinel 2B: with imagery available since 2017 (ESA, 2025).

> Both Sentinel-2 satellites have a MultiSpectral Instrument (MSI) that can measure wavelengths from \~443 to \~2190 nm (blue to shortwave infrared (SWIR)) at 10-60 m spatial resolutions.

-   The U.S. Geological Survey (USGS) and National Aeronautics and Space Administration (NASA) Landsat program with a resolution of 30 m and a combined 8-day revisit:

    -   Landsat-8: with imagery available since 2013 (NASA and USGS, 2025a).

    -   Landsat-9: with historical images available from 2021 (NASA and USGS, 2025b).

> Both Landsat-8 and Landsat-9 have an Operational Land Imager (OLI) that can measure wavelengths from \~435 to \~1384 nm (blue to thermal infrared) at 15-100 m spatial resolutions.

All satellite datasets were sourced and processed using Google Earth Engine (Google Earth Engine, 2025a, 2025b, 2025c). From each satellite dataset, we relied on the surface reflectance products and computed the ratio of the difference between two SWIR bands and near infrared (NIR) bands of each satellite. This is based on the study to detect high-temperature anomalies from Sentinel-2 MSI images where a tri-spectral thermal anomaly index (TAI) that jointly uses the two high-temperature sensitive SWIR bands and the high-temperature-insensitive NIR band to enhance High Temperature Anomalies (Yongxue et al., 2021). For the respective satellite collections, we infer the TAI through the following equations:

-   Sentinel-2A/B: $TAI\  = \ \frac{(B12\  - \ B11)}{(B8a)}$

-   Landsat-8/9: $TAI\  = \ \frac{(B7\  - \ B6)}{(B5)}$

Where B\# refers to the band number for the specific satellite. This ratio was used to identify thermal anomalies within the temperature range of industrial processes, while eliminating most of the noise from reflectance interference. Pixel values between the Sentinel 2A/B MSI and Landsat OLI were harmonized using NASA’s band pass adjustments allowing the two image collections to be used as if they were a single collection (NASA, 2018). The harmonized dataset ensured higher revisit for time-series surface applications. Partial images (coverage of the steel facility’s boundaries less than 80%) and cloudy images (more than 20% clouds) were excluded. [Figure](#bookmark=id.1hmsyys) 3 shows an example of TAI with identified hotspots at a steel plant.

**Figure 3** Left**:** Identified hotspots at POSCO’s Gwangyang steel plant, South Korea, during different quarters in 2023. Right: Identified sub-assets within the facility based on thermal anomalies. Sources: modified Copernicus and USGS data, ESRI base map.<img src="figures/figure3.png" style="width:3.33611in;height:1.91966in" /><img src="figures/figure4.png" style="width:3.40923in;height:1.939in" />

### **2.1.3. Production datasets**

National-level steel production data used in our models is primarily sourced from the World Steel Association (WSA), based on monthly reporting.

### **2.1.4. Emissions factors dataset**

The direct emissions factors and electricity consumption for different steel production routes were sourced from multiple references, including the World Steel Association (WSA, 2024b), the IPCC (2006), the Mission Possible Partnership’s Steel Transition Strategy (MPP, 2024), and the International Energy Agency (IEA, 2020), providing global average values specific to each production route.

**2.1.5. Percentage of scrap used in EAF**

The composition of the feedstock mix used in EAF production was provided by GEM, including the percentages of scrap, DRI, sponge iron, pig iron and other sources of iron. This data was used to adjust the emission factor for the EAF production route.

**2.1.6 Emissions Reduction Solutions**

Each ERS is applied to steelmaking assets according to their technology, feedstock mix, and operational context. Each ERS has a strategy that was analysed in this study:

1.  **Strategy 0 – Continue Current Operation:** Baseline scenario where assets continue current operations without technology upgrades.

2.  **Strategy 1 – 100% Scrap-EAF:** Increase scrap share to 100% in EAF assets not currently operating at full scrap capacity. These facilities are common in the US, Japan, and Europe (GEM, 2025).

3.  **Strategy 2 – H₂-DRI/EAF (100% green):** Substitute natural gas with green hydrogen in DRI–EAF plants. Early pilot projects, such as HYBRIT in Sweden and SALCOS in Germany, have demonstrated technical feasibility, with several initiatives moving towards industrial scale (HYBRIT, 2024; Salzgitter AG, 2022).

4.  **Strategy 3 – BF/BOF + CCUS:** Apply carbon capture to existing BF/BOF plants as a transitional measure. The Al Reyadah project in the UAE confirms the technical viability of capturing CO₂ from steel operations (Nicholas, 2024).

5.  **Strategy 4 – Shut Down Plant:** Decommission low-output BF/BOF plants and substitute production with lower-emission routes. This strategy has been implemented in China as part of national policies to phase out small, inefficient blast furnaces.

6.  **Strategy 5 – Shift Production towards EAF:** Redirect production from BF/BOF to EAF at dual-technology facilities.

7.  **Strategy 6 - Replace BF with H2-DRI/EAF\_100%\_green:** Transition primary steel production from conventional BF/BOF routes to DRI–EAF facilities powered entirely by green hydrogen. Early pilot projects, such as HYBRIT in Sweden and SALCOS in Germany, have demonstrated technical feasibility, with several initiatives moving towards industrial scale (HYBRIT, 2024; Salzgitter AG, 2022).

*Note: Only rank 1 strategies are provided for assets on the Climate TRACE website and additional strategies will be made available in future releases.*

**2.2. Methods**
----------------

### **2.2.1. Production methodology**

Two approaches were used to estimate source level production. As a priority, satellite-derived production estimates were used whenever a facility released enough heat to be captured by a satellite’s sensor that can measure short-wave infrared (SWIR) and near infrared (NIR) wavelengths (Zhou *et al.*, 2018; Marchese *et al.*, 2019; Liangrocapart, Khetkeeree and Petchthaweetham, 2020). This is the case for BF-BOF facilities which have several units that function at temperatures higher than 1,200<sup>o</sup>C. These hotspots include signals from BFs, coke ovens, sinter plants, pellet plants and BOFs.

Our methodology scours satellite imagery for heat signatures from the operating steel plants. Each steel production unit is outlined with a hand-drawn polygon as shown in Figure 4. Using the GIST as a foundation, we built a global dataset of blast furnaces, coke oven batteries, sinters and pellet plants with the help of our satellite-based hotspot methodology. The current BF/BOF dataset spans 40 countries and contains the location, shape, crude steel capacity and operation start year for 334 steel plants, along with the location, shape, and type for their associated sub-assets. More details on the methodology and dataset are available on the TransitionZero website ([<span class="underline">https://www.transitionzero.org/insights/steel-data-explainer</span>](https://www.transitionzero.org/insights/steel-data-explainer)).

<img src="figures/figure5.png" style="width:5.44331in;height:3.06771in" />  
**Figure 4** Zooming in on Hyundai Steel Integrated Steel Works (Dangjin, South Korea), with identified sub-asset polygons.

The intensity of the hotspot above each identified unit is calibrated against the monthly country-level data source from WSA (2024) to estimate plant activity in each month.

For BF/BOF plants without usable hotspot signals, we estimate production using a regional or global average of satellite-derived utilization rates. Assets may be excluded from satellite monitoring due to a small signal-to-noise ratio which makes it difficult to distinguish production from background fluctuations. Other sources of complication can be the occasional presence of strong reflections from a-priori cold elements.

For all the other production routes (e.g. EAFs) for which hotspots are not currently measured, we applied a regional average utilization rate based on historical national production and aggregated capacity. These combined techniques, applied to operating plants sourced from the GIST database, yield a total of 951 facilities monitored monthly for production and CO₂ emissions.

### **2.2.2. Emissions methodology**

Facility-level direct and indirect emissions were estimated through application of emissions factors accounting for the technology type and input materials, where known (IPCC, 2006; WSA 2024b; IEA, 2020). In particular, for direct emissions, the following emission factors were considered depending on the production route for the crude steel (Table 1).

**Table 1** Direct emission, electricity use and process emission factors for the different crude steel production routes.

<table><thead><tr class="header"><th><strong>Production Route</strong></th><th><strong>Direct Emission Factor (t-CO<sub>2</sub>/t-steel)</strong></th><th><p><strong>Electricity Use Factor</strong></p><p><strong>(MWh/t-steel)</strong></p></th><th><p><strong>Process Emissions Factors</strong></p><p><strong>(t-CO<sub>2</sub>/t-steel)</strong></p></th></tr></thead><tbody><tr class="odd"><td>BF/BOF</td><td>1.9</td><td>0.83</td><td>1.71</td></tr><tr class="even"><td>DRI-EAF</td><td>1.0</td><td>0.87</td><td>0.62</td></tr><tr class="odd"><td>EAF</td><td>0.08</td><td>0.87</td><td>0.08</td></tr></tbody></table>

In the case of EAF production, the proportion of scrap in the feedstock mix was used to refine the estimation of emission factors. To calculate the effective emission factor $E_{a}(EAF)$ based on the actual feedstock composition, the following weighted average formula was applied:

$E_{a}(EAF)\  = \ {E_{a}}^{\text{scrap}}\text{\ \ x\ \ \ p}c_{\text{scrap}}\  + \ {E_{a}}^{\text{DRI}}\text{\ x\ \ p}c_{\text{DRI}}\  + \ {E_{a}}^{\text{pig\ iron}}\text{\ x\ \ p}c_{pig\_ iron} + \ {E_{a}}^{\text{DRI}}\text{\ x\ \ p}c_{other\_ iron}$

Where:

${E_{a}}^{\text{scrap}}$= 0.08 (IPCC 2006) , ${E_{a}}^{\text{DRI}}\  = \ 1.0$ (IEA, 2020)​, and ${E_{a}}^{\text{pig\ iron}}$​ = 1.71 (IPCC, 2006) represent the emission factors for EAF production using 100% scrap, DRI, and pig iron, respectively.

$\text{\ p}c_{\text{scrap}}$​, $pc_{\text{DRI}}$, $pc_{pig\_ iron}$​, and $pc_{other\_ iron}$ are the corresponding proportions of each feedstock type used.

Emissions from other sources of iron were assumed to be equal to those from DRI. When the percentage of scrap ($\text{\ p}c_{\text{scrap}}$) was not available in the database, it was assumed to be equal to the average $\text{\ p}c_{\text{scrap}}$ of the assets where this value was below 100%, based on the assumption that assets using 100% scrap would report this openly owing to the ‘green’ credentials associated. To determine the proportion of each feedstock used at a given asset, a weighted average was calculated based on the capacities of its EAF units.

Indirect emissions factors were calculated using the average electricity use for different production routes (MPP contributors, 2024) and the regional grid intensity (Ember contributors, 2025). These factors were adjusted to obtain an global average per production route matching the values reported by other sources (WSA, 2024b; IEA 2020). These values can be found in Table 1.

For plants with multiple steel production routes, the emissions factor was calculated based on the weighted share of production capacity.

Direct emissions can be divided into process emissions (IPPU) and emissions from fuel combustion used to provide energy to the process. To estimate process emissions, the guidance provided by the IPCC (2006) was followed, which specifies direct emission factors for different steel technologies. This information was complemented with factors from Fan et al. (2021) to estimate the IPPU emissions of the DRI–EAF route. The factors used to calculate IPPU can be found in Table 1.

**2.3. Coverage**
-----------------

Based on 2024 data, asset-level emissions estimates accounted for 83% (3.0 Gt-CO2) of the sector emissions. While satellite-monitored steel facilities represent around 41% of total sources, these plants contributed to about 87% of the total asset level emissions.

**2.4. Incorporating ERS**

To integrate emissions reduction solutions (ERS) into facility-level emissions estimates, we applied a consistent method across all strategies. In general, the method involves identifying the set of assets eligible for a given ERS. For each ERS, eligible assets were identified based on their technology and feedstock mix using the Global Energy Monitor’s Global Iron and Steel Tracker (GEM, 2025). Their facility’s emissions were then adjusted according to either literature-based emission factors or assumed percentage reductions, and then recalculated under the ERS scenario.

The following subsections describe each ERS strategy.

**-** **Strategy 0 – Continue Current Operation (Scrap-EAF at 100%):** This strategy was applied to facilities already operating Electric Arc Furnaces (EAF) with 100% scrap as feedstock. Because these assets represent the most decarbonized pathway currently available in terms of direct process emissions, no additional reductions were applied to their emissions factors (IEA, 2020). Their remaining carbon footprint is largely linked to indirect emissions from electricity use, which were not explicitly adjusted here but are recognized as dependent on the decarbonization of the grid. In this way, Strategy 0 serves as a baseline condition rather than an additional mitigation pathway.

### **- Strategy 1 – Increase Scrap Share to 100% in EAF:** This strategy was applied to EAF facilities that operate with less than 100% scrap feedstock (GEM, 2025). In these cases, we assumed that the share of scrap could be increased to full utilization, thereby reducing emissions associated with virgin iron inputs such as direct reduced iron (DRI) or pig iron. Emission reductions were applied proportionally, with the greatest reductions occurring in facilities with low baseline scrap use, where reductions could reach up to 80% (IPCC, 2006; IEA, 2020). Facilities that already use high scrap shares saw correspondingly smaller reductions. This approach reflects both theoretical assumptions and widespread real-world practice, as scrap-EAF is a mature and widely adopted technology.

### **- Strategy 2 – Hydrogen-based DRI–EAF (100% green hydrogen)**

-   ### **Hydrogen-based DRI–EAF (100% green hydrogen):** This strategy was applied to DRI–EAF facilities that currently rely on natural gas as a reductant. We replaced their existing emissions factors with hydrogen-based benchmarks, which estimates an emissions factor of 0.27 tCO₂ per tonne of steel when hydrogen is produced entirely from renewable electricity (Millner, 2021; Trinca 2023). The difference between current natural gas-based emissions and this hydrogen benchmark was applied as the emissions reduction for eligible facilities.

-   **Replace BF with H2-DRI/EAF\_100%\_green:** This strategy represents a long-term solution to decarbonize BF/BOF steel production. Existing BF/BOF units are replaced with hydrogen-based DRI–EAF facilities powered entirely by renewable hydrogen, achieving near-zero direct emissions (Millner, 2021; Trinca, 2023). While adoption is limited by green hydrogen availability, cost, and high capital requirements, rising demand for low-carbon steel and falling renewable energy costs could accelerate deployment. The resulting reductions represent the full decarbonization potential for primary steel production at the affected facilities, achieving emission cuts of up to 85–100% of Scope 1 emissions relative to conventional BF/BOF production.

### **- Strategy 3 – Carbon Capture, Utilization, and Storage (CCUS):** This strategy was applied to blast furnace–basic oxygen furnace (BF/BOF) assets that are unlikely to be shut down in the near term (see Strategy 4). For these facilities, we assumed that carbon capture technologies could be retrofitted to reduce process emissions. Based on reported capture rates from demonstration projects, we applied an average 59% reduction to direct emissions from eligible facilities (MPP, 2024). This reflects typical capture efficiencies in the range of 50–60% found in literature.

### **- Strategy 4 – Shutdown of BF/BOF Plants with Low Production:** This strategy was applied to BF/BOF facilities characterized by relatively low production volumes, specifically those in China producing less than 4 million tonnes of steel per year. For these assets, emissions were set to zero to reflect complete retirement of production. The underlying rationale is that concentrating steel output in fewer, larger facilities may facilitate the application of CCUS or accelerate the shift to alternative technologies. While in reality, production would likely be reallocated to other routes such as scrap-EAF or hydrogen-based DRI, this framework focuses only on the elimination of direct emissions from the retired plants. The method is therefore a theoretical assumption, but it is supported by real-world examples of enforced closures of inefficient and small BF/BOF facilities in China. For instance, in 2023, China retired 25 million tonnes per annum (mtpa) of blast furnace capacity—slightly more than the 20 mtpa of new capacity that came online—highlighting the net reduction in older, less efficient units (GEM, 2024).

### **- Strategy 5 – Shift Production from BF/BOF to EAF:** This strategy was applied to facilities operating both BF/BOF and EAF technologies. We assumed that these assets could migrate BF/BOF production to the EAF route, to existing units where these are below full capacity, or to new units. To capture the full emissions reduction potential, we have assumed 100% scrap feedstock. Depending on the current share of EAF versus BF/BOF production at each facility, the resulting emission reductions varied, with a maximum reduction of up to 95% of Scope 1 emissions compared to full BF/BOF operation (IEA, 2020; IPCC, 2006). This method reflects real-world practice in some facilities in China that have shifted production towards EAF under policy incentives.

**2.5 Verifying modeled ERS emissions estimates**

Verification of the modeled ERS varies depending on the strategy and the type of change assumed. For scrap-based strategies (Strategies 0–1), implementation could in principle be monitored through company reports, trade statistics, and updates to facility feedstock data in the Global Iron and Steel Tracker (GEM, 2025), although these sources may not provide real-time confirmation. Hydrogen-based DRI (Strategy 2 and 6) and CCUS retrofits (Strategy 3) are not directly observable from satellite data but can be tracked through company disclosures, pilot project announcements, and regulatory filings. In contrast, strategies involving the shutdown of low-production BF/BOF assets (Strategy 4) can be verified more robustly through satellite-based activity monitoring, which allows for direct observation of whether a facility has ceased operation. Finally, the prioritization of EAF production over BF/BOF at dual-technology sites (Strategy 5) could also be partially confirmed through satellite activity data, as a sustained reduction in BF/BOF operations would be observable.

**3. Results and analysis**
===========================

**3.1 TAI and Emissions**

Figure 5 illustrates the relationship between satellite-derived Thermal Anomaly Index (TAI) and the corresponding emissions for a steel plant in France. The data demonstrates that, for most months, estimated emissions (based on production levels) align closely with fluctuations in TAI. For example, both peak just after July 2021, followed by a decrease after January 2022.

<img src="figures/figure6.png" style="width:7.65625in;height:2.17546in" />

**Figure 5** Satellite-based Thermal Anomaly Index (TAI; red solid line) and estimated emissions (blue solid line) at ArcelorMittal’s Fos-sur-Mer steel plant during January 2021– September 2024.

However, further calibration is needed to enhance the model that translates TAI into asset-level production, as TAI data can vary significantly by asset depending on factors like equipment type, age, geographic location, and other operational conditions. The TAI values presented here are derived from the hotspot data shown in Figure 6.

<img src="figures/figure7.png" style="width:4.13542in;height:3.30208in" />

**Figure 6** Satellite-detected hotspots (green boxes in upper centre and centre right) over ArcelorMittal’s Fos-sur-Mer steel plant during Sep. 2024.

Tables 2 and 3 show the biggest producers and emitters in the steel industry at country and plant level, respectively. China accounts for more than half of the global steel production and emissions, and has some of the largest and most emitting steel plants (Table 3).

**Table 2** Top 10 emitters in the steel sector in 2024 - by country (direct emissions only)

| Country | CO<sub>2</sub> emissions (MtCO<sub>2</sub>) |
|---------|---------------------------------------------|
| China   | 1679                                        |
| India   | 260                                         |
| Japan   | 121                                         |
| Russia  | 89                                          |
| S Korea | 82                                          |
| USA     | 57                                          |
| Brazil  | 52                                          |
| Germany | 51                                          |
| Iran    | 29                                          |
| Turkey  | 24                                          |

**Table 3** Top 10 emitting steel plants in 2024 (direct emissions only).

<table><thead><tr class="header"><th>Plant name</th><th>Country</th><th>Plant capacity (Mt)</th><th><p>CO<sub>2</sub> emissions</p><p>(MtCO<sub>2</sub>)</p></th></tr></thead><tbody><tr class="odd"><td>POSCO Gwangyang steel plant</td><td>S Korea</td><td>23</td><td>33.6</td></tr><tr class="even"><td>Angang Steel Co Ltd.</td><td>China</td><td>20.6</td><td>30.3</td></tr><tr class="odd"><td>Wuhan Iron and Steel Co., Ltd.</td><td>China</td><td>15.9</td><td>26.1</td></tr><tr class="even"><td>Ma'anshan Iron &amp; Steel Co Ltd</td><td>China</td><td>17.3</td><td>25.6</td></tr><tr class="odd"><td>Inner Mongolia BaoTou Steel Union Co Ltd</td><td>China</td><td>15.6</td><td>25.5</td></tr><tr class="even"><td>Baoshan Iron and Steel Co Ltd H</td><td>China</td><td>19.2</td><td>24.3</td></tr><tr class="odd"><td>POSCO Pohang steel plant</td><td>S Korea</td><td>17.6</td><td>23.5</td></tr><tr class="even"><td>Zhangjiagang Hongchang Steel Co Ltd</td><td>China</td><td>17.6</td><td>22.2</td></tr><tr class="odd"><td>Shougang Jingtang United Iron &amp; Steel Co Ltd</td><td>China</td><td>13.7</td><td>21.3</td></tr><tr class="even"><td>NLMK Lipetsk steel plant</td><td>Russia</td><td>14.4</td><td>20.7</td></tr></tbody></table>

**3.2 ERS Emissions Estimates**

### Applying ERS strategies to the main steel production routes demonstrates the significant mitigation potential of technological and operational shifts. Figure 7 presents the change in emission factors before and after applying each ERS to their specific BF/BOF, DRI-EAF, or EAF production route.

### For the BF/BOF route in Figure 7, which is the most carbon-intensive, average emission factors were reduced from 2.43 tCO₂/t steel to \~1.0 tCO₂/t steel under Strategy 3, primarily through the application of carbon capture and storage (CCS). While not fully eliminating emissions, this reduction highlights the role of CCS as an important transitional option for existing blast furnace infrastructure. Plants that have both BF/BOF and EAF facilities were assigned Strategy 5, allowing migration of production to the EAF route where possible, considering limitations in scrap supply and the fact that these plants might have already started transitioning to cleaner steel production. The long-term solution for fully decarbonizing the BF/BOF route is Strategy 6, which replaces conventional BF/BOF production with hydrogen-based DRI–EAF facilities powered entirely by green hydrogen. This is why CCS is proposed here as a primary strategy to provide significant near-term emission reductions while enabling the gradual transition toward the ultimate hydrogen-based pathway.

### For DRI–EAF facilities, shifting from natural gas to green hydrogen (Strategy 2) lowers average emission factors from 0.80 tCO₂/t steel to 0.26 tCO₂/t steel. This represents one of the deepest potential cuts in the sector and illustrates how hydrogen-based pathways could provide a near-zero emissions solution if renewable hydrogen is available at scale.

### For EAF facilities, which already operate at comparatively low direct emissions, further reductions can be achieved by increasing the scrap share to 100% (Strategy 1). In such cases, emissions linked to the production of virgin iron inputs are eliminated, making EAF the lowest-emission pathway currently available.

### Overall, these results show that while scrap-based EAF offers the lowest direct emissions, scaling global decarbonization will also require CCS retrofits for legacy BF/BOF plants and the deployment of hydrogen-based DRI–EAF.

<img src="figures/figure8.png" style="width:3.66135in;height:3.03646in" alt="Chart" />
=====================================================================================

**Figure 7** Average emission factors (tCO₂ per tonne of steel) before (yellow bars) and after (blue bars) the application of primary emission reduction solutions (ERS) across major steel production routes worldwide.

**4. Discussion**
=================

**4.1 Emissions Estimates**

The use of satellite-derived Thermal Anomaly Index (TAI) provides a promising approach to estimate steel production at the asset level on a monthly basis. By calibrating TAI against production data, it is possible to derive capacity factors that, when combined with route-specific process parameters, enable CO₂ emission estimates for individual plants. This approach offers a more temporally resolved and consistent method for monitoring emissions compared to traditional reporting, particularly for regions or assets with limited disclosure.

However, the accuracy of TAI-based estimates depends on asset-specific characteristics, including equipment type, age, and operational practices, which can influence thermal signatures. Further calibration across different technologies and geographies is therefore essential to improve reliability. Despite these challenges, integrating satellite observations with process-based emission modeling provides a scalable framework for tracking steel sector emissions and supporting decarbonization strategies at both plant and country levels.

**4.2 ERS Application and Challenges**

Steel emissions depend fundamentally on the iron reduction method and the source of energy used. The conventional BF/BOF route remains the most carbon-intensive, while DRI–EAF can approach near-zero emissions if powered by renewable electricity and green hydrogen. Scrap-based EAF avoids ore reduction altogether, relying mainly on electricity, but its further growth is constrained by high recycling rates (\~80–85%) and material quality requirements (IStructE, 2025). Below, each strategy is discussed in terms of practicality and deployment.

**4.2.1 EAF and DRI–EAF Routes**

EAF and DRI–EAF strategies primarily focus on reducing emissions by increasing scrap use, switching to low-carbon feedstocks, or adopting hydrogen-based production. These approaches leverage mature technologies for near-term reductions while also providing pathways for deep decarbonization where renewable electricity and green hydrogen are available.

Strategy 0 (Maintain 100% Scrap-EAF) represents the most decarbonized form of current steelmaking, with minimal scope for additional direct emission reductions. Its primary challenge lies not in technology but in the availability of clean electricity. Widespread deployment of low-carbon grids is therefore essential for this route to contribute fully to net-zero ambitions.

Strategy 1 (Increase Scrap Share in EAF) shows large potential reductions—up to \~80% for plants currently operating with low scrap input. Because scrap-EAF is a mature and widely adopted practice, this strategy offers a highly practical near-term option. However, global scrap supply is already heavily utilized, and further recovery is technically and economically difficult. Moreover, certain high-quality steel grades still require primary iron inputs. Thus, while scrap maximization is a cost-effective step, it cannot on its own deliver full sectoral decarbonization (IStructE, 2025).

Strategy 2 (Hydrogen-based DRI–EAF) highlights one of the most transformative pathways, reducing emissions factors from \~0.8 to 0.26 tCO₂/t steel. Early pilots such as HYBRIT (Sweden) and SALCOS (Germany) have demonstrated technical feasibility, and several projects are moving towards industrial scale (HYBRIT, 2024; Salzgitter AG, 2022). Adoption, however, is constrained by the cost and availability of green hydrogen and the need for substantial investment in renewables and electrolysis capacity (Bhaskar, 2022). With supportive policy and falling renewable costs, this route could play a central role in a net-zero steel sector by mid-century.

**4.2.2 BF/BOF Route**

BF/BOF strategies focus on transitional and long-term solutions to mitigate emissions from primary steel production. While incremental improvements, such as implementation of CCS or increasing EAF participation, can achieve some reductions, deep decarbonization relies on technology shifts, including full replacement with hydrogen-based DRI–EAF.

Strategy 3 (BF/BOF + CCUS) provides only a partial solution, reducing emissions by 50–60%. This makes it a transitional measure rather than a long-term pathway. Demonstrations such as Al Reyadah in the UAE confirm technical viability (Nicholas, 2024), but large-scale adoption is hindered by high costs, infrastructure needs, and uncertainty around long-term storage. Moreover, residual emissions remain significant. Nevertheless, given the longevity of existing BF/BOF assets, CCUS may serve as a bridge option until full replacements can be deployed.

Strategy 4 (Shutdown of Low-Production BF/BOF Plants) eliminates emissions at the facility level, offering immediate reductions. In practice, this depends on stringent regulatory measures, as seen in China’s policy-driven closure of small inefficient blast furnaces. The challenge lies in ensuring that demand is met by lower-emission alternatives rather than shifting production to other high-emission assets. Economic disruption and workforce impacts also present major barriers.

Strategy 5 (Shift Production from BF/BOF to EAF) is particularly relevant for hybrid facilities, many of which are located in China. By prioritising EAF, emission reductions of up to \~94% (assuming 100% scrap input) are achievable. This strategy is technologically straightforward, since both production routes already exist at the facility. However, the practical constraint is again scrap availability, along with electricity grid intensity. Where these conditions are favourable, this strategy can accelerate reductions quickly.

Strategy 6 (Replace BF/BOF with H₂-DRI/EAF) represents the long-term solution for fully decarbonizing the BF/BOF route. By replacing conventional blast furnaces with hydrogen-based DRI–EAF facilities powered entirely by green hydrogen, near-zero direct emissions can be achieved. While current adoption is limited by the availability and cost of green hydrogen and the need for substantial capital investment, this pathway provides the ultimate reduction potential for primary steel production and serves as the benchmark toward which transitional strategies like CCUS or partial shifts to EAF should converge.

**5. Conclusions**
==================

In this work a new approach has been implemented to estimate steel production and emissions at facility level on a monthly basis for 890 operating steel plants in 81 countries in the GEM contributors (2025) database.

Our modelling approach consists of estimating facility-level production and then applying the relevant emissions factors to yield emissions estimates. The approach for estimating production depends on the facility type. The activity of BF/BOF facilities was tracked by satellite-based thermal anomalies, as these plants contain several units -BFs, coke plants, sinter plants, BOFs- that operate at temperatures higher than 1,200°C. Such high temperatures present a strong signal that can be used as a proxy to infer activity at a given time. Production for other facilities that do not have such strong thermal signals, such as DRI-EAF and EAF facilities, was instead estimated via a regional utilization rate based on historical production and capacity data. The satellite-based approach is advantageous as it can provide dynamic estimates of plant activity. Limitations in this approach may arise from either incorrect detection of relevant hotspots or insufficient data due to cloud cover. In both cases, a longer study period is expected to improve the accuracy of our model estimates.

This work demonstrates that timely, facility-level production and monthly CO₂ emissions estimates can be obtained without relying on company-reported figures, which are often outdated by several years. This capability offers a valuable tool for more responsive climate policy development. Future work may benefit from increased availability of asset-level data to further enhance model training and accuracy.

In this study, we also developed and systematically applied a set of emissions reduction solutions (ERS) to steel production assets worldwide in order to evaluate their potential to lower greenhouse gas emissions. These strategies reflect both technological and operational pathways available to the sector. Scrap-based EAF remains the most effective pathway, though its expansion is constrained by limited scrap availability and quality requirements. Hydrogen-based DRI offers deep reductions but is currently limited by the high cost and low availability of green hydrogen. This technology could also represent a long-term solution to fully decarbonize primary steel production by replacing conventional BF/BOF facilities with hydrogen-based DRI–EAF technology. CCS can provide transitional reductions in BF/BOF, yet deployment is challenged by high costs and the need for CO₂ transport and storage infrastructure. Shutting down smaller BF/BOF plants or shifting production towards EAF can accelerate decarbonization, but both depend on managing market demand, regional supply security, and socio-economic impacts.

Overall, the analysis underscores that decarbonising steel will require a portfolio of strategies tailored to regional conditions, with careful consideration of technological readiness, infrastructure needs, and material constraints. Emerging technologies, such as direct electrolysis of iron ore, may also play a role in the longer term, though they remain at an early stage of development.

**6. Supplementary metadata section** 
=====================================

Steel sector CO<sub>2</sub> emissions have been reported for individual sources from January 2021. The emissions described here represent a subset of specific country-level emissions estimates from the Climate TRACE manufacturing sector. All data is freely available on the Climate TRACE website ([<span class="underline">https://climatetrace.org/</span>](https://climatetrace.org/)). A detailed description of what is available is described in Tables 4 - 6.

**Table 4** Details on the asset metadata

| **General Description**                                                     | **Definition**                                                                                                                                                                                                               |
|-----------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Sector definition**                                                       | *Emissions from iron and steel production*                                                                                                                                                                                   |
| **UNFCCC sector equivalent**                                                | *2.C.1 Iron and steel production*                                                                                                                                                                                            |
| **Temporal Coverage**                                                       | *2021 - present*                                                                                                                                                                                                             |
| **Temporal Resolution**                                                     | *Monthly*                                                                                                                                                                                                                    |
| **Data format**                                                             | *CSV*                                                                                                                                                                                                                        |
| **Coordinate Reference System**                                             | *None. ISO3 country code provided*                                                                                                                                                                                           |
| **Number of sources available for download**                                | *866 sources covering 89 countries*                                                                                                                                                                                          |
| **What emission factors were used?**                                        | *Global average emission factors for different production routes*                                                                                                                                                            |
| **What is the difference between a “0” versus “NULL/none/nan” data field?** | *“0” values are for true non-existent emissions. If we know that the sector has emissions for that specific gas, but the gas was not modelled, this is represented by “NULL/none/nan”*                                       |
| **total\_CO2e\_100yrGWP and total\_CO2e\_20yrGWP conversions**              | *Climate TRACE uses IPCC AR6 CO<sub>2</sub>e GWPs. CO<sub>2</sub>e conversion guidelines are here: <span class="underline">https://www.ipcc.ch/report/ar6/wg1/downloads/report/IPCC\_AR6\_WGI\_FullReport\_small.pdf</span>* |

**Table 5** Definition of the fields in asset dataset

| **Data attribute**           | **Definition**                                                         |
|------------------------------|------------------------------------------------------------------------|
| **sector**                   | manufacturing                                                          |
| **source\_sub-sector\_name** | iron and steel                                                         |
| **source definition**        | emissions from iron and steel production                               |
| **start\_date**              | start date for time period of emissions estimation (YYYY-MM-DD format) |
| **end\_date**                | end date for time period of emissions estimation (YYYY-MM-DD format)   |
| **asset\_identifier**        | internal identifier                                                    |
| **asset\_name**              | name of the facility                                                   |
| **iso3\_country**            | ISO 3166-1 alpha-3 country code                                        |
| **location**                 | well-known text (WKT) point location                                   |
| **type**                     | manufacturing method                                                   |
| **capacity**                 | monthly plant capacity                                                 |
| **capacity\_factor**         | utilization rate of steel mills                                        |
| **activity**                 | production estimates                                                   |
| **CO2\_emissions\_factor**   | direct emissions factor (t-CO2/t-steel)                                |
| **CH4\_emissions\_factor**   | not used; N/A                                                          |
| **N2O\_emissions\_factor**   | not used; N/A                                                          |
| **CO2\_emissions**           | direct emissions estimates (t-CO<sub>2</sub>)                          |
| **CH4\_emissions**           | not used; N/A                                                          |
| **N2O\_emissions**           | not used; N/A                                                          |
| **total\_CO2e\_100yrGWP**    | 100 years global warming potential (t-CO<sub>2</sub>e)                 |
| **total\_CO2e\_20yrGWP**     | 20 years global warming potential (t-CO<sub>2</sub>e)                  |
| **other1**                   | direct and indirect emissions factor: includes electricity use         |
| **other2**                   | direct and indirect emissions: includes electricity use                |
| **other3**                   | electricity use factor (MWh/t-steel)                                   |
| **other4**                   | electricity consumption (MWh)                                          |
| **other5**                   | grid emissions intensity (t-CO<sub>2</sub>/MWh)                        |
| **other6**                   | model methodology (e.g. satellite\_monitored or extrapolation)         |
| **other7**                   | Percentage of scrap utilized in EAF                                    |
| **other8**                   | Percentage of IPPU emissions                                           |
| **model\_number**            | version of the model (e.g. 1, 2, …)                                    |

**Table 6** Definition for confidence and uncertainty in emissions.

<table><thead><tr class="header"><th><strong>Data attribute</strong></th><th><strong>Confidence Definition</strong></th><th><strong>Uncertainty Definition</strong></th></tr></thead><tbody><tr class="odd"><td><strong>type</strong></td><td><ul><li><p><em>Very low:</em> Based on highly speculative or obsolete information. Very low level of confidence in the accuracy of steel plant classification.</p></li><li><p><em>Low:</em> Limited or somewhat outdated data. Low level of confidence in the classification's correctness.</p></li><li><p><em>Medium:</em> A mix of historical and more recent data. A medium level of confidence in its accuracy.</p></li><li><p><em>High:</em> Grounded in comprehensive and recent data. A high level of confidence in the precise classification of the steel plant.</p></li><li><p><em>Very high:</em> Extensive, up-to-date, and verified data. A very high level of confidence in the accurate and detailed identification of the steel plant.</p></li></ul></td><td>Not used; N/A</td></tr><tr class="even"><td><strong>capacity</strong></td><td><ul><li><p><em>Very low:</em> Limited or outdated data, and significant uncertainties exist.</p></li><li><p><em>Low:</em> Outdated and/or incomplete data.</p></li><li><p><em>Medium:</em> A mix of historical and recent data.</p></li><li><p><em>High:</em> Comprehensive and recent data updates. High level of certainty.</p></li><li><p><em>Very high:</em> Extensive, up-to-date, and verified data. A very high level of certainty.</p></li></ul></td><td>Not used; N/A</td></tr><tr class="odd"><td><strong>capacity_factor</strong></td><td><ul><li><p><em>Very low:</em> Data is sparse or highly unreliable. Considerable uncertainty in capacity factor estimations.</p></li><li><p><em>Low:</em> Moderate uncertainty in capacity factor calculations.</p></li><li><p><em>Medium:</em> Data is sufficiently available, though not comprehensive. No absolute accuracy in capacity factor estimations.</p></li><li><p><em>High:</em> High confidence in the accuracy of capacity factor calculations.</p></li><li><p><em>Very high:</em> Derived from thorough and validated data sources. Very high precision of capacity factor estimations.</p></li></ul></td><td>Not used; N/A</td></tr><tr class="even"><td><strong>activity</strong></td><td><ul><li><p><em>Very low:</em> Largely speculative or based on outdated information. A very low level of confidence in activity assessments.</p></li><li><p><em>Low:</em> Limited or somewhat outdated sources. A low level of confidence in the activity assessments.</p></li><li><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in activity insights.</p></li><li><p><em>High:</em> Detailed and current operational data ensures a high level of confidence in the accuracy of activity assessments.</p></li><li><p><em>Very high:</em> Extensive, verified, and up-to-date data. A very high level of confidence in their accuracy.</p></li></ul></td><td>±8 to 15 % of production estimates</td></tr><tr class="odd"><td><strong>CO2_emissions_factor</strong></td><td><ul><li><p><em>Very low:</em> Highly uncertain due to insufficient or unreliable data.</p></li><li><p><em>Low:</em> Estimated from incomplete data. Low confidence level in its precision.</p></li><li><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in their accuracy.</p></li><li><p><em>High:</em> Derived from comprehensive and recent data. A high level of confidence in their precision.</p></li><li><p><em>Very high:</em> Based on extensive and validated data, providing a very high level of confidence in their precision.</p></li></ul></td><td>±10 to 12 % of assumption (based on IPCC)</td></tr><tr class="even"><td><strong>CH4_emissions_factor</strong></td><td>Not used; N/A</td><td>Not used; N/A</td></tr><tr class="odd"><td><strong>N2O_emissions_factor</strong></td><td>Not used; N/A</td><td>Not used; N/A</td></tr><tr class="even"><td><strong>CO2_emissions</strong></td><td><ul><li><p><em>Very low:</em> Based on very rough estimations or outdated information. A very low level of confidence in its accuracy.</p></li><li><p><em>Low:</em> Estimated from incomplete data. Low confidence level in its precision.</p></li><li><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in their accuracy.</p></li><li><p><em>High:</em> Derived from comprehensive and recent data. A high level of confidence in their precision.</p></li><li><p><em>Very high:</em> Based on extensive and validated data, providing a very high level of confidence in their precision.</p></li></ul></td><td>±13 to 20 % of emissions estimates</td></tr><tr class="odd"><td><strong>CH4_emissions</strong></td><td>Not used; N/A</td><td>Not used; N/A</td></tr><tr class="even"><td><strong>N2O_emissions</strong></td><td>Not used; N/A</td><td>Not used; N/A</td></tr><tr class="odd"><td><strong>total_CO2e_100yrGWP</strong></td><td><ul><li><p><em>Very low:</em> Based on very rough estimations or outdated information. A very low level of confidence in its accuracy.</p></li><li><p><em>Low:</em> Estimated from incomplete data. Low confidence level in its precision.</p></li><li><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in their accuracy.</p></li><li><p><em>High:</em> Derived from comprehensive and recent data. A high level of confidence in their precision.</p></li><li><p><em>Very high:</em> Based on extensive and validated data, providing a very high level of confidence in their precision.</p></li></ul></td><td>±20% of emissions estimates</td></tr><tr class="even"><td><strong>total_CO2e_20yrGWP</strong></td><td><ul><li><p><em>Very low:</em> Based on very rough estimations or outdated information. A very low level of confidence in its accuracy.</p></li><li><p><em>Low:</em> Estimated from incomplete data. Low confidence level in its precision.</p></li><li><p><em>Medium:</em> A mix of historical and more recent data. Medium level of confidence in their accuracy.</p></li><li><p><em>High:</em> Derived from comprehensive and recent data. A high level of confidence in their precision.</p></li><li><p><em>Very high:</em> Based on extensive and validated data, providing a very high level of confidence in their precision.</p></li></ul></td><td>±20% of emissions estimates</td></tr></tbody></table>

**Table 7.** Emissions reduction solutions for the steel sector. *Note: Only rank 1 strategies are provided for assets on the Climate TRACE website and additional strategies will be made available in future releases.*

| **native\_strategy\_id** | **strategy\_name**             | **strategy\_description**                                                                                                                                                                      | **mechanism** | **co2\_emissions\_factor\_new\_absolute** | **co2\_emissions\_factor\_new\_to\_old\_ratio** |
|--------------------------|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------|-------------------------------------------------|
| 0                        | Continue current operation     | Plants with very low CO2 emission per tonne of steel can continue with their current operation                                                                                                 |               |                                           | 1                                               |
| 1                        | 100% Scrap-EAF                 | Increase scrap steel content, eliminating process emissions from iron ore reduction                                                                                                            | resourcing    | 0.08                                      |                                                 |
| 2                        | H2-DRI/EAF\_100%\_green        | Replace natural gas in DRI production with 100% green hydrogen, fully eliminating fossil fuel emissions from iron reduction.                                                                   | retrofit      | 0.27                                      |                                                 |
| 3                        | BF/BOF + CCUS                  | Install CCUS for the CO2 produced in the process                                                                                                                                               | retrofit      |                                           | 0.41                                            |
| 4                        | Shut Down plant                | BF/BOF steel production is coal based and emissions intensive. There is currently global overcapacity that can be addressed by shutting down the most emissive plants and rerouting production | subtract      | 0                                         |                                                 |
| 5                        | Direct production towards EAF  | Small plants with both BF/BOF and EAF technology redirect their production to EAF (applicable to plants in China) due to relative lower emission factors                                       | retrofit      | 0.08                                      |                                                 |
| 6                        | Replace BF/BOF with H₂-DRI/EAF | Replace blast furnace production by DRI production with 100% green hydrogen, fully eliminating fossil fuel emissions from iron reduction.                                                      | retrofit      | 0.27                                      |                                                 |

**Permissions and Use:** All Climate TRACE data is freely available under the Creative Commons Attribution 4.0 International Public License, unless otherwise noted below.

> **Citation format:** Crane, V. and Ebri, G. (2026). *Manufacturing and Industrial Processes sector - Iron & Steel Manufacturing Emissions*. TransitionZero, UK, Climate TRACE Emissions Inventory - [<span class="underline">https://climatetrace.org</span>](https://climatetrace.org)

The above usage is not warranted to be error free and does not imply the expression of any opinion whatsoever on the part of Climate TRACE Coalition and its partners concerning the legal status of any country, area or territory or of its authorities, or concerning the delimitation of its borders.

> **Disclaimer:** The emissions provided for this sector are our current best estimates of emissions, and we are committed to continually increasing the accuracy of the models on all levels. Please review our terms of use and the sector-specific methodology documentation before using the data. If you identify an error or would like to participate in our data validation process, please [<span class="underline">contact us</span>](mailto:coalition@climatetrace.org).

**6. References**
=================

1.  Ember (2025) ‘*Regional grid intensity retrieved from: Monthly Electricity Data’*, Ember. Available at: [<span class="underline">https://ember-energy.org/data/monthly-electricity-data/</span>](https://ember-energy.org/data/monthly-electricity-data/)

2.  EEA (2025) ‘*Total GHG emissions and removals in the EU’,* European Environment Agency. Available at: [<span class="underline">https://www.eea.europa.eu/en/datahub/datahubitem-view/3b7fe76c-524a-439a-bfd2-a6e4046302a2</span>](https://www.eea.europa.eu/en/datahub/datahubitem-view/3b7fe76c-524a-439a-bfd2-a6e4046302a2)

3.  ESA (2025) ‘*Satellite images data retrieved from: Copernicus Sentinel-2 ESA*’, European Space Agency. Available at: [<span class="underline">https://www.esa.int/Applications/Observing\_the\_Earth/Copernicus/Sentinel-2</span>](https://www.esa.int/Applications/Observing_the_Earth/Copernicus/Sentinel-2)

4.  GEM (2025) ‘*Steel inventory data retrieved from: The Global Iron and Steel Tracker*’, Global Energy Monitor. Available at: [<span class="underline">https://globalenergymonitor.org/projects/global-iron-and-steel-tracker/</span>](https://globalenergymonitor.org/projects/global-iron-and-steel-tracker/)

5.  Google Earth Engine (2025a) *Landsat 8 Datasets in Earth Engine*, *Google Developers*. Available at: [<span class="underline">https://developers.google.com/earth-engine/datasets/catalog/landsat-8</span>](https://developers.google.com/earth-engine/datasets/catalog/landsat-8)

6.  Google Earth Engine (2025b) *Landsat 9 Datasets in Earth Engine*, *Google Developers*. Available at: [<span class="underline">https://developers.google.com/earth-engine/datasets/catalog/landsat-9</span>](https://developers.google.com/earth-engine/datasets/catalog/landsat-9)

7.  Google Earth Engine (2025c) *Sentinel-2 Datasets in Earth Engine*, *Google Developers*. Available at: [<span class="underline">https://developers.google.com/earth-engine/datasets/catalog/sentinel-2</span>](https://developers.google.com/earth-engine/datasets/catalog/sentinel-2)

8.  Google Maps contributors (2025) ‘*Steel inventory data retrieved from: Google Maps*’. Google. Available at: [<span class="underline">https://www.google.co.uk/maps</span>](https://www.google.co.uk/maps)

9.  IEA (2020) ‘*Iron and Steel Technology Roadmap - Towards more sustainable steelmaking*’. International Energy Agency.

10. Liangrocapart, S., Khetkeeree, S. and Petchthaweetham, B. (2020) ‘*Thermal Anomaly Level Algorithm for Active Fire Mapping by Means of Sentinel-2 Data*’, in 2020 17th International Conference on Electrical Engineering/Electronics, Computer, Telecommunications and Information Technology (ECTI-CON).

11. Marchese, F. *et al.* (2019) ‘*A Multi-Channel Algorithm for Mapping Volcanic Thermal Anomalies by Means of Sentinel-2 MSI and Landsat-8 OLI Data*’, Remote Sensing, 11(23), p. 2876. Available at: [<span class="underline">https://doi.org/10.3390/rs11232876</span>](https://doi.org/10.3390/rs11232876)

12. MPP (2024), ‘*Steel emissions factor retrieved from: MPP*’, Mission Possible Partnership Steel Transition Strategy. Available at: [<span class="underline">https://www.missionpossiblepartnership.org/action-sectors/steel/</span>](https://www.missionpossiblepartnership.org/action-sectors/steel/)

13. NASA (2018) ‘Band Pass Adjustment’, National Aeronautics and Space Administration. Available at: [<span class="underline">https://hls.gsfc.nasa.gov/algorithms/bandpass-adjustment/</span>](https://hls.gsfc.nasa.gov/algorithms/bandpass-adjustment/) (Accessed: 1 June 2024).

14. NASA and USGS (2025a) ‘Satellite images data retrieved from: Landsat-8 NASA/USGS’, National Aeronautics and Space Administration and United States Geological Survey. Available at: [<span class="underline">https://www.usgs.gov/landsat-missions/landsat-8</span>](https://www.usgs.gov/landsat-missions/landsat-8)

15. NASA and USGS (2025b) ‘Satellite images data retrieved from: Landsat-9 NASA/USGS’, National Aeronautics and Space Administration and United States Geological Survey. Available at: [<span class="underline">https://www.usgs.gov/landsat-missions/landsat-9</span>](https://www.usgs.gov/landsat-missions/landsat-9)

16. NBSC (2025) ‘*Chinese steel production data retrieved from: NBSC*’, National Bureau of Statistics of China. Available at: [<span class="underline">http://www.stats.gov.cn/english/</span>](http://www.stats.gov.cn/english/)

17. OpenStreetMap (2025) ‘*Steel inventory data retrieved from: OpenStreetMap*’. OpenStreetMap. Available at: [<span class="underline">https://www.openstreetmap.org/</span>](https://www.openstreetmap.org/)

18. US EPA (2025) ‘*Steel emissions data retrieved from: US EPA’*, United States Environmental Protection Agency. Available at: [<span class="underline">https://www.epa.gov/</span>](https://www.epa.gov/)

19. WSA (2024) ‘*Steel production data retrieved from: Worldsteel*’, Worldsteel Association. Available at: [<span class="underline">https://worldsteel.org/wp-content/uploads/World-Steel-in-Figures-2024.pdf</span>](https://worldsteel.org/wp-content/uploads/World-Steel-in-Figures-2024.pdf)

20. Yongxue, L., Weifeng, Z., Bihua, X., Wenxuan, X., Wei, W. (2021) ‘*Detecting high-temperature anomalies from Sentinel-2 MSI images*’, [ISPRS Journal of Photogrammetry and Remote Sensing](https://www.sciencedirect.com/journal/isprs-journal-of-photogrammetry-and-remote-sensing), [177](https://www.sciencedirect.com/journal/isprs-journal-of-photogrammetry-and-remote-sensing/vol/177/suppl/C), p. 174-193, Available at: [<span class="underline">https://doi.org/10.1016/j.isprsjprs.2021.05.00</span>](https://doi.org/10.1016/j.isprsjprs.2021.05.008)

21. Zhou, Y. *et al.* (2018) ‘*A Method for Monitoring Iron and Steel Factory Economic Activity Based on Satellites*’, Sustainability, 10(6), p. 1935. Available at: [<span class="underline">https://doi.org/10.3390/su10061935</span>](https://doi.org/10.3390/su10061935)

22. IPCC (2006) *Chapter 4: Metal Industry Emissions*, in *2006 IPCC Guidelines for National Greenhouse Gas Inventories, Volume 3: Industrial Processes and Product Use*. Available at: [<span class="underline">https://www.ipcc-nggip.iges.or.jp/public/2006gl/pdf/3\_Volume3/V3\_4\_Ch4\_Metal\_Industry.pdf</span>](https://www.ipcc-nggip.iges.or.jp/public/2006gl/pdf/3_Volume3/V3_4_Ch4_Metal_Industry.pdf?utm_source=chatgpt.com) (Accessed: 15 Aug 2025)

23. WSA (2024b) *Sustainability Indicators – 2024 report: Sustainability performance of the steel industry 2003-2023*, World Steel Association. Available at: [<span class="underline">https://worldsteel.org/wp-content/uploads/Sustainability-Indicators-report-2024.pdf</span>](https://worldsteel.org/wp-content/uploads/Sustainability-Indicators-report-2024.pdf?utm_source=chatgpt.com) (Accessed: 15 Aug 2025).

24. Fan, Z. and Friedmann, S.J. (2021) Low-Carbon Production of Iron & Steel: Technology Options, Economic Assessment, and Policy. Center on Global Energy Policy, Columbia University. Available at: [<span class="underline">https://www.energypolicy.columbia.edu/publications/low-carbon-production-iron-steel-technology-options-economic-assessment-and-policy/</span>](https://www.energypolicy.columbia.edu/publications/low-carbon-production-iron-steel-technology-options-economic-assessment-and-policy/?utm_source=chatgpt.com) (Accessed: 30 August 2025).

25. Millner R., Rothberger J., Rammer B., Boehm C., Sterrer W., Ofner H., Chevrier V. (2021), MIDREX H2 — The Road to CO2-Free Iron and Steelmaking. Proceedings of AISTech.

26. Trinca, A., Patrizi, D., Verdone, N., Bassano, C. and Vilardi, G., (2023). Toward green steel: Modeling and environmental economic analysis of iron direct reduction with different reducing gases. Journal of Cleaner Production, 427, p.139081.

27. The Institution of Structural Engineers (IStructE), BCSA and Climate Group (2025). The role of scrap in steel decarbonization: key facts and considerations for the construction sector. London: The Institution of Structural Engineers. Available at: https://www.istructe.org/resources/guidance/the-role-of-scrap-in-steel-decarbonisation/ (Accessed: 15 Aug 2025)

28. HYBRIT (2024). Fossil-free steel production ready for industrialization. HYBRIT brochure. Available at: [<span class="underline">https://www.hybritdevelopment.se/wp-content/uploads/2024/08/hybrit-broschure-fossil-free-steel-production-ready-for-industrialisation.pdf</span>](https://www.hybritdevelopment.se/wp-content/uploads/2024/08/hybrit-broschure-fossil-free-steel-production-ready-for-industrialisation.pdf) (Accessed: 22 Sep 2025).

29. Salzgitter AG. (2022). “Hydrogen: Decarbonizing Steel Production” (SALCOS technical report). Available at: [<span class="underline">https://www.salzgitter-ag.com/fileadmin/footage/MEDIA/SZAG\_microsites/salcos/STIL-02-19-SpecialPrint-Salcos-Hydrogen-en.pdf</span>](https://www.salzgitter-ag.com/fileadmin/footage/MEDIA/SZAG_microsites/salcos/STIL-02-19-SpecialPrint-Salcos-Hydrogen-en.pdf) (Accessed: 22 Sep 2025).

30. Bhaskar, A., Abhishek, R., Assadi, M. and Somehesaraei, H.N., 2022. Decarbonizing primary steel production: Techno-economic assessment of a hydrogen based green steel production plant in Norway. Journal of Cleaner Production, 350, p.131339.

31. Nicholas, S., & Basirat, S. (2024). Carbon capture for steel? Institute for Energy Economics and Financial Analysis. [<span class="underline">https://ieefa.org/sites/default/files/2024-04/Carbon%20capture%20for%20steel-April24.pdf</span>](https://ieefa.org/sites/default/files/2024-04/Carbon%20capture%20for%20steel-April24.pdf). (Accessed: 22 Sep 2025)

32. GEM (2024). Pedal to the Metal 2024: Building Momentum for Iron and Steel Decarbonization. Global Energy Monitor. Available at: [<span class="underline">https://globalenergymonitor.org/wp-content/uploads/2024/07/GEM-Pedal-to-the-Metal-2024-steel-iron-report.pdf</span>](https://globalenergymonitor.org/wp-content/uploads/2024/07/GEM-Pedal-to-the-Metal-2024-steel-iron-report.pdf). (Accessed: 25 September 2025).

**7. Appendices**
=================

**7.1. Appendix 1: Overview of the steel production process**
-------------------------------------------------------------

The principal inputs to steelmaking today are iron ore, energy, limestone and scrap. Iron ore and scrap are used to provide the metallic charge, with scrap having a much higher metallic concentration than iron ore. Energy inputs provide heat to melt the metallic input, and in the case of iron ore, to chemically remove oxygen. Limestone is used at various stages of the steelmaking process to help remove impurities. [Figure](#bookmark=id.2u6wntf) 8 highlights these main routes to produce steel.

[<img src="figures/figure9.png" style="width:6.4552in;height:4.00521in" />](#bookmark=id.19c6y18)  
**Figure 8** Steel production routes - adapted from IEA (2020).
