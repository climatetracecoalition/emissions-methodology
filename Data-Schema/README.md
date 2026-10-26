### Climate TRACE Inventory November 2025 (Version 5.0.0)

**Data Licensing, Schema, and Citation Guide**

**Permissions and Use:** All Climate TRACE data is freely available under the Creative Commons Attribution 4.0 International Public License, unless otherwise noted below.

**Suggested citation format:** For sources from different sectors or global data accessed and downloaded, please cite as: Climate TRACE (2025), Climate TRACE Emissions Inventory v5.0.0, <https://climatetrace.org> [Date Accessed]. For sector-specific citations, see below.

**Disclaimer:** The emissions models provide our current best estimates of emissions, and we are committed to continually increasing the accuracy of the models on all levels. Please review our terms of use (https://climatetrace.org/terms) and the sector-specific methodology documentation (https://climatetrace.org/downloads) before using the data. If you identify an error or would like to participate in our data validation process please contact us (coalition@climatetrace.org).

#### Files available

| File | Description |
|---|---|
| `detailed_data_schema.csv` | File with the mapping and explanation of what each data column means for all various subsectors. |
| `<subsector-name>_emissions_sources.csv` | File containing the emissions data at the emissions source level across all subsectors monitored by Climate TRACE. |
| `<subsector-name>_country_emissions.csv` | File containing the emissions data at the country level across all subsectors monitored by Climate TRACE. |
| `<subsector-name>_emissions_sources_confidence.csv` | File specifying the confidence classification of the reported data from emissions sources present on the file &lt;subsector-name&gt;_emissions_sources.csv |
| `<subsector-name>_emissions_sources_ownership.csv` | File containing the ownership information of the emissions sources on the file &lt;subsector-name&gt;_emissions_sources.csv |
| `ers_plan_global.zip` | File containing the emission reduction solutions for all subsectors globally |

A full list of emissions sectors that Climate TRACE provides data for, is available on the website at <https://climatetrace.org/sectors>. For some sectors, Climate TRACE has geospatial data beyond what is included in this download package. To request that data, please contact us (coalition@climatetrace.org) .

#### v5.0.0 updates to the Climate TRACE inventory

| Update | Details |
|---|---|
| Data on emission reduction solutions | For more information on the new tool, please see the methodology documentation: <https://github.com/climatetracecoalition/emissions-methodology/tree/main/Sector-Methodologies/2-Cross-Cutting/emissions-reducing-solutions> |
| See changelog for all sector-specific and Climate TRACE-wide updates | <https://github.com/climatetracecoalition/emissions-methodology/tree/main/Changelogs/V5.X/2025-11_v5.0.0> |

#### Metadata description for: `<subsector-name>_emissions_sources.csv`

| Data attribute | Definition |
|---|---|
| `source_id` | The internal Climate TRACE identifier for each individual source of emissions. Every distinct emissions source is defined by a unique combination of facility name, country, source type, and subsector. |
| `source_name` | Name of the entity or source that produced the emissions. Where exact names were not available, Climate TRACE has created descriptive names based on source location. |
| `source_type` | Description of the emission source classification. |
| `iso3_country` | Corresponds to the ISO 3166-1 alpha-3 specification of the country where the entity is physically located. |
| `sector` | The high level sector that the subsectors fall under (i.e. Agriculture, Mineral Extraction, etc.) |
| `subsector` | The more granular sector name for the emissions being measured (i.e. rice-cultivation, copper-mining, etc.) |
| `start_time` | The time using Coordinated Universal Time (UTC) of emissions, either as an instance of start time of observation. |
| `end_time` | The time using Coordinated Universal Time (UTC) of emissions, either as an instance of end time of observation. |
| `lat` | Approximate latitude location of the source. When source is an aggregation of smaller emissions sources (e.g county, urban area etc), the latitude centroid of the geometry is provided. |
| `lon` | Approximate longitude location of the source. When source is an aggregation of smaller emissions sources (e.g county, urban area etc), the latitude centroid of the geometry is provided. |
| `geometry_ref` | Corresponds to the reference id in the global geopackage at climatetrace.org/data. This id allows matching an aggregated emission source with its boundary geometry. |
| `gas` | Air emissions which are reported in metric tonnes. Climate TRACE reports greenhouse gas emissions from Carbon Dioxide (CO2), Methane (CH4) and Nitrous oxide (N2O) as well as all three gases combined and expressed in CO2-equivalents are available (100 year and 20 year time frame using IPCC Sixth Assessment Report (AR6) Global Warming Potentials). Climate TRACE reports the air pollutants: Particulate Matter (PM2.5), Black Carbon (BC), and Organic Carbon (OC), sulphur dioxide (SO2), Volatile Organic Compounds (VOCs), Carbon Monoxide (CO), Ammonia (NH3), and Nitrogen Oxides (NOx). |
| `emissions_quantity` | Quantity of gas emitted in metric tonnes. If reported quantity is zero, it means that gas is not emitted. If reported quantity is empty/null/N-A, data is not yet available. |
| `temporal_granularity` | Resolution of the data available. |
| `activity` | Activity of the entity producing the emissions, not including units. See definition of "capacity". Activity data are not available for some subsectors due to licensing restrictions. |
| `activity_units` | Units of reported "activity". Climate TRACE used SI base units and standard abbreviations when possible. <https://www.nist.gov/pml/owm/metric-si/si-units> |
| `emissions_factor` | Emissions factor of reported activity. Emissions factors vary by sector, subsector, and source type. Emission factors data are not available for some subsectors due to licensing restrictions. |
| `emissions_factor_units` | Units of reported "emissions factor" field. Climate TRACE used SI base units and standard abbreviations when possible. <https://www.nist.gov/pml/owm/metric-si/si-units> |
| `capacity` | Capacity of the entity producing emissions, not including units. Because 'capacity' has different definitions in different sectors. Please see the capacity units column for detailed information. |
| `capacity_units` | Units of reported "capacity" field. Climate TRACE used SI base units and standard abbreviations when possible. <https://www.nist.gov/pml/owm/metric-si/si-units> |
| `capacity_factor` | Corresponds to the ratio of the actual source output (activity) to the source capacity. When data not available, this is not relevant for the subsector. |
| `capacity_factor_units` | Units of reported "capacity_factor" field. If units are not available, this is not relevant for the subsector. |
| `other1` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other1_def. When this field is null,blank or na, no additional data is provided to the subsector. |
| `other1_def` | Definition of reported data of Other1 field. |
| `other2` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other2_def. When this field is null, blank or na, no additional data is provided to the subsector. |
| `other2_def` | Definition of reported data of Other2 field. |
| `other3` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other3_def. When this field is null, blank or na, no additional data is provided to the subsector. |
| `other3_def` | Definition of reported data of Other3 field. |
| `other4` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other4_def. When this field is null, blank or na, no additional data is provided to the subsector. |
| `other4_def` | Definition of reported data of Other4 field. |
| `other5` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other5_def. When this field is null, blank or na, no additional data is provided to the subsector. |
| `other5_def` | Definition of reported data of Other5 field. |
| `other6` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other6_def. When this field is null, blank or na, no additional data is provided to the subsector. |
| `other6_def` | Definition of reported data of Other6 field. |
| `other7` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other7_def. When this field is null, blank or na, no additional data is provided to the subsector. |
| `other7_def` | Definition of reported data of Other7 field. |
| `other8` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other8_def. When this field is null, blank or na, no additional data is provided to the subsector. |
| `other8_def` | Definition of reported data of Other8 field. |
| `other9` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other9_def. When this field is null, blank or na, no additional data is provided to the subsector. |
| `other9_def` | Definition of reported data of Other9 field. |
| `other10` | Additional data field available for the subsector. For description of this field and its meaning, please reference to other10_def. When this field is null, blank or na, no additional data is provided to the subsector. |
| `other10_def` | Definition of reported data of Other10 field. |
| `created_date` | Date emissions source was added to the Climate TRACE database. |
| `modified_date` | Last date on which any updates were made to the dataset for the specific source. |

#### Metadata description for: `<subsector-name>_country_emissions.csv`

| Data attribute | Definition |
|---|---|
| `iso3_country` | Corresponds to the ISO 3166-1 alpha-3 code for the country. |
| `start_time` | The time using Coordinated Universal Time (UTC) of emissions, either as an instance of start time of observation. |
| `end_time` | The time using Coordinated Universal Time (UTC) of emissions, either as an instance of end time of observation. |
| `sector` | The high level sector that the subsectors fall under (i.e. Agriculture, Mineral Extraction, etc.) |
| `subsector` | The more granular sector name for the emissions being measured (i.e. rice-cultivation, copper-mining, etc.) |
| `gas` | Air emissions which are reported in metric tonnes. Climate TRACE reports greenhouse gas emissions from Carbon Dioxide (CO2), Methane (CH4) and Nitrous oxide (N2O) as well as all three gases combined and expressed in CO2-equivalents are available (100 year and 20 year time frame using IPCC Sixth Assessment Report (AR6) Global Warming Potentials). Climate TRACE reports the following air pollutants: Particulate Matter (PM2.5), Black Carbon (BC), and Organic Carbon (OC), sulphur dioxide (SO2), Volatile Organic Compounds (VOCs), Carbon Monoxide (CO), Ammonia (NH3), and Nitrogen Oxides (NOx). |
| `emissions_quantity` | Quantity of gas emitted in metric tonnes. If reported quantity is zero, it means that gas is not emitted. If reported quantity is empty/null/N-A, data is not yet available. |
| `emissions_quantity_units` | Units of reported "emissions_quantity" field. Climate TRACE used SI base units and standard abbreviations when possible. <https://www.nist.gov/pml/owm/metric-si/si-units> |
| `temporal_granularity` | Resolution of the data available. |
| `created_date` | Date country emissions quantity was added to the Climate TRACE database. |
| `modified_date` | Last date on which any updates were made to the dataset for the specific country. |

#### Metadata description for: `<subsector-name>_confidence.csv`

| Data attribute | Definition |
|---|---|
| `source_id` | The internal Climate TRACE identifier for each individual source of emissions. Every distinct source is defined by a unique combination of facility name, country, source type, and subsector. |
| `source_name` | Name of the entity or source that produced the emissions. Where exact names were not available, Climate TRACE has created descriptive names based on source location. |
| `iso3_country` | Corresponds to the ISO 3166-1 alpha-3 specification of the country where the entity is physically located. |
| `sector` | The high level sector that the subsectors fall under (i.e. Agriculture, Mineral Extraction, etc.) |
| `subsector` | The more granular sector name for the emissions being measured (i.e. rice-cultivation, copper-mining, etc.) |
| `start_time` | The time using Coordinated Universal Time (UTC) of emissions, either as an instance of start time of observation. |
| `end_time` | The time using Coordinated Universal Time (UTC) of emissions, either as an instance of end time of observation. |
| `source_type` | Qualitative confidence level for the emissions source type classification data available on the file &lt;subsector-name&gt;_emissions_sources.csv, when type data is reported. Entries that are available are: "very high","high","medium","low" and "very low". |
| `capacity` | Qualitative confidence level for the emissions source capacity data available on the file &lt;subsector-name&gt;_emissions_sources.csv, when capacity data is reported. Entries that are available are: "very high","high","medium","low" and "very low". |
| `capacity_factor` | Qualitative confidence level for the emissions source capacity factor data available on the file &lt;subsector-name&gt;_emissions_sources. csv, when capacity factor data is reported. Entries that are available are: "very high","high","medium","low" and "very low". |
| `activity` | Qualitative confidence level for the emissions source activity data available on the file &lt;subsector-name&gt;_emissions_sources.csv, when activity data is reported. Entries that are available are: "very high","high","medium","low" and "very low". |
| `[gas]_emissions_factor` | Qualitative confidence level for the emissions source [gas] emissions factor data available on the file &lt;subsector-name&gt;_emissions_sources.csv, when [gas] emissions factor data is reported. Entries that are available are: "very high","high"," medium","low" and "very low". |
| `[gas]_emissions` | Qualitative confidence level for the emissions source [gas] emissions data available on the file &lt;subsector-name&gt;_emissions_sources.csv, when [gas] emissions data is reported. Entries that are available are: "very high","high","medium"," low" and "very low". |
| `total_co2e_100gwp` | Qualitative confidence level for the emissions source carbon dioxide equivalent on 100 year global warming potential (co2e_100gwp) emissions data available on the file &lt;subsector-name&gt;_emissions_sources.csv, when co2e_100gwp emissions data is reported. Entries that are available are: "very high","high","medium","low" and "very low". |
| `total_co2e_20yrgwp` | Qualitative confidence level for the emissions source carbon dioxide equivalent on 20 year global warming potential (co2e_20gwp) emissions data available on the file &lt;subsector-name&gt;_emissions_sources.csv, when co2e_20gwp emissions data is reported. Entries that are available are: "very high","high","medium","low" and "very low". |
| `created_date` | Date emissions source was added to the Climate TRACE database. |
| `modified_date` | Last date on which any updates were made to the dataset for the specific emissions source. |

#### Metadata description for: `<subsector-name>_emissions_sources_ownership.csv`

| Data attribute | Definition | Format |
|---|---|---|
| `parent_name` | Name of parent entity | text |
| `parent_entity_id` | TRACE ID for parent entity | text |
| `parent_entity_type` | Whether the parent entity is a legal entity, arrangement, state, state body, or unknown | text |
| `parent_lei` | GLEIF Legal Entity Identifier for parent entity | text |
| `parent_permid` | Refinitive PermID for parent entity | text |
| `parent_registration_country` | Country of jurisdiction for the entity | text |
| `parent_headquarter_country` | Country where the entity is headquartered | text |
| `overall_share_percent` | Share percent from multiplying all the share percentages in the ownership_path together | float |
| `ownership_path` | Shortest ownership path between the entity and the asset | text |
| `ownership_path_datasource_ids` | List of datasources used to map ownership path | list |
| `immediate_source_owner` | Entity that directly owns the asset | text |
| `immediate_source_owner_entity_id` | TRACE ID for immediate source owner | text |
| `source_operator` | Entity that operates the asset | text |
| `source_operator_id` | TRACE ID for entity that operates the emission source | text |
| `source_id` | The internal Climate TRACE identifier for each individual source of emissions. Every distinct source is defined by a unique combination of facility name, country, source type, and subsector. | text |
| `source_name` | Name of the entity or source that produced the emissions. Where exact names were not available, Climate TRACE has created descriptive names based on source location. | text |
| `source_sector` | source sector | text |
| `source_subsector` | source subsector | text |

#### Metadata description for: `ers_plan_global.zip`

| Data attribute | Definition |
|---|---|
| `source_id` | The internal Climate TRACE identifier for each individual source of emissions. Every distinct source is defined by a unique combination of facility name, country, source type, and subsector. |
| `source_name` | Name of the entity or source that produced the emissions. Where exact names were not available, Climate TRACE has created descriptive names based on source location. |
| `iso3_country` | Corresponds to the ISO 3166-1 alpha-3 specification of the country where the entity is physically located. |
| `original_inventory_sector` | The more granular sector name for the emissions being measured (i.e. rice-cultivation, copper-mining, etc.) |
| `strategy_id` | The internal Climate TRACE identifier for a strategy that can be applied to multiple sources. Each strategy_name may have multiple strategy_ids. |
| `strategy_name` | A short human-readable name for the strategy. This can be repeated for multiple strategy IDs. |
| `total_emissions_reduced_per_year` | Total emissions reduced per year including any negative impacts from consequential increased emissions in a different sector. |
| `gas` | GHG emissions which are reported in metric tonnes. For the ers, all data are represented in CO2-equivalents (100 years). |
| `strategy_description` | A longer description of the strategy, maximum 280 characters. This can contain more detailed information about the strategy. |
| `difficulty_score` | The difficulty score reflects the potential impact, effort, and capital cost required to implement an emissions reduction solution – lower scores indicate easier, more practical options, while higher scores represent more complex or resource-intensive ones. |

#### Recommended citation format for data from a specific sector

| Sector | Subsector | Citation |
|---|---|---|
| Power | Electricity generation | Freeman, J., Rouzbeh Kargar, A., Couture, H., Jeyaratnam, J., Lewis, J., Alvara, M., Koenig, H., Nakano, T., Davitt, A., Lewis, C., and McCormick, G.(2025). Power sector: Emissions from Electricity Generation. WattTime, USA Pixel Scientia Labs, USA and Global Energy Monitor, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Heat Plants | Freeman, J., Sridhar, L., and Alvara, M. (2025). Power sector- Emissions from Heat Plants. WattTime, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
| Buildings | Residential and Non-Residential Onsite Fuel Usage | Markakis, P., Gowdy, T.M., Sheng, Z., Lancellotti, B., Malof, J.M., and Bradbury, K. (2025). Building sector: Estimating Global, High-resolution Onsite Building Emissions. Nicholas Institute for Energy, Environment & Sustainability, Duke University, Dept. of Electrical & Computer Engineering, Duke University; and Dept. of Electrical Engineering and Computer Science, University of Missouri, USA, Climate TRACE Emissions Inventory. https://climatetrace.org\[Accessed date\] |
| Manufacturing | Iron and Steel | Crane, V. and Ebri, G., (2025). Manufacturing and Industrial Processes sector: Iron & Steel Manufacturing Emissions. TransitionZero, UK, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Cement | Crane, V. and Ebri, G., (2025). Manufacturing and Industrial Processes sector: Cement Manufacturing Emissions. TransitionZero, UK, Climate TRACE Emissions Inventory. https://climatetrace.org\[Accessed date\] |
|  | Aluminum | Crane, V., Ebri, G., Underwood, C., and Heal, J. (2025). Manufacturing and Industrial Processes sector: Aluminium Production Emissions. TransitionZero, UK, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Chemicals and Pulp and Paper | Crane, V., Ebri, G., Galib, K.M., and Underwood, C. (2025). Manufacturing and Industrial Processes sector: Chemicals, and Pulp and Paper Emissions. TransitionZero, UK, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Petrochemicals Steam Cracking | Peltier, M., Fallurin, J., Wang, J., Conway, TJ, and Gordon, D. (2025). Manufacturing and Industrial Processes sector: Petrochemical Ethylene Steam Cracker Emissions. RMI, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
| Transport | Domestic and international shipping, Non-broadcasting vessels | Mayes, B., Thomas, T., Masanova, M., Tuckerman, M., Powell, M., Knights, D., Schofield, M., and Mackereth, T. (2025). Transportation sector: Domestic and International Shipping Emissions. OceanMind, UK and the University of Minnesota, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\]<br><br>McDonald, G., Kroodsma, D., Carbo-Mestre, P., Powell, M., and Wei, Z. (2025), Transportation sector: Emissions From Non Broadcasting Vessels. Global Fishing Watch (GFW) and the Environmental Markets Lab (emLab) at the University of California, Santa Barbara, USA, Climate TRACE Emissions Inventory. https://climatetrace.org\[Accessed date\] |
|  | Domestic and international aviation | Saraswat, I. (2025). Transportation sector: Domestic and International Aviation Emissions. WattTime, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Road Transportation | Kott, T., Foster, K., Villafane-Delgado, M., Loschen, W., Sicurello, P., Ghebreselassie, M., Reilly, E., and Hughes, M. (2025). Transportation Sector - Global Road Emissions. The Johns Hopkins University Applied Physics Laboratory (JHU/APL), USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
| Fossil Fuel Operations | Oil and gas production and transport | Schmeisser, L., Chaney, C., Tecza, A., Stanger, J., Bylsma, S., Delang, M., Gauthier, K., and Gordon, D. (2025). Fossil Fuel Operations Sector: Oil and Gas Production and Transport Emissions. RMI, USA, Climate TRACE Emissions Inventory. https://climatetrace.org\[Accessed date\] |
|  | Oil Refining | Wang, J., Fallurin, J., Peltier, M., Conway, TJ, and Gordon, D. (2025). Fossil Fuel Operations Sector: Refining Emissions, RMI, USA, Climate TRACE Emissions Inventory. https://climatetrace.org\[Accessed date\] |
|  | Coal Mining | Lewis, C., Tate, R.D., Mei, D.L. and Piscopo, P., (2025). Fuel Operations sector: Coal Mining Emissions Methodology. WattTime and Global Energy Monitor, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
| Mineral Extraction | Bauxite mining, copper mining, iron mining. rock and sand quarrying | Jolleys, M., (2025). Mineral Extraction sector: Mining and Quarrying Emissions from Copper, Iron, Bauxite, Rock and Sand, Hypervine, UK, Climate TRACE Emissions Inventory. https://climatetrace.org\[Accessed date\] |
| Agriculture | Rice cultivation | Rudiyanto, Minasny, B., Powell, V., and Schiller, S. (2025). Rice Cultivation Emissions Estimates using Sentinel-1A/B and -2A/B. Universiti Malaysia Terengganu, Malaysia and the University of Sydney, Australia, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Enteric fermentation and Manure management (cattle operations, source-level) | Davitt, A., Tesser, D., Boyda, E., Pawar, A., Al Akkad, O., Tulloch, P., Tulloch, A., Schiller, S., Betz, L., Sridhar, L., and Sagan, V. (2025). Enteric fermentation and manure management emissions from feedlots and dairies. WattTime, Dept. of Earth, Environmental and Geospatial Science, Saint Louis Univ., Earth Genome, USA and Machine Learning and Env., Applied Research Consultant- Ottawa, Canada, Climate TRACE Emissions Inventory. https://climatetrace.org\[Accessed date\] |
|  | Enteric fermentation and Manure management (cattle operations, country-level) | Davitt, A., Tulloch, A., Thomas, P., Piscopo, A., and Schiller, S. (2025). Agriculture sector- Country-level Enteric fermentation and Manure Management Emissions Estimates from Cattle Operations. WattTime, USA and Carbon Yield, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Enteric fermentation and Manure management (pastures) | Haireti, A., Sagan, V., Tesser, V., Davitt, A., Sridhar, L., and Betz, L. (2025): Agriculture sector- Cattle Emissions from Enteric Fermentation and Manure Left on Pasture. Remote Sensing Lab, Saint Louis University, St. Louis, USA, and WattTime, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Synthetic Fertilizers, Crop Residue, Manure-applied-to-soils | Sharma, P. Trivedi, R., and Basso, B. (2025). Agriculture sector: Emissions from Synthetic Fertilizers, Crop Residue, and Manure Application. Department of Earth and Environmental Sciences, Michigan State University, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
| Waste | Wastewater Treatment | Anderson, S., Collins, G., Jain, A., Tulloch, P., Sicurello, Chen, A., Sridhar, L., Piatko, C., Reilly, E., (2025). Waste sector: Emissions from Wastewater Treatment Plants. The Johns Hopkins University Applied Physics Laboratory (JHU/APL), USA, Imperial College London, UK, Machine Learning and Env., Applied Research Consultant, CAN, and WattTime, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Solid Waste Disposal | Runyan, H., Wu, Y., Scheinwald, A., Wang, Y., Frankiewicz, T., McGrath, J., and Raniga, K., (2025). Waste Sector: Estimating CH4 Emissions from Solid Waste Disposal Sites. RMI, USA and WattTime, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
| Forestry and Land Use | Water Reservoirs | Hunter, H., Robinette, M., Brown, N., Sridhar, L., Lewis, C., and Reilly, E. (2025). Forestry and Land Use Change sector: Emissions from Reservoirs. The Johns Hopkins University Applied Physics Laboratory (JHU/APL), USA, and WattTime, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  | Net forest, grassland and wetland emissions | Saatchi, S., Yang, Y. and Ling, W., (2025). Forestry and Land Use Change sector: Net Forest & Mangrove, Net Grassland, and Net Wetland Carbon Stock Change - Living Biomass. CTrees, USA, Climate TRACE Emissions Inventory. https://climatetrace.org\[Accessed date\] |
| Other Sectors |  | Moore, D., Lewis, C., Sridhar, L., Piscopo, A., Betz, L., Raniga, K., Doctor, Z, and McCormick, G. (2025). Data-Informed Disaggregation and Implicit Estimation of Emissions in Other Sub-sectors. WattTime, USA, Climate TRACE Emissions Inventory. https://climatetrace.org\[Accessed date\] |
| Post Processing for Global Emissions and Metadata Completeness |  | Collins, G., D., Nellis, Raniga, K., Brown, N., Pekala, M, Doctor, Z., Moore, D., Thomas, Reilly, E., Hughes, M., McCormick, G. (2025), Spatial Disaggregation of Spatially Uncertain Emissions. WattTime, USA, and The Johns Hopkins University Applied Physics Laboratory (JHU/APL), USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  |  | Moore, D., Raniga, K., Doctor, Z., Lewis, C., Sridhar, L., Thomas, P., Saraswat, I., Betz, L., Piscopo, A., Collins, G., D., Nellis, A., Brown, N., Pekala, M, Rokisky, J., Reilly, E., Hughes, M., McCormick, G. (2025), Completeness of Bottom-up Emissions Estimates and Associated Metadata. WattTime, USA, and The Johns Hopkins University Applied Physics Laboratory (JHU/APL), USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
|  |  | Raniga, K., Betz, L., Doctor, Z., Kouch, A., Lewis, C., Moore, D., Piscopo, A., Russo, A., Saraswat, I., So, T., Sridhar, L., Thomas, P., and M., McCormick, G. (2025). Emissions-Reducing Solutions Framework for Climate TRACE. WattTime, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
| Non GHG emissions |  | Collins, G., Robinette, M., Sridhar, L., Reilly, E., Maranchi, J., and Hughes, M. (2025), Non-Greenhouse Gas Emissions Estimates Across Sectors. The Johns Hopkins University Applied Physics Laboratory (JHU/APL), USA, and WattTime, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |
| Asset Ownership | Source ownership | Mowat, A., Louis, G., and Bird, M. (2025). Climate TRACE Ownership Information: Global Energy Monitor Methodology for Ownership Data. Global Energy Monitor, USA, Climate TRACE Emissions Inventory. https://climatetrace.org \[Accessed date\] |

#### Detailed terms of use and licensing information

All emissions data has been made available via Climate TRACE under the Creative Commons Attribution 4.0 International License (CC BY 4.0) with the following exceptions.

The following datasets have been reproduced directly from their source. It is the sole responsibility of the data user to review the terms and conditions for all the above sources prior to using the data. The Climate TRACE Coalition makes no claims or warranties regarding the accuracy, completeness or licensing terms for these datasets.

| Data | Source |
|---|---|
| Country level emissions estimates for Other energy use, Railways, Other transportation, Other onsite fuel usage, Solid fuel transformation, Other fossil fuel operations, Other manufacturing, Solid waste disposal, Biological treatment of solid waste, Incineration and open burning of waste, and Fluorinated gases, Cropland fires (country and source level) | EDGAR (Emissions Database for Global Atmospheric Research) Community GHG Database, a collaboration between the European Commission, Joint Research Centre (JRC), the International Energy Agency (IEA), and comprising IEA-EDGAR CO2, EDGAR CH4, EDGAR N2O, EDGAR F-GASES version 8.0, (2023) European Commission, JRC (Datasets): <https://edgar.jrc.ec.europa.eu/><br><br>The Community Emissions Data System (CEDS) developed by the Pacific Northwest National Laboratory(v_2024_07_08): <https://www.pnnl.gov/projects/ceds>. |
| Country level emissions estimates for Rice cultivation (in some geographies), Other Agricultural Soil Emissions, Enteric Fermentation- Other, and Manure Management - Other | FAO, 2024. FAOSTAT Climate Change: Agrifood systems emissions, Emissions Totals, <http://www.fao.org/faostat/en/#data/GT> |
| Source-level emissions estimates for some sources in the “Other manufacturing” sector | European Pollutant Release and Transfer Register: <https://www.eea.europa.eu/data-and-maps/data/member-states-reporting-art-7-under-the-european-pollutant-release-and-transfer-register-e-prtr-regulation-23/european-pollutant-release-and-transfer-register-e-prtr-data-base><br><br>US Environmental Protection Agency FLIGHT dataset: <https://ghgdata.epa.gov/ghgp/main.do?site_preference=normal><br><br>Israel Pollutant Release and Transfer Register: <https://www.gov.il/en/departments/topics/prtr/govil-landing-page> |
| Source-level emissions estimates for some sources under the “Solid Waste Disposal” sector | US Environmental Protection Agency FLIGHT dataset: <https://ghgdata.epa.gov/ghgp/main.do?site_preference=normal><br><br>US Environmental Protection Agency Landfill Methane Outreach Program: <https://www.epa.gov/lmop> (some landfills only)<br><br>Canada Greenhouse Gas Reporting Program - Facility GHG Data: <https://open.canada.ca/data/en/dataset/a8ba14b7-7f23-462a-bdbb-83b0ef629823>.<br><br>European Pollutant Release and Transfer Register: <https://www.eea.europa.eu/data-and-maps/data/member-states-reporting-art-7-under-the-european-pollutant-release-and-transfer-register-e-prtr-regulation-23/european-pollutant-release-and-transfer-register-e-prtr-data-base> |

#### Geographic boundaries and names (`iso3_country` data attribute)

The depiction and use of boundaries, geographic names and related data shown on maps and included in lists, tables, documents, and databases on Climate TRACE are generated from the following sources. The stated usage is not warranted to be error free and does not imply the expression of any opinion whatsoever on the part of Climate TRACE Coalition and its partners concerning the legal status of any country, area or territory or of its authorities, or concerning the delimitation of its borders.

| Level | Source |
|---|---|
| Country, state province, county/ district level | Global Administrative Areas (GADM) project (Version 4.1 released on 16 July 2022) along with their corresponding ISO3 codes, and with the following adaptations:<br>- HKG (China, Hong Kong Special Administrative Region) and MAC (China, Macao Special Administrative Region) are reported at GADM level 0 (country/national);<br>- Kosovo has been assigned the ISO3 code ‘XKX’;<br>- XCA (Caspian Sea) has been removed from GADM level 0 and the area assigned to countries based on the extent of their territorial waters;<br>- XAD (Akrotiri and Dhekelia), XCL (Clipperton Island), XPI (Paracel Islands) and XSP (Spratly Islands) are not included in the Climate TRACE dataset;<br>- ZNC name changed to ‘Turkish Republic of Northern Cyprus’ at GADM level 0;<br>- The borders between India, Pakistan and China have been assigned to these countries based on GADM codes Z01 to Z09.<br>- Two IDs have been created for a region in UKR with missing IDs (at Level 1 and Level 2).<br>- UNK added to GADM level 0 to denote 'unknown' countries, which primarily applies to non-broadcasting-vessels whose port berthing locations are not known.<br>- TUR name changed to “Türkiye”<br>- SWZ name changed to “Eswatini”<br>- Missing Con Dao Island added as VNM.7.X_1 and Kili Island added as MHL.X_1. |
| City level | The Global Human Settlements Layer - Functional Urban Areas (2019). |

---

Source PDF: [READ ME_v5.0.0_Climate TRACE_About the data_Nov2025.pdf](./READ%20ME_v5.0.0_Climate%20TRACE_About%20the%20data_Nov2025.pdf)
