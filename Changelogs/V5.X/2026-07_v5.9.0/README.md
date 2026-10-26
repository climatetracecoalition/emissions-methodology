# [5.9.0] - 2026-07-29

## ClimateTRACE,deprecation-warning

- The data download packages at https://climatetrace.org/data will be replaced with a new data download tool on our upcoming August 27, V5.10.0, release.

- The other-fossil-fuel-operations subsector will be deprecated in an upcoming release, no earlier than V5.10.0, as coal-mining, oil-and-gas-production, and oil-and-gas-transport will be incorporated into this subsector’s emissions.

## ClimateTRACE,multiple-sectors,post-processing

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known issue] other-energy-use PM2.5 emissions may be inflated up to 20x due to an incorrect ratio applied to CO2e values.

## ClimateTRACE,individual-changelogs

## agriculture,crop-residues

### Added

- [Added] New dataset - Spatial Production Allocation Model (SPAM) 2020 - used to extend emissions to 40 crop groups. Source: https://sti-portal.fao.org/innovations/spatial-production-allocation-model-spam -2020-country-studies-crop-production-systems

- [Added] Extended crop residue emissions to an additional 158 countries.

### Changed

- [Changed] 2025 production and harvested area forecasts generated using an AI-based ensemble model.

### Deprecated

- [Deprecated] 26 crop groups derived from Grogan et al. (2022). Source: https://www.nature.com/articles/s41597-021-01115-2

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## agriculture,cropland-fires

### Added

- [Added] New dataset - Spatial Production Allocation Model (SPAM) 2020 - used to extend emissions to 40 crop groups. Source: https://sti-portal.fao.org/innovations/spatial-production-allocation-model-spam -2020-country-studies-crop-production-systems

- [Added] Extended cropland fires emissions to an additional 158 countries.

### Changed

- [Changed] 2025 production and harvested area forecasts generated using an AI-based ensemble model.

### Deprecated

- [Deprecated] 26 crop groups derived from Grogan et al. (2022). Source: https://www.nature.com/articles/s41597-021-01115-2

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## agriculture,manure-applied-to-soils

### Added

- [Added] New dataset - Spatial Production Allocation Model (SPAM) 2020 - used to extend emissions to 40 crop groups. Source: https://sti-portal.fao.org/innovations/spatial-production-allocation-model-spam -2020-country-studies-crop-production-systems

- [Added] Extended manure applied to soil emissions to an additional 158 countries.

### Changed

- [Changed] Updated the manure application calculation methodology for 2015 to 2025 to include 40 crop groups across 174 countries.

- [Changed] 2025 production and harvested area forecasts generated using an AI-based ensemble model.

- [Changed] Manure application estimates derived using updated methods that distribute manure across crops and grid cells.

### Deprecated

- [Deprecated] 26 crop groups derived from Grogan et al. (2022). Source: https://www.nature.com/articles/s41597-021-01115-2

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## agriculture,synthetic-fertilizer-application

### Added

- [Added] New dataset - Spatial Production Allocation Model (SPAM) 2020 - used to extend emissions to 40 crop groups. Source: https://sti-portal.fao.org/innovations/spatial-production-allocation-model-spam -2020-country-studies-crop-production-systems

- [Added] Extended synthetic fertilizer emissions to an additional 158 countries.

### Changed

- [Changed] Updated the synthetic fertilizer calculation methodology for 20152025 to include 40 crop groups across 174 countries.

- [Changed] 2025 production and harvested area forecasts generated using an AI-based ensemble model.

- [Changed] Synthetic fertilizer estimates derived using updated methods that distribute nitrogen fertilizer across crops and grid cells.

### Deprecated

- [Deprecated] 26 crop groups derived from Grogan et al. (2022). Source: https://www.nature.com/articles/s41597-021-01115-2

### Fixed

- [Fixed] Synthetic fertilizer application activity units corrected to be the kg of N applied in each month corresponding to monthly granularity timestamps rather than the average kg/year.

### Known Issues

- [Known Issues] Unrealistic disjoint in 2023 timeseries for CHN and UKR.

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2026-05-01 to end_date 2026-05-31.

### Changed

- [Changed] Updated historical data for existing sources. Start_date 2026-01-01 to end_date 2026-04-30.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## forestry-and-land-use,forest-land-clearing

### Added

-[Added] Added the missing Ghana 2026 Q1 data for forest land clearing and degradation sectors.

### Changed

- [Changed] None

### Deprecated

-[Deprecated] None

### Fixed

-[Fixed] None

### Known Issues

- [Known Issue] The 2026 quarterly emissions dataset utilizes CTrees 2026 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. Due to heavy snow cover in late 2025 and early 2026, LUCA does not update Q1 disturbance estimates in some high-latitude northern countries, which may affect the attribution of emissions among deforestation, degradation, and fire. For countries without updated LUCA observations, temporal mean values were used to fill the estimates.

## forestry-and-land-use,forest-land-degradation

### Added

-[Added] Added the missing Ghana 2026 Q1 data for forest land clearing and degradation sectors.

### Changed

- [Changed] None

### Deprecated

-[Deprecated] None

### Fixed

-[Fixed] None

### Known Issues

- [Known Issue] The 2026 quarterly emissions dataset utilizes CTrees 2026 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. Due to heavy snow cover in late 2025 and early 2026, LUCA does not update Q1 disturbance estimates in some high-latitude northern countries, which may affect the attribution of emissions among deforestation, degradation, and fire. For countries without updated LUCA observations, temporal mean values were used to fill the estimates.

## fossil-fuel-operations,coal-mining

### Added

- [Added] Historical refresh of existing data and data period extended through

2025. New period: Start_date 2015-01-01 to end_date 2025-12-31.

- [Added] Additional coverage- 516 coal mines added.

- [Added] Emissions from fuel combustion in other10

### Changed

- [Changed] Updated underlying historical data for existing sources (and added 2025 data) based on Global Energy Monitor's (GEM) May 2026 update of its Global Coal Mine Tracker dataset.

### Deprecated

- [Deprecated] 61 coal mines removed due to updated Operating Status of Cancelled or Shelved for sources without production data.

### Fixed

- [Fixed] Some ‘Opening Year’ data wasn't previously being used to due a bug; as such, sources missing production data for some years may have been incorrectly backfilled to before the actual ‘Opening Year’.

### Known Issues

- [Known Issues] GEM's May 2026 update to its Global Coal Mine Tracker changed the ‘Opening Year’ dataset to reflect the ‘Opening Year’ of a mine expansion in many cases. While prior Opening Year data was substituted in this release to prevent use of an incorrect ‘Opening Year’ representing an expansion, the true ‘Opening Year’ data from the May 2026 GEM update is being obtained from GEM and any necessary corrections will be made in V5.10.0.

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for all existing assets. Start_date 2025-07-01 to end_date 2025-09-30.

- [Added] Added percent breakdowns of CO2 emissions across combustion (other3 column), fugitive and process (other4 column), and flaring (other5 column). These modeled results are estimated for all existing assets. See methodology for additional information.

### Changed

- [Changed] Updated the historical annual PM2.5 results (emission factor and total emissions) for all existing assets from 2021–2024.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] schema units for other3, other4, and other5 are blank but should be % Tonnes of CO2

## manufacturing,aluminum

### Added

- [Added] Full refresh of aluminium and alumina assets (01/01/2021 - 04/30/2026).

- [Added] New “Integrated” asset_type for facilities with both smelting and refining.

- [Added] Additional columns ‘other6’ (Percentage of emissions from smelting) and ‘other7’ (Percentage of emissions from fuel combustion) added. See methodology for additional information.

- [Added] The number of operating assets drops from 290 in 2021 to 239 in 2022. This represents 51 Chinese aluminium smelters and refineries that were closed in 2021 due to a number of reasons including government energy consumption limits, the 2021 coal and power crisis, and the 45-million tonne national capacity cap.

- [Added] Included new asset capacity data source (Industrial Information Resources) and updated asset smelter capacity data using the Light Metal Age data source.

### Changed

- [Changed] Emissions factor methodology changed to include fuel type as a factor.

### Deprecated

- [Deprecated] Regional 'assets' e.g. IND-Belgaum are removed.

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,cement

### Added

- [Added] Full refresh of asset-level emissions from 2021 to May 2026.

- [Added] Newly identified cement assets added to the database.

- [Added] Full refresh of country-level emissions from 2015 to May 2026.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] Data period extended for existing sources. Start_date 2025-07-01 to end_date 2025-09-30.

- [Added] Percent of CO2 emissions attributed to combustion, fugitive, and flaring emissions. Based on literature it is estimated 90% of CO2 emissions come from combustion (other3), 3% of emissions from fugitive (other4), and 7% of emissions from flaring (other5). See methodology for additional information.

### Changed

- [Changed] Updated the historical annual PM2.5 results (emission factor and total emissions) for all existing assets from 2021–2024.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] schema units for other3, other4, and other5 are blank but should be % Tonnes of CO2.

- [Known Issues] Data on percent of CO2 emissions attributed to combustion, fugitive, and flaring emissions only available for 2025.

## manufacturing,iron-and-steel

### Added

- [Added] Full refresh of asset-level emissions from 2021 to May 2026.

- [Added] New steel capacity type for induction furnaces (IF) and direct reduced iron - induction furnace (DRI-IF).

- [Added] Full refresh of country-level emissions from 2021 to May 2026.

### Changed

- [Changed] Direct reduced iron (DRI) emission factor now accounts for the proportion of natural gas, coal, and hydrogen DRI at asset level.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] Country, GADM, and GHS-FUA aggregated emissions quantities in HUN in the iron-and-steel sector are spuriously inflated pre-2021 and deflated in 2024 onward due to poor extrapolation.

- [Known Issue] 45 assets persist in this sector that should have been removed with the V5.9.0 data update. As a result, the asset emissions table is inflated by a total of ~40M tonnes per year.

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

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-05-31.

### Changed

- [Changed] Updated unit/plant level information due to manual research. These can result in changes to our estimates.

- [Changed] Improved linkages to generation sources, which results in changes to our estimates.

- [Changed] Included most recent months from reported generation sources. These can result in changes to our estimates.

- [Changed] Minor naming convention updates across ownership entities (sourced from Global Energy Monitor).

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

- [Known Issues] Our remote sensing-based estimates of plant activity are biased low in some grid regions including China. We are working to address the bias in future releases.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-05-31.

- [Added] Added coverage. 7 new sources added, listed with their International Air Transport Association (IATA) code: {'iata_AXO', 'iata_DBM', 'iata_DEJ', 'iata_LTT', 'iata_LYN', 'iata_MTF', 'iata_OKU'}.

- [Added] Landing and take-off (LTO)-cycle emissions fields. other1 = LTO cycle CO2 emissions (tonnes); other2 = LTO-cycle NOx emissions (tonnes).

### Changed

- [Changed] None

### Fixed

- [Fixed] None

### Deprecated

- [Deprecated] None

#### Known Issues

- [Known Issues] None

## transportation,non-broadcasting-vessels

### Added

- [Added] Data period extended. Start_date 2026-05-01 to 2026-05-31.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## transportation,domestic-shipping

### Added

- [Added] Data period extended. Start date 2026-05-01 to 2026-05-31.

- [Added] ERS data refresh for 2025 baseline.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-05-31.

- [Added] Added coverage. 4 new sources added, listed with their International Air Transport Association (IATA) code: {'iata_BUX', 'iata_MGM', 'iata_MTR', 'iata_TUL'}

- [Added] Landing and take-off (LTO)-cycle emissions fields. other1 = LTO cycle CO2 emissions (tonnes); other2 = LTO-cycle NOx emissions (tonnes).

### Changed

- [Changed] None

### Fixed

- [Fixed] None

### Deprecated

- [Deprecated] None

#### Known Issues

- [Known Issues] None

## transportation,international-shipping

### Added

- [Added] Data period extended. Start date 2026-05-01 to 2026-05-31.

- [Added] ERS data refresh for 2025 baseline.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends

- [Known Issues] Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port

## transportation,road-transportation

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Unrealistic spike in pm2.5 emissions at the sector level in 2026.

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Domestic-wastewater-treatment-and-discharge: seasonally inconsistent n2o emissions factor values used in Ethiopia are likely deflating emissions for most of 2025 through Feb 2026, causing the March 2026 data to appear as an outlier.

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known issue] Some industrial-wastewater-treatment-and-discharge emissions are not accounted for in GADM and GHS-FUA aggregations, specifically source ids: 4416918, 4416936, 4416951, 4416956, 4416968, 4416970, 4416979, 4417011, 4417021, 4417025, 4417083, 4417086, 4417116, 4417119, 4417122, 4417125, 4417183, 4417185, 4417190, 4417194, 4417197, 4417198, 4417206, 4417214, 4417220, 4417225, 4417228, 4417244, 4417251, 4417252, 4417291, 4417305, 4417321, 4417355, 4417357, 4417361, 4417363, 4417364, 4417366, 4417373, 4417375, 4417377, 4417382, 4417384, 4417387, 4417388, 4417391, 4417396, 4417399, 4417405, 4417411, 4417413, 4417414, 4417422, 4417423, 4417426, 4417432, 4417440, 4417442, 4417443, 4417444, 4417445, 4417446, 4417447, 4417451, 4417452, 4417453, 4417457, 4417462, 4417473, 4417490, 4417494, 4417496, 4417498, 4417502, 4417507, 4417509, 4417534, 4417558, 4417560, 4417566, 4417574, 4417583, 4417596, 4417597, 4417593, 4417619, 4417622, 4417634, 4417637, 4417639, 4417650, 4417653, 4417654, 4417695, 4417699, 4417701, 4417712, 4417726, 4417738, 4417748, 4417757, 4417780, 4417809, 4417813, 4417528.

---

PDF: [5.9.0_combined-changelog-climate-trace.docx.pdf](./5.9.0_combined-changelog-climate-trace.docx.pdf) · Source: [methodology-documents/2026/CHANGELOG/07_Jul_V5.9.0/5.9.0_combined-changelog-climate-trace.docx.pdf](https://github.com/climatetracecoalition/methodology-documents/blob/main/2026/CHANGELOG/07_Jul_V5.9.0/5.9.0_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
