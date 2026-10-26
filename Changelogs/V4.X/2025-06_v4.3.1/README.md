# [4.3.1] - 2025-06-05

## ClimateTRACE,multiple-sectors

### Added

### Changed

- [Changed] Missing data that are filled using forward or backward fills or averages now use only data from 2020 onwards, except for other-manufacturing, other-chemicals, and other-metals which continue to use all historical data available.

### Deprecated

### Fixed

- [Fixed] Default N2O emissions factor for Oil and Gas Production set to zero, fixing previous N2O data for this subsector which was being set by dummy activity values.

### Known Issues

- [Known Issues] Emissions totals for chemicals and other-chemicals are discrepant between country-level estimates and those in GADM and asset-level estimates for France and Spain due to mis-tagged ISO3 codes for a chemicals plant.

- [Known Issues] Discrepant global totals for other-metals between country-level and gadm-level estimates

- [Known Issues] iron-and-steel, petrochemicals and oil-and-gas-refining have some assets missing data for some timestamps.

## agriculture,crop-residues

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,cropland-fires

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,enteric-fermentation-cattle-operation

### Added

### Changed

### Deprecated

### Fixed

- [Fixed] Previously, total USA country-level emissions (A) were less than the sum of the aggregated USA asset-level emissions (B) due to a bug. Meaning, “A” emissions were less than “B” emissions. This has been fixed where “A” emissions are larger and encompasses “B” emissions.

### Known Issues

- [Known Issues] 469 locations have duplicates. These are located in (iso3 country code): ARG, AUS, BRA, CHN, FRA, GBR, and USA. These duplicate locations will be removed in a future release.

## agriculture,enteric-fermentation-cattle-pasture

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,enteric-fermentation-other

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,manure-applied-to-soils

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,manure-left-on-pasture-cattle

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,manure-management-cattle-operation

### Added

### Changed

### Deprecated

### Fixed

- [Fixed] Previously, total USA country-level emissions (A) were less than the sum of the aggregated USA asset-level emissions (B) due to a bug. Meaning, “A” emissions were less than “B” emissions. This has been fixed where “A” emissions are larger and encompasses “B” emissions.

### Known Issues

- [Known Issues] 469 locations have duplicates. These are located in (iso3 country code): ARG, AUS, BRA, CHN, FRA, GBR, and USA. These duplicate locations will be removed in a future release.

## agriculture,manure-management-other

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,other-agricultural-soil-emissions

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,rice-cultivation

### Added

- Data period extended for 19 existing countries in Southeast Asia, South Asia, and East Asia. Start_date 2024-01-1 to end_date 2024-12-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,synthetic-fertilizer-application

### Added

- Added data going back to 2015, which replaces backfilled values previously used for dates prior to 2021.

### Changed

- [Changed] Updated 2024 csv files

### Changed

### Deprecated

### Fixed

- [Fixed] As referenced in "changed," we were able to correct the 2024 CSV file for country-scale emissions, which did not match the TIFF files.

### Known Issues

## buildings,non-residential-onsite-fuel-usage

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## buildings,other-onsite-fuel-usage

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## buildings,residential-onsite-fuel-usage

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## fluorinated-gases,fluorinated-gases

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,forest-land-clearing

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,forest-land-degradation

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,forest-land-fires

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,net-forest-land

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,net-shrubgrass

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,net-wetland

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,removals

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,shrubgrass-fires

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,water-reservoirs

### Added

- [Added] Data period extended for existing sources. Start_date 2025-01-01 to end_date 2025-03-31.

### Changed

- [Changed] Updated climate data for calculating climate zones to latest version: CRU TS v.4.09 (https://crudata.uea.ac.uk/cru/data/hrg/index.htm#current)

### Deprecated

### Fixed

### Known Issues

- [Known Issues] For certain reservoirs, especially during months where a lack of quality satellite imagery (due to clouds) inhibits accurate surface area estimates, emissions estimates are either anomalously small or zero, relative to previous months. This is technically incorrect and will be mitigated in the future.

## forestry-and-land-use,wetland-fires

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,coal-mining

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-production

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in North America and Europe. Start_date 2024-07-01 to end_date 2024-09-30.

### Changed

- [Changed] #465 ENI Livorno Oil Refinery stopped crude processing on 01/30/2024, in progress to convert to a biorefinery; changed the capacity, capacity factor, and all modeled results for Q2 2024 results.

- [Changed] Updated refinery type for a couple of US refineries, #4, #5, #18,

#63, #64, #68, #98, which has a huge impact on all modeled results.

### Deprecated

### Fixed

- [fixed] Updated #228 all emissions results as we missed modeling that one when turning in the Q2 2024 deliverables.

## fossil-fuel-operations,oil-and-gas-transport

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,other-fossil-fuel-operations

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,other-solid-fuels

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,aluminum

### Added

- [Added] Data period extended for existing sources. Start_date 2025-02-01 to end_date 2025-02-28.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,cement

### Added

- [Added] Data period extended for existing sources. Start_date 2025-02-01 to end_date 2025-02-28.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,chemicals

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,other-manufacturing

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] Data period extended for existing sources in Asia Pacific, Middle East, and rest of world. Start_date 2024-04-01 to end_date 2024-06-30.

- [Added] Data period extended for existing sources in North America and Europe. Start_date 2024-07-01 to end_date 2024-09-30.

- [Added] Added ownership data

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,pulp-and-paper

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,iron-and-steel

### Added

- [Added] Data period extended for existing sources. Start_date 2025-02-01 to end_date 2025-02-28.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,other-chemicals

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,glass

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,lime

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,food-beverage-tobacco

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,wood-and-wood-products

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,textiles-leather-apparel

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,other-metals

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,other-mining-quarrying

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,bauxite-mining

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,copper-mining

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,iron-mining

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,rock-quarrying

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,sand-quarrying

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2019-01-01 to end_date 2025-03-31.

### Changed

- [Changed] Several unit attributes were updated due to manual research. These can reflect changes in our estimates.

- [Changed] Updated underlying source data from GEM and EIA. These can reflect changes in our estimates.

### Fixed

### Known Issues

## power,other-energy-use

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## power,heat-plants

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-03-31.

- [Added] Added coverage. 79 airports were added.

### Changed

- [Changed] Updated historical data from 2015-01-01 to 2022-12-31 from annual to monthly temporal granularity.

- [Changed] Updated fuel burn estimates for some aircraft types. Aircraft types which depend on ICAO Fuel consumption tables updated to use ICAO Carbon Emissions Calculator Methodology v13.1.

- [Changed] Updated metadata [confidence, uncertainty, ownership].

### Fixed

- [Fixed] Updated ownership data fixes issue with airline operation percentages at airports.

## transportation,non-broadcasting-shipping

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,domestic-shipping

### Added

- [Added] Data period extended for existing sources. Start_date 2025-03-01 to end_date 2025-03-31.

### Changed

- [Changed] - All pollutant emissions columns (i.e., *_emissions) are now in units of metric tonnes.

- [Changed] - All pollutant emissions factor columns (i.e., *_emissions_factor) are now in units of metric tonnes per unit activity (i.e., nautical mile).

- [Changed] - Ports that have previously been reported on but do not have any emissions for the current month are now included with 0 values for all emissions and emissions factors.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] Duplicated ports identified : Furna vs Fuma.

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-03-31.

- [Added] Added coverage. 15 airports were added.

### Changed

- [Changed] Updated historical data from 2015-01-01 to 2022-12-31 from annual to monthly temporal granularity.

- [Changed] Updated fuel burn estimates for some aircraft types. Aircraft types which depend on ICAO Fuel consumption tables updated to use ICAO Carbon Emissions Calculator Methodology v13.1.

- [Changed] Updated metadata [confidence, uncertainty, ownership]

### Fixed

- [Fixed] Updated ownership data fixes issue with airline operation percentages at airports.

## transportation,international-shipping

### Added

- [Added] Data period extended for existing sources. Start_date 2025-03-01 to end_date 2025-03-31.

### Changed

- [Changed] - All pollutant emissions columns (i.e., *_emissions) are now in units of metric tonnes.

- [Changed] - All pollutant emissions factor columns (i.e., *_emissions_factor) are now in units of metric tonnes per unit activity (i.e., nautical mile).

- [Changed] - Ports that have previously been reported on but do not have any emissions for the current month are now included with 0 values for all emissions and emissions factors.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] Duplicated ports identified : Furna vs Fuma.

## transportation,other-transport

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,railways

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources. New end_date 2025-03-31.

- [Added] Full uncertainty calculations for GADM 1 and GADM 2 assets.

### Changed

- [Changed] Updated data due to interpolation from 2024-07-01 to 2025-02-28.

- [Changed] Uncertainty calculations have changed from partial data set.

### Deprecated

### Fixed

- [Fixed] Corrected city aggregation data to match data updates due to interpolation from 2024-07-01 to 2025-02-28.

### Known issues

- [Known Issues] Missing fields in uncertainty calculations due to insufficient statistics of some sparse road assets.

## waste,biological-treatment-of-solid-waste-and-biogenic

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-02-01 to end_date 2025-03-01. Now all data runs from 2015-01-01 to 2025-03-01.

### Fixed

- [Fixed] Added back missing July 2024.

- [Fixed] Corrected technology type labeling and emissions for lagoons in Brazil.

### Known potential issues

- [Known Issues] 1,461 assets in Mexico need to be removed. These assets have start dates beginning in ‘2024-08-01’.

## waste,incineration-and-open-burning-of-waste

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-02-01 to end_date 2025-03-01. Now all data runs from 2015-01-01 to 2025-03-01.

### Fixed

- [Fixed] Added back missing July 2024.

### Known potential issues

- [Known Issues] Asset in China (3199430_INDWW) significantly larger emissions. This will be fixed in future releases.

## waste,solid-waste-disposal

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

---

PDF: [4.3.1_combined-changelog-climate-trace.docx.pdf](./4.3.1_combined-changelog-climate-trace.docx.pdf) · Source: [methodology-documents/2025/CHANGELOG/05_May_v4.3.1/4.3.1_combined-changelog-climate-trace.docx.pdf](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/CHANGELOG/05_May_v4.3.1/4.3.1_combined-changelog-climate-trace.docx.pdf)

[← V4.X Changelogs](../)
