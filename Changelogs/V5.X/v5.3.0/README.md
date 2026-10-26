# [5.3.0] - 2026-01-28

## ClimateTRACE,deprecation-warning

- No deprecation warnings in this release.

## ClimateTRACE,multiple-sectors,post-processing

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] Error in imputation of country-level pre-2021 road-transportation resulting in a ~2% increase in road transportation emissions before 2021.

- [Known Issue] iron-and-steel assets were incorrectly extrapolated forward rather than being set to a “closed” state with 0 emissions. Affected asset IDs are: 1566424, 1566477, 1566542, 1566555, 1566559, 1566564, 1566578, 1566580, 1566620, 1566648, 1566669, 1566770, 1566825, 1566949, 1566965, 1567083, 1567106, 1567145, 1567184, 1567187, 1567226, 1567250, 1567255, 1567256, 1567257, 1567259, 1567263, 1567268, 1567271, 1567273, 1567274, 1567275, 1567280, 1567281, 1567282, 1567285, 1567286, 1567290, 1567291, 1567292, 1567294, 1567295, 1567296, 1567297, 1567299, 1567300, 1567301, 1567303, 1567305, 1567312, 1567313, 1567314, 1567315, 1567316, 1567317, 1567318, 1567319, 1567320, 1567321, 1567322, 1567323, 1567324, 1567325, 1567326, 1567327, 32441205, 32441208, 32441223, 32441224, 32441229, 32441253, 38089228, 42741547, 42741574, 42741753, 42741756, 42741765, 42741804, 42741864, 42741875.

- [Known Issue] Two domestic-wastewater-treatment-and-discharge assets were assigned the wrong ISO-3 country code: 48250739 and 48251021 were incorrectly tagged to CAF and COD rather than SLB and UGA, respectively.

## ClimateTRACE,individual-changelogs

## agriculture,crop-residues

### Added

- [Added] Monthly data added from Oct'25 to Dec'25.

### Changed

### Deprecated

### Removed

### Known Issues

## agriculture,cropland-fires

### Added

- [Added] Monthly data added from Oct'25 to Dec'25.

### Changed

### Deprecated

### Removed

### Known Issues

## agriculture,enteric-fermentation-cattle-operation

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] An error in the agolin emission reduction solution (ERS) applied to individual cattle operations has existed since the v4.8.0 release, resulting in overestimated methane emissions’ reductions. This will be corrected in a future release.

- [Known Issues] Duplicate and false-positive/false-negative cattle operations may exist since the v4.8.0 release. Please report any issues by email with the asset ID and latitude/longitude.

## agriculture,enteric-fermentation-cattle-pasture

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] An error in the agolin emission reduction solution (ERS) applied to individual cattle operations has existed since the v4.8.0 release, resulting in overestimated methane emissions’ reductions. This will be corrected in a future release.

## agriculture,manure-applied-to-soils

### Added

- [Added] Monthly data added from Oct'25 to Dec'25

### Changed

### Deprecated

### Removed

### Known Issues

## agriculture,rice-cultivation

### Added

### Changed

- [Changed] We identified an issue where monthly emissions associated with rice cultivation in Southeast Asia were previously concentrated in the harvest month rather than the distributing emissions throughout the growing season. We implemented an approach to more evenly distribute those emissions in this release.

- [Changed] We identified an issue where some GADMs in PRK and CHN had outsized emission factors. We corrected these emission factors by re-running the model.

### Deprecated

### Removed

### Known Issues

## agriculture,manure-management-cattle-operation

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] An error in the agolin emission reduction solution (ERS) applied to individual cattle operations has existed since the v4.8.0 release, resulting in overestimated methane emissions’ reductions. This will be corrected in a future release.

- [Known Issues] Duplicate and false-positive/false-negative cattle operations may exist since the v4.8.0 release. Please report any issues by email with the asset ID and latitude/longitude.

## agriculture,synthetic-fertilizer-application

### Added

- [Added] Monthly data added from Oct'25 to Dec'25

### Changed

### Deprecated

### Removed

### Known Issues

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2025-6-01 to end_date 2025-6-30.

### Changed

### Deprecated

### Fixed

### Known Issues

## buildings,residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2025-6-01 to end_date 2025-6-30.

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,forest-land-clearing

### Added

- [Added] Added 2025 Q3 emissions data.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## forestry-and-land-use,forest-land-degradation

### Added

- [Added] Added 2025 Q3 emissions data.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## forestry-and-land-use,forest-land-fires

### Added

- [Added] Added 2025 Q3 emissions data.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## forestry-and-land-use,shrubgrass-fires

### Added

- [Added] Added 2025 Q3 emissions data.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## forestry-and-land-use,wetland-fires

### Added

- [Added] Added 2025 Q3 emissions data.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early-mid 2025.

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in the rest of the world. Start_date 2025-01-01 to end_date 2025-03-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,aluminum

### Added

- [Added] Added new month, October 2025 data included in this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,cement

### Added

- [Added] Added new month, October 2025 data included in this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] Data period extended for existing sources in Asia Pacific and Middle East. Start_date 2025-01-01 to end_date 2025-03-31. -[Added] Asset ID 239 Long Son Petrochemicals in Vietnam. -[Added] Non-GHG emissions for existing sources in Asia Pacific and Middle East. CO, N2O, PM10, PM2.5, SO2, and VOC emissions are modeled. For methodology for non-ghg emissions please visit the methodology: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/M anufacturing%20and%20Industrial%20Processes/Petrochemical%20Ethylene%20Steam%20 Cracker%20Emissions-ManufacturingandIndustrialProcessesSector-112025.docx.pdf

### Changed

-[Changed] Asset ID 84 changed refinery match ID from 296 to 343.

### Deprecated

### Fixed

### Known Issues

## manufacturing,iron-and-steel

### Added

- [Added] Added new month, October 2025 data included in this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## mineral-extraction,bauxite-mining

### Added

### Changed

- [Changed] Updated metadata [activity, CO2_emissions_factor, CO2_emissions].

### Deprecated

### Fixed

- [Fixed] Removed activity and emissions data incorrectly duplicated to additional asset (BAU-042003).

### Known Issues

- [Known Issues]

## mineral-extraction,copper-mining

### Added

### Changed

- [Changed] Updated metadata [location, capacity_factor, activity, CO2_emissions_factor, CO2_emissions, status]

### Deprecated

### Fixed

- [Fixed] Corrected CO2 emissions factor for multiple assets under group ownership, with subsequent updates to national/regional average values.

### Known Issues

- [Known Issues]

## mineral-extraction,iron-mining

### Added

### Changed

- [Changed] Updated metadata [location, CO2_emissions_factor, CO2_emissions].

### Deprecated

### Fixed

- [Fixed] Updated incorrect CO2 emissions factor for 3 assets (IRO-003004, IRO-003005 and IRO-045092).

### Known Issues

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2019-01-01 to end_date 2025-11-30.

- [Added] 1,888 assets. Total assets = 11,615.

### Changed

- [Changed] Updated to Global Energy Monitor Global Bioenergy Power Tracker (version: October 2025).

- [Changed] Updated unit/plant level information due to manual research. These can reflect changes in our estimates.

- [Changed] Updated and added new links to source data. These can reflect changes in our estimates.

- [Changed] Pulled newly released and most recent months from reported generation sources.

- [Changed] Updated reported generation validation tests.

### Fixed

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

## power,other-energy-use

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-11-30.

- [Added] 6 assets. Total assets 4,861.

### Changed

### Fixed

## transportation,non-broadcasting-shipping

### Added

- [Added] Data period extended. Start_date 2025-11-01 to 2025-11-30.

### Changed

### Deprecated

### Fixed

### Known issue

## transportation,domestic-shipping

### Added

- [Added] Data period extended. Start date 2025-11-01 to 2025-11-30.

- [Added] 3 assets. Total assets = 9,143.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-11-30.

- [Added] 10 assets Total assets = 2,214.

### Changed

### Fixed

## transportation,international-shipping

### Added

- [Added] Data period extended. Start date 2025-11-01 to 2025-11-30.

- [Added] 6 assets. Total assets = 8,718.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

---

PDF: [5.3.0_combined-changelog-climate-trace.docx.pdf](./5.3.0_combined-changelog-climate-trace.docx.pdf) · Source: [methodology-documents/2026/CHANGELOG/01_Jan_V5.3.0/5.3.0_combined-changelog-climate-trace.docx.pdf](https://github.com/climatetracecoalition/methodology-documents/blob/main/2026/CHANGELOG/01_Jan_V5.3.0/5.3.0_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
