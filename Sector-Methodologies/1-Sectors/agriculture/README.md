# Agriculture

Livestock, rice, fertilizer, and soil emissions, estimated from satellite imagery, herd data, and process models.

| | |
|---|---|
| **Full methodology** | pdf and readme provided |
| **Subsectors covered** | 12 |
| **See the data** | [Explore on the map](https://climatetrace.org/explore#admin=&gas=co2e&year=2025&timeframe=100&sector=agriculture&asset=) |

## Subsectors

Subsector names below are the same ones used in the [data downloads](https://climatetrace.org/data)
and the API. Each links to the methodology that documents it.

Where a subsector is covered by more than one methodology (e.g. an asset-level model and a
country-level model), the **Methodology** column lists each one separately rather than picking
just one link — that's the case for the two cattle-operation subsectors below.

| Subsector | Description | Methodology | Organization |
|---|---|---|---|
| `crop-residues` | Burning and decomposition of plant material left after harvest | [View methodology](./crop-residue-retained-n2o/README.md) | Michigan State University, Dept. of Earth and Environmental Sciences |
| `cropland-fires` | Fires set or occurring on agricultural land | [View methodology](./cropland-fires/README.md) | Michigan State University, Dept. of Earth and Environmental Sciences |
| `enteric-fermentation-cattle-operation` | Methane from cattle digestion in feedlots and managed operations | [View Asset-level methodology](./cattle-operations-asset-level/README.md) · [View Country-level methodology](./cattle-operations-country-level/README.md) | WattTime; Earth Genome; Remote Sensing Lab at Saint Louis University |
| `enteric-fermentation-cattle-pasture` | Methane from cattle digestion on pasture and rangeland | [View methodology](./cattle-enteric-fermentation-manure-pasture/README.md) | Remote Sensing Lab at Saint Louis University; WattTime |
| `enteric-fermentation-other` | Methane from digestion in sheep, goats, buffalo and other livestock | [View methodology](../../2-Cross-Cutting/other-sectors/README.md) | WattTime |
| `manure-applied-to-soils` | Emissions from manure spread on fields as fertilizer | [View methodology](./manure-application-n2o/README.md) | Michigan State University, Dept. of Earth and Environmental Sciences |
| `manure-left-on-pasture-cattle` | Emissions from manure deposited directly by grazing cattle | [View methodology](./cattle-enteric-fermentation-manure-pasture/README.md) | Remote Sensing Lab at Saint Louis University; WattTime |
| `manure-management-cattle-operation` | Emissions from stored and treated manure at cattle operations | [View Asset-level methodology](./cattle-operations-asset-level/README.md) · [View Country-level methodology](./cattle-operations-country-level/README.md) | WattTime; Earth Genome; Remote Sensing Lab at Saint Louis University |
| `manure-management-other` | Emissions from stored and treated manure for other livestock | [View methodology](../../2-Cross-Cutting/other-sectors/README.md) | WattTime |
| `other-agricultural-soil-emissions` | Remaining nitrous oxide emissions from managed soils | [View methodology](../../2-Cross-Cutting/other-sectors/README.md) | WattTime |
| `rice-cultivation` | Methane from flooded rice paddies | [View methodology](./rice-cultivation/README.md) | Universiti Malaysia Terengganu; Carbon Yield |
| `synthetic-fertilizer-application` | Nitrous oxide from manufactured fertilizer applied to cropland | [View methodology](./synthetic-fertilizer-n2o/README.md) | Michigan State University, Dept. of Earth and Environmental Sciences |

Subsectors marked *Other Sectors* have no dedicated model. They are estimated by
[data-informed disaggregation or implicit estimation](../../2-Cross-Cutting/other-sectors/).

---

[← All sectors](../) · [FAQ](https://climatetrace.org/faqs) · [Report an error](https://climatetrace.org/contact)
