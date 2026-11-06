# [4.5.0] - 2025-07-25

## ClimateTRACE,multiple-sectors,post-processing:

### Added

### Changed

- [Changed] All asset estimates are now extrapolated to the final timestamp of the full data set if any recent data are missing. Previously, assets with uncommon end times (end times that were unique to < 25% of assets in the sector) were not extrapolated forward. Notably, this improved estimates of rice-cultivation assets for 2025 which should have been extrapolated. Exceptions to this handling include (1) the forestry and land-use sectors, which are set to zero for all missing estimates, (2) the shipping and aviation sectors, and electricity-generation sub-sector for which activity is assumed to be zero for any assets’ missing timestamps, while capacity is imputed based on other existing timestamps, and (3) the iron-and-steel subsector, which follows earlier practice where assets with uncommon (< 25% of assets) final timestamps are assumed to be closed after the final timestamp.

- [Changed] Fluorinated-gases CO2e values are calculated independently of EDGAR, using IPCC AR6 values from Table 7.SM.7.See document: https://www.ipcc.ch/report/ar6/wg1/downloads/report/IPCC_AR6_WGI_Chapter07_SM.p df

- [Changed] Updated country-level extrapolation method now performed on entire sub-sector where external inventory data are unavailable. Previously, external inventory subsector estimates were extrapolated prior to gap-fill calculations. See methodology: [Other Sectors methodology](../../../Sector-Methodologies/2-Cross-Cutting/other-sectors/README.md)

- [Changed] Emissions estimates from 2023 onward are affected by country-level extrapolation method for the following Manufacturing sectors: food-beverage-tobacco, glass, lime, other-chemicals,  other-manufacturing, other-metals, textiles-leather-apparel, and wood-and-wood-products.

- [Changed] Emissions estimates from 2023 onward are affected by country-level extrapolation method for the following Mineral extraction sector: other-mining-quarrying.

- [Changed] Emissions estimates from 2023 onward are affected by country-level extrapolation method for the following Agriculture sectors: enteric-fermentation-other, manure-management-other, and other-agricultural-soil-emissions.

- [Changed] Emissions estimates from 2024 onward were affected for the Fluorinated-gases subsector.

- [Changed] Emissions estimates from 2024 onward were affected by country-level extrapolation method for the Power subsector: other-energy-use.

- [Changed] Emissions estimates from 2024 onward were affected by country-level extrapolation method for the Transportation subsectors: other-transport and railways.

- [Changed] Emissions estimates from 2024 onward were affected by country-level extrapolation method for the Buildings subsector: other-onsite-fuel-usage.

- [Changed] Emissions estimates from 2024 onward were affected by country-level extrapolation method for the Fossil-fuel-operations subsectors: other-fossil-fuel-operations and other-solid-fuels.

- [Changed] Emissions estimates from 2024 onward were affected by country-level extrapolation method for the Waste subsectors: biological-treatment-of-solid-waste-and-biogenic and incineration-and-open-burning-of-waste.

### Deprecated

### Fixed

- [Fixed] cropland-fires unit string to “km^2”, which was incorrectly reported as “ha”.

- [Fixed] “ZNC” ISO3 code is now present in the country data set for any sub-sectors with emissions in ZNC. These include synthetic-fertilizer-application, electricity-generation, residential-onsite-fuel-usage, non-residential-onsite-fuel-usage, road-transportation, crop-residues, domestic-wastewater-treatment-and-discharge, domestic-shipping, international-aviation, and manure-applied-to-soils.

### Known Issues

## ClimateTRACE,individual-changelogs:

## agriculture,crop-residues

### Added

- Added monthly country-level data from 2015-2024 for crop residue for 251 countries. See methodology: [Agriculture methodologies (synthetic fertilizer, crop residue and manure application)](../../../Sector-Methodologies/1-Sectors/agriculture/)

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

### Known Issues

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

- [Changed] This sector approach to estimate emissions has been added to “Emissions from Synthetic Fertilizer, Crop Residue, and Manure Application” Methodology. However, for the 4.5.0 release, the approach described in the methodology and resulting emissions will be a future release. Refer to the changelog for “ClimateTRACE,multiple-sectors” in the 4.5.0_combined-changelog-climate-trace.pdf for a description on this month’s release for manure-applied-to-soils emissions.

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

### Known Issues

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

- [Added] 2024 asset level emissions data for the following countries (iso country codes): BRA, ECU, EGY, ESP, ETH, GUY, ITA, MDG, MEX, RUS, SUR, TUR, TZA, URY, and USA.

### Changed

- [Changed] Fixed column mismatches for IRN and BTN from previous submission.

### Deprecated

### Fixed

### Known Issues

## agriculture,synthetic-fertilizer-application

### Added

### Changed

- [Changed] This sector’s methodology name has been changed to “Emissions from Synthetic Fertilizer, Crop Residue, and Manure Application”. See updated methodology: [Agriculture methodologies (synthetic fertilizer, crop residue and manure application)](../../../Sector-Methodologies/1-Sectors/agriculture/)

### Deprecated

### Fixed

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

- [Added] Data period extended for existing sources. Start_date 2025-01-01 to end_date 2025-03-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 Q1 urban areas emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current Q1 emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early 2025.

## forestry-and-land-use,forest-land-degradation

### Added

- [Added] Data period extended for existing sources. Start_date 2025-01-01 to end_date 2025-03-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 Q1 urban areas emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current Q1 emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early 2025.

## forestry-and-land-use,forest-land-fires

### Added

- [Added] Data period extended for existing sources. Start_date 2025-01-01 to end_date 2025-03-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 Q1 urban areas emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current Q1 emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early 2025.

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

- [Added] Data period extended for existing sources. Start_date 2025-01-01 to end_date 2025-03-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 Q1 urban areas emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current Q1 emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early 2025.

## forestry-and-land-use,water-reservoirs

### Added

- [Added] Data period extended for existing sources. Start_date 2025-01-01 to end_date 2025-05-31.

### Changed

- [Changed] Reservoir surface areas were previously calculated using Normalized Difference Water Index (NDWI) derived from Landsat or Sentinel-2's green and near-infrared bands. For this model version, and going forward, this sector is leveraging Sentinel-2's Scene Classification Layer (SCL), produced by the European Space Agency (ESA). See methodology: [Reservoirs methodology](../../../Sector-Methodologies/1-Sectors/forestry-and-land-use/reservoirs/README.md)

- [Changed] Due to the switch to Sentinel-2's SCL, this release’s emissions will be different compared to last release.

### Deprecated

### Fixed

- [Fixed] The Sentinel-2’s SCL significantly improved surface area estimates and reduced uncertainty caused by previously used Sentinel-2 and Landsat NDWI estimates.

### Known Issues

## forestry-and-land-use,wetland-fires

### Added

- [Added] Data period extended for existing sources. Start_date 2025-01-01 to end_date 2025-03-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issue] The 2025 Q1 urban areas emissions dataset utilizes CTrees 2025 land use change alert (LUCA) data as the basis for estimating disturbance-related emissions. The current Q1 emission estimates may not fully attribute specific disturbance types (deforestation, degradation, and fire) that occurred in early 2025.

## fossil-fuel-operations,coal-mining

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-production

### Added

- [Added] Data period calculated for all sources. Start_date 2015-01-01 to end_date 2025-06-01.

- [Added] Added coverage. Belize data added.

### Changed

- [Changed] Updated model for all data. OPGEE3c revamp, see: [https://github.com/RMI/ogsi_OPGEE_excel/tree/main]

- [Changed] Input data sources have changed and are fully employed in this release, which has changed model outputs and estimates. See methodology sections 3.1 to 3.3 for more information: [Oil and Gas Production and Transport methodology](../../../Sector-Methodologies/1-Sectors/fossil-fuel-operations/oil-and-gas-production-and-transport/README.md)

- [Changed] Updated metadata confidence, emissions to reflect model changes and new post-processing.

- [Changed] Updated venting emissions calculations using IEA values.

- [Changed] Renamed and re-identified assets to reflect new aggregation scheme.

### Deprecated

- [Deprecated] Removal of UNK (unknown) country. Assets that fall in disputed territories have been assigned evenly between countries.

### Fixed

### Known Issues

- [Known Issues] electrical grid mix accounting is currently missing from the model.

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in the rest of the world. Start_date 2024-07-01 to end_date 2024-09-30.

- [Added] The modeled results of ALB refineries #841 and #842 for the period Q42023 & Q12024.

- [Added] The modeled results of those assets with missing timestamps have all been completed. Annual 2015 - 2023 results for 21 newly added refineries.

### Changed

- [Changed] Updated a couple of Japanese refineries' maintenance issues and remodeled results for Q2 2024, including #470 and #486.

- [Changed] Updated Q2 2024 modeled results of two Chinese teapots that shut down in Q2 2024 due to the weak margin, #323, #339.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Current Chinese capacity factors estimates for refineries will be improved in future releases as more granular and accurate data sources have become available.

## fossil-fuel-operations,oil-and-gas-transport

### Added

- [Added] Data period calculated for all sources. Start_date 2015-01-01 to end_date 2025-06-01.

- [Added] Added coverage. Belize data added.

### Changed

- [Changed] Updated model for all data. OPGEE3c revamp, see [https://github.com/RMI/ogsi_OPGEE_excel/tree/main]

- [Changed] Input data sources have changed and are fully employed in this release, which has changed model outputs and estimates. See methodology sections 3.1 to 3.3 for more information: [Oil and Gas Production and Transport methodology](../../../Sector-Methodologies/1-Sectors/fossil-fuel-operations/oil-and-gas-production-and-transport/README.md)

- [Changed] Updated metadata confidence and emissions to reflect model changes and new post-processing.

- [Changed] Renamed and re-identified assets to reflect new aggregation scheme.

### Deprecated

- [Deprecated] Removal of UNK (unknown) country. Assets that fall in disputed territories have been assigned evenly between countries.

### Fixed

### Known Issues

- [Known Issues] electrical grid mix accounting is currently missing from the model.

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

- [Added] Data period extended for existing sources. Start_date 2025-04-01 to end_date 2025-04-30.

### Changed

### Deprecated

### Fixed

- [Fixed] Swapped asset names and asset identifiers for smelters fixed

### Known Issues

## manufacturing,cement

### Added

- [Added] Added coverage. New assets included, identifiable by their TZCMT2505 ID prefix.

- [Added] New fields indicating cement type (cement_type) and any emissions reduction technologies (ers_technology) employed at the asset.

### Changed

- [Changed] Updated metadata [ownership, capacity, coordinates, emissions_factor]: our primary asset metadata source is no longer Spatial Finance Initiative but Global Energy Monitor's new Global Cement and Concrete Tracker. See methodology: [Cement Manufacturing methodology](../../../Sector-Methodologies/1-Sectors/manufacturing/cement-manufacturing/README.md)

- [Changed] Due to metadata source change, the emissions for this release will overall increase compared to last release.

- [Changed] Updated historical data from 2021-01-01 to 2025-04-30.

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

- [Added] Data period extended for existing sources in the rest of the world. Start_date 2024-07-01 to end_date 2024-09-30.

- [Added] Historical data for 4 assets (#235 - #238) that missed certain data timestamps.

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

- [Added] Data period extended for existing sources. Start_date 2025-04-01 to end_date 2025-04-30.

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

- [Added] Data period extended for existing sources. Start_date 2019-01-01 to end_date 2025-05-31.

### Changed

- [Changed] Improved plant operation start and end dates. These can reflect changes in our estimates.

- [Changed] Updated unit/plant level information. These can reflect changes in our estimates.

- [Changed] EMBER data was updated to Jun 4 2025 version. EMBER updated estimates can reflect changes in our estimates.

### Deprecated

### Fixed

- [Fixed] Fixed bug that affected weather data; as a result more images were able to be analyzed by machine learning models than in the previous release.

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

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

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-05-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,non-broadcasting-shipping

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,domestic-shipping

### Added

- [Added] Data period extended for existing sources. Start_date 2025-05-01 to end_date 2025-05-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends

- [Known Issues] Duplicated ports identified : Furna vs Fuma. Will fix this in future updates.

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-05-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## transportation,international-shipping

### Added

- [Added] Data period extended for existing sources. Start_date 2025-05-01 to end_date 2025-05-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] Duplicated ports identified : Furna vs Fuma. Will fix this in future updates.

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

- [Added] Data period extended for existing sources. New end_date 2025-05-31.

### Changed

- [Changed] Updated data due to interpolation from 2024-07-01 on.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Have not updated to the latest Climate TRACE patch of GADM data (v1.1.2).

## waste,biological-treatment-of-solid-waste-and-biogenic

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-05-01 to end_date 2025-05-31. Now all data runs from 2015-01-01 to 2025-05-31.

### Changed

### Deprecated

### Fixed

- [Fixed] Incorrect ISO3 values for a handful of assets at borders.

### Known Issues

## waste,incineration-and-open-burning-of-waste

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-05-01 to end_date 2025-05-31. Now all data runs from 2015-01-01 to 2025-05-31.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Asset in China (3199430_INDWW) significantly larger emissions.

## waste,solid-waste-disposal

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

---

PDF: [4.5.0_combined-changelog-climate-trace_2025-07-25.pdf](./4.5.0_combined-changelog-climate-trace_2025-07-25.pdf)

[← V4.X Changelogs](../)
