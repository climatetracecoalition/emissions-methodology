# Sectors

Ten sectors. Each folder holds the full technical methodology and its subsector table.
The complete list of all 68 subsectors is at the bottom of this page.

| Sector | What it covers | Subsectors |
|---|---|---|
| [Agriculture](./agriculture/) | Livestock, rice, fertilizer, soil emissions | 12 |
| [Buildings](./buildings/) | On-site fuel use in homes and commercial buildings | 3 |
| [Fluorinated Gases](./fluorinated-gases/) | Refrigerants and industrial gases | 1 |
| [Forestry and Land Use](./forestry-and-land-use/) | Forest clearing, degradation, fire, removals | 10 |
| [Fossil Fuel Operations](./fossil-fuel-operations/) | Coal, oil, and gas extraction and transport | 6 |
| [Manufacturing](./manufacturing/) | Cement, steel, aluminum, chemicals, paper | 14 |
| [Mineral Extraction](./mineral-extraction/) | Mining and quarrying | 6 |
| [Power](./power/) | Electricity and heat generation | 3 |
| [Transportation](./transportation/) | Road, rail, aviation, shipping | 8 |
| [Waste](./waste/) | Landfills, wastewater, incineration | 5 |

Methods that apply across sectors live in [`2-Cross-Cutting/`](../2-Cross-Cutting/).

---

## All subsectors

Every subsector across all ten sectors. Names match the [data downloads](https://climatetrace.org/data) and the API, so you can go from a row in a CSV straight to the methodology behind it.

| Sector | Subsector | Description | Organization |
|---|---|---|---|
| [Agriculture](./agriculture/) | [`agriculture_crop-residues`](./agriculture/crop-residue-retained-n2o/README.md) | Burning and decomposition of plant material left after harvest | Michigan State University, Dept. of Earth and Environmental Sciences |
| [Agriculture](./agriculture/) | [`agriculture_cropland-fires`](./agriculture/cropland-fires/README.md) | Fires set or occurring on agricultural land | Michigan State University, Dept. of Earth and Environmental Sciences |
| [Agriculture](./agriculture/) | [`agriculture_enteric-fermentation-cattle-operation`](./agriculture/cattle-operations-asset-level/README.md) (asset-level) · [country-level](./agriculture/cattle-operations-country-level/README.md) | Methane from cattle digestion in feedlots and managed operations | WattTime; Earth Genome; Remote Sensing Lab at Saint Louis University |
| [Agriculture](./agriculture/) | [`agriculture_enteric-fermentation-cattle-pasture`](./agriculture/cattle-enteric-fermentation-manure-pasture/README.md) | Methane from cattle digestion on pasture and rangeland | Remote Sensing Lab at Saint Louis University; WattTime |
| [Agriculture](./agriculture/) | [`agriculture_enteric-fermentation-other`](../2-Cross-Cutting/other-sectors/README.md) | Methane from digestion in sheep, goats, buffalo and other livestock | WattTime |
| [Agriculture](./agriculture/) | [`agriculture_manure-applied-to-soils`](./agriculture/manure-application-n2o/README.md) | Emissions from manure spread on fields as fertilizer | Michigan State University, Dept. of Earth and Environmental Sciences |
| [Agriculture](./agriculture/) | [`agriculture_manure-left-on-pasture-cattle`](./agriculture/cattle-enteric-fermentation-manure-pasture/README.md) | Emissions from manure deposited directly by grazing cattle | Remote Sensing Lab at Saint Louis University; WattTime |
| [Agriculture](./agriculture/) | [`agriculture_manure-management-cattle-operation`](./agriculture/cattle-operations-asset-level/README.md) (asset-level) · [country-level](./agriculture/cattle-operations-country-level/README.md) | Emissions from stored and treated manure at cattle operations | WattTime; Earth Genome; Remote Sensing Lab at Saint Louis University |
| [Agriculture](./agriculture/) | [`agriculture_manure-management-other`](../2-Cross-Cutting/other-sectors/README.md) | Emissions from stored and treated manure for other livestock | WattTime |
| [Agriculture](./agriculture/) | [`agriculture_other-agricultural-soil-emissions`](../2-Cross-Cutting/other-sectors/README.md) | Remaining nitrous oxide emissions from managed soils | WattTime |
| [Agriculture](./agriculture/) | [`agriculture_rice-cultivation`](./agriculture/rice-cultivation/README.md) | Methane from flooded rice paddies | Universiti Malaysia Terengganu; Carbon Yield |
| [Agriculture](./agriculture/) | [`agriculture_synthetic-fertilizer-application`](./agriculture/synthetic-fertilizer-n2o/README.md) | Nitrous oxide from manufactured fertilizer applied to cropland | Michigan State University, Dept. of Earth and Environmental Sciences |
| [Buildings](./buildings/) | [`buildings_non-residential-onsite-fuel-usage`](./buildings/onsite-building-emissions/README.md) | Fuel burned on site in commercial, institutional and public buildings | Duke University, Nicholas Institute for Energy, Environment & Sustainability and Dept. of Electrical & Computer Engineering; University of Missouri, Dept. of Electrical Engineering and Computer Science |
| [Buildings](./buildings/) | [`buildings_other-onsite-fuel-usage`](../2-Cross-Cutting/other-sectors/README.md) | On-site fuel use in buildings not classified as residential or commercial | WattTime |
| [Buildings](./buildings/) | [`buildings_residential-onsite-fuel-usage`](./buildings/onsite-building-emissions/README.md) | Fuel burned on site in homes for heating, hot water and cooking | Duke University, Nicholas Institute for Energy, Environment & Sustainability and Dept. of Electrical & Computer Engineering; University of Missouri, Dept. of Electrical Engineering and Computer Science |
| [Fluorinated Gases](./fluorinated-gases/) | [`fluorinated-gases_fluorinated-gases`](../2-Cross-Cutting/other-sectors/README.md) | Refrigerants and industrial gases with very high warming potential | WattTime |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_forest-land-clearing`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Forestry%20and%20Land%20Use%20Change/Net%20Forest%20and%20Mangrove%20Net%20Grassland%20and%20Net%20Wetland%20Carbon%20Stock%20Change%20-%20Living%20Biomass-LULUCFSector-112025.docx.pdf) | Emissions from forest converted to other land uses | CTrees |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_forest-land-degradation`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Forestry%20and%20Land%20Use%20Change/Net%20Forest%20and%20Mangrove%20Net%20Grassland%20and%20Net%20Wetland%20Carbon%20Stock%20Change%20-%20Living%20Biomass-LULUCFSector-112025.docx.pdf) | Emissions from forest that loses biomass without being cleared | CTrees |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_forest-land-fires`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Forestry%20and%20Land%20Use%20Change/Net%20Forest%20and%20Mangrove%20Net%20Grassland%20and%20Net%20Wetland%20Carbon%20Stock%20Change%20-%20Living%20Biomass-LULUCFSector-112025.docx.pdf) | Emissions from fires burning in forested land | CTrees |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_net-forest-land`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Forestry%20and%20Land%20Use%20Change/Net%20Forest%20and%20Mangrove%20Net%20Grassland%20and%20Net%20Wetland%20Carbon%20Stock%20Change%20-%20Living%20Biomass-LULUCFSector-112025.docx.pdf) | Net balance of emissions and removals on land remaining forest | CTrees |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_net-shrubgrass`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Forestry%20and%20Land%20Use%20Change/Net%20Forest%20and%20Mangrove%20Net%20Grassland%20and%20Net%20Wetland%20Carbon%20Stock%20Change%20-%20Living%20Biomass-LULUCFSector-112025.docx.pdf) | Net balance of emissions and removals on shrubland and grassland | CTrees |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_net-wetland`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Forestry%20and%20Land%20Use%20Change/Net%20Forest%20and%20Mangrove%20Net%20Grassland%20and%20Net%20Wetland%20Carbon%20Stock%20Change%20-%20Living%20Biomass-LULUCFSector-112025.docx.pdf) | Net balance of emissions and removals on wetlands | CTrees |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_removals`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Forestry%20and%20Land%20Use%20Change/Net%20Forest%20and%20Mangrove%20Net%20Grassland%20and%20Net%20Wetland%20Carbon%20Stock%20Change%20-%20Living%20Biomass-LULUCFSector-112025.docx.pdf) | Carbon drawn out of the atmosphere and stored in vegetation and soil | CTrees |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_shrubgrass-fires`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Forestry%20and%20Land%20Use%20Change/Net%20Forest%20and%20Mangrove%20Net%20Grassland%20and%20Net%20Wetland%20Carbon%20Stock%20Change%20-%20Living%20Biomass-LULUCFSector-112025.docx.pdf) | Emissions from fires on shrubland and grassland | CTrees |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_water-reservoirs`](./forestry-and-land-use/reservoirs/README.md) | Methane and carbon dioxide from artificial reservoirs | The Johns Hopkins University Applied Physics Laboratory; WattTime |
| [Forestry and Land Use](./forestry-and-land-use/) | [`forestry-and-land-use_wetland-fires`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Forestry%20and%20Land%20Use%20Change/Net%20Forest%20and%20Mangrove%20Net%20Grassland%20and%20Net%20Wetland%20Carbon%20Stock%20Change%20-%20Living%20Biomass-LULUCFSector-112025.docx.pdf) | Emissions from fires burning in wetlands, including peat | CTrees |
| [Fossil Fuel Operations](./fossil-fuel-operations/) | [`fossil-fuel-operations_coal-mining`](./fossil-fuel-operations/coal-mining/README.md) | Methane released from underground and surface coal mines | WattTime; Global Energy Monitor |
| [Fossil Fuel Operations](./fossil-fuel-operations/) | [`fossil-fuel-operations_oil-and-gas-production`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Fossil%20Fuel%20Operations/Oil%20and%20Gas%20Production%20and%20Transport-FossilFuelOperationsSector-05272026.docx.pdf) | Emissions and leaks from extracting oil and gas at the wellhead | RMI |
| [Fossil Fuel Operations](./fossil-fuel-operations/) | [`fossil-fuel-operations_oil-and-gas-refining`](./fossil-fuel-operations/oil-and-gas-refining/README.md) | Emissions from processing crude oil into finished products | RMI |
| [Fossil Fuel Operations](./fossil-fuel-operations/) | [`fossil-fuel-operations_oil-and-gas-transport`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Fossil%20Fuel%20Operations/Oil%20and%20Gas%20Production%20and%20Transport-FossilFuelOperationsSector-05272026.docx.pdf) | Emissions and leaks from pipelines, tankers and storage | RMI |
| [Fossil Fuel Operations](./fossil-fuel-operations/) | [`fossil-fuel-operations_other-fossil-fuel-operations`](../2-Cross-Cutting/other-sectors/README.md) | Remaining fossil fuel activity not covered by the categories above | WattTime |
| [Fossil Fuel Operations](./fossil-fuel-operations/) | [`fossil-fuel-operations_other-solid-fuels`](../2-Cross-Cutting/other-sectors/README.md) | Production and handling of solid fuels other than coal | WattTime |
| [Manufacturing](./manufacturing/) | [`manufacturing_aluminum`](./manufacturing/aluminum-production/README.md) | Smelting and refining of aluminum | TransitionZero |
| [Manufacturing](./manufacturing/) | [`manufacturing_cement`](./manufacturing/cement-manufacturing/README.md) | Clinker production, including CO2 released chemically from limestone | TransitionZero |
| [Manufacturing](./manufacturing/) | [`manufacturing_chemicals`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Manufacturing%20and%20Industrial%20Processes/Chemicals%20and%20Pulp-Paper%20Emissions-ManufacturingandIndustrialProcessesSector-112025.docx.pdf) | Production of industrial chemicals | TransitionZero |
| [Manufacturing](./manufacturing/) | [`manufacturing_food-beverage-tobacco`](../2-Cross-Cutting/other-sectors/README.md) | Processing of food, drink and tobacco products | WattTime |
| [Manufacturing](./manufacturing/) | [`manufacturing_glass`](../2-Cross-Cutting/other-sectors/README.md) | Melting and forming of glass | WattTime |
| [Manufacturing](./manufacturing/) | [`manufacturing_iron-and-steel`](./manufacturing/iron-and-steel-manufacturing/README.md) | Blast furnaces, electric arc furnaces and steelmaking | TransitionZero |
| [Manufacturing](./manufacturing/) | [`manufacturing_lime`](../2-Cross-Cutting/other-sectors/README.md) | Calcination of limestone to produce lime | WattTime |
| [Manufacturing](./manufacturing/) | [`manufacturing_other-chemicals`](../2-Cross-Cutting/other-sectors/README.md) | Chemical production not covered by a dedicated category | WattTime |
| [Manufacturing](./manufacturing/) | [`manufacturing_other-manufacturing`](../2-Cross-Cutting/other-sectors/README.md) | Remaining industrial production | WattTime |
| [Manufacturing](./manufacturing/) | [`manufacturing_other-metals`](../2-Cross-Cutting/other-sectors/README.md) | Production of metals other than iron, steel and aluminum | WattTime |
| [Manufacturing](./manufacturing/) | [`manufacturing_petrochemical-steam-cracking`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Manufacturing%20and%20Industrial%20Processes/Petrochemical%20Steam%20Cracker%20Emissions-ManufacturingandIndustrialProcessesSector-072426.docx.pdf) | Cracking of hydrocarbons to produce ethylene and related products | RMI |
| [Manufacturing](./manufacturing/) | [`manufacturing_pulp-and-paper`](./manufacturing/pulp-and-paper/README.md) | Pulping, paper making and the heat used in both | TransitionZero |
| [Manufacturing](./manufacturing/) | [`manufacturing_textiles-leather-apparel`](../2-Cross-Cutting/other-sectors/README.md) | Textile, leather and garment production | WattTime |
| [Manufacturing](./manufacturing/) | [`manufacturing_wood-and-wood-products`](../2-Cross-Cutting/other-sectors/README.md) | Sawmilling and wood product manufacturing | WattTime |
| [Mineral Extraction](./mineral-extraction/) | [`mineral-extraction_bauxite-mining`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Mineral%20Extraction/Mining%20and%20Quarrying%20Emissions%20from%20Copper%2C%20Iron%2C%20Bauxite%2C%20Rock%20and%20Sand-MineralExtractionSector-11025.docx.pdf) | Extraction of bauxite ore for aluminum production | WattTime |
| [Mineral Extraction](./mineral-extraction/) | [`mineral-extraction_copper-mining`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Mineral%20Extraction/Mining%20and%20Quarrying%20Emissions%20from%20Copper%2C%20Iron%2C%20Bauxite%2C%20Rock%20and%20Sand-MineralExtractionSector-11025.docx.pdf) | Extraction and initial processing of copper ore | WattTime |
| [Mineral Extraction](./mineral-extraction/) | [`mineral-extraction_iron-mining`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Mineral%20Extraction/Mining%20and%20Quarrying%20Emissions%20from%20Copper%2C%20Iron%2C%20Bauxite%2C%20Rock%20and%20Sand-MineralExtractionSector-11025.docx.pdf) | Extraction and initial processing of iron ore | WattTime |
| [Mineral Extraction](./mineral-extraction/) | [`mineral-extraction_other-mining-quarrying`](../2-Cross-Cutting/other-sectors/README.md) | Mining and quarrying not covered by a dedicated category | WattTime |
| [Mineral Extraction](./mineral-extraction/) | [`mineral-extraction_rock-quarrying`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Mineral%20Extraction/Mining%20and%20Quarrying%20Emissions%20from%20Copper%2C%20Iron%2C%20Bauxite%2C%20Rock%20and%20Sand-MineralExtractionSector-11025.docx.pdf) | Extraction of stone and aggregate | WattTime |
| [Mineral Extraction](./mineral-extraction/) | [`mineral-extraction_sand-quarrying`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Mineral%20Extraction/Mining%20and%20Quarrying%20Emissions%20from%20Copper%2C%20Iron%2C%20Bauxite%2C%20Rock%20and%20Sand-MineralExtractionSector-11025.docx.pdf) | Extraction of sand and gravel | WattTime |
| [Power](./power/) | [`power_electricity-generation`](./power/electricity-generation/README.md) | Power plants generating electricity for the grid | WattTime |
| [Power](./power/) | [`power_heat-plants`](./power/heat-plants/README.md) | Plants producing heat for district heating and industry | WattTime |
| [Power](./power/) | [`power_other-energy-use`](../2-Cross-Cutting/other-sectors/README.md) | Remaining energy industry own-use and fuel conversion | WattTime |
| [Transportation](./transportation/) | [`transportation_domestic-aviation`](./transportation/domestic-and-international-aviation/README.md) | Flights beginning and ending within the same country | WattTime |
| [Transportation](./transportation/) | [`transportation_domestic-shipping`](./transportation/domestic-and-international-shipping/README.md) | Vessel movements within a single country's waters | OceanMind; Global Fishing Watch |
| [Transportation](./transportation/) | [`transportation_international-aviation`](./transportation/domestic-and-international-aviation/README.md) | Flights between countries | WattTime |
| [Transportation](./transportation/) | [`transportation_international-shipping`](./transportation/domestic-and-international-shipping/README.md) | Vessel movements between countries | OceanMind; Global Fishing Watch |
| [Transportation](./transportation/) | [`transportation_non-broadcasting-vessels`](./transportation/non-broadcasting-vessels/README.md) | Ships not transmitting AIS transponder data, estimated by other means | Global Fishing Watch |
| [Transportation](./transportation/) | [`transportation_other-transport`](../2-Cross-Cutting/other-sectors/README.md) | Remaining transport not covered by the categories above | WattTime |
| [Transportation](./transportation/) | [`transportation_railways`](../2-Cross-Cutting/other-sectors/README.md) | Freight and passenger rail | WattTime |
| [Transportation](./transportation/) | [`transportation_road-transportation`](https://github.com/climatetracecoalition/methodology-documents/blob/main/2025/Transportation/Global%20Road%20Emissions-TransportationSector-112025.pdf) | Cars, trucks, buses and motorcycles | The Johns Hopkins University Applied Physics Laboratory |
| [Waste](./waste/) | [`waste_biological-treatment-of-solid-waste-and-biogenic`](../2-Cross-Cutting/other-sectors/README.md) | Composting and anaerobic digestion of organic waste | WattTime |
| [Waste](./waste/) | [`waste_domestic-wastewater-treatment-and-discharge`](./waste/wastewater-treatment-plants/README.md) | Treatment and discharge of household sewage | The Johns Hopkins University Applied Physics Laboratory |
| [Waste](./waste/) | [`waste_incineration-and-open-burning-of-waste`](../2-Cross-Cutting/other-sectors/README.md) | Waste burned in facilities or in the open | WattTime |
| [Waste](./waste/) | [`waste_industrial-wastewater-treatment-and-discharge`](./waste/wastewater-treatment-plants/README.md) | Treatment and discharge of industrial effluent | The Johns Hopkins University Applied Physics Laboratory |
| [Waste](./waste/) | [`waste_solid-waste-disposal`](./waste/solid-waste-disposal/README.md) | Methane from landfills and dumps | RMI |

---

[← Home](../)
