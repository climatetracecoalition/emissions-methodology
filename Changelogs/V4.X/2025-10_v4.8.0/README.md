# [4.8.0] - 2025-10-22

## ClimateTRACE,deprecation-warning:

The following Deprecation Warnings were announced in V4.7.0 and is now active in V4.8.0:

- [Deprecation Warning] the following fields are now  renamed in the ‘trace-data-383422.climate_trace.gadm_emissions’ and ‘trace-data-383422.climate_trace.city_emissions’ BigQuery tables:

- ‘remainder_capacity’ renamed to ‘spatially_uncertain_capacity’;

- ‘remainder_activity’ renamed to ‘spatially_uncertain_activity’;

- ‘remainder_emissions’ renamed to ‘spatially_uncertain_emissions’.

## ClimateTRACE,multiple-sectors,post-processing:

### Added

- [Added] Facility-level emissions estimates for all 8 non-ghgs now available: Carbon monoxide (CO), ammonia (NH3), non-methane volatile organic compounds (NMVOC), nitrogen oxides (NOx), sulfur dioxide (SO2), particulate matter smaller than 2.5 microns (PM2.5), and speciated components of PM2.5 that are byproducts of combustion – black carbon (BC) and organic carbon (OC). Previously, some subsector-gas combinations did not have estimates.

### Changed

- [Changed] Updated handling of non-ghgs imputed using existing CO2e values. Ratios of non-ghg emissions to CO2e 100 Year GWP now calibrated to both EDGAR and CEDS estimates at the country level. Additionally, separate non-ghg-to-CO2e ratios are applied to process emissions and combustion emissions for cement. Additional non-GHG sources of emissions in the mining sector that do not produce GHGs are now included, such as drilling and blasting, materials processing, internal transport, material handling operations, and wind erosion from stockpiles as defined by the EEA.

### Deprecated

### Fixed

- [Fixed] Now impute CO2 emissions factors for bauxite-mining, iron-mining, copper-mining that were incorrectly set to zero in cases where activity was zero. The previously-zero emissions factors no longer affect imputation of cases where activity is non-zero, changing final emissions estimates.

- [Fixed] CO2 Equivalents for spatially uncertain assets are now self-consistently computed using underlying GHGs.

### Known Issues

- [Known Issues] Metadata for gadm and city aggregations is missing for sub-sectors that are disaggregations of country values: fluorinated-gases, other-solid-fuel, other-mining-quarrying, wood-and-wood-products, other-fossil-fuel-operations, other-onsite-fuel-usage, other-energy-use, other-transport, railways, other-agricultural-soil-emissions, enteric-fermentation-other, manure-management-other, incineration-and-open-burning-of-waste, biological-treatment-of-solid-waste-and-biogenic.

- [Known Issues] Oil-and-gas-production country-level estimates are inflated for IDN, SEN, and USA by 10%, 200%, and 2% respectively.

- [Known Issues] solid-waste-disposal country, GADM, and city aggregations for 2025 are inflated by approximately 50%.

## ClimateTRACE,individual-changelogs:

## agriculture,crop-residues

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## agriculture,enteric-fermentation-cattle-operation

### Added

- [Added] New assets (cattle operations) added and updated existing coverage for the following countries: AUS, AUT, BEL, BGD, BRA, BWA, CHE, CHN, DEU, DNK, ESP, FRA, GBR, IND, IRL, ITA, LUX, MEX, NLD, NZL, PAK, POL, PRT, PRY, RUS, UKR, URY, USA, and ZAF.

- [Added] New U.S. state coverage assets and updated existing coverage.

### Changed

- [Changed] Country-level emissions estimated with IPCC 2019 equations and emission factors. Updated methodology will be made available next release.

- [Changed] Assets’ (operations) emissions estimated with IPCC 2019 equations and emission factors. It’s recommended to use this version’s emission data for analysis. Updated methodology will be made available next release.

- [Changed] For cattle assets (operations) with no reported total head of cattle and not estimated with the regression model, reported and literature review determined country-level mean total head of cattle, by type, per operation.

- [Changed] This version’s release has fewer operations identified in Belarus, Mexico, and Russia. A new set of cattle operations was detected to reduce false-positive locations (i.e. a poultry farm misclassified as cattle). As a result, each of these countries have fewer locations in the Climate TRACE database compared to last year’s, 2024, release.

- [Changed] U.S. Department of Agriculture National Agriculture Statistics Services data were used to estimate state level mean total head of cattle for each operation within their respective U.S. states with no reported estimates or where the regression model was not applied.

- [Changed] U.S. Department of Agriculture National Agriculture Statistics Services data were used to cattle on feed (capacity factor) for beef cattle operations.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S., duplicates were caused when a reported location had coordinates set away from the cattle operation, not within the operation. For example, at the end of the CAFO driveway or the owner’s home not at the CAFO. Further work will continue  to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist in this sector. If found, please let us know via email and provide the asset id, and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity set to 40,000, and any dairy farm operation with a total head (capacity) greater than 4,000 had their capacity set to 4,000. These are marked in the ‘other2’ column. Future updates will address this issue.

## agriculture,enteric-fermentation-cattle-pasture

### Added

- [Added] New updated FAO statistic data (2015-2024) used to estimate the Global 1-degree CH4 (2015–2024).

### Changed

- [Changed] Replaced IPCC 2006 emission factor–based CH4 estimation. Global country-level enteric fermentation CH4 emissions recalculated using the IPCC 2019 Tier 2 method. Method source link, Page 10.43-10.49: https://www.ipcc-nggip.iges.or.jp/public/2019rf/pdf/4_Volume4/19R_V4_Ch10_Lives tock.pdf

- [Changed] Updated FAOSTAT data for slaughtered and non-dairy cattle (2015–2023). Cattle data for 2024 estimated using Holt’s linear exponential smoothing method. Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

- [Known Issue] We identified several countries where our initial “cattle on pasture” metric yielded negative values: Albania, Armenia, Bahamas, Bahrain, Brunei Darussalam, China (Hong Kong SAR), Faroe Islands, Israel, Jordan, Lebanon, Mauritius, Palestine, Republic of Moldova, Sao Tome and Principe, Saudi Arabia, Tunisia, Ukraine, United Arab Emirates, Azerbaijan, Syrian Arab Republic, Netherlands, Egypt, Montenegro, and Morocco. These regions generally have limited pasture; many are arid, densely populated, or are small/special administrative regions where beef consumption exceeds domestic cattle production. For these areas, we substituted the annual number of slaughtered cattle as a conservative proxy for the cattle-on-pasture population. Future work will address this issue to create a representative cattle on pasture estimate.

## agriculture,manure-applied-to-soils

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## agriculture,manure-left-on-pasture-cattle

### Added

- [Added] New updated FAO statistic data (2015-2024) used to estimate the Global 1-degree CH4 (2015–2024).

### Changed

- [Changed] Replaced IPCC 2006 emission factor–based CH4 and N2O estimation. Global country-level Manure Left on Pasture CH4 and N2O emissions recalculated using the IPCC 2019 Tier 2 method. Method source link Manure Left on Pasture CH₄, sections 10.64 - 10.93: https://www.ipcc-nggip.iges.or.jp/public/2019rf/pdf/4_Volume4/19R_V4_Ch10_Lives tock.pdf and Manure Left on Pasture N2O, sections 10.1 - 11.48: https://www.ipcc-nggip.iges.or.jp/public/2019rf/pdf/4_Volume4/19R_V4_Ch11_Soils _N2O_CO2.pdf

- [Changed] The Tier 2 method incorporates this data to apply climate-specific methane conversion factors (MCFs) and animal waste management system (AWMS) fractions.

- [Changed] FAOSTAT data for slaughtered and non-dairy cattle (2015–2023). Cattle data for 2024 estimated using Holt’s linear exponential smoothing method. Updated methodology will be made available next release.

- [Changed] Climate zones were assigned using the Climatic Research Unit Gridded Time Series (1991–2024) and IPCC 2019 thresholds.

### Deprecated

### Fixed

### Known Issues

- [Known Issue] We identified several countries where our initial “cattle on pasture” metric yielded negative values: Albania, Armenia, Bahamas, Bahrain, Brunei Darussalam, China (Hong Kong SAR), Faroe Islands, Israel, Jordan, Lebanon, Mauritius, Palestine, Republic of Moldova, Sao Tome and Principe, Saudi Arabia, Tunisia, Ukraine, United Arab Emirates, Azerbaijan, Syrian Arab Republic, Netherlands, Egypt, Montenegro, and Morocco. These regions generally have limited pasture; many are arid, densely populated, or are small/special administrative regions where beef consumption exceeds domestic cattle production. For these areas, we substitute the annual number of slaughtered cattle as a conservative proxy for the cattle-on-pasture population.Future work will address this issue to create a representative cattle on pasture estimate.

## agriculture,manure-management-cattle-operation

### Added

- [Added] New assets (operations) added and updated existing asset coverage for the following countries: AUS, AUT, BEL, BGD, BRA, BWA, CHE, CHN, DEU, DNK, ESP, FRA, GBR, IND, IRL, ITA, LUX, MEX, NLD, NZL, PAK, POL, PRT, PRY, RUS, UKR, URY, USA, and ZAF.

- [Added] New U.S. state coverage assets and updated existing coverage.

### Changed

- [Changed] Country-level emissions estimated with IPCC 2019 equations and emission factors. Updated methodology will be made available next release.

- [Changed] Assets’ (cattle operations) emissions estimated with IPCC 2019 equations and emission factors. It’s recommended to use this version’s emission data for analysis. Updated methodology will be made available next release.

- [Changed] For cattle operations with no reported total head of cattle and/or not estimated with the regression model, reported or literature supported country-level mean total head of cattle, by type, was applied to each individual operation.

- [Changed] This version’s release has fewer operations identified in Belarus, Mexico, and Russia. A new set of cattle operations have been detected to reduce false-positive locations (i.e., a poultry farm misclassified as cattle). As a result, each of these countries has fewer locations in the Climate TRACE database relative to last year’s 2024 release.

- [Changed] U.S. Department of Agriculture National Agriculture Statistics Services data were used to estimate state level mean total head of cattle for each operation within their respective U.S. states with no reported estimates or where the regression model was not applied.

- [Changed] U.S. Department of Agriculture National Agriculture Statistics Services data were used to cattle on feed (capacity factor) for beef cattle operations.

- [Changed] Certain cattle operations wet manure management (i.e., lagoons, ponds) were identified using a preliminary beta manure pond detection model. Updated methodology discussing this model will be made available next release.

- [Changed] For cattle operations in countries where the wet manure management beta models weren't deployed, manure management types were defaulted to country-level reported management types and applied to the operations.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Country-level cattle operation manure management emissions may be higher than what is expected for that country. For example, AFG is assigned some lagoon and liquid/slurry systems that may not exist in AFG. As a result, higher than expected emissions occur.

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S., duplicates were caused when a reported location had coordinates set away from the cattle operation, not within the operation. For example, at the end of the CAFO driveway or the owner’s home not at the CAFO. Further work will continue to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist in this sector. If found, please let us know via email and provide the asset id, and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity set to 40,000, and any dairy farm operation with a total head (capacity) greater than 4,000 had their capacity set to 4,000. These are marked in the ‘other2’ column. Future updates will address this issue.

## agriculture,rice-cultivation

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## agriculture,synthetic-fertilizer-application

### Added

- [Added] Data from January through August of 2025. These data were produced using forecasted yields, given that many agricultural systems have not yet harvested crops and there is typically latency in reporting yields in traditional agricultural inventories.

### Changed

-[Changed] Amended methodology to include updates to include detail on emissions reduction solutions. Amended methodology will be made available next release.

### Deprecated

### Removed

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2025-03-01 to end_date 2025-03-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## buildings,residential-onsite-fuel-usage

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,forest-land-clearing

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

- [Fixed] Corrected NaN values in the confidence level column in the 2024 quarterly emissions datasets.

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## forestry-and-land-use,forest-land-degradation

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

- [Fixed] Corrected NaN values in the confidence level column in the 2024 quarterly emissions datasets.

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## forestry-and-land-use,forest-land-fires

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

- [Fixed] Corrected abnormal emission values in Brazil.

- [Fixed] Corrected NaN values in the confidence level column in the 2024 quarterly emissions datasets.

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## forestry-and-land-use,net-forest-land

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,net-shrubgrass

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,net-wetland

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,removals

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,shrubgrass-fires

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

- [Fixed] Corrected NaN values in the confidence level column in the 2024 quarterly emissions datasets.

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## forestry-and-land-use,water-reservoirs

### Added

- [Added] Data period extended for existing sources; added August 2025. The end date is now August 30, 2025.

### Changed

### Deprecated

### Fixed

- [Fixed] ISO3 country code mismatches were fixed.

- [Fixed] Maximum capacities are now estimated from satellite-derived data only, over any given year. Previously, the maximum capacity of a reservoir was calculated using all surface area estimates over a given year, where the values for some months may be equal to the GRanD database surface area value if no satellite-derived estimates are available (i.e., insufficient satellite data for a given month). This resulted in some reservoirs having maximum capacities with very large variance over time, as the GRanD surface area and the satellite-derived surface area may be very different.

### Known Issues

## forestry-and-land-use,wetland-fires

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

- [Fixed] Corrected NaN values in the confidence level column in the 2024 quarterly emissions datasets.

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## fossil-fuel-operations,coal-mining

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-production

### Added

- [Added] Data period calculated for all sources to the end of September 2025.

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in the rest of the world. Start_date 2024-10-01 to end_date 2024-12-31.

### Changed

- [Changed] Updated #403 all Q4 2024 results, including asset, country, and uncertainty, incorporating a lasting operational hurdle that was missed in the previous model.

- [Changed] Updated Q1, Q2, and Q3 2024 results for all Chinese refineries and China country data, as we are incorporating new input from the China National Bureau of Statistics. To be more specific, remodeled capacity factors caused most of the changes.

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-transport

### Added

- [Added] Data period calculated for all sources to the end of September 2025

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## manufacturing,aluminum

### Added

[Added] Submitted a full refresh of the data from 2021 until July 2025.

### Changed

[Changed] Updated the method to report all residual production for alumina and derived capacities by region, using regional capacity factors. The previous method relied on aggregated regional capacities, which were incomplete relative to IAI production data and therefore gave the false impression that production levels were lower than they actually are. Updated methodology will be made available next release. [Changed] Updated model_number to version 3.

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## manufacturing,cement

### Added

[Added] Added new month, July 2025 data included in this release.

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## manufacturing,chemicals

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] Data period extended for existing sources in rest of the world. Start_date 2024-10-01 to end_date 2024-12-31.

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## manufacturing,pulp-and-paper

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## manufacturing,iron-and-steel

### Added

- [Added] Added the estimation of process emissions (IPPU) in column “other8”. This is reported as the ratio between process emissions and direct emissions for each asset.

- [Added] The submission is a full refresh of the data from 2021 until July 2025.

- [Added] Country-level emissions have been submitted with adjusted emission factor values.

### Changed

- [Changed] Adjusted emission factors for different steel production routes to align estimates more closely with WSA and IEA data, both for direct and total emissions.

- [Changed] Calibrated asset-level production values against WSA data to improve correlation with country-level production, and adjusted the emission factors at country level to also improve correlation with country-level emissions.

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,bauxite-mining

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,copper-mining

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,iron-mining

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,rock-quarrying

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,sand-quarrying

### Added

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2019-01-01 to end_date 2025-08-31.

### Changed

- [Changed] Added IND and AUS reported generation to our validation set.

- [Changed] Improved activity based on reported generation data (from CAMD, ENTSO-E, ONS, NPP, and NEM).

- [Changed] Updated unit/plant level information due to manual research. These can reflect changes in our estimates.

- [Changed] Updated links to source data. These can reflect changes in our estimates.

- [Changed] We now have better ownership data, due to improved links in underlying sources.

- [Changed] Pulled fresh EMBER (version 2025-09-25) and EIA International (version 2025-09-24) data used in baseline model estimates.

- [Changed] Updated methodology will be made available next release.

### Fixed

- [Fixed]

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-08-31.

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## transportation,non-broadcasting-shipping

### Added

- [Added] Data period extended. Start_date 2025-09-01 to 2025-09-30

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## transportation,domestic-shipping

### Added

- [Added] OM 1248 new or updated ports

### Changed

- [Changed] Updated methodology will be made available next release.

- [Changed] OM emissions model updated to version om.310725, changes included below.

- [Changed] OM emissions model improved by calculating the required power for a vessel to carry out activities, including acceleration and deceleration.

- [Changed] OM emissions model now uses required power along with fuel calorific content to calculate emissions specific to the predicted fuel type being used by a vessel.

- [Changed] OM port attribution methodology has been improved using clustering algorithms to detect true berthing events. Updated methodology will be provided next release.

- [Changed] OM port attribution algorithm added functionality to identify loitering behaviour before and after port stays.

- [Changed] GFW model updated to version _v20250701.

- [Changed] GFW updated model values for the entire time series of data (2015-01-01 through 2025-08-31). The new model leverages extensive improvements to our vessel characteristics of low-information vessels, as well as improves our modeling of low-load activity, as well as the IMO low sulphur fuel requirement that was implemented in 2020.

- [Changed] GFW expanded vessel coverage to include more 'low-information' vessels.

- [Changed] GFW improved the emissions model by incorporating emissions correction factors for low main engine loads.

- [Changed] GFW improved the emissions model for SOX and PM by accounting for the fact that starting on January 1, 2020, the IMO required lower sulfur content fuel.

- [Changed] GFW improved vessel characteristic model for inferring the main engine power, length, and gross tonnage of low-information vessels.

- [Changed] GFW improved vessel characteristic model for inferring the vessel class of low-information vessels.

- [Changed] GFW improved vessel characteristic model for inferring the subclass of low-information cargo vessels.

- [Changed] GFW developed a new vessel characteristic model for inferring the subclass of low-information tanker vessels (i.e., chemical or oil, liquefied gas, or other liquid).

- [Changed] GFW developed a new vessel characteristic model for inferring the maximum speed design characteristic of low-information vessels.

### Deprecated

- [Deprecated] OM 479 defunct or incorrect ports.

- [Deprecated] OM 34 vessels which did not have sufficient information available to run through the new methodology. Updated methodology will be made available next release.

### Fixed

- [Fixed] OM Duplicated ports removed: Furna vs Fuma.

- [Fixed] OM Various port shapes having incorrect ISO3 codes, or incorrect locations associated.

- [Fixed] OM Some unfinished port stay emissions are incorrectly included in port and country level data from 2018 - 2025 resulting in higher emissions.

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-08-31.

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources. New end_date 2025-08-31.

### Changed

- [Changed] Updated methodology will be made available next release.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Have not updated to the latest Climate TRACE patch of GADM data (v1.1.2).

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-08-01 to end_date 2025-08-31. Now all data runs from 2015-01-01 to 2025-08-31.

### Changed

- [Changed] Updated methodology will be made available next release.

### Fixed

- [Fixed] None

### Known potential issues

- [Known Issues] Asset in China (3199430_INDWW) significantly larger emissions.

---

PDF: [4.8.0_combined-changelog-climate-trace.docx.pdf](./4.8.0_combined-changelog-climate-trace.docx.pdf) · Source: [methodology-documents/2025/CHANGELOG/10_Oct_V4.8.0/4.8.0_combined-changelog-climate-trace.docx.pdf](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/CHANGELOG/10_Oct_V4.8.0/4.8.0_combined-changelog-climate-trace.docx.pdf)

[← V4.X Changelogs](../)
