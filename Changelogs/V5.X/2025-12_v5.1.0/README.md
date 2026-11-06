# [5.1.0] - 2025-12-01

## ClimateTRACE,deprecation-warning

For the current (V5.1.0) release, we are including the following Deprecation Warning:

- [Deprecation Warning] The following BigQuery tables will be deprecated and removed in the upcoming December release V5.2.0: `climate_trace.road-segments_road-transportation_202505` and `climate_trace.shipping-voyages_shipping_2025`. These tables have been replaced by the following BigQuery tables: `climate_trace.road_segments` and `climate_trace.shipping_voyages` respectively. All future updates will be applied to the new tables only.

## ClimateTRACE,multiple-sectors,post-processing

### Added

### Changed

- [Changed] Ratio-based method for non-GHG estimates now superseded by non-GHG estimates provided by sector leads for petrochemical-steam-cracking, cropland-fires, and oil-and-gas-refining where they exist.

### Deprecated

### Fixed

### Known Issues

- [Known Issue] domestic-wastewater-treatment-and-discharge country-level data for 2015-2020 has been reverted to V5.0.0 due to a post-processing artifact leading to inflated numbers.

## ClimateTRACE,individual-changelogs

## agriculture,crop-residues

### Added

- [Added] Monthly data from January 2025 to September 2025.

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,cropland-fires

### Added

- [Added] Monthly data from January 2025 to September 2025.

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,manure-applied-to-soils

### Added

- [Added] Monthly data from January 2025 to September 2025.

### Changed

### Deprecated

### Fixed

### Known Issues

## agriculture,rice-cultivation

### Added

- [Added] 2021 - 2024 yearly historical data for MLI and NGA.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] We identified an issue where monthly emissions associated with rice cultivation in Southeast Asia are concentrated in the harvest month rather than the distributing emissions throughout the growing season. We will implement an approach to more evenly distribute those emissions in an upcoming data release.

## agriculture,synthetic-fertilizer-application

### Added

- [Added] Monthly data from January 2025 to September 2025.

### Changed

### Deprecated

### Fixed

### Known Issues

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2025-4-01 to end_date 2025-4-30.

### Changed

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,water-reservoirs

### Added

- [Added] Data period extended for existing sources. The end_date is now September 30, 2025.

### Changed

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-production

### Added

### Changed

- [Changed] Satellite emissions attribution improvements.

### Deprecated

- [Deprecated] Due to a lack of U.S. 2025 forecasted activity data, all modeled 2025 data, for all countries, has been removed to maintain consistency. Any 2025 data that is generated is done by post-processing.

### Fixed

### Known Issues

- [Known Issues] Because model runs for the US are currently only available for 2023 and 2024, backfilled and forward-filled output production values include some inherent uncertainty. Since activity and intensity influence one another, this limitation has resulted in artificial changes in activity levels leading to a drop in emissions for U.S. assets in 2025.

- [Known Issues] JDA fields production backfill errors are making Malaysia and Thailand total emissions skewed

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in the US and Europe. Start_date 2025-01-01 to end_date 2025-03-31.

- [Added] Separately modeled SO2 and PM2.5, so added two emission factors columns and two absolute emissions columns in the asset sheet, uncertainty sheet, and confidence sheet. Added the non-GHG results in the asset sheet and confidence sheet, while uncertainty results will be updated next round.

### Changed

- [Changed] Updated 2024 annual SO2 emissions and PM2.5 emissions for all refining assets, given the non-GHG data categories change and methodology adjustment.

### Deprecated

[Deprecated] Dropped all five environmental impact indicators in columns other 1 to 5 given that non-GHG results are added.

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-transport

### Added

### Changed

### Deprecated

- [Deprecated] Due to a lack of U.S. 2025 forecasted activity data, all modeled 2025 data, for all countries, has been removed to maintain consistency. Any 2025 data that is generated is done by post-processing.

### Fixed

### Known Issues

## manufacturing,aluminum

### Added

- [Added] Added new month. August 2025 data included this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,cement

### Added

- [Added] Added new month, August 2025 data included in this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] Data period extended for existing sources in North America and Europe. Start_date 2025-01-01 to end_date 2025-03-31. -[Added] Non-GHG emissions for existing sources in Europe and North America. CO, N2O, PM10, PM2.5, SO2, and VOC emissions are modeled. For methodology for non-ghg emissions please visit methodology: [Petrochemical Steam Cracking methodology](../../../Sector-Methodologies/1-Sectors/manufacturing/petrochemical-steam-cracking/README.md)

### Changed

- [Changed] Updated United States capacity factor to adjust for EIA purity stream definition of 90% ethane.

### Deprecated

### Fixed

### Known Issues

## manufacturing,iron-and-steel

### Added

- [Added] Added new month, August 2025 data included in this release.

### Changed

### Deprecated

### Fixed

[Fixed] Corrected the idled and retired dates for steel assets sourced from the tracker.

### Known Issues

## mineral-extraction,bauxite-mining

### Added

- [Added] Data period extended for existing sources. Start_date 2020-01-01 to end_date 2024-12-31.

- [Added] Added coverage. 10 new sources added (1 in AZE, 9 in GIN).

### Changed

- [Changed] Updated metadata [capacity_factor, activity, CO2_emissions_factor, CO2_emissions].

### Deprecated

### Fixed

- [Fixed] Previous releases had mines with reported capacity factors greater than 1 due to outdated/inaccurate capacity data. In these cases, capacity factor was set to null. Post-processing was done to ensure capacity factor is not greater than 1.

### Known Issues

## mineral-extraction,copper-mining

### Added

- [Added] Data period extended for existing sources. Start_date 2020-01-01 to end_date 2024-12-31.

- [Added] Added coverage. 239 new sources added (14 in AUS, 2 in AZE, 4 in BRA, 3 in BWA, 4 in CAN, 11 in CHL, 9 in CHN, 110 in COD, 4 in CYP, 21 in KAZ, 2 in MEX, 1 in MNG, 1 in NAM, 28 in RUS, 9 in USA, 18 in ZMB, 1 in ZNC).

### Changed

- [Changed] Updated metadata [location, capacity_factor, activity, CO2_emissions_factor, CO2_emissions].

### Deprecated

### Fixed

- [Fixed] Previous releases had mines with reported capacity factors greater than 1 due to outdated/inaccurate capacity data. In these cases, capacity factor was set to null. Post-processing was done to ensure capacity factor is not greater than 1.

### Known Issues

## mineral-extraction,iron-mining

### Added

- [Added] Data period extended for existing sources. Start_date 2020-01-01 to end_date 2024-12-31.

- [Added] Added coverage. 31 new sources were added (4 in AUS, 4 in BRA, 2 in CAN, 4 in CHN, 15 in IND, 1 in PHL, 5 in UKR).

### Changed

- [Changed] Updated metadata [location, capacity_factor, activity, CO2_emissions_factor, CO2_emissions]

### Deprecated

### Fixed

- [Fixed] Previous releases had mines with reported capacity factors greater than 1 due to outdated/inaccurate capacity data. In these cases, capacity factor was set to null. Post-processing was done to ensure capacity factor is not greater than 1.

### Known Issues

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-09-30.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,non-broadcasting-shipping

### Added

- [Added] Data period extended. Start_date 2025-10-01 to 2025-10-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,domestic-shipping

### Added

- [Added] Data period extended. Start date 2025-09-01 to 2025-09-30.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-09-30.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,international-shipping

### Added

- [Added] Data period extended. Start date 2025-09-01 to 2025-09-30.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources. New end_date 2025-09-30.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Have not updated to the latest Climate TRACE patch of GADM data (v1.1.2).

- [Known Issues] Some countries have spuriously inflated emissions for 2025. Particular examples include: Indonesia, Timor-Leste, Dominican Republic, Malawi, Tanzania, Democratic Republic of the Congo, Paraguay, Peru, Rwanda, Haiti, Uruguay, Uganda, Vanuatu, Fiji, Micronesia, Kenya, Tokelau, Solomon Islands, Iran, Colombia, and Gambia.

## waste,domestic-wastewater-treatment-and-discharge

### Added

### Changed

- [Changed] Country-level data for 2015-2020 has been reverted to V5.0.0 due to a post-processing artifact leading to inflated numbers.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Duplicate assets, issue originating from underlying dataset

- [Known Issues] 56 additional assets have location coordinates which are insufficiently precise, and which have not been verified.

- [Known Issues] 133 countries have a marked increase or decrease in August-September 2025, compared to behavior in the same months for 2024. For global totals, this leads to a net increase inconsistent with the time-series from historical data and will be addressed in the next release.

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-09-01 to end_date 2025-09-30. Now all data runs from 2015-01-01 to 2025-09-30.

### Changed

### Deprecated

### Fixed

### Known Issues

## waste,solid-waste-disposal

### Added

### Changed

- [Changed] Assets of unknown type are assigned "Sanitary Landfill" if they are in a country determined to be high income by the World Bank; all others are assigned "Dumpsite".

### Deprecated

### Fixed

= [Fixed] Area-to-incoming-waste model now correctly has group-specific slopes.

### Known Issues

---

PDF: [5.1.0_combined-changelog-climate-trace.docx.pdf](./5.1.0_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
