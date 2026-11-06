# [5.4.0] - 2026-02-23

## ClimateTRACE,deprecation-warning

- None this release.

## ClimateTRACE,multiple-sectors,post-processing

### Added

### Changed

### Deprecated

### Fixed

- [Fixed] Fixed ranking for emissions reducing solutions (ERS)for solid-waste-disposal for most sensible solutions. Yields a total ~100,000 tonne lower reduction potential than in V5.3.0 (which are not due to expected monthly emissions quantity updates), contributed to by 165 assets.

### Known Issues

- [Known Issue] Still present from V5.3.0: iron-and-steel assets were incorrectly extrapolated forward rather than being set to a “closed” state with 0 emissions. Affected asset IDs are: 1566424, 1566477, 1566542, 1566555, 1566559, 1566564, 1566578, 1566580, 1566620, 1566648, 1566669, 1566770, 1566825, 1566949, 1566965, 1567083, 1567106, 1567145, 1567184, 1567187, 1567226, 1567250, 1567255, 1567256, 1567257, 1567259, 1567263, 1567268, 1567271, 1567273, 1567274, 1567275, 1567280, 1567281, 1567282, 1567285, 1567286, 1567290, 1567291, 1567292, 1567294, 1567295, 1567296, 1567297, 1567299, 1567300, 1567301, 1567303, 1567305, 1567312, 1567313, 1567314, 1567315, 1567316, 1567317, 1567318, 1567319, 1567320, 1567321, 1567322, 1567323, 1567324, 1567325, 1567326, 1567327, 32441205, 32441208, 32441223, 32441224, 32441229, 32441253, 38089228, 42741547, 42741574, 42741753, 42741756, 42741765, 42741804, 42741864, 42741875.

- [Known Issue] Still present from V5.3.0: Two domestic-wastewater-treatment-and-discharge assets were assigned the wrong ISO-3 country code: 48250739 and 48251021 were incorrectly tagged to CAF and COD rather than SLB and UGA, respectively.

- [Known Issue] Still present from V5.3.0: Some city emissions data have multiple rows for a given timestamp in the data downloads packages for individual gases (co2, ch4, n2o). To be fixed in V5.5.0.

- [Known Issue] non-broadcasting-vessels CO2e_100yr and CO2e_20yr emissions are doubled for only January in the GADM emissions data.

- [Known Issue] Oil-and-gas-transport asset data were not updated in this release. As such, December 2025 asset data are missing, and 2025 country-, gadm-, and city-level data may reflect these missing data.

## ClimateTRACE,individual-changelogs

## agriculture,enteric-fermentation-cattle-operation

### Added

- [Added] Korea (KOR) and Turkiye/Turkey (TUR) coverage to the Climate TRACE database- an estimated 1,536 and 515 assets (cattle operations), respectively, have been identified.

### Changed

- [Changed] Total Brazil estimated cattle operations decreased in this release, from 17,389 to 17,159 assets in V5.4.0. We performed additional QC’ing for cattle operations in the Amazon region, added new operations, and removed duplicates and false-positives resulting in 1,397 assets removed.

- [Changed] Ukraine estimated cattle operations increased in this release, from 310 to 769 assets in V5.4.0, due to increased country coverage. We performed additional QC’ing for cattle operations and removed duplicates and false-positives resulting in 303 assets removed.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] An error in the agolin emission reduction solution (ERS) applied to individual cattle operations has existed since the v4.8.0 release, resulting in overestimated methane emissions’ reductions. This will be corrected in a future release.

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S. this was caused when a reported state government CAFOs had location coordinates set away from the operation        not within the operation. For example, at the end of the CAFO driveway leading into the operation or the owners home away from the CAFO. Further work will continue  to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist for this sector. If found, please let us know via email and provide the asset id and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity capped at 40,000. Additionally, any dairy farm operation with a total head (capacity) greater than 4,000 had their capacity capped at 4,000. These are marked in the ‘other2’ column. Future updates will address this issue.

## agriculture,manure-management-cattle-operation

### Added

- [Added] Korea (KOR) and Turkiye/Turkey (TUR) coverage to the Climate TRACE database- an estimated 1,536 and 515 assets (cattle operations), respectively, have been identified.

### Changed

- [Changed] Total Brazil estimated cattle operations decreased in this release, from 17,389 to 17,159 assets in V5.4.0. We performed additional QC’ing for cattle operations in the Amazon region, added new operations, and removed duplicates and false-positives resulting in 1,397 assets removed.

- [Changed] Ukraine estimated cattle operations increased in this release, from 310 to 769 assets in V5.4.0, due to increased country coverage. We performed additional QC’ing for cattle operations and removed duplicates and false-positives resulting in 303 assets removed.

- [Changed] Country-level Brazil cattle manure management emissions were updated to reflect revised coverage.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] An error in the agolin emission reduction solution (ERS) applied to individual cattle operations has existed since the v4.8.0 release, resulting in overestimated methane emissions’ reductions. This will be corrected in a future release.

- [Known Issues] Effort has been made to reduce duplicate operations in the U.S. and globally. In the U.S. this was caused when a reported state government CAFOs had location coordinates set away from the operation not within the operation. For example, at the end of the CAFO driveway leading into the operation or the owners home away from the CAFO. Further work will continue  to deduplicate Climate TRACE cattle operations in the U.S.

- [Known Issues] Duplicates and false-positive locations can exist for this sector. If found, please let us know via email and provide the asset id and latitude and longitude information.

- [Known Issues] Certain cattle operations may be multiple cattle operations combined into one. As a result, the regression model overestimated the total head of cattle at these operations. Any beef cattle operation with a total head (capacity) greater than 40,000 had their capacity capped at 40,000. Additionally, any dairy farm operation with a total head (capacity) greater than 4,000 had their capacity capped at 4,000. These are marked in the  ’other’ column. Future updates will address this issue.

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2025-1-01 to end_date 2025-12-31.

### Changed

- [Changed] For all activity, emissions factor, and emissions data within above dates, updated based on 2025 temperature data.

### Deprecated

### Fixed

### Known Issues

## forestry-and-land-use,water-reservoirs

### Added

- [Added] Data period extended for existing sources. Added November 2025 and December 2025. The end_date is now December 31, 2025.

### Changed

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in North America and Europe. Start_date 2025-04-01 to end_date 2025-06-30.

- [Added] Two new columns added to the asset sheet: ‘other 1’ - total non-fuel products (tons) and ‘other 2’ - mass ratio of non-fuel products to total refined products.

### Changed

- [Changed] Attached the separated Q1 2024 results (split from Q12024 AND Q42023 combined) at the bottom of the asset sheet for two refineries in Albania.

### Deprecated

### Fixed

### Known Issues

## manufacturing,aluminum

### Added

- [Added] Added new month, November 2025 data included in this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,cement

### Added

- [Added] Added new month, November 2025 data included in this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] Data period extended for existing sources in North America and Europe. Start_date 2025-03-01 to end_date 2025-06-30 -[Added] ‘other2’ column added to asset sheet in tons of high value chemical (HVC)/month. Note HVC is defined as ethylene, propylene, butadiene, and aromatics.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,iron-and-steel

### Added

[Added] Added new month, November 2025 data included in this release.

### Changed

### Deprecated

### Fixed

### Known Issues

## power,electricity-generation

### Added

- [Added] Data period extended for existing assets. Start_date 2019-01-01 through end_date 2025-12-31.

### Changed

- [Changed] Updated unit/plant level information due to manual research. These can reflect changes in our estimates.

- [Changed] Updated and added new links to reported generation data. These can reflect changes in our estimates.

- [Changed] Pulled new most recent months from reported generation sources. These can reflect changes in our estimates.

### Deprecated

### Fixed

- [Fixed] Incorrect country codes fixed. These can reflect changes in country-level estimates and asset information.

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-12-31.

- [Added] 7 airports added, listed by their IATA airport identifier:  MKU, NMI, DPP, JNH, ENG, RVY, and AHA.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,domestic-shipping

### Added

- [Added] Data period extended. Start date 2025-12-01 to 2025-12-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-12-31.

- [Added] 6 new airports added, listed by their IATA airport identifier : CTF, GLU, IKG, WHA, ENO, and DHX.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,international-shipping

### Added

- [Added] Data period extended. Start date 2025-12-01 to 2025-12-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources. New end_date 2025-12-31.

### Changed

- [Changed] Updated vehicle fleet mix data for ALB, BRN, KHM, IDN, LAO, MYS, MMR, PHL, SGP, THA, VNM.

- [Changed] Country level changed to a monthly temporal granularity to match other GADM aggregations.

### Deprecated

### Fixed

- [Fixed] Missing asset level data for the following countries is now included to match road segment level data: ABW, CCK, CUW, CXR, FLK, GIB, IOT, KIR ,MAF, MCO, MDV, NFK, NIU, PCN, SXM, VAT. When data is missing a GADM2 id, we now refer to higher level GADM boundaries.

- [Fixed] Submitted dates now only provided for months with data.

### Known Issues

- [Known Issues] Have not updated to the latest ClimateTRACE patch of GADM data (v1.1.2).

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing assets (start_date 2025-12-01 to end_date 2025-12-31. Now all data runs from 2015-01-01 to 2025-12-31).

- [Added] For all USA assets and global assets with modified metadata: historic country-level and asset-level data from 2015-01-01 to 2025-12-31.

- [Added] 1,989 new USA assets. Other countries had assets added: 1 in BEL, BRA, CHE, SVK, and ZWE each, and 2 in CAN, CYP, and DEU each.

- [Added] Historical asset and country-level data for the USA.

### Changed

- [Changed] Assets decreased in the following countries: 3 in AUT, and 1 in ARG, LUX, and POL each.

### Fixed

- [Fixed] Added indication of closure date for 115 USA assets

- [Fixed] Updated population estimates and technology level for USA assets based on 2016 and 2022 US EPA survey data

- [Fixed] Adjusted location coordinates for USA assets when a more precise location could be identified via satellite imagery based on a gridded search with a 1.5 km bound box around EPA reported locations.

- [Fixed] Fixed location coordinates which are insufficiently precise.

- [Fixed] Fixed ISO3 code mismatches.

### Known Issues

- [Known Issues] Potential duplicate assets, issue originating from underlying dataset. Investigation ongoing with fixes made where obvious.

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-12-01 to end_date 2025-12-31. Now all data runs from 2015-01-01 to 2025-12-31.

### Fixed

### Known Issues

- [Known Issues] Potential duplicate assets.

## waste,solid-waste-disposal

### Added

- [Added] 11 assets added, contributing 326,136.49 tonnes CH4.

### Changed

- [Changed] Total emissions increased by +2.18% (+287,732.73 tonnes CH4).

- [Changed] 8% of assets’ emissions increased and 75% of assets’ emissions decreased. Top 10 increasing assets account for 71.4% of total increases.

- [Changed] Eastern Asia shows the largest regional emission change (+311,365.00 t).

- [Changed] Sudokwon (KOR) asset emissions have changed by +147,806.59 tonnes of CH4.

- [Changed] - [Changed] 2 assets dropped, removing 3,334.25 tonnes of CH4.

### Deprecated

### Fixed

- [Fixed] Some assets had incorrect ISO3 values (e.g., landfills in Puerto Rico labeled as USA, Hong Kong labeled as China).

### Known Issues

---

PDF: [5.4.0_combined-changelog-climate-trace.docx.pdf](./5.4.0_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
