# [5.5.0] - 2026-03-25

## ClimateTRACE,deprecation-warning

- None

## ClimateTRACE,multiple-sectors,post-processing

### Added

- [Added] None

### Changed

– [Changed] Data from EDGAR (vEDGAR_2025_GHG; see https://edgar.jrc.ec.europa.eu/dataset_ghg2025#conditions)and FAOSTAT’s Domain Table ‘Crops and livestock products’ (version December 31, 2025) have been integrated, replacing EDGAR v9.0 and FAOSTAT 2024. The table below compares 2024 CO2e_100yr emissions between Climate TRACE v5.4.1 and v5.5.0, reflecting these updates. See “Data-Informed Disaggregation and Implicit Estimation of Emissions in Other Subsectors” methodology (version March 2026)in the methodology documents 2025 github folder. Note, changes from coalition member submitted data also impact these comparisons: Sub-sector  V5.4.1 CO2e_100yr  V5.5.0 CO2e_100yr  Change (Mt/yr)  (Mt/yr)  (Mt/yr) biological-treatment-of-solid 24.6  22.3  -2.3 -waste-and-biogenic enteric-fermentation-other  790.4  792.1  1.8 fluorinated-gases  1,652.5  1,740.0  87.5 incineration-and-open-burning 65.5  19.3  -46.1 -of-waste manure-management-other  223.9  544.1  320.2 other-agricultural-soil-emiss 1,388.4  1,067.1  -321.3 ions other-energy-use   2,282.1   2,492.0   210.0 other-fossil-fuel-operations 298.4 428.8 130.4 other-manufacturing 1,914.6 1,914.8 0.2 other-metals 186.5 86.4 -100.1 other-mining-quarrying   40.8   42.6   1.7 other-onsite-fuel-usage 206.3 172.6 -33.8 Sub-sector  V5.4.1 CO2e_100yr  V5.5.0 CO2e_100yr  Change (Mt/yr)  (Mt/yr)  (Mt/yr) other-solid-fuels   730.9   796.4   65.5 other-transport 182.1 189.6 7.6 railways  104.7  101.3  -3.3 Total  11,432.8  11,756.0  323.1

### Deprecated

- [Deprecated] None

### Fixed

– [Fixed] Fixed the equation for calculating country-level emissions for `other-metals`. Previously CEDS `1A2a_Ind-Comb-Iron-steel` was included, which resulted in a double counting of these emissions with those in the `iron-and-steel` sector. This update removes this double-counting, resulting in a sector-wide reduction in emissions. – [Fixed] Fixed iron-and-steel assets were previously extrapolated forward rather than being set to a “closed” state with 0 emissions. Affected asset IDs are: 1566424, 1566477, 1566542, 1566555, 1566559, 1566564, 1566578, 1566580, 1566620, 1566648, 1566669, 1566770, 1566825, 1566949, 1566965, 1567083, 1567106, 1567145, 1567184, 1567187, 1567226, 1567250, 1567255, 1567256, 1567257, 1567259, 1567263, 1567268, 1567271, 1567273, 1567274, 1567275, 1567280, 1567281, 1567282, 1567285, 1567286, 1567290, 1567291, 1567292, 1567294, 1567295, 1567296, 1567297, 1567299, 1567300, 1567301, 1567303, 1567305, 1567312, 1567313, 1567314, 1567315, 1567316, 1567317, 1567318, 1567319, 1567320, 1567321, 1567322, 1567323, 1567324, 1567325, 1567326, 1567327, 32441205, 32441208, 32441223, 32441224, 32441229, 32441253, 38089228, 42741547, 42741574, 42741753, 42741756, 42741765, 42741804, 42741864, 42741875. – [Fixed] Previously, some city emissions data had multiple rows for a given timestamp in the data downloads packages for individual gases (CO2, CH4, N2O).

- [Fixed] non-broadcasting-vessels CO2e_100yr and CO2e_20yr emissions were previously doubled for only January in the GADM emissions data.

### Known Issues

- [Known Issue] Still present from V5.4.1: Two domestic-wastewater-treatment-and-discharge assets were assigned the wrong ISO-3 country code: 48250739 and 48251021 were incorrectly tagged to CAF and COD rather than SLB and UGA, respectively.

- [Known Issue] Still present from V5.4.1: Due to handling of multiple rank=1 strategy inputs for a given asset, asset ERS for the following sectors may differ between releases until coding updates remain. Generally, sector-country total reductions should remain consistent, but asset-level reductions may differ slightly until this issue is resolved: `manure-management-cattle-operation`, `coal-mining`, `domestic-wastewater-treatment-and-discharge`, `solid-waste-disposal`, `enteric-fermentation-cattle-operation`, `iron-and-steel`, `domestic-shipping`, `international-shipping`

## ClimateTRACE,individual-changelogs

## buildings,non-residential-onsite-fuel-usage

### Added

- [Added] - [Added] Data period extended for existing sources through end_date 2026-01-31.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## forestry-and-land-use,forest-land-clearing

### Added

- [Added] Added 2025 Q4 emissions data.

### Changed

- [Changed] Updated 2024 emission estimations, emission raster file, and capacity-factor raster file based on the newly available 2024 Global Annual Burned Area Maps (GABAM) data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in 2025.

## forestry-and-land-use,forest-land-degradation

### Added

- [Added] Added 2025 Q4 emissions data.

### Changed

- [Changed] Updated 2024 emission estimations, emission raster file, and capacity-factor raster file based on the newly available 2024 Global Annual Burned Area Maps (GABAM) data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in 2025.

## forestry-and-land-use,forest-land-fires

### Added

- [Added] Added 2025 Q4 emissions data.

### Changed

- [Changed] Updated 2024 emission estimations, emission raster file, capacity-factor raster file, and activity raster file based on the newly available 2024 Global Annual Burned Area Maps (GABAM) data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in 2025.

## forestry-and-land-use,shrubgrass-fires

### Added

- [Added] Added 2025 Q4 emissions data.

### Changed

- [Changed] Updated 2024 emission estimations, emission raster file, capacity-factor raster file, and activity raster file based on the newly available 2024 Global Annual Burned Area Maps (GABAM) data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in 2025.

## forestry-and-land-use,wetland-fires

### Added

- [Added] Added 2025 Q4 emissions data.

### Changed

- [Changed] Updated 2024 emission estimations, emission raster file, capacity-factor raster file, and activity raster file based on the newly available 2024 Global Annual Burned Area Maps (GABAM) data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issue] The 2025 quarterly emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current 2025 quarterly emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in 2025.

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] None

### Changed

- [Changed] Updated reported emissions for Q1 2024. Start_date 2024-01-01 to end_date 2024-03-31. Country, uncertainty, and confidence sheets have been updated too.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,aluminum

### Added

- [Added] 2 new months added (month lag set to 2 months.

### Changed

- [Changed] Full refresh (01 Jan 2021 - 01 Jan 2026) due some assets removed and added more accurate locations to other assets.

- [Changed] Submitted an update to the historical asset-level data (i.e., back to 2021)

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Removed duplicates & fixed asset locations.

- [Fixed] Country level data (2015-2024) uploaded with unique country count matching unique countries in asset level data.

- [Fixed] South Korea country-level emissions added.

### Known Issues

- [Known Issues] None

## manufacturing,cement

### Added

[Added] Added new months, December 2025 and January 2026 data included in this release.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,other-manufacturing

### Added

- [Added] None

### Changed

- [Changed] Updated contribution of combustion emissions from non-metallic-mineral production based on updated EDGAR data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] None

### Changed

-[Changed] Separately reported emissions for Q1 2024 start_date 2024-01-01 to end_date 2024-03-31 for all assets.

### Deprecated

- [Deprecated] None

### Fixed

-[Fixed] Updated historical country emissions 2015-2024 for VNM, IND, BGR to reflect updated asset data.

### Known Issues

- [Known Issues] None

## manufacturing,iron-and-steel

### Added

[Added] Full refresh of asset-level data through January 2026 and country-level data through 2024.

### Changed

[Changed] Updated retirement and start dates of steel assets based on the latest data from the GEM tracker. [Changed] Improved the country-level emissions factor estimation model to better align with asset-level emission factors.

### Deprecated

- [Deprecated] None

### Fixed

[Fixed] Corrected the emission factor for the Netherlands in the country-level emissions dataset.

### Known Issues

- [Known Issues] None

## manufacturing,glass

### Added

- [Added] None

### Changed

- [Changed] Updated contribution of combustion emissions based on updated EDGAR data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,lime

### Added

- [Added] None

### Changed

- [Changed] Updated contribution of combustion emissions based on updated EDGAR data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,food-beverage-tobacco

### Added

- [Added] None

### Changed

- [Changed] Updated contribution of combustion emissions based on updated EDGAR data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,textiles-leather-apparel

### Added

- [Added] None

### Changed

- [Changed] Updated contribution of combustion emissions based on updated EDGAR data.

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known Issues

- [Known Issues] None

## manufacturing,other-metals

### Added

- [Added] None

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Fixed the equation for calculating country-level emissions for `other-metals`. Previously CEDS `1A2a_Ind-Comb-Iron-steel` was included, which resulted in a double counting of these emissions with those in the `iron-and-steel` sector. This update removes this double-counting, resulting in a sector-wide reduction in emissions.

### Known Issues

- [Known Issues] None

## mineral-extraction,bauxite-mining

### Added

- [Added] None

### Changed

- [Changed] Updated metadata [activity, CO2_emissions_factor, CO2_emissions].

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Removed activity and emissions data incorrectly duplicated to additional asset (BAU-042003).

### Known Issues

- [Known Issues] None

## mineral-extraction,copper-mining

### Added

- [Added] None

### Changed

- [Changed] Updated metadata [location, capacity_factor, activity, CO2_emissions_factor, CO2_emissions, status].

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Corrected CO2 emissions factor for multiple assets under group ownership, with subsequent updates to national/regional average values.

### Known Issues

- [Known Issues] None

## mineral-extraction,iron-mining

### Added

- [Added] None

### Changed

- [Changed] Updated metadata [location, CO2_emissions_factor, CO2_emissions].

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Updated incorrect CO2 emissions factor for 3 assets (IRO-003004, IRO-003005 and IRO-045092).

### Known Issues

- [Known Issues] None

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Start_date 2019-01-01 to end_date 2026-01-31.

### Changed

- [Changed] Updated Global Coal Power Tracker (version: Feb 2026).

- [Changed] Updated Global Gas/Oil Power Tracker (version: Feb 2026).

- [Changed] Updated Global Integrated Power Tracker (version: Feb 2026).

- [Changed] Updated unit/plant level information due to manual research. These can reflect changes in our estimates.

- [Changed] Updated plant definitions from EIA (version: Dec 2025).

- [Changed] Updated ownership information from GEM (version: Feb 2026).

- [Changed] Pulled new most recent months from reported generation sources and updated reported generation validation tests. These can reflect changes in our estimates.

- [Changed] We identified plants that employ different cooling technologies than our remote-sensing methods are based on. At these plants, we no longer apply our inference models.

### Fixed

- [Fixed]

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

- [Known Issues] Our remote sensing-based estimates of plant activity are biased low in some grid regions. We are working to address the bias in future releases.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-01-31.

### Changed

- [Changed] None

### Fixed

- [Fixed] None

## transportation,non-broadcasting-vessels

### Added

- [Added] Data period extended. Start_date 2026-01-01 to 2026-01-31.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] None

### Known issue

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2026-01-31.

### Changed

- [Changed] None

### Fixed

- [Fixed] None

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources. New end_date 2026-01-31.

### Changed

- [Changed] None

### Deprecated

- [Deprecated] None

### Fixed

- [Fixed] Updated bug that caused undercounting in vehicle fleet data for ALB, BRN, KHM, IDN, LAO, MYS, MMR, PHL, SGP, THA, VNM for years 2020 through 2025.

### Known Issues

- [Known Issues] Have not updated to the latest Climate TRACE patch of GADM data (v1.1.2).

---

PDF: [5.5.0_combined-changelog_2026.docx.pdf](./5.5.0_combined-changelog_2026.docx.pdf)

[← V5.X Changelogs](../)
