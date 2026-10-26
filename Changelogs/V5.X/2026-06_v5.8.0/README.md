# [5.8.0] - 2026-06-25

## ClimateTRACE,deprecation-warning

- None

## ClimateTRACE,multiple-sectors,post-processing

- None

## ClimateTRACE,individual-changelogs

## agriculture,synthetic-fertilizer-application

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

[Known Issue] Synthetic-fertilizer-application activity is reported as nitrogen application rate in units of kg/year, not the kg applied in each month corresponding to monthly granularity timestamps.

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2026-04-01 to end_date 2026-04-30.

### Changed

- [Changed] Updated historical data for existing sources. Start_date 2026-01-01 to end_date 2026-03-31.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## forestry-and-land-use,forest-land-clearing

### Added

- [Added] Added 2026 Q1 emissions data.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2026 quarterly emissions dataset utilizes CTrees 2026 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. Due to heavy snow cover in late 2025 and early 2026, LUCA does not update Q1 disturbance estimates in some high-latitude northern countries, which may affect the attribution of emissions among deforestation, degradation, and fire. For countries without updated LUCA observations, temporal mean values were used to fill the estimates.

## forestry-and-land-use,forest-land-degradation

### Added

- [Added] Added 2026 Q1 emissions data.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2026 quarterly emissions dataset utilizes CTrees 2026 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. Due to heavy snow cover in late 2025 and early 2026, LUCA does not update Q1 disturbance estimates in some high-latitude northern countries, which may affect the attribution of emissions among deforestation, degradation, and fire. For countries without updated LUCA observations, temporal mean values were used to fill the estimates.

## forestry-and-land-use,forest-land-fires

### Added

- [Added] Added 2026 Q1 emissions data.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2026 quarterly emissions dataset utilizes CTrees 2026 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. Due to heavy snow cover in late 2025 and early 2026, LUCA does not update Q1 disturbance estimates in some high-latitude northern countries, which may affect the attribution of emissions among deforestation, degradation, and fire. For countries without updated LUCA observations, temporal mean values were used to fill the estimates.

## forestry-and-land-use,shrubgrass-fires

### Added

- [Added] Added 2026 Q1 emissions data.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2026 quarterly emissions dataset utilizes CTrees 2026 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. Due to heavy snow cover in late 2025 and early 2026, LUCA does not update Q1 disturbance estimates in some high-latitude northern countries, which may affect the attribution of emissions among deforestation, degradation, and fire. For countries without updated LUCA observations, temporal mean values were used to fill the estimates.

## forestry-and-land-use,water-reservoirs

### Added

- [Added] Data period extended for existing sources; added March 2026 and April

2026. The end date is now April 30, 2026.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Sentinel-2 SCL spatial resolution was incorrectly set to 10 m for surface area calculations. It has been updated to 20 m, the correct spatial resolution of the Sentinel-2 SCL product. This fix has been successfully applied to the historical record from 2017 to the present. For the years 2015-2017, due to the lack of global Sentinel-2 data, we use NDWI calculated from available Landsat data.

### Known Issues

- [Known Issues] Globally, emissions appear to jump between 2016 and 2017, which we currently attribute to the discrepancy in data sources - i.e., Landsat NDWI versus Sentinel-2 SCL.

## forestry-and-land-use,wetland-fires

### Added

- [Added] Added 2026 Q1 emissions data.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2026 quarterly emissions dataset utilizes CTrees 2026 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. Due to heavy snow cover in late 2025 and early 2026, LUCA does not update Q1 disturbance estimates in some high-latitude northern countries, which may affect the attribution of emissions among deforestation, degradation, and fire. For countries without updated LUCA observations, temporal mean values were used to fill the estimates.

## manufacturing,iron-and-steel

### Added

-[Added] Full refresh for asset-level emissions data from 2021 until April 2026 included in this release. -[Added] Full refresh for monthly country-level emissions from 2015 until April 2026 included in this release.

### Changed

-[Changed] Adjusted calibration curve between satellite detection and capacity factor using the latest available data.

### Deprecated

-[Deprecated] None

### Fixed

-[Fixed] Country, GADM, and GHS-FUA aggregated emissions quantities in HUN (Hungary) for the iron-and-steel sub-sector were spuriously inflated pre-2021 due to poor extrapolation, now fixed. (Issue has been present since at least V4.5.0.).

### Known Issues

- [Known Issues] None

## manufacturing,other-metals

### Added

- [Added] None

### Changed

- [Changed] Full 2015-present timeseries has been updated in response to updates to iron-and-steel data. Global changes were minimal, in aggregate, for this sector (e.g. 2025 CO2e emissions 85.7 Mt CO2e100yr vs. 85.1 Mt CO2e100yr in V5.7.0), but may be more pronounced for individual countries.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

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

- [Known Issues] Country-level copper-mining CO2e emissions show an unrealistic step change at 2019 to 2020 — global totals roughly double from ~45 Mt CO2e/yr (2015–2019) to ~90 Mt CO2e/yr (2020–present), affecting many copper-producing countries simultaneously. Countries with step changes over 1 Mt/year in emissions between the pre-2020 mean and 2020-onward mean are KAZ, COD, IRN, USA, PER, ZMB, PAN. This issue has been present since at least V4.0.

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-04-30.

### Changed

- [Changed] For a very small power plants in the data submitted before this version, the equation ‘activity = capacity * cf’ was off due to capacity rounding. This version fixed the capacity rounding so that for all power plants the equation is not affected.

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

- [Known Issues] Our remote sensing-based estimates of plant activity are biased low in some grid regions including China. We are working to address the bias in future releases.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-04-30.

- [Added] Added coverage. 5 new sources added, presented by their international air transportation association (iata) code: {'iata_BFY', 'iata_GEO', 'iata_GON', 'iata_QBU', 'iata_STQ'}.

### Changed

- [Changed] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## transportation,non-broadcasting-vessels

### Added

- [Added] Data period extended. Start_date 2026-04-01 to 2026-04-30.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known issues

- [Known issues] None

## transportation,domestic-shipping

### Added

- [Added] Data period extended. Start date 2026-04-01 to 2026-04-30.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends

- [Known Issues] Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-04-30.

- [Added] Added coverage. 5 new sources added presented by their international air transportation association (iata) code: {'iata_BFY', 'iata_GEO', 'iata_GON', 'iata_QBU', 'iata_STQ'}.

### Changed

- [Changed] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## transportation,international-shipping

### Added

- [Added] Data period extended. Start date 2026-04-01 to 2026-04-30.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends

- [Known Issues] Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2026-03-01 to end_date 2026-04-31.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Fixed the coordinates for the SOUTH RIVER WWTP to 33.683407803203, -84.3628685262687 after manual verification.

- [Fixed] Fixed the coordinates for the Batonyterenye Wastewater Treatment Plant to 47.98600976222678, 19.81691427721818.

### Known issues

- [Known Issues] Potential duplicate assets.

- [Known Issues] Seasonally inconsistent n2o emissions factor values used in Ethiopia are likely deflating emissions for most of 2025 through Feb 2026, causing the March 2026 data to appear as an outlier.

## waste,solid-waste-disposal

### Added

- [Added] Data period extended for existing sources to end_date 2026-04-30.

### Changed

- [Changed] Improved the area-to-incoming-waste model, which predicts missing annual incoming waste from landfill surface area. This impacted the emissions estimates at many landfills. A multiplicative coefficient was added to the power law model (which behaves as an intercept in log space).

- [Changed] Most uncertainty estimates have changed. Formerly, the uncertainty file had a single uncertainty estimate per row that was assigned to all column values (capacity, activity, emissions, the factors). Now, uncertainty values for capacity, activity, emissions, and their factors are calculated individually and can vary within a row.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Removed a bug assigning incorrect methane conversion factor (MCF) based on site type in some cases. This will increase emissions estimates at ~10% of sites.

### Known Issues

- [Known Issues] None

---

PDF: [5.8.0_combined-changelog-climate-trace.docx.pdf](./5.8.0_combined-changelog-climate-trace.docx.pdf) · Source: [methodology-documents/2026/CHANGELOG/06_Jun_V5.8.0/5.8.0_combined-changelog-climate-trace.docx.pdf](https://github.com/climatetracecoalition/methodology-documents/blob/main/2026/CHANGELOG/06_Jun_V5.8.0/5.8.0_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
