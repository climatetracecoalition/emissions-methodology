# [5.0.0] - 2025-11-11

## ClimateTRACE,multiple-sectors,general:

- [Added] All methodologies have been updated to reflect v4.8.0 sector updates.

- [Added] Methodology files and sector names have been updated.

## ClimateTRACE,multiple-sectors,post-processing:

### Added

- [Added] Emissions-reducing solutions (ERS) and their resultant reduction potentials have been added for all assets in all subsectors. ERS is based on v4.8.0 emissions data release. Reference each sector’s and “Data informed disaggregation and Implicit Estimation in Other Sectors” methodologies for more information on ERS application.

### Deprecated

### Fixed

### Known Issues

- [Known Issues] Metadata for gadm and city aggregations is missing for sub-sectors that are disaggregations of country values: fluorinated-gases, other-solid-fuel, other-mining-quarrying, wood-and-wood-products, other-fossil-fuel-operations, other-onsite-fuel-usage, other-energy-use, other-transport, railways, other-agricultural-soil-emissions, enteric-fermentation-other, manure-management-other, incineration-and-open-burning-of-waste, biological-treatment-of-solid-waste-and-biogenic.

- [Known Issues] oil-and-gas-production sector - country-level estimates are inflated for IDN, SEN, and USA by 10%, 200%, and 2% respectively.

- [Known Issues] oil-and-gas-production sector - a forward-filling error in one of two data sources used for U.S. production resulted in missing or near-zero values for 2025, causing an emissions drop, most notably in U.S. assets.

- [Known Issues] solid-waste-disposal country, GADM, and city aggregations for 2025 are inflated by approximately 50%.

- [Known Issues] coal-mining ERS “Capture and route fugitive methane in underground mines” has been erroneously crosswalked to surface mines, and “Capture and route fugitive methane in surface mines” has been erroneously crosswalked to underground mines. In addition, the “abatement potential” (which includes the applicability factor) from the IEA Global Methane Tracker documentation was not applied as intended, leading to underestimation of CH4 reduction potential.

- [Known Issues] solid-waste-disposal minor error in landfill diversion ERS, which slightly underestimates ERS effectiveness for lower-middle income countries (including Indonesia) and slightly overestimates effectiveness for low income countries.

---

PDF: [5.0.0_combined-changelog-climate-trace.pdf](./5.0.0_combined-changelog-climate-trace.pdf)

[← V5.X Changelogs](../)
