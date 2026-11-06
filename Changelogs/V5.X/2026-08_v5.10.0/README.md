# [5.10.0] - 2026-08-26

## ClimateTRACE,deprecation-warning

- The data download packages at https://climatetrace.org/data have been replaced with a new data download tool.

- The other-fossil-fuel-operations subsector will be deprecated in an upcoming release, no earlier than V5.11.0, as coal-mining, oil-and-gas-production, and oil-and-gas-transport will include all of the emissions previously captured by this subsector.

## ClimateTRACE,new-sector

- forestry-and-land-use,net-soil-organic-carbon The net-soil-organic-carbon sector estimates annual changes in soil organic carbon (SOC) stocks (top 30 cm) and the associated CO2 sink or source across global croplands. Annual SOC changes are estimated using the process-based System Approach for Land Use Sustainability (SALUS) model, which simulates soil biogeochemical processes influenced by agricultural management and environmental conditions, including residue inputs, tillage practices, soil properties, and weather. A net increase in SOC represents carbon sequestration, while a net decrease indicates the release of CO2 to the atmosphere. The dataset provides annual global estimates at the gridded level, along with aggregated country-level totals. See forestry-and-land-use,net-soil-organic-carbon changelog for additional information.

## ClimateTRACE,multiple-sectors,post-processing

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Organic carbon (OC) and black carbon (BC) are, by definition, components of PM2.5. Previous versions erroneously reported instances where BC+OC emissions for select countries/sectors exceeded PM2.5 emissions. The following constraints are now applied:

1. PM2.5 > 0 and BC+OC > PM2.5: BC and OC are scaled down proportionally so they sum to exactly PM2.5, preserving the BC:OC ratio.

2. PM2.5 = 0 but BC + OC > 0: PM2.5 is deemed unreliable, so is set equal to BC+OC. Below is a list of sectors and number of countries where BC+OC exceeded PM2.5 in V5.9.0 for 2025:

- sector = # countries violating

- road-transportation = 235

- domestic-aviation = 164

- residential-onsite-fuel-usage = 141

- other-onsite-fuel-usage = 123

- oil-and-gas-production = 93

- oil-and-gas-transport = 93

- food-beverage-tobacco = 77

- non-residential-onsite-fuel-usage = 67

- coal-mining = 66

- electricity-generation = 66

- fluorinated-gases = 42

- iron-mining = 39

- copper-mining = 36

- other-manufacturing = 27

- international-aviation = 18

- international-shipping = 16

- other-chemicals = 13

- bauxite-mining = 11

- petrochemical-steam-cracking = 11

- other-mining-quarrying = 10

- domestic-shipping = 9

- iron-and-steel = 9

- other-energy-use = 8

- textiles-leather-apparel = 8

- other-metals = 7

- chemicals = 6

- rock-quarrying = 6

- sand-quarrying = 6

- aluminum = 5

- other-transport = 5

- pulp-and-paper = 5

- wood-and-wood-products = 5

- non-broadcasting-vessels = 1

### Known Issues

- [Known issue] other-energy-use PM2.5 emissions may be inflated up to 20x due to an incorrect ratio applied to CO2e values.

## ClimateTRACE,individual-changelogs

## agriculture,cropland-fires

### Added

- [Added] 2026 emissions data from January through July.

- [Added] The 2026 production data were predicted using a regression-based approach. Historical annual production values from 2015 to 2025 were analyzed at a 10 × 10 km pixel resolution to identify trends and estimate production values for 2026.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## agriculture,crop-residues

### Added

- [Added] 2026 emissions data from January through July.

- [Added] The 2026 production data were predicted using a regression-based approach. Historical annual production values from 2015 to 2025 were analyzed at a 10 × 10 km pixel resolution to identify trends and estimate production values for 2026.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## agriculture,enteric-fermentation-cattle-operation

### Added

- [Added] Expanded U.S. ‘OtherBeefCattle’ Inventory Coverage: Added U.S. Department of Agriculture (USDA) Other States categories under ‘CATTLE, ON FEED

- INVENTORY’ to the U.S. national level. USDA only provides reports for the 12 top-producing states (AZ, CA, CO, ID, IA, KS, MN, NE, OK, SD, TX, and WA). This update incorporates additional remaining state totals to ensure more complete national beef cattle inventory representation for emission modeling.

### Changed

- [Changed] The number of cattle operations identified in each country may have changed due to further deduplication processing.

- [Changed] Manure ponds detected at each cattle operation were used to assign higher IPCC 2019 enteric fermentation emission factors, by country, to these operations to reflect intensive cattle management. Operations with no pond detected, depending on the country, may have been assigned lower IPCC 2019 emission factors to reflect less intensive cattle management.

- [Changed] Aligned country-level enteric fermentation CH4 emissions with asset-level (cattle operation) modeling by adopting the IPCC 2019 Tier 2 methodology. This update modifies regional emission factors and overall CH4 emission totals. See the methodology documentation for details.

- [Changed] Country-level CH4 estimation: Updated the methodology to sum estimated cattle at each cattle operation per country, subtracted asset summed cattle total from FAO country totals, and then applied Tier 2 approach to the remaining cattle. These components are then combined to calculate the new total country-level CH4 emissions.

- [Changed] Distributed FAO total annual 'OtherBeefCattle' estimates evenly across each quarter per year to better model the continuous turnover of beef cattle entering and exiting cattle operations.

- [Changed] New emissions reduction solutions (ERS) for each cattle operation have been generated for v5.10. This includes additional feed additives.

- [Changed] The new ERS in v5.10 are ranked based on a weighted approach that includes cost, safety, confidence in use, and emission reduction potential when applying feed additives to mitigate enteric fermentation.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] The error with the agolin emission reduction solution (ERS) applied to individual cattle operations, since the v4.8.0 release, has been fixed.

### Known Issues

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S. this was caused when a reported state government CAFOs had location coordinates set away from the operation not within the operation. For example, at the end of the CAFO driveway leading into the operation or the owners home away from the CAFO. Further work will continue to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist for this sector. If found, please let us know via email and provide the asset id and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity capped at 40,000. Additionally, any dairy farm operation with a total head (capacity) greater than 4,000 had their capacity capped at 4,000. These are marked in the ‘other2’ column. Future updates will address this issue.

## agriculture,enteric-fermentation-cattle-pasture

### Added

- [Added] Gross Primary Production (GPP) layers were added to support seasonal pasture, capacity, and activity calculations. GPP is used to represent quarterly vegetation productivity and pasture support.

- [Added] Gridded Livestock Watch (GLW) cattle density data was added to improve the spatial distribution of cattle across pasture-supported areas. The layers are from 2015 and 2020, while annual FAOSTAT cattle totals were used to correct and scale country-level cattle counts for each year from 2015 to 2025.

- [Added] Quarterly Pasture-supported cattle activity rasters were generated for Q1, Q2, Q3, and Q4 for each year in the 2015-2025 modeling period.

- [Added] Annual pasture-supported cattle activity rasters were generated from quarterly activity estimates to represent annual mean cattle head-equivalents on pasture.

- [Added] New emissions reduction solutions (ERS) were generated for pasture-based enteric fermentation. These include stocking-rate optimization and herd-size reduction, feed additives, and silvopastoral rotation with improved forage quality.

### Changed

- [Changed] Replaced the previous static SEDAC pasture layer with Global Pasture Watch (GPW) pasture-fraction data to improve spatial representation of pastureland.

- [Changed] Increased the spatial resolution of global pasture-cattle modeling from the previous 10km course grid to 1km resolution.

- [Changed] Updated the activity calculation from a national inventory subtraction approach to a spatial pasture support approach. Activity is now estimated from pasture fraction, seasonal GPP, GLW cattle-density weighting, and FAOSTAT cattle totals.

- [Changed] Enteric Fermentation CH4 emissions are now calculated specifically for cattle activity supported by mapped pasture areas, rather than representing total national cattle emissions.

- [Changed] Updated FAOSTAT cattle data were incorporated for the 2015-2025 modeling period and used with the spatial cattle density layer to distribute cattle activity across pasture-supported areas.

### Deprecated

- [Deprecated] Removed the static SEDAC pasture layer from the pasture cattle activity calculation.

- [Deprecated] Removed the previous “Total Non_dairy - Total Slaughtered” logic for estimating cattle on pasture.

- [Deprecated] Removed the coarse-grid pasture allocation method in favor of the updated 1km pasture support and cattle density workflows

- [Deprecated] Deprecated the interpretation of pasture-cattle emissions as total national cattle emissions. The updated outputs represent cattle-on-pasture emissions only.

### Fixed

- [Fixed] Resolved negative cattle-on-pasture activity estimates caused by the “Total Non_dairy - Total Slaughtered” subtraction logic.

### Known Issues

- [Known Issues] Countries with limited overlap between GLW cattle density layer and GPW pasture fraction layer may have low or near-zero pasture-supported cattle activity, even if the national cattle inventories are higher.

- [Known Issues] The global 1 km model may not fully capture local grazing movement or small-scale managed grazing systems.

## agriculture,manure-left-on-pasture-cattle

### Added

- [Added] Gross Primary Production (GPP) layers were added to support seasonal pasture, capacity and activity calculations. GPP is used to represent quarterly vegetation productivity and pasture support.

- [Added] Gridded Livestock Watch (GLW) cattle density data was added to improve the spatial distribution of cattle across pasture-supported areas. The layers are from 2015 and 2020, while annual FAOSTAT cattle totals were used to correct and scale country-level cattle counts for each year from 2015 to 2025.

- [Added] Quarterly Pasture-supported cattle activity rasters were generated for Q1, Q2, Q3, and Q4 for each year in the 2015-2025 modeling period.

- [Added] Annual pasture-supported cattle activity rasters were generated from quarterly activity estimates to represent annual mean cattle head-equivalents on pasture.

- [Added] New emissions reduction solutions (ERS) were generated for manure left on pasture. These include pasture rotation with optimized stocking and nitrogen-reducing fodder crops, and silvopastoral rotation.

### Changed

- [Changed] Replaced the previous static SEDAC pasture layer with Global Pasture Watch (GPW) pasture-fraction data to improve spatial representation of pastureland.

- [Changed] Increased the spatial resolution of global manure-left-on-pasture modeling from the previous 10km course grid to 1km resolution.

- [Changed] Updated the activity calculation from a national inventory subtraction approach to a spatial pasture support approach. Activity is now estimated from pasture fraction, seasonal GPP, GLW cattle-density weighting, and FAOSTAT cattle totals.

- [Changed] Manure-left-on-pasture CH4 and N2O emissions are now calculated specifically for cattle activity supported by mapped pasture areas, rather than representing total national cattle emissions.

- [Changed] Updated FAOSTAT cattle data were incorporated for the 2015-2025 modeling period and used with the spatial cattle density layer to distribute cattle activity across pasture-supported areas.

### Deprecated

- [Deprecated] Removed the static SEDAC pasture layer from the manure-left-on-pasture activity calculation.

- [Deprecated] Removed the previous “Total Non_dairy - Total Slaughtered” logic for estimating cattle on pasture.

- [Deprecated] Removed the coarse-grid pasture allocation method in favor of the updated 1km pasture support and cattle density workflows

- [Deprecated] Deprecated the interpretation of manure-left-on-pasture emissions as total national cattle emissions. The updated outputs represent cattle-on-pasture manure emissions only.

### Fixed

- [Fixed] Resolved negative cattle-on-pasture activity estimates caused by the “Total Non_dairy - Total Slaughtered” subtraction logic.

### Known Issues

- [Known Issues] Countries with limited overlap between GLW cattle density layer and GPW pasture fraction layer may have low or near-zero manure-left-on-pasture cattle activity, even if the national cattle inventories are higher.

- [Known Issues] The global 1 km model may not fully capture local grazing movement or small-scale managed grazing systems.

## agriculture,manure-applied-to-soils

### Added

- [Added] 2026 emissions data from January through July.

- [Added] The 2026 production data were predicted using a regression-based approach. Historical annual production values from 2015 to 2025 were analyzed at a 10 × 10 km pixel resolution to identify trends and estimate production values for 2026.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## agriculture,manure-management-cattle-operation

### Added

- [Added] Expanded U.S. OtherBeefCattle Inventory Coverage: Added U.S. Department of Agriculture (USDA) Other States categories under ‘CATTLE, ON FEED

- INVENTORY’ to the U.S. national level. USDA only provides reports for the 12 top-producing states (AZ, CA, CO, ID, IA, KS, MN, NE, OK, SD, TX, and WA). This update incorporates additional remaining state totals to ensure more comprehensive national inventory representation for emission modeling at the country-level.

### Changed

- [Changed] The number of cattle operations identified in each country may have changed due to further deduplication processing.

- [Changed] The cattle operation manure management sector now applies IPCC 2019 Tier 2 approach to estimate CH4 and N2O emissions for multiple manure management systems (MMS) assumed at an operation. This replaces the single-system assumption in previous releases. See ‘Cattle Operations- Asset-level Enteric Fermentation and Manure Management Emissions’ methodology at [Agriculture methodologies](../../../Sector-Methodologies/1-Sectors/agriculture/)

- [Changed] Previous releases assumed 100% of manure entered the single MMS at each cattle operation. For v5.10- multiple MMS at each cattle operation were assigned a fraction of manure entering each system. This will change CH4 and N2O emission estimates in v5.10.

- [Changed] Compared to previous releases, the new asset approach used in v5.10 manure management overall has decreased CH4 emissions and increased N2O emissions due to assigning multiple MMS and fraction of manure to each cattle operation for assets.

- [Changed] Country-level CH4 and N2O estimation: Updated the methodology to sum estimated cattle at each cattle operation per country, subtracted them from FAO country totals, and then applied Tier 2 approach to the remaining cattle and allocating them to IPCC 2019 animal waste management system regional defaults. These components are then combined to calculate the new total country-level CH4 and N2O emissions.

- [Changed] Distributed FAO total annual 'OtherBeefCattle' estimates evenly across each quarter per year to better represent the continuous turnover of beef cattle entering and exiting cattle operations.

- [Changed] Compared to previous releases, the new country approach used in v5.10 manure management overall has decreased CH4 emissions and increased N2O emissions due to combining asset-level and country-level emissions data.

- [Changed] Each asset (cattle operations) has new emissions reduction solutions (ERS) based on changing a single MMS in multiple MMS. See ‘Cattle Operations- Asset-level Enteric Fermentation and Manure Management Emissions’ methodology at [Agriculture methodologies](../../../Sector-Methodologies/1-Sectors/agriculture/)

- [Changed] The new manure management emissions reduction solutions (ERS) in v5.10 are ranked based on a weighted approach that includes cost and emission reduction potential when retrofitting a single MMS in the multiple MMS at each cattle operation.

### Deprecated

- [Deprecated] Previous emissions reduction solutions (ERS)before v5.10 are now deprecated.

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S. this was caused when a reported state government CAFOs had location coordinates set away from the operation not within the operation. For example, at the end of the CAFO driveway leading into the operation or the owners home away from the CAFO. Further work will continue to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist for this sector. If found, please let us know via email and provide the asset id and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity capped at 40,000. Additionally, any dairy farm operation with a total head (capacity) greater than 4,000 had their capacity capped at 4,000. These are marked in the ‘other2’ column. Future updates will address this issue.

- [Known Issues] Manure emissions in conflict-affected regions with large cattle populations (e.g., Afghanistan, East Africa) may overestimate emissions due to IPCC 2019 animal waste management system regional defaults assigned. Future updates will implement country-specific MMS to resolve this issue.

- [Known Issues] Current country-level manure emissions assume a single climate zone and one multiple MMS type per cattle category (beef/dairy), potentially biasing CH4 and N2O emissions’ estimates, especially in temperate climates (i.e. Russia and Canada) where CH4 production is reduced in cooler/temperate climates. Future updates will improve accuracy by implementing multi-MMS allocations and refined country-specific climate zones.

## agriculture,manure-applied-to-soils

### Added

- [Added] 2026 emissions data from January through July.

- [Added] The 2026 production data were predicted using a regression-based approach. Historical annual production values from 2015 to 2025 were analyzed at a 10 × 10 km pixel resolution to identify trends and estimate production values for 2026.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## agriculture,rice-cultivation

### Added

- [Added] Monthly data backfilled for Southeast Asian countries from 2021-2023 using 2024 emissions factor and planting patterns at the asset level.

### Changed

- [Changed] The AR6 GWP multiplier of 27.0 for methane is being used in accordance with Climate Trace's standards. Previously, a value of 27.2 was used for all rice fields globally.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Non-GHGs were previously non-zero, corrected to now be zero, as this sector covers only methane emissions from anaerobic activity.

### Known Issues

- [Known Issues] There will be a discontinuous pattern in monthly rice activity and emissions for countries outside the Southeast Asia region from 2015 to 2024 compared to 2025. For years 2015 to 2024, annual data is being disaggregated to monthly data by post processing, which uses different methods than monthly estimated 2025 data. Future updates will address this issue to make monthly data consistent.

## agriculture,synthetic-fertilizer-application

### Added

- [Added] 2026 emissions data from January through July.

- [Added] The 2026 production data were predicted using a regression-based approach. Historical annual production values from 2015 to 2025 were analyzed at a 10 × 10 km pixel resolution to identify trends and estimate production values for 2026.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## fossil-fuel-operations,coal-mining

### Added

- [Added] Full refresh of asset- and country-level emissions from 2015 to 2025 to account for some additional opening year data.

- [Added] Emissions from fuel combustion during coal mining activities (mostly co2, some n2o, and very minor ch4) and co2 emissions from rock weathering/acidification previously handled by post-processing.

- [Added] Updated the emission reduction strategy (ERS) list and ERS crosswalk to include a new emission reduction solution, Electrification of mobile equipment, relevant to emissions from fuel combustion. Also updated previous ERS values.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Addressed 4 duplicate mines.

### Known Issues

- [Known Issues] None

## fossil-fuel-operations,oil-and-gas-production

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] ERS scores were omitted since V5.7.0 and are now populated in this version.

### Known Issues

- [Known Issues] None

## fossil-fuel-operations,oil-and-gas-transport

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] ERS scores were omitted since V5.7.0 and are now populated in this version.

### Known Issues

- [Known Issues] None

## fossil-fuel-operations,other-fossil-fuel-operations

### Added

- [Added] None

### Changed

- [Changed] CO2 and CH4 emissions from coal-mining combustion emissions were previously captured by other-fossil-fuel-operations, and are now correctly reported under coal-mining. Therefore this sector’s CO2e values have decreased by approximately 99% in V5.10.0, now covering only N2O emissions from fossil fuel operations.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] None

## fossil-fuel-operations,other-solid-fuels

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known issue] Post-processing adjustments for coal-mining treats 100% of imputed emissions as fugitive, when the true value is only ~32% (remainder being combustion). Therefore, for countries with imputed values, other-solid-fuels emissions are incorrectly depressed during implicit estimation because the sector should only cover fugitive emissions. The effect is limited to ~13 Mt CO2e over the period 2015-2026, or approximately 0.2% of the global CO2e emissions for other-solid-fuels over the same period (7,400 Mt).

## forestry-and-land-use,forest-land-fires

### Added

- [Added] Non-GHG emissions are now quantified for 2015 through 2024 for countries and 2021 through 2024 for assets, and GADM/city aggregations.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Non-GHG emissions estimates for 2025 and 2026 are reported as 0 due to a lack of data to extrapolate forward.

- [Known Issues] Non-GHGs BC and OC are reported as 0s in this release due to a processing error. To be fixed in V5.11.0

## forestry-and-land-use,net-soil-organic-carbon

### Added

- [Added] This is a new sector.

- [Added] Emissions estimated for 2016–2025 for 40 crop groups and >170 countries. Spatial resolution: 5 arc-minutes (~10 km), aggregated to GADM level 0 (GID0).

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Emission Reduction Solution (ERS) for this sector are omitted.

- [Known Issues] Asset-level activity values (tonnes change in soil organic carbon) for CH4 and N2O are incorrectly set to 0 across the board. For true activity values, users are pointed to the CO2 rows, which represent the true SOC change. To be fixed in V5.11.0.

- [Known Issues] GADM and city aggregation asset_activity, emissions_factor, and capacity_factor are incorrect. To be fixed in V5.11.0.

## forestry-and-land-use,shrubgrass-fires

### Added

- [Added] Non-GHG emissions are now quantified for 2015 through 2024 for countries and 2021 through 2024 for assets, and GADM/city aggregations.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Non-GHG emissions estimates for 2025 and 2026 are reported as 0 due to a lack of data to extrapolate forward.

- [Known Issues] Non-GHGs BC and OC are reported as 0s in this release due to a processing error. To be fixed in V5.11.0

## forestry-and-land-use,wetland-fires

### Added

- [Added] Non-GHG emissions are now quantified for 2015 through 2024 for countries and 2021 through 2024 for assets, and GADM/city aggregations.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Non-GHG emissions estimates for 2025 and 2026 are reported as 0 due to a lack of data to extrapolate forward.

- [Known Issues] Non-GHGs BC and OC are reported as 0s in this release due to a processing error. To be fixed in V5.11.0

## manufacturing,aluminum

### Added

- [Added] June 2026 emissions update.

### Changed

- [Changed] ROU, MYS, RUS historic data (2021-present) submitted with updated emissions factors.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,cement

### Added

- [Added] Added new month, June 2026 asset level emissions.

- [Added] Added new month, June 2026 country level emissions.

- [Added] Updated mission reduction strategy (ERS) and ERS  crosswalk files for emission reduction solutions.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,chemicals

### Added

- [Added] 2025 data using updated U.S. Geological Survey (USGS) production data (released in 2026).

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,iron-and-steel

### Added

- [Added] Full refresh of asset-level emissions from 2021 to Jun 2026.

- [Added] Full refresh of country-level emissions from 2021 to Jun 2026.

- [Added] Updated the emission reduction strategy (ERS) list and ERS crosswalk to include new ERS and new assets for emission reduction solutions.

### Changed

- [Changed] Direct reduced iron (DRI) activity is now calculated from satellite-derived thermal anomaly index (TAI).

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Country emissions quantities in HUN are no longer spuriously inflated pre-2021.

### Known Issues

- [Known Issues] None

## mineral-extraction,copper-mining

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] Country-level copper-mining co2e emissions show an unrealistic step change at 2019 to 2020 — global totals roughly double from ~34 Mt CO2e/yr (2015–2019) to ~53–68 Mt CO2e/yr (2020–2024), affecting many copper-producing countries simultaneously. Present since, at least, V4.0.

## mineral-extraction,other-mining-quarrying

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] YEM country and GADM emissions contained minor negative emissions that are now 0.

### Known Issues

- [Known Issues] None

## mineral-extraction,sand-quarrying

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] YEM country and GADM emissions contained minor negative emissions that are now 0.

### Known Issues

- [Known Issues] None

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2019-01-01 to end_date 2026-06-30.

- [Added] Included reported plant/unit-level activity data from these additional sources for ensembling of capacity factor estimate:

* ARG - Compañía Administradora del Mercado Mayorista Eléctrico (CAMMESA)

* AUS (NEM) - Australian Energy Market Operator - National Electricity Market

* AUS (WEM) - Australian Energy Market Operator - Market Data Western Australia

* CAN (Alberta) - Alberta Electric System Operator

* CAN (Ontario) - Independent Electricity System Operator

* CHL - Coordinador Eléctrico Nacional

* COL - XM Compañía De Expertos En Mercados

* DOM  - Organismo Coordinador del Sistema Eléctrico Nacional Interconectado (OC)

* IND - Central Electricity Authority, Ministry of Power, Government of India

* GBR - Elexon

* JPN - Organization for Cross-regional Coordination of Transmission Operators (OCCTO)

* KOR - Korea Electric Power Corporation

* MYS - Suruhanjaya Tenaga Malaysia

* NGA - Nigerian Independent System Operator (NISO)

* NIC - El Centro Nacional de Despacho de Carga (CNDC)

* PAN - Empresa De Transmisión Eléctrica, S.A. (ETESA)

* PER - Comité de Operación Económica del Sistema (COES)

* TUR - Epias Transparency Platform (EPIAS)

* TWN - Taiwan Power Company (Monthly)

* UAE (Dubai) - Dubai Electricity and Water Authority

* USA - EIA-923

### Changed

- [Changed] Updated unit/plant level information due to manual research. These can result in changes to our estimates.

- [Changed] Improved linkages to generation sources, which results in changes to our estimates.

- [Changed] Improved ensembling of multiple sources of plant capacity factor data and model predictions to create the capacity factor estimate.

- [Changed] improve the estimation of uncertainty for reported generation sources.

- [Changed] Improved the estimation and use of gap-filled reported generation estimates and the reported generation validation tests to better use the available data.

- [Changed] Refactored the codebase to enable the above improvements. Improved the performance of the estimation process.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-06-30.

- [Added] Added coverage. 24 new sources added, listed by International Air Transport Association (IATA): {'iata_AYW', 'iata_DXN', 'iata_FOO', 'iata_FSH', 'iata_GEB', 'iata_GWI', 'iata_HEZ', 'iata_INX', 'iata_IYO', 'iata_JHN', 'iata_KBX', 'iata_KEQ', 'iata_KGJ', 'iata_LMB', 'iata_LSR', 'iata_LTJ', 'iata_NSA', 'iata_OQN', 'iata_ORK', 'iata_PMQ', 'iata_RUI', 'iata_TBX', 'iata_TXM', 'iata_UTA'}

### Changed

- [Changed] Flight-distance correction for ICAO-modeled aircraft. Aircraft types estimated with the ICAO fuel-consumption tables (primarily smaller and older aircraft not covered by the ICAO CORSIA fleet tables) now apply the ICAO distance correction factor to the great-circle distance between airports, consistent with the ICAO Carbon Emissions Calculator methodology. This produces a slight increase in modeled fuel burn and emissions for the affected aircraft types, on the order of 0.6% of total domestic-aviation emissions across all years.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Corrected overstated emissions on a small number of very short-distance routes where the previous method assigned erroneously high fuel burn. The affected airports show substantially lower emissions in the corrected series.

### Known Issues

- [Known Issues] None

## transportation,non-broadcasting-vessels

### Changed

- [Changed] Updated model number to ‘_v20260714’.

- [Changed] Updated our entire time series of data (2017-01-01 through 2026-06-30).

- [Changed] Uses latest AIS-broadcasting emissions estimates (AIS model version _v20260714) as the basis for non-broadcasting vessel emissions estimates.

- [Changed] Updated to the latest Sentinel-1 (S1) detection dataset (sentinel1_clean_v20250827), which includes a refined matching score for determining whether each S1 vessel detection is broadcasting or non-broadcasting.

- [Changed] S1 detections that match to an AIS vessel are now treated as ‘non-broadcasting’ if that vessel is not included in our AIS-broadcasting emissions estimates (e.g., vessels excluded for identity offsetting or other quality filters). Previously such detections were counted as AIS-broadcasting even though no AIS-based emissions were estimated for them; this change attributes their emissions to the non-broadcasting fleet and substantially increases non-broadcasting fleet emissions estimates.

- [Changed] K-Nearest Neighbors (KNN) interpolation of non-broadcasting-to-AIS-broadcasting ratios is now exact and global: nearest neighbors are selected from precomputed distances between all pixel pairs on a fixed global ocean grid, with no distance cutoff.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] 2015 emissions data were previously 0, now are correctly non-zero.

### Known Issues

- [Known Issues] None

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-06-30.

- [Added] Added coverage. 9 new sources added, listed by International Air Transport Association (IATA): {'iata_BGC', 'iata_DLZ', 'iata_ERS', 'iata_JJU', 'iata_KSY', 'iata_NMI', 'iata_QOW', 'iata_URE', 'iata_ZZU'}

### Changed

- [Changed] Flight-distance correction for ICAO-modeled aircraft. Aircraft types estimated with the ICAO fuel-consumption tables (primarily smaller and older aircraft not covered by the ICAO CORSIA fleet tables) now apply the ICAO distance correction factor to the great-circle distance between airports, consistent with the ICAO Carbon Emissions Calculator methodology. This produces a slight increase in modeled fuel burn and emissions for the affected aircraft types, on the order of 0.25% of total international-aviation emissions across all years.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources. New end_date 2026-06-30.

### Changed

- [Changed] Countries outside of the USA, CAN, PRI, and VIR will use updated PM2.5 modeling based on PM2.5 emission ratios derived from EDGAR. Most countries will see a noticeable increase in PM2.5 emissions.

- [Changed] Vehicle fuel mix was updated using road vehicle fleet information from the UNECE statistical database and various country-level inventories. Relative to the previous baseline, the portions of the vehicle fleet with EV and PHEV powertrains have been increased. Countries affected include: ALB, AUT, BEL, BGR, BIG, BMU, CAN, CHE, CYR, CZE, DEU, DNK, ESP, EST, FIN, FRA, GBR, GEO, GRC, GRL, HRV, HUN, IRL, ISL, ISR, ITA, KAZ, LIE, LTU, LUX, LVA, MDA, MKD, MLT, MNE, NLD, NOR, POL, PRT, ROU, SPM, SRB, SVK, SVN, SWE, TUR, UKR, USA, HKG, KOR, SGP, and UGY.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Remove null asset_identifier rows in asset data.

- [Fixed] Anomalous jump in non-GHG emissions starting in January 2026 has been corrected.

### Known Issues

- [Known Issues] Have not updated to the latest ClimateTRACE patch of GADM data (v1.1.2).

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Historical Data. Start_date 2015-01-01 to end_date 2026-06-30.

- [Added] 3,092 latrine and septic assets with historical data for countries where the percentage of wastewater left untreated is higher than 50%: ETH, TCD, ERI, PNG, SSD, NER, CAF, COD, MDG, UGA, BEN, SLB, MOZ, SDN, GNB, TGO, NAM, LBR, COM. Start_date 2015-01-01 to end_date 2026-06-30.

- [Added] 4,926 latrine, septic, and untreated assets with historical data for PHL. Start_date 2015-01-01 to end_date 2026-06-30.

### Changed

- [Changed] Added plant_identification_method column.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Manually adjusted the coordinates for the SOUTH RIVER WWTP to 33.683407803203, -84.3628685262687.

- [Fixed] Manually adjusted the coordinates for the Batonyterenye Wastewater Treatment Plant to 47.98600976222678, 19.81691427721818.

### Known Issues

- [Known Issues] Inconsistent year-over-year population values for Kiribati in underlying population source data carrying forward into country-level emissions estimates. To be addressed in a future release.

- [Known Issues] The dilution factor column (other1) relies on HydroWASTE values and will remain blank for non-HydroWASTE assets.

- [Known Issues] Potential duplicate assets.

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Historical data. Start_date 2015-01-01 to end_date 2026-06-30.

### Changed

- [Changed] Refreshed emissions estimates for steel based on asset metadata from the current year's industrial asset submission.

- [Changed] For the steel wastewater dataset: we integrated current-year asset metadata by matching current plants to historic asset IDs where possible, while assigning new IDs to unmatched plants. In total, the dataset covers 958 steel plants— 804 matched historic IDs, and 154 were identified as new plants. Additionally, 106 historic plants did not appear in the new submission and were excluded from the dataset.

- [Changed] Added plant_identification_method column.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] industrial-wastewater-treatment-and-discharge emissions from all sources are now properly accounted for in GADM and GHS-FUA aggregations.

### Known Issues

- [Known Issues] Potential duplicate assets.

## waste,solid-waste-disposal

### Added

- [Added] None

### Changed

- [Changed] Introduced country-level waste composition defaults where available (fallback is regional defaults).

- [Changed] Site area logic updated to choose best source quality available. When several providers report an area for the same site, the most reliable sources - (Greenhouse Gas Reporting Program (GHGRP) / Landfill Methane Outreach Program (LMOP) / Waste Atlas / National Institute of Statistics and Geography (INEGI)) - are averaged, falling back to OpenStreetMap, then to other sources, and only to Global Plastic Watch (GPW) / Brazilian national solid waste system (SINIR) as a last resort. Because area drives the modeled incoming-waste estimate, modeled waste and emissions change for sites that previously relied on a GPW area are now using a better source(s) available; the published area value and its data-source label have also changed.

- [Changed] A physical ceiling now caps the CH4 emissions factor: no site can emit more methane per tonne of waste than the waste can produce (~0.143 t CH4 / t of waste annually). Where a site's implied emissions factor exceeded that ceiling — a sign its waste-in-place was under-counted, not that its emissions were wrong — the estimated waste-in-place (activity) is inflated to satisfy the ceiling and emissions are held fixed. Affected sites get a larger reported activity and capacity factor and are marked with a new activity_ef_capped flag.

- [Changed] Country assignment (ISO3) now uses Climate TRACE's own country-boundary shapefile instead of the boundaries used previously. Sites near borders or in special/disputed territories may be assigned to a different country than in prior runs.

- [Changed] The modeled decay rate is now floored at 0.04/yr and the temperature factor is clamped to its valid range, preventing implausible near-zero decay — and hypersensitivity to small temperature differences — at cold/dry sites. No effect on warm/wet sites.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Fixed data-source provenance labels being silently dropped from the published source columns. Several source names (e.g. USA GHGRP, Mexico's INEGI, Clean Air Task Force) were not recognized by the source-label mapper and were dropped, which could leave a site with an empty source list; aliases were added and a validation check now fails the run if any site ends up with no source list.

### Known Issues

- [Known Isuue] None

---

PDF: [5.10.0_combined-changelog-climate-trace.docx.pdf](./5.10.0_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
