# [4.6.0] - 2025-08-21

## ClimateTRACE,multiple-sectors,post-processing:

### Added

### Changed

- [Changed] The method for quantifying non-GHG emissions from the following sectors was improved to include fractional contribution from fuel combustion and other direct sources: lime, glass, cement.

- [Changed] All subsectors for which the Data Informed Emissions Disaggregation and Implicit Estimation methods are used for quantifying country-level emissions using CEDS and/or FAOSTAT data have been updated to the most recent version of both dataset (CEDS v_2025_03_18 and FAOSTAT v_2025_11_14). Emissions for the following subsectors were affected by updates to CEDS: food-beverage-tobacco, lime, other-chemicals, other-manufacturing, other-metals, other-mining-quarrying, wood-and-wood-products. Emissions for the following subsectors were affected by updates to FAOSTAT: enteric-fermentation-other, manure-left-on-pasture-other, manure-management-other, other-agricultural-soil-emissions

### Deprecated

### Fixed

### Known Issues

- [Known Issue] Some iso3 country mismatch corrections for assets were reverted from previous releases, leading to minor differences in country totals vs sum of GADM emissions within the affected countries.

- [Known Issue] Negative emissions not exceeding 2.1 tonnes CO2e_100yr for YEM in sand-quarrying and PHL, TWN for other-mining-quarrying, related to outdated data and artifacts from implicit estimation methods. To be fixed in V4.7.0.

## ClimateTRACE,individual-changelogs:

## agriculture,crop-residues

### Added

- [Added] Added crop-residue N2O, updated emission with refined country-scale emission factors. This data includes all gridded and country-scale, both annual and monthly time-scales from 2015 to 2024. Overall, emissions will change due to model updates.

### Changed

- [Changed] methodology edited to include updates to emissions factors: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/A griculture/Agriculture%20sector-Emissions%20from%20Synthetic%20Fertilizer%2C%20 Crop%20Residue%2C%20and%20Manure%20Application%20Methodology.pdf

### Deprecated

### Fixed

### Known Issues

## agriculture,manure-applied-to-soils

### Added

- [Added] Added manure applied to soil N2O, updated emission with refined country-scale emission factors. This data includes all gridded and country-scale, both annual and monthly time-scales from 2015 to 2024. Overall, emissions will slightly decrease.

### Changed

- [Changed] methodology edited to include updates to emissions factors: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/A griculture/Agriculture%20sector-Emissions%20from%20Synthetic%20Fertilizer%2C%20 Crop%20Residue%2C%20and%20Manure%20Application%20Methodology.pdf

### Deprecated

### Fixed

## agriculture,rice-cultivation

### Added

- [Added] 2024 asset level emissions data for Peru.

- [Added] updates to the emissions factors for new countries.

### Changed

### Deprecated

### Fixed

## agriculture,synthetic-fertilizer-application

### Added

- [Added] Added synthetic fertilizer N2O, updated emission with refined country-scale emission factors. This data includes all gridded and country-scale, both annual and monthly time-scales from 2015 to 2024.  Overall, emissions will slightly decrease.

### Changed

- [Changed] methodology edited to include updates to emissions factors: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/A griculture/Agriculture%20sector-Emissions%20from%20Synthetic%20Fertilizer%2C%20 Crop%20Residue%2C%20and%20Manure%20Application%20Methodology.pdf

### Deprecated

### Fixed

### Known Issues

## fossil-fuel-operations,oil-and-gas-production

### Added

- [Added] Data period calculated for all sources to the end of July 2025.

- [Added] ZNC country code for country file.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Electrical grid mix accounting is currently missing from model.

## fossil-fuel-operations,oil-and-gas-refining

### Added

- [Added] Data period extended for existing assets in North America and Europe. Start_date 2024-10-01 to end_date 2024-12-31.

### Changed

- [Changed] Updated #789 all Q3 2024 results, including asset, country, and uncertainty, as the sole refinery in Serbia has more granular capacity factor data available now.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Current estimates of capacity factors for Chinese refineries will be improved in the future releases as more granular and accurate data sources have become available.

## fossil-fuel-operations,oil-and-gas-transport

### Added

- [Added] Data period calculated for all sources to the end of July 2025.

- [Added] ZNC country code for country file.

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Electrical grid mix accounting is currently missing from model.

## manufacturing,aluminum

### Added

- [Added] Data period extended for existing sources. Start_date 2025-05-01 to end_date 2025-05-31.

### Changed

### Deprecated

### Fixed

### Known Issues

## manufacturing,cement

### Added

- [Added] Data period extended for existing sources. Start_date 2025-05-01 to end_date 2025-05-31.

### Changed

- [Changed] Updated metadata (emissions factors): Ground Granulated Blast Furnace Slag (GGBS) cement clinker ratio reduced to 50% to be more realistic across all monitored geographies; fuel emissions reduced to 0.59 for wet process and increased to 0.39 for semidry. Link to updated methodology: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/M anufacturing%20and%20Industrial%20Processes/Manufacturing%20and%20Industrial%20 Processes%20sector-Cement%20Manufacturing%20Emissions.docx.pdf

- [Changed] Historical rerun to reflect impact of changed emissions factors above. Start_date 2021-01-01 to end_date 2025-04-30.

### Deprecated

### Fixed

### Known Issues

## manufacturing,petrochemical-steam-cracking

### Added

- [Added] Data period extended for existing sources in North America and Europe. Start_date 2024-10-01 to end_date 2024-12-31.

### Changed

### Deprecated

### Fixed

-[Fixed] Fixed error with capacity for some assets due to incorrectly translating from annual to monthly.

### Known Issues

## manufacturing,iron-and-steel

### Added

- [Added] Added production and CO2 emissions estimates for steel assets for May 2025.

- [Added] Included the percentage of scrap input for EAF and DRI-EAF technologies (noted in the “other7” column in asset downloads).

- [Added] Integrated the new GEM steel asset tracker, increasing the number of monitored assets from 832 to 888.

### Changed

- [Changed] Improved the estimation of direct CO2 emissions for EAF and DRI-EAF routes by incorporating scrap and feedstock percentage data. This adjustment led to a slight increase in estimated emissions for those technologies. See https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/M anufacturing%20and%20Industrial%20Processes/Manufacturing%20and%20Industrial%20 Processes%20sector-Iron%20%26%20Steel%20Manufacturing%20Emissions.docx.pdf

- [Changed] Expanded the number of satellite-monitored assets from 334 to 362. The number of BF/BOF was increased from 262 to 313.

### Deprecated

### Fixed

- [Fixed] Corrected an issue in February 2025 where a sudden increase in asset count caused an artificial spike in the average emissions factor. The updated methodology now accounts for the corrected number of assets.

### Known Issues

## manufacturing,glass

### Added

- [Added] Updated content in “Data informed disaggregation and Implicit Estimation in Other Sectors” Methodology, see: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/O ther%20Sectors/Other%20Sectors-Data%20informed%20disaggregation%20and%20Implici t%20Estimation%20in%20Other%20Sectors.pdf

### Changed

- [Changed] Updated CEDS to version v_2025_03_18.

- [Changed] Updated EDGAR to version EDGAR_2024_GHG.

- [Changed] Removed forward projection of external inventory data. The final reported year is now the final year of CEDS (2023).

### Deprecated

### Fixed

- [Fixed] Fixed bug that inflated asset-level activity and deflated emissions factors. Summing asset-level activity is now less than or equal to country total activity.

### Known Issues

## manufacturing,lime

### Added

- [Added] Updated content in “Data informed disaggregation and Implicit Estimation in Other Sectors” Methodology, see: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/O ther%20Sectors/Other%20Sectors-Data%20informed%20disaggregation%20and%20Implici t%20Estimation%20in%20Other%20Sectors.pdf

### Changed

- [Changed] Updated CEDS to version v_2025_03_18.

- [Changed] Removed forward projection of external inventory data. The final reported year is now the final year of CEDS (2023).

### Deprecated

### Fixed

- [Fixed] Fixed bug that inflated asset-level activity and deflated emissions factors. Summing asset-level activity is now less than or equal to country total activity.

### Known Issues

## manufacturing,food-beverage-tobacco

### Added

- [Added] Updated content in “Data informed disaggregation and Implicit Estimation in Other Sectors” Methodology, see: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/O ther%20Sectors/Other%20Sectors-Data%20informed%20disaggregation%20and%20Implici t%20Estimation%20in%20Other%20Sectors.pdf

### Changed

- [Changed] Updated CEDS to version v_2025_03_18.

- [Changed] Removed forward projection of external inventory data. The final reported year is now the final year of CEDS (2023).

### Deprecated

### Fixed

- [Fixed] Fixed bug that was excluding combustion emissions from country totals.

- [Fixed] Fixed bug that inflated asset-level activity and deflated emissions factors. Summing asset-level activity is now less than or equal to country total activity.

### Known Issues

## manufacturing,textiles-leather-apparel

### Added

- [Added] Updated content in “Data informed disaggregation and Implicit Estimation in Other Sectors” Methodology, see: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/O ther%20Sectors/Other%20Sectors-Data%20informed%20disaggregation%20and%20Implici t%20Estimation%20in%20Other%20Sectors.pdf

### Changed

- [Changed] Updated CEDS to version v_2025_03_18.

- [Changed] Removed forward projection of external inventory data. The final reported year is now the final year of CEDS (2023).

### Deprecated

### Fixed

- [Fixed] Fixed bug that inflated asset-level activity and deflated emissions factors. Summing asset-level activity is now less than or equal to country total activity.

### Known Issues

## power,electricity-generation

### Added

- [Added] Data period extended for existing sources. Asset-level start_date 2019-01-01 to end_date 2025-06-30; country-level start_date 2015-01-01 to end_date 2025-06-30.

### Changed

- [Changed] Fixed a few plant/unit level information. These can reflect changes in our estimates.

- [Changed] Database and underlying improvements for source generation data. See methodology: https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/P ower/Power%20sector-Emissions%20from%20Electricity%20Generation.docx.pdf

- [Changed] For the subset of plants in USA, BRA, ESP, NLD, POL, BEL, FIN, AUT, ITA, DEU that pass a set of validation checks, we report the activity based on reported generation data (CAMD, ENTSO-E, and ONS.

### Fixed

### Known Issues

- [Known Issues] For non-operational plants the data is reported as zero values for capacity, capacity factor, activity, emissions intensity, and emissions. The related uncertainties are also reported as zero. This is not strictly correct since there can be uncertainty in the operating status in a given month. Future work will better quantify the uncertainty when the plant is reported as non-operational.

## transportation,domestic-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-06-30.

### Changed

### Fixed

## transportation,domestic-shipping

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] Duplicated ports identified : Furna vs Fuma.

## transportation,international-aviation

### Added

- [Added] Data period extended for existing sources. Start_date 2015-01-01 to end_date 2025-06-30.

### Changed

### Fixed

## transportation,international-shipping

### Added

### Changed

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Invalid transmissions can cause interpolation of trips over extended data gaps which may result in large erroneous emissions spikes at a port at the time when the data gap ends.

- [Known Issues] Duplicated ports identified : Furna vs Fuma.

## transportation,road-transportation

### Added

- [Added] Data period extended for existing sources. New end_date 2025-05-31.

### Changed

- [Changed] Updated data due to revised emission factors from 2023-01-01 on.

- [Changed] Updated uncertainties to reflect updated data.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Have not updated to the latest Climate TRACE patch of Global Administrative Areas (GADM) data (v1.1.2).

## waste,domestic-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-06-01 to end_date 2025-06-30. Now all data runs from 2015-01-01 to 2025-06-30.

### Fixed

### Known Issues

## waste,industrial-wastewater-treatment-and-discharge

### Added

- [Added] Data period extended for existing sources. Start_date 2025-06-01 to end_date 2025-06-30. Now all data runs from 2015-01-01 to 2025-06-30.

### Fixed

### Known Issues

- [Known Issues] Asset in China (3199430_INDWW) potentially producing significantly larger emissions.

---

PDF: [4.6.0_combined-changelog-climate-trace_2025-08-21.docx.pdf](./4.6.0_combined-changelog-climate-trace_2025-08-21.docx.pdf) · Source: [methodology-documents/2025/CHANGELOG/08_Aug_V4.6.0/4.6.0_combined-changelog-climate-trace_2025-08-21.docx.pdf](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/CHANGELOG/08_Aug_V4.6.0/4.6.0_combined-changelog-climate-trace_2025-08-21.docx.pdf)

[← V4.X Changelogs](../)
