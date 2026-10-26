# [4.7.0] - 2025-09-24

## ClimateTRACE,deprecation-warning:

### Deprecation Warning

Climate TRACE is implementing a Deprecation Warning System to inform users ahead of time when we anticipate a breaking change in any of our data delivery mechanisms. Our goal is to help users prepare for changes and avoid disruptions to workflows. We will provide at least a **one-month notice** before any covered change goes into effect. Climate TRACE data releases, including the changelog, are published on the last Thursday of the month. Therefore, Deprecation Warnings affecting a monthly release will be communicated no later than the preceding monthly release. Covered Changes include:

- Discontinuing regular monthly updates to the following public data locations:

- [climatetrace.org](http://climatetrace.org) website data download packages at [climatetrace.org/data](https://climatetrace.org/data)

- The Climate TRACE API at [api.climatetrace.org](http://api.climatetrace.org)

- BigQuery tables at ‘trace-data-383422.climate_trace’

- Breaking changes to data structures

- Removing or renaming columns or fields

- Removing or renaming sectors and subsectors

- Changing existing file types or file naming conventions

- Access changes

- Adding authentication requirements

- Adding rate limits. Additions of new tables, files, fields, sectors, and subsectors are not considered breaking changes and will not trigger a deprecation warning. For the current (V4.7.0) release, we are including the following Deprecation Warning:

- [Deprecation Warning] the following fields will be renamed in the ‘trace-data-383422.climate_trace.gadm_emissions’ and ‘trace-data-383422.climate_trace.city_emissions’ BigQuery tables on 2025-10-30:

- ‘remainder_capacity’ will be renamed to ‘spatially_uncertain_capacity’;

- ‘remainder_activity’ will be renamed to ‘spatially_uncertain_activity’;

- ‘remainder_emissions’ will be renamed to ‘spatially_uncertain_emissions’.

## ClimateTRACE,multiple-sectors,post-processing:

### Added

### Changed

- [Changed] Emissions estimates for PM2.5 from the following sectors were updated to include contribution from both process- and fuel-based emissions: bauxite-mining, coal-mining, copper-mining, iron-mining, oil-and-gas-production, oil-and-gas-refining, oil-and-gas-transport.

### Deprecated

### Fixed

- [Fixed] Erroneous negative emissions in ‘sand-quarrying’ and ‘other-mining-quarrying’ have been set to 0.

- [Fixed] A bug creating discrepancies between GADM and country emissions for oil-and-gas-production and oil-and-gas-transport was fixed.

- [Fixed] Emissions for ‘lime’ and ‘glass’ for 2023 onward for non-GHGs were reported incorrectly as 0 in release V4.6.0, fixed in the current (V4.7.0) release.

### Known Issues

- [Known Issues] Multiple GADM and city rows for a given ‘gadm_id’/’city_id’, gas and time. Occurs when 1) an asset’s tagged country location (i.e. gadm_0 value) and iso3_country assignment are mismatched, and 2) a city boundary intersects multiple countries and assets within the city boundary are tagged to more than one distinct country. This affects a total of 4 (of ~3 million) gadm_id/sector pairs, and 30 (of ~600 thousand) city_id/sector pairs. The following gadm_id’s and city_id’s are affected:

- gadm_id’s: COD.11.14_1; SVK.8.10_1; BIH.3.3_1.

- city_id’s: ghs-fua_9871; ghs-fua_9871; ghs-fua_3200; ghs-fua_103; ghs-fua_1287; ghs-fua_1479; ghs-fua_1690; ghs-fua_1752; ghs-fua_199; ghs-fua_312; ghs-fua_3400; ghs-fua_4293; ghs-fua_44; ghs-fua_5098; ghs-fua_514; ghs-fua_60; ghs-fua_696; ghs-fua_7141; ghs-fua_935; ghs-fua_2227; ghs-fua_4331; ghs-fua_531; ghs-fua_6948.

- [Known Issues] Aggregations to GADM regions of raster data for regions crossing the antimeridian (180th meridian of longitude) overcount emissions. Affected sectors include: manure-applied-to-soils, non-residential-onsite-fuel-usage, residential-onsite-fuel-usage, and synthetic-fertilizer-application. Affected regions include: FJI, FJI.2_1, FJI.3_1, FJI.2.2_1, FJI.3.2_1, RUS.12_1, RUS.12.6_1, and RUS.12.8_1.

## ClimateTRACE,individual-changelogs:

## agriculture,rice-cultivation

### Added

- [Added] Monthly 2024 asset level and country level data for Southeast Asian countries.

### Changed

- [Changed] The CH4 emissions factor for alternate wetting and drying solutions to reflect induced N2O emissions from the proposed solution. The gross CH4 reductions were found to be 52% but incorporating the N2O emissions change brought that number to 39%. While these N2O emissions mostly occurred from changes in crop residue activity, the N2O impacts also occurred within other untracked microbial activities, thus it was simpler to reduce the methane efficacy of alternate wetting and drying.

### Deprecated

### Removed

- Removed 2024 yearly data for Southeast Asia assets and countries in favor of monthly data.

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] Biomass-specific raster emissions estimates for CO2bio, N2Obio, and CH4bio. CO2bio, N2Obio, and CH4bio estimates are provided and can be used to determine the amount of biomass contribution to GHGs relative to nonbiomass sources.

### Changed

- [Changed] Updated to monthly temporal disaggregation for CO2, N2O, CH4, CO2bio, N2Obio, CH4bio, NMVOC, CO, NOx, SO2, PM2.5, and PM10 using monthly temperature data from ERA5.

- [Changed] Updated model for all data. [Area, capacity factor, activity, and emissions factor methods are all updated.]

- [Changed] Updated all monthly estimates to encompass January 2015 through February 2025 (inclusive).

- [Changed] Updated metadata units for emissions data to be tonnes for all emissions.

- [Changed] Updated metadata units for activity data to be megajoules (MJ).

- [Changed] Updated metadata units for emissions factor data to be MJ/tonne for all emissions factors.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Some other4-9 column values for biomass CO2, CH4, and N2O (CO2bio, N2Obio, CH4bio)emissions and emissions factors were omitted due to an error in the raster aggregation process and will be included in the next release.

## buildings,residential-onsite-fuel-usage

### Added

- [Added] Added biomass-specific raster emissions estimates for CO2bio, N2Obio, and CH4bio. CO2bio, N2Obio, and CH4bio estimates are provided and can be used to determine the amount of biomass contribution to GHGs relative to  nonbiomass sources.

### Changed

- [Changed] Updated to monthly temporal disaggregation for CO2, N2O, CH4, CO2bio, N2Obio, CH4bio, NMVOC, CO, NOx, SO2, PM2.5, and PM10 using monthly temperature data from ERA5.

- [Changed] Updated model for all data. [Area, capacity factor, activity, and emissions factor methods are all updated.]

- [Changed] Updated all monthly estimates to encompass January 2015 through February 2025 (inclusive).

- [Changed] Updated metadata units for emissions data to be tonnes for all emissions.

- [Changed] Updated metadata units for activity data to be megajoules (MJ).

- [Changed] Updated metadata units for emissions factor data to be MJ/tonne for all emissions factors.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Some other4-9 column values for biomass CO2, CH4, and N2O (CO2bio, N2Obio, CH4bio)emissions and emissions factors were omitted due to an error in the raster aggregation process and will be included in the next release.

## coal-mining

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2024-12-31.

- [Added] 572 coal mines to the Climate TRACE database with the largest additions taking place in CHN (218 new mines), USA (140 new mines), IDN (85 new mines), IND (59 new mines), and ZAF (13 new mines).

### Changed

-  [Changed] Metadata: historical activity data for some mines was updated from backfilled values to actual collected values from Global Energy Monitor.

-  [Changed] Adjusted methodology for approximating missing years of data for a given asset (from ‘averaging’ approach to ‘nearest available’ approach).

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in Asia-Pacific (APAC) and the Middle East regions. Start_date 2024-10-01 to end_date 2024-12-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,aluminum

### Added

- [Added] Added coverage. Incorporated 39 assets for alumina (previously aggregated by region), with total capacity coverage increased by 18%.

### Changed

- [Changed] Updated model for all data, with values recalculated. Start_date 2021-01-01 to end_date 2025-06-30. A regional utilization factor is used to calculate production and capacity factor for assets (where the data exists); remaining estimated capacity and production is aggregated by region.

- [Changed] Updated capacity and ownership metadata: Refreshed the source of data for smelters assets. Previously static; now updated on a year-by-year basis to track retirements and openings. Data for refineries assets have been added using a new large language model (LLM) to enable more granular reporting.

- [Changed] Updated uncertainty and confidence metadata: Improved estimation based on source of information of capacities and the methodology used to estimate the asset production.

### Deprecated

### Fixed

### Known Issues

## manufacturing,cement

### Added

### Changed

- [Changed] Improved the uncertainty and confidence definitions for cement assets depending on method used for activity estimation (satellite vs national/global averages).

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Country-level emissions may be slightly overestimated, as emission factors are derived from asset data. Our current asset data has incomplete capacity coverage and is more heavily weighted towards the most emitting assets. We aim to improve this as we refine our national coverage estimates.

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] Data period extended for existing sources in Middle East and Asia Pacific regions. Start_date 2024-10-01 to end_date 2024-12-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,pulp-and-paper

### Added

- [Added] Added coverage. Increased number of assets by 93 (36%) with total capacity coverage increased by 58%.

- [Added] New technology type added: Pulp from fibres other than wood.

### Changed

- [Changed] Updated model for all data. Regional aggregates replaced by assets, with calculations rerun. Start_date 2021-01-01 to end_date 2024-12-31.

- [Changed] Updated capacity_factor metadata: calculated using the most recent Food and Agriculture Organization (FAO) national capacities and production data. Applied per country where available, otherwise global average applied (pulp assets tend to have a high capacity utilization with FAO global average sitting around 0.93 (compared to more conservative previous estimate of 0.64).

- [Changed] Updated confidence and uncertainty metadata: Improved estimation based on source of information of capacities and the methodology used to estimate the asset production.

- [Changed] Updated ownership and capacity metadata: Now sourced from Spatial Finance Initiative, with data gaps supplemented by a purpose-built large language model (LLM. QC'd and appropriate adjustments made based on FAO national data.

- [Changed] Updated activity metadata: Owing to increased capacity and capacity factors, reported activity has significantly increased (by 115%).

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Asset aggregates do not in all cases equal reported country-level emissions due to incomplete asset coverage.

## manufacturing,iron-and-steel

### Added

### Changed

- [Changed] Improved the uncertainty and confidence definitions for steel assets depending on method used for activity estimation (satellite vs national/global averages).

### Deprecated

### Fixed

### Known Issues

## manufacturing,glass

### Added

### Changed

- [Changed] Added check for previously unique assets in identically the same location (within 0.0001 degrees latitude/longitude) in the European Pollutant Release and Transfer Register (E-PRTR) dataset, and combined them into one asset.

### Deprecated

### Fixed

- [Fixed] Eliminated [33] duplicates: asset_identifier = ['eprtrFR.EEA.1084.FACILITY', 'eprtrFR.EEA.5984.FACILITY', 'eprtrAT.EEA.5958.FACILITY', 'eprtrFR.CAED.3453.FACILITY', 'eprtrFR.CAED.9049.FACILITY', 'eprtrDE.EEA.43122.FACILITY', 'eprtrDE.EEA.45939.FACILITY', 'eprtrDE.EEA.46650.FACILITY', 'eprtrDE.EEA.189451.FACILITY', 'eprtrIT.EEA.325.FACILITY', 'eprtrIT.EEA.339.FACILITY', 'eprtrIT.EEA.117634.FACILITY', 'eprtrES.CAED.001020000.FACILITY', 'eprtrGB.EEA.125545.FACILITY', 'eprtrGB.EEA.31875.FACILITY', 'eprtrGB.EEA.31923.FACILITY', 'eprtrGB.EEA.31983.FACILITY', 'eprtrGB.EEA.32000.FACILITY', 'eprtrGB.EEA.32044.FACILITY', 'eprtrGB.EEA.32091.FACILITY', 'eprtrGB.EEA.88364.FACILITY', 'eprtrGB.EEA.190310.FACILITY', 'eprtrGB.EEA.190318.FACILITY', 'eprtrGB.EEA.190429.FACILITY', 'eprtrGB.EEA.190463.FACILITY', 'eprtrGB.EEA.190677.FACILITY', 'eprtrGB.EEA.190737.FACILITY', 'eprtrGB.EEA.190766.FACILITY', 'eprtrGB.EEA.190775.FACILITY', 'eprtrGB.EEA.190813.FACILITY', 'eprtrGB.EEA.190953.FACILITY', 'eprtrGB.EEA.191017.FACILITY', 'eprtrGB.EEA.191199.FACILITY']

## manufacturing,lime

### Added

### Changed

- [Changed] Added check for previously unique assets in identically the same location (within 0.0001 degrees latitude/longitude) in the European Pollutant Release and Transfer Register (E-PRTR) dataset, and combined them into one asset.

### Deprecated

### Fixed

- [Fixed] Eliminated [1] duplicate: asset_identifier=eprtrFR.CAED.7598.FACILITY

### Known Issues

- [Known Issues] 48 assets (47 in USA, 1 in AUS) have near-zero activity and emissions for all times/gases. To be fixed in V5.0.0.

## manufacturing,food-beverage-tobacco

### Added

### Changed

- [Changed] Added check for previously unique assets in identically the same location (within 0.0001 degrees latitude/longitude) in the EPRTR dataset, and combined them into one asset.

### Deprecated

### Fixed

- [Fixed] Eliminated [44] duplicates: asset_identifier = ['eprtrFR.EEA.1083.FACILITY',  'eprtrFR.EEA.19004.FACILITY', 'eprtrFR.EEA.19007.FACILITY',  'eprtrFR.EEA.4447.FACILITY', 'eprtrFR.EEA.4491.FACILITY',    'eprtrFR.EEA.786.FACILITY', 'eprtrAT.EEA.229218.FACILITY', 'eprtrFR.EEA.966.FACILITY', 'eprtrAT.EEA.284923.FACILITY', 'eprtrFR.EEA.104400.FACILITY', 'eprtrFR.EEA.11079.FACILITY',  'eprtrFR.EEA.11080.FACILITY', 'eprtrFR.EEA.4812.FACILITY',    'eprtrFR.EEA.69353.FACILITY', 'eprtrFR.EEA.69572.FACILITY',  'eprtrFR.EEA.104727.FACILITY', 'eprtrFR.EEA.17565.FACILITY',  'eprtrFR.EEA.18651.FACILITY', 'eprtrFR.CAED.14501.FACILITY', 'eprtrFR.EEA.158643.FACILITY', 'eprtrFR.EEA.18598.FACILITY',  'eprtrFR.CAED.14427.FACILITY', 'eprtrFR.CAED.14802.FACILITY', 'eprtrFR.EEA.158692.FACILITY', 'eprtrFR.EEA.175689.FACILITY', 'eprtrFR.CAED.4283.FACILITY', 'eprtrFR.CAED.9983.FACILITY',  'eprtrFR.CAED.2488.FACILITY', 'eprtrFR.EEA.293953.FACILITY', 'eprtrFR.EEA.4061.FACILITY', 'eprtrDE.EEA.46341.FACILITY',  'eprtrDE.EEA.46820.FACILITY', 'eprtrIT.EEA.120.FACILITY',    'eprtrIT.EEA.5069.FACILITY', 'eprtrIT.EEA.26817.FACILITY',  'eprtrPT.EEA.5639.FACILITY', 'eprtrES.EEA.84969.FACILITY',  'eprtrES.EEA.85117.FACILITY', 'eprtrES.EEA.85307.FACILITY',  'eprtrGB.EEA.31327.FACILITY', 'eprtrGB.EEA.32498.FACILITY',  'eprtrGB.EEA.130179.FACILITY', 'eprtrGB.EEA.191086.FACILITY', 'eprtrCZ.EEA.66167.FACILITY', 'eprtrDK.EEA.7126.FACILITY',   'eprtrFR.CAED.3859.FACILITY']

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2019-01-01 to end_date 2025-07-31.

### Changed

- [Changed] Updated Global Energy Monitor (GEM) tracker information (Coal tracker was updated using the July 2025 version & Gas/Oil tracker was updated using the August 2025 version). These can reflect changes in our estimates.

- [Changed] Updated unit/plant level information due to manual research. These can reflect changes in our estimates.

- [Changed] Updated links to source data. These can reflect changes in our estimates.

### Fixed

- [Fixed]

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-07-31.

### Changed

### Fixed

## transportation,non-broadcasting-shipping

### Added

- [Added] Data period extended. Start_date 2025-07-01 to 2025-07-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,domestic-shipping

### Added

- [Added] OceanMind (OM) added and updated a combined 1,248 ports.

### Changed

- [Changed] OM emissions model updated to version ‘om.310725’, changes included below.

- [Changed] OM emissions model improved by calculating the required power for a vessel to carry out activities, including acceleration and deceleration.

- [Changed] OM emissions model now uses required power along with fuel calorific content to calculate emissions specific to the predicted fuel type being used by a vessel.

- [Changed] OM port attribution methodology has been improved using clustering algorithms to detect true berthing events.

- [Changed] OM port attribution algorithm added functionality to identify loitering behaviour before and after port stays.

- [Changed] Global Fishing Watch (GFW) model updated to version ‘_v20250701’.

- [Changed] GFW updated model values for the entire time series of data (2015-01-01 through 2025-06-30). The new model leverages extensive improvements to our vessel characteristics of low-information vessels, as well as improves our modeling of low-load activity, as well as the International Maritime (IMO) low sulphur fuel requirement that was implemented in 2020.

- [Changed] GFW expanded vessel coverage to include more 'low-information' vessels.

- [Changed] GFW improved the emissions model by incorporating emissions correction factors for low main engine loads.

- [Changed] GFW improved the emissions model for SOX and PM by accounting for the fact that starting on January 1, 2020, the IMO required lower sulfur content fuel.

- [Changed] GFW improved vessel characteristic model for inferring the main engine power, length, and gross tonnage of low-information vessels.

- [Changed] GFW improved vessel characteristic model for inferring the vessel class of low-information vessels.

- [Changed] GFW improved vessel characteristic model for inferring the subclass of low-information cargo vessels.

- [Changed] GFW developed a new vessel characteristic model for inferring the subclass of low-information tanker vessels (i.e., chemical or oil, liquefied gas, or other liquid).

- [Changed] GFW developed a new vessel characteristic model for inferring the maximum speed design characteristic of low-information vessels.

### Deprecated

- [Deprecated] OM removed a combined 479 defunct or incorrect ports.

- [Deprecated] OM 34 vessels which did not have sufficient information available to run through the new methodology.

### Fixed

- [Fixed] OM Duplicated ports removed: Furna vs Fuma.

- [Fixed] OM Various port shapes having incorrect ISO3 codes, or incorrect locations associated.

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-07-31.

### Changed

### Fixed

## transportation,international-shipping

### Added

- [Added] OceanMind (OM) added a combined 1248 new or updated ports

### Changed

- [Changed] OM emissions model updated to version ‘om.310725’, changes included below.

- [Changed] OM emissions model improved by calculating the required power for a vessel to carry out activities, including acceleration and deceleration.

- [Changed] OM emissions model now uses required power along with fuel calorific content to calculate emissions specific to the predicted fuel type being used by a vessel.

- [Changed] OM port attribution methodology has been improved using clustering algorithms to detect true berthing events.

- [Changed] OM port attribution algorithm added functionality to identify loitering behaviour before and after port stays.

- [Changed] GFW model updated to version ‘_v20250701’.

- [Changed] GFW updated model values for the entire time series of data (2015-01-01 through 2025-06-30). The new model leverages extensive improvements to our vessel characteristics of low-information vessels, as well as improves our modeling of low-load activity, as well as the IMO low sulphur fuel requirement that was implemented in 2020.

- [Changed] GFW expanded vessel coverage to include more 'low-information' vessels.

- [Changed] GFW improved the emissions model by incorporating emissions correction factors for low main engine loads.

- [Changed] GFW improved the emissions model for SOX and PM by accounting for the fact that starting on January 1, 2020, the IMO required lower sulfur content fuel.

- [Changed] GFW improved vessel characteristic model for inferring the main engine power, length, and gross tonnage of low-information vessels.

- [Changed] GFW improved vessel characteristic model for inferring the vessel class of low-information vessels.

- [Changed] GFW improved vessel characteristic model for inferring the subclass of low-information cargo vessels.

- [Changed] GFW developed a new vessel characteristic model for inferring the subclass of low-information tanker vessels (i.e., chemical or oil, liquefied gas, or other liquid).

- [Changed] GFW developed a new vessel characteristic model for inferring the maximum speed design characteristic of low-information vessels.

### Deprecated

- [Deprecated] OM a combined 479 defunct or incorrect ports.

- [Deprecated] OM removed 34 vessels which did not have sufficient information available to run through the new methodology.

### Fixed

- [Fixed] OM Duplicated ports removed: Furna vs Fuma.

- [Fixed] OM Various port shapes having incorrect ISO3 codes, or incorrect locations associated.

### Known Issues

- [Known Issues] OM Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OM Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources. New end_date 2025-07-31.

### Changed

- [Changed] Updated data due to revised emission factors from 2023-01-01 on.

- [Changed] Updated uncertainties to reflect updated data.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Have not updated to the latest ClimateTRACE patch of GADM data (v1.1.2).

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-07-01 to end_date 2025-07-31. Now all data runs from 2015-01-01 to 2025-07-31.

- [Added] Untreated wastewater assets. Start_date 2015-01-01 to end_date 2025-07-31.

### Fixed

### Known Issues

- [Known Issues] HydroWASTE sometimes sets the wrong ISO3 code for a plant, often when the plant is close to a national boundary.Future updates will address this issue.

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-07-01 to end_date 2025-07-31. Now all data runs from 2015-01-01 to 2025-07-31.

### Fixed

### Known Issues

- [Known Issues] Asset in China (3199430_INDWW) significantly larger emissions.

---

PDF: [4.7.0_combined-changelog-climate-trace.docx.pdf](./4.7.0_combined-changelog-climate-trace.docx.pdf) · Source: [methodology-documents/2025/CHANGELOG/09_Sept_V4.7.0/4.7.0_combined-changelog-climate-trace.docx.pdf](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/CHANGELOG/09_Sept_V4.7.0/4.7.0_combined-changelog-climate-trace.docx.pdf)

[← V4.X Changelogs](../)
