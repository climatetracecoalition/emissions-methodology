# [5.4.1] -  2026-03-02

## ClimateTRACE,deprecation-warning

-   None this release.

## ClimateTRACE,multiple-sectors,post-processing

### Added

### Changed

### Deprecated

### Fixed

- [Fixed] Oil-and-gas-transport asset data were updated to include December 2025 asset data. 2025 country-, gadm-, and city-level data reflect these updates.

### Known Issues

- [Known Issue] Still present from V5.4.0: iron-and-steel assets were incorrectly extrapolated forward rather than being set to a “closed” state with 0 emissions. Affected asset IDs are: 1566424, 1566477, 1566542, 1566555, 1566559, 1566564, 1566578, 1566580, 1566620, 1566648, 1566669, 1566770, 1566825, 1566949, 1566965, 1567083, 1567106, 1567145, 1567184, 1567187, 1567226, 1567250, 1567255, 1567256, 1567257, 1567259, 1567263, 1567268, 1567271, 1567273, 1567274, 1567275, 1567280, 1567281, 1567282, 1567285, 1567286, 1567290, 1567291, 1567292, 1567294, 1567295, 1567296, 1567297, 1567299, 1567300, 1567301, 1567303, 1567305, 1567312, 1567313, 1567314, 1567315, 1567316, 1567317, 1567318, 1567319, 1567320, 1567321, 1567322, 1567323, 1567324, 1567325, 1567326, 1567327, 32441205, 32441208, 32441223, 32441224, 32441229, 32441253, 38089228, 42741547, 42741574, 42741753, 42741756, 42741765, 42741804, 42741864, 42741875.

- [Known Issue] Still present from V5.4.0: Two domestic-wastewater-treatment-and-discharge assets were assigned the wrong ISO-3 country code: 48250739 and 48251021 were incorrectly tagged to CAF and COD rather than SLB and UGA, respectively.

- [Known Issue] Still present from V5.4.0: Some city emissions data have multiple rows for a given timestamp in the data downloads packages for individual gases (co2, ch4, n2o).

- [Known Issue] non-broadcasting-vessels CO2e_100yr and CO2e_20yr emissions are doubled for only January in the GADM emissions data.

---

PDF: [5.4.1_combined-changelog-climate-trace.docx.pdf](./5.4.1_combined-changelog-climate-trace.docx.pdf) · Source: [methodology-documents/2026/CHANGELOG/02_Feb_V5.4.1/5.4.1_combined-changelog-climate-trace.docx.pdf](https://github.com/climatetracecoalition/methodology-documents/blob/main/2026/CHANGELOG/02_Feb_V5.4.1/5.4.1_combined-changelog-climate-trace.docx.pdf)

[← V5.X Changelogs](../)
