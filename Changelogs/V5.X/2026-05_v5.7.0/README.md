# [5.7.0] - 2026-05-27

## ClimateTRACE,deprecation-warning

- None

## ClimateTRACE,multiple-sectors,post-processing

### Added

### Changed

- [Changed] Electricity marginal emissions rates now are based on a 2025 baseline rather than 2024 baseline.

- [Changed] Emissions reductions calculations for “net” forestry sectors (including removals) were previously reported as NULL. They are now removed entirely.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Iron-and-steel, domestic-shipping, and international-shipping assets that are closed or inactive no longer carry over spurious non-zero activity and emissions to dates outside the asset's actual active window. (Issue was present in V5.6.0 only)

- [Fixed] Asset closures in the iron-and-steel subsector are now accounted for in extrapolated country-level emissions when asset and country level totals have matched in historical data. (Issue has been present since at least V4.0.0.).

- [Fixed] Non-GHG emissions (pm2.5, nox, so2, nmvoc, nh3, co, bc, oc) for the 41 sectors that derive non-GHG values from CEDS ratios (e.g., aluminum, cement, chemicals, coal-mining, iron-and-steel, oil-and-gas-production, oil-and-gas-transport, most metals/mining/manufacturing) were not computed for 2026 in V5.5.0 and V5.6.0. In V5.7.0 these series now extend through March 2026.

### Known Issues

- [Known Issues] None

## ClimateTRACE,individual-changelogs

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] Data period extended for existing sources. Start_date 2026-02-01 to end_date 2026-03-31.

### Changed

- [Changed] Updated historical data for existing sources. Start_date 2026-01-01 to end_date 2026-02-28.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## fossil-fuel-operations,oil-and-gas-production

### Added

- [Added] Data period calculated for all sources through Dec 2025.

### Changed

- [Changed] United States data now uses monthly production data directly rather than extrapolating from annual data, improving accuracy.

- [Changed] Methodology updated describing Basin Mapping. See: Oil and Gas Production and Transport-FossilFuelOperationsSector-05272026 in the Climate TRACE GitHub repo.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] 2025 international production input data is out of date.

- [Known Issues] Kentucky emissions are zero in 2024/2025 due to lack of activity data in the state.

- [Known Issues] 2015-2020 California data missing due to current lack of historical data inputs.

- [Known Issues] Emissions data does not currently reflect changes due to the conflict in the Middle East.

## fossil-fuel-operations,oil-and-gas-transport

### Added

- [Added] Data period calculated for all sources through Dec 2025.

### Changed

- [Changed] United States data now uses monthly production data directly rather than extrapolating from annual data, improving accuracy.

- [Changed] Methodology updated describing Basin Mapping. See: Oil and Gas Production and Transport-FossilFuelOperationsSector-05272026 in the Climate TRACE GitHub repo.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] Transport CO2 emissions missing in most California fields and Macachín (Argentina) due to modeling glitches

- [Known Issues] 2025 international production input data is out of date.

- [Known Issues] Kentucky emissions are zero in 2024/2025 due to lack of activity data in the state.

- [Known Issues] 2015-2020 California data missing due to current lack of historical data inputs.

- [Known Issues] Emissions data does not currently reflect changes due to the conflict in the Middle East.

## manufacturing,aluminum

### Added

-[Added] Added new month, March 2026 data included in this release.

### Changed

-[Changed] 2026 capacity values updated across all assets to reflect the latest Light Metal Age (LMA) dataset (April 2026 ingest).

- [Changed] One Chinese asset was deduplicated: 43765129-Fukang, Xinjiang (Nongliushi) Renamed/Merged into 3673026-Fukang, Xinjiang aluminium plant as they represent the same plant.

- [Changed] Two Chinese sites were removed in this version of the dataset (43765122 & 43765128) but the active asset coverage is consistent with the previous months.

### Deprecated

-[Deprecated] None

### Fixed

-[Fixed] None

### Known Issues

-[Known Issues] Korba (IND) shows an anomalously high 2026 capacity value (1,000,000t) in the LMA source data compared to its historical operational capacity (~410,000t). This is a known data quality issue in the raw source and will be investigated for the next submission.

## manufacturing,cement

### Added

-[Added] Added new month, March 2026 data included in this release.

### Changed

-[Changed] None

### Deprecated

-[Deprecated] None

### Fixed

-[Fixed] None

### Known Issues

-[Known Issues] None

## manufacturing,iron-and-steel

### Added

-[Added] Added new month, March 2026 data included in this release. -[Added] Added the monthly country level emissions from 2015 until March 2026.

### Changed

-[Changed] None

### Deprecated

-[Deprecated] None

### Fixed

-[Fixed] None

### Known Issues

- [Known Issues] Country, GADM, and GHS-FUA aggregated emissions quantities in HUN (Hungary) for the iron-and-steel sub-sector are spuriously inflated pre-2021 due to poor extrapolation.

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

- [Known Issues] Country-level copper-mining co2e emissions show an unrealistic step change at 2019 to 2020 — global totals roughly double from ~45 Mt CO2e/yr (2015–2019) to ~90 Mt CO2e/yr (2020–present), affecting many copper-producing countries simultaneously. Countries with step changes over 1 Mt/year in emissions between the pre-2020 mean and 2020-onward mean are KAZ, COD, IRN, USA, PER, ZMB, PAN. This issue has been present since at least V4.0.

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-03-31.

### Changed

- [Changed] Updated unit/plant level information due to manual research. These can result in changes to our estimates.

- [Changed] Included most recent months from reported generation sources. These can result in changes to our estimates.

- [Changed] Updated asset predictions to include predictions from 2015-01-01 onward.

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

- [Known Issues] Our remote sensing-based estimates of plant activity are biased low in some grid regions including China. We are working to address the bias in future releases.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-03-31.

### Changed

-[Changed] None

### Fixed

-[Fixed] None

### Known Issues

-[Known Issues] None

## transportation,non-broadcasting-vessels

### Added

- [Added] Data period extended. Start_date 2026-03-01 to 2026-03-31.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issue

- [Known Issues] None

## transportation,domestic-shipping

### Added

- [Added] Data period extended. Start date 2026-03-01 to 2026-03-31.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] OceanMind invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OceanMind attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-03-31.

### Changed

-[Changed] None

### Fixed

-[Fixed] None

### Known Issues

-[Known Issues] None

## transportation,international-shipping

### Added

- [Added] Data period extended. Start date 2026-03-01 to 2026-03-31.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] OceanMind invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] OceanMind Attribution of emissions to ports as 50/50 on trips with significant loitering can cause emissions reductions assigned to a port that is greater than the emissions assigned to that port.

## waste,biological-treatment-of-solid-waste-and-biogenic

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Historic data for existing sources. Start_date 2015-01-01 to end_date 2026-02-28.

### Changed

- [Changed] Updated technology level metadata for 2,017 assets from EU countries from the latest data release (2021-2023) from the European Environment Agency (EEA).

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known issues

- [Known Issues] Potential duplicate assets.

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Historic data for existing sources. Start_date 2015-01-01 to end_date 2026-02-28.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known issues

- [Known Issues] Potential duplicate assets.

---

PDF: [5.7.0_combined-changelog-climate-trace.docx.pdf](./5.7.0_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
