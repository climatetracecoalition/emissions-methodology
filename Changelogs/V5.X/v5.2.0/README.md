# [5.2.0] - 2025-12-12

## ClimateTRACE,deprecation-warning

For the current (V5.2.0) release, the following Deprecation Warning is now in effect:

- [Deprecation Warning] The following BigQuery tables are now deprecated and removed in V5.2.0: `climate_trace.road-segments_road-transportation_202505` and `climate_trace.shipping-voyages_shipping_2025`. These tables have been replaced by the following BigQuery tables: `climate_trace.road_segments` and `climate_trace.shipping_voyages` respectively. All future updates will be applied to the new tables only.

## ClimateTRACE,multiple-sectors,post-processing

### Added

### Changed

### Deprecated

### Fixed

- [Fixed] Country emissions for domestic-wastewater-treatment were missing in V5.1.0 for January 2015 for all countries. Fixed in this release.

### Known Issues

- [Known Issues] For sectors with native temporal granularity of “quarterly”, published monthly data (including emissions_quantity, activity, capacity, etc.) are rounded to the 5th decimal place, which results in very small values being rounded down to 0. Affected sectors: ‘enteric-fermentation-cattle-operation’ and ‘manure-management-cattle-operation’.

## ClimateTRACE,individual-changelogs

## agriculture,enteric-fermentation-cattle-operation

### Added

- [Added] Japan (JPN) coverage to the Climate TRACE database- an estimated 2,287 assets (cattle operations) have been identified. See methodology for more information: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/A griculture/Cattle%20Operations-%20Asset-level%20Enteric%20Fermentation%20and%20 Manure%20Management%20Emissions-AgricultureSector-112025.docx.pdf

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S. this was caused when a reported state government CAFOs had location coordinates set away from the operation        not within the operation. For example, at the end of the CAFO driveway leading into the operation or the owners home away from the CAFO. Further work will continue  to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist for this sector. If found, please let us know via email and provide the asset id and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity capped at 40,000. Additionally, any dairy farm operation with a total head (capacity) greater than 4,000 had their capacity capped at 4,000. These are marked in the ‘other2’ column. Future updates will address this issue.

## agriculture,manure-management-cattle-operation

### Added

- [Added] Japan (JPN) coverage to the Climate TRACE database- an estimated 2,287 assets (cattle operations) have been identified. See methodology for more information: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/A griculture/Cattle%20Operations-%20Asset-level%20Enteric%20Fermentation%20and%20 Manure%20Management%20Emissions-AgricultureSector-112025.docx.pdf

- [Added] JPN cattle operations wet manure management (i.e., lagoon ponds) were identified using a preliminary beta manure pond detection model.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S., this was caused when a reported state government CAFOs had location coordinates set away from the operation not within the operation. For example, at the end of the CAFO driveway leading into the operation or the owners home away from the CAFO. Further work will continue to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist for this sector. If found, please let us know via email and provide the asset id and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity capped at 40,000. Additionally, any dairy farm operation with a total head (capacity) greater  than 4,000 had their capacity capped at 4,000. These are marked in the ‘other2’ column. Future updates will address this issue.

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2025-5-01 to end_date 2025-5-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## buildings,residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2025-5-01 to end_date 2025-5-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,water-reservoirs

### Added

- [Added] Data period extended for existing sources; added September 2025. End date is now October 31, 2025.

### Changed

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in APAC and the Middle East. Start_date 2025-01-01 to end_date 2025-03-31.

- [Added] SO2 and PM2.5 uncertainty results added, including all assets in US, Europe, APAC, and the Middle East. Start_date 2025-01-01 to end_date 2025-03-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,aluminum

### Added

- [Added] Added new month. September 2025 data included this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,cement

### Added

- [Added] Added new month, September 2025 data included in this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,chemicals

### Added

### Changed

- [Changed] Resubmission of asset dataset with duplicates removed & asset location fixed (see below). Start_date 2021-01-01 to end_date 2024-12-31.

### Deprecated

### Fixed

- [Fixed] Corrected location for asset 45257091.

### Known Issues

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] Data period extended for existing sources in Asia Pacific and Middle East. Start_date 2025-01-01 to end_date 2025-03-31

- [Added] Non-GHG emissions for existing sources in Asia Pacific and Middle East. CO, N2O, PM10, PM2.5, SO2, and VOC emissions are modeled. For methodology for non-ghg emissions please visit methodology page: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/M anufacturing%20and%20Industrial%20Processes/Petrochemical%20Ethylene%20Steam%20 Cracker%20Emissions-ManufacturingandIndustrialProcessesSector-112025.docx.pdf

- [Added] Asset ID 239 Long Son Petrochemicals in Vietnam.

### Changed

- [Changed] Asset ID 84 changed refinery match ID from 296 to 343.

### Deprecated

### Fixed

### Known Issues

## manufacturing,pulp-and-paper

### Added

### Changed

- [Changed] Resubmission of asset dataset with duplicates removed & asset location fixed (see below). Start_date 2021-01-01 to end_date 2024-12-31.

### Deprecated

### Fixed

- [Fixed] Corrected location for asset 44375455.

### Known Issues

## manufacturing,iron-and-steel

### Added

- [Added] Added new month, September 2025 data included in this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2019-01-01 to end_date 2025-10-31.

### Changed

- [Changed] Updated unit/plant level information due to manual research. These can reflect changes in our estimates.

- [Changed] Updated and added new links to source data. These can reflect changes in our estimates.

- [Changed] Updated reported generation validation tests.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-10-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,domestic-shipping

### Added

- [Added] Data period extended. Start date 2025-10-01 to 2025-10-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-10-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,international-shipping

### Added

- [Added] Data period extended. Start date 2025-10-01 to 2025-10-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources (start_date 2025-10-01 to end_date 2025-10-31).

- [Added] Data period updated for historic country data (start_date 2015-01-01 to end_date 2025-09-30).

- [Added] Data period updated for historic asset data (start_date 2021-01-01 to end_date 2025-09-30)

### Changed

- [Changed] Fixed inflated 2025 emissions data

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Have not updated to the latest Climate TRACE patch of GADM data (v1.1.2).

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-10-01 to end_date 2025-10-31.

### Changed

- [Changed] Previous versions’ country-level data from start_date 2015-01-01 to end_date 2025-10-31 excluded `untreated wastewater` contributions. This release includes ‘untreated wastewater’ contributions.

### Deprecated

### Fixed

- [Fixed] Updated country data has corrected erroneously high emissions for some countries for July - September 2025 in V5.1.0.

### Known Issues

- [Known Issues] Duplicate assets, issues originating from underlying dataset.

- [Known Issues] 56 additional assets have location coordinates which are insufficiently precise, and which have not been verified.

### Known Issues

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-10-01 to end_date 2025-11-30. Now all data runs from 2015-01-01 to 2025-11-30.

### Changed

- [Changed] Previous versions’ country-level data from start_date 2015-01-01 to end_date 2025-10-31 excluded `untreated wastewater` contributions. This release includes ‘untreated wastewater’ contributions.

### Deprecated

### Fixed

- [Fixed] Updated country data has corrected erroneously high emissions for some countries for July - September 2025 in V5.1.0.

### Known Issues

- [Known Issues] Duplicate assets, issues originating from underlying dataset.

- [Known Issues] 56 additional assets have location coordinates which are insufficiently precise, and which have not been verified.

## waste,solid-waste-disposal

### Added

### Changed

- [Changed] Previous releases’ monthly data were created by disaggregating annual estimates. For this release, monthly data is now generated natively with modeling.

- [Changed] Previously, the area-to-incoming-waste model intercept was not set to (0,0). The (0,0) intercept has been reintroduced to this version update. As a result, modeled waste based on landfill size has been changed for landfills that use this model.

- [Changed] Sites flagged by International Methane Emissions Observatory (IMEO) as ‘not waste sites’ were removed.

- [Changed] Aligned ISO3 codes to asset latitude and longitude. Previously, ISO3 codes did not match their respective latitude and longitude location.

- [Changed] Adjusted emissions and waste in place projection model for non-first-order decay (FOD) sites.

### Deprecated

### Fixed

### Known Issues

---

PDF: [5.2.0_combined-changelog-climate-trace.docx.pdf](./5.2.0_combined-changelog-climate-trace.docx.pdf) · Source: [methodology-documents/2025/CHANGELOG/12_Dec_V5.2.0/5.2.0_combined-changelog-climate-trace.docx.pdf](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/CHANGELOG/12_Dec_V5.2.0/5.2.0_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
