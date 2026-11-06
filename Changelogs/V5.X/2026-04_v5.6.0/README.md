# [5.6.0] - 2026-04-29

## ClimateTRACE,deprecation-warning

- None

## ClimateTRACE,multiple-sectors,post-processing

### Added

- [Added] None

### Changed

- [Changed] Emissions reductions from ERS are now calculated against 2025 annual emissions quantities as the baseline (previously, this was 2024).

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Oil-and-gas-production, domestic-shipping, and international-shipping ERS need to be updated to be valid for the 2025 baseline. Currently, uses 2024-dependent information for strategies.

- [Known Issues] A subset of assets in the iron-and-steel , domestic-shipping and international-shipping sub-sectors have incorrect non-zero activity and emissions when the asset is closed or inactive. We provided the “5.6.0_inactive_closed_assets.csv” which  lists the asset_ids of these assets and additional information: the min_start and max_end dates when the asset was actually active, the spurious additional 100-yr-GWP CO2E emissions (in Mt) extrapolated outside those active dates (inflated_extrap_emis ), the total emissions when the asset was open (baseline_emissions), and ratio of the these two quantities in percent (inflated_over_baseline_pct). This issue is only present in V5.6.0, not in previous releases.

- [Known Issues] Asset closures in the iron-and-steel subsector are not accounted for in extrapolated country-level emissions. This issue has been present since at least V4.0.0.

- [Known Issues] Country, GADM, and GHS-FUA aggregated emissions quantities in HUN in the iron-and-steel sector are spuriously inflated pre-2021 due to poor extrapolation.

## ClimateTRACE,individual-changelogs

## agriculture,enteric-fermentation-cattle-operation

### Added

- [Added] Added coverage. South Africa (ZAF) estimated cattle operations increased in this release, from 108 to 311 assets in V5.6.0. The TerraDetect model was applied to detect additional cattle operations, along with additional QC’ing, to increase coverage.

### Changed

- [Changed] South Africa (ZAF) cattle operations with area (footprint) estimates had their total head of cattle predicted with the U.S. and AUS linear beef model. Previously, mean total head of cattle, by type, were applied to these locations with area estimates.

- [Changed] South Africa (ZAF) beef and dairy mean total head of cattle values are derived from more recent estimates.

- [Changed] South Africa (ZAF) beef capacity factors are derived from more recent estimates.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] An error in the agolin emission reduction solution (ERS) applied to individual cattle operations has existed since the v4.8.0 release, resulting in overestimated methane emissions’ reductions. This will be corrected in a future release.

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S. this was caused when a reported state government CAFOs had location coordinates set away from the operation not within the operation. For example, at the end of the CAFO driveway leading into the operation or the owners home away from the CAFO. Further work will continue  to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist for this sector. If found, please let us know via email and provide the asset id and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity capped at 40,000. Additionally, any dairy farm operation with a total head (capacity) greater than 4,000 had their capacity capped at 4,000. These are marked in the ‘other2’ column. Future updates will address this issue.

## agriculture,manure-management-cattle-operation

### Added

- [Added] Added coverage. South Africa (ZAF) estimated cattle operations increased in this release, from 108 to 311 assets in V5.6.0. The TerraDetect model was applied to detect additional cattle operations, along with additional QC’ing, to increase coverage.

### Changed

- [Changed] South Africa (ZAF) cattle operations with area (footprint) estimates had their total head of cattle predicted with the U.S. and AUS linear beef model. Previously, mean total head of cattle, by type, were applied to these locations with area estimates.

- [Changed] South Africa (ZAF) beef and dairy mean total head of cattle values are derived from more recent estimates.

- [Changed] South Africa (ZAF) beef capacity factors are derived from more recent estimates.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] An error in the agolin emission reduction solution (ERS) applied to individual cattle operations has existed since the v4.8.0 release, resulting in overestimated methane emissions’ reductions. This will be corrected in a future release.

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S. this was caused when a reported state government CAFOs had location coordinates set away from the operation not within the operation. For example, at the end of the CAFO driveway leading into the operation or the owners home away from the CAFO. Further work will continue  to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist for this sector. If found, please let us know via email and provide the asset id and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity capped at 40,000. Additionally, any dairy farm operation with a total head (capacity) greater than 4,000 had their capacity capped at 4,000. These are marked in the ‘other2’ column. Future updates will address this issue.

## agriculture,rice-cultivation

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] A smoothing factor was applied to data starting in 2024 that may misallocate monthly emissions across the harvest cycle, present since V5.3. Future updates will fix this issue.

## fossil-fuel-operations,oil-and-gas-production

### Added

- [Added] Data period calculated for all sources to the end of December 2025.

- [Added] New input data for the U.S. with greater granularity. These new assets replace the old ones and further split them based upon state, basin, and resource type.

- [Added] Asset to basin (also called petroleum play or play) polygon matching now included in the ‘other’ column data fields.

### Changed

- [Changed] Data latency added to account for lag in new U.S. data source lag. Up-to-date data for the United States is now more accurately distributed across assets.

- [Changed] 2025 activity data source changed to U.S. Energy Information Administration (EIA) for several states to meet latency requirements

### Known Issues

- [Known Issues] U.S. emissions for 2015-2022 are based on annual production data while 2023-Present uses monthly production data. Future iterations will improve upon this by replicating the 2025 methodology across all years.

- [Known Issues] 2025 international production input data is out of date. Next submission will include more updated numbers including non-zero emission in Timor L'este.

- [Known Issues] Kentucky asset emissions are zero in 2024/2025 due to lack of activity data in the state.

- [Known Issues] 2015-2020 California data missing due to current lack of historical data inputs.

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in the rest of the world (Asia-Pacific, Middle East, Africa, Latin America, and Commonwealth of Independent States). Start_date 2025-04-01 to end_date 2025-06-30.

### Changed

- [Changed] Updated the historical annual results (2015–2023) for seven assets and the corresponding six countries. Asset IDs: #253, #348, #496, #537, #628,

#630, and #682. Country ISO3 codes: CMR, CRI, KEN, NZL, SDN, and ZMB.

Uncertainty results have been updated too.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## fossil-fuel-operations,oil-and-gas-transport

### Added

- [Added] Data period calculated for all sources to the end of December 2025.

- [Added] New input data for the U.S. with greater granularity. These new assets replace the old ones and further split them based upon state, basin, and resource type.

- [Added] Asset to basin (also called petroleum play or ‘play’) polygon matching now included in the ‘other’ column data fields.

### Changed

- [Changed] Data latency added to account for lag in new U.S. data source lag. Up-to-date data for the United States is now more accurately distributed across assets.

- [Changed] 2025 activity data source changed to U.S. Energy Information Administration (EIA) for several states to meet latency requirements.

- [Changed] Changes in transport emissions accounting in the The Oil Production Greenhouse Gas Emissions Estimator (OPGEE) caused significant decreases in several countries (especially QAT, IRN, RUS) for all years.

### Known Issues

- [Known Issues] U.S. emissions for 2015-2022 are based on annual production data while 2023-Present uses monthly production data. Future iterations will improve upon this by replicating the 2025 methodology across all years.

- [Known Issues] 2025 international production input data is out of date. Next submission will include more updated numbers including non-zero emission in Timor L'este.

- [Known Issues] Kentucky asset emissions are zero in 2024/2025 due to lack of activity data in the state.

- [Known Issues] 2015-2020 California data missing due to current lack of historical data inputs.

## manufacturing,aluminum

### Added

[Added] Added new month, February 2026 data included in this release.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,cement

### Added

- [Added] Added new month, February 2026 data included in this release.

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

- [Added] Data period extended for existing sources. Start_date 2025-03-01 to end_date 2025-06-30

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

- [Added] Added new month, February 2026 data included in this release.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2019-01-01 to end_date 2026-02-28.

### Changed

- [Changed] Updated unit/plant level information due to manual research. These can result in changes to our estimates.

- [Changed] International U.S. Energy Information Administration (EIA; latest in 2025) and annual Ember data (year 2024) were updated.

- [Changed] Included most recent months from reported generation sources and updated reported generation validation tests. These can result in changes to our estimates.

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

- [Known Issues] Our remote sensing-based estimates of plant activity are biased low in some grid regions including China. We are working to address the bias in future releases.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-02-28.

- [Added] Added coverage. 18 new sources added, ordered by international air transportation association (iata) code: {'iata_AGD', 'iata_AVR', 'iata_BRG', 'iata_CIC', 'iata_HWR', 'iata_IQR', 'iata_JJU', 'iata_KLP', 'iata_LKM', 'iata_LXD', 'iata_OYC', 'iata_RDE', 'iata_SFF', 'iata_SMO', 'iata_SRX', 'iata_TVT', 'iata_UKI', 'iata_WSR'}.

### Changed

### Fixed

## transportation,non-broadcasting-vessels

### Added

- [Added] Data period extended. Start_date 2026-02-01 to 2026-02-28.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known issue

## transportation,domestic-shipping

### Added

- [Added] Data period extended. Start date 2026-01-01 to 2026-02-28.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-02-28.

- [Added] Added coverage. 4 new sources added, ordered by international air transportation association (iata) code: {'iata_MNC', 'iata_RGS', 'iata_SOQ', 'iata_TEE'}.

### Changed

### Fixed

## transportation,international-shipping

### Added

- [Added] Data period extended. Start date 2026-01-01 to 2026-02-28.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources. New end_date 2026-02-28.

### Changed

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Added missing asset data for following countries, addressing dropped assets from previous deliverable: KIR, IOT, BVT, GIB, FLK, CCK, PCN, SXM, MAF, CUW, ABW, CXR, NIU, MDV, SGS, HMD, NFK, and MCO.

- [Fixed] Fixed issue with road segment level data where activity & emissions data were artificially inflated due to duplicate data entries; aggregated data were unaffected.

### Known Issues

- [Known Issues] Have not updated to the latest Climate TRACE patch of GADM data (v1.1.2).

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2026-01-01 to end_date 2026-02-28.

### Changed

- [Changed] Updated population metadata for EU countries from the latest data release (2021-2023) from the European Environment Agency (EEA).

- [Changed] Updated location for EU assets using results of machine learning model based on satellite imagery.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Removed historical information for ITA02279 (duplicate that was merged with ITA02280).

- [Fixed] Corrected ISO3 codes for assets in U.S. territories.

### Known potential issues

- [Known Issues] Potential duplicate assets can exist in the sector.

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2026-01-01 to end_date 2026-02-28.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known issues

- [Known Issues] Potential duplicate assets.

## waste,solid-waste-disposal

### Added

- [Added] Data period extended for existing sources to end_date 2026-02-28. 11 assets added, contributing 326,136.49 tonnes.

### Changed

- [Changed] Adjusted fit algorithm for satellite-assisted incoming waste estimation, (small increase of emissions).

- [Changed] Adjusted interpolation/extrapolation of annual incoming waste to carry-forward, from linear fit.

- [Changed] Total emissions in 2025 increased by +5.5% from previous estimate (+740,429.7 tonnes CH4)

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Some landfill assets were mismatched to the wrong city in v5.5.1, so some city estimates will change in v5.6.0.

### Known Issues

- [Known Issues] None

---

PDF: [5.6.0_combined-changelog-climate-trace.docx.pdf](./5.6.0_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
