# GNESTE: The Global and National Energy Systems Techno-Economic Database

The goal of GNESTE is to develop a comprehensive database of cost and performance data for key electricity generation and storage technologies:	
* Coal Power
* Gas Power
* Hydro Power
* Nuclear Power
* Solar Power
* Wind Power
* Battery Energy Storage Systems

Data are collected on:	
* Capital Cost
* Fixed O&M Cost
* Variable O&M Cost
* Total O&M Cost
* Fuel Price
* Efficiency
* Construction Time
* Operating Lifetime
* Cost of Capital
	
The GNESTE database is documented in a paper published in the [Data in Brief journal](https://doi.org/10.1016/j.dib.2024.110669).  That article details the process for collecting data, defines all variables and categories of data, and gives examples of its usage. 

The original data published with that article are available in Excel format from [Zenodo](https://zenodo.org/records/11065567).

This repository presents the data in machine-readable CSV format, and expands the database with new sources.

## Repository structure

The GNESTE database covers 33 technology subtypes across seven families.

**GNESTE_Battery_Storage.csv** contains data on battery storage technologies:
- Lead-acid
- Lithium-ion
- Lithium-ion LFP (lithium iron phosphate)
- Lithium-ion NMC (nickel manganese cobalt oxide)
- Sodium-sulphur
- Vanadium Redox-flow

**GNESTE_Coal_Power.csv** contains data on coal-fired power technologies:
- Subcritical
- Supercritical
- Ultrasupercritical
- IGCC (integrated gasification combined cycle)
- Coal CCUS (with carbon capture, utilisation and storage)
- Coal CCUS - Supercritical
- Coal CCUS - Ultrasupercritical
- Lignite
- Lignite - Supercritical
- Lignite CCUS - Supercritical

**GNESTE_Gas_Power.csv** contains data on gas-fired power technologies:

- CCGT (combined cycle gas turbine)
- CCGT CCUS (CCGT with carbon capture, utilisation and storage)
- Gas Boiler
- Gas Engine
- Gas Peaking (plants used to meet peak demand)
- OCGT (open cycle gas turbine)

**GNESTE_Hydro_Power.csv** contains data on hydroelectric power technologies:

- Lock (hydropower at navigation locks)
- Reservoir (conventional storage behind a dam)
- RoR (run-of-river)
- Storage (pumped hydro storage)

**GNESTE_Nuclear_Power.csv** contains data on nuclear power technologies:

- ALWR (advanced light water reactor)
- EPR (European pressurised reactor)
- LWR (light water reactor)
- PHWR (pressurised heavy water reactor)
- PWR (pressurised water reactor)
- SMR (small modular reactor)
- VVER (Russian pressurised water reactor design)

**GNESTE_Solar_Power.csv** contains data on solar power technologies:

- Rooftop
- Fixed Axis (ground-mounted panels at a fixed angle)
- Single Axis Tracking
- Double Axis Tracking

**GNESTE_Wind_Power.csv** contains data on wind power technologies:

- Floating (floating foundation offshore turbines)
- Offshore (fixed bottom offshore turbines)
- Onshore

**Meta_Sources.csv** - Full bibliography of sources used.

## Data format

Each technology CSV has 29 columns.  Each row contains data from one source about one technology, location, and scenario.  Each row can contain one or more observations across different years.

| Column | Definition |
| --- | --- |
| Technology | Either: Battery, Coal, Gas, Hydro, Nuclear, Solar or Wind. |
| ID | Unique row identifier (technology initial and four digits). |
| Continent | Continent covered, or Global if worldwide coverage. |
| Country | Country or region covered if the data are specific, blank if continental or global coverage. |
| ISO2 | Two-letter country code. |
| ISO3 | Three-letter country code. |
| Variable | Name of the parameter measured, described in the table below. |
| Code | Short identifier for the variable. |
| Unit | Units for the data. |
| Category | Technology subtype, as defined above. |
| Source | Short citation, defined in Meta_Sources.csv. |
| Notes | Details on the scenario, case, plant size, method that the data relate to. |
| Currency | Original currency and price year, with the factor used to express monetary values in 2023 USD where recorded. |
| Energy/Power Ratio | For battery energy storage, the discharge duration in hours, calculated as rated energy divided by rated power. |
| 2014–2025 | Historical data for the years 2014 to 2025. |
| 2030, 2040, 2050 | Projected or modelled data for the years 2030 to 2050. |

| Variable | Code | Unit | Definition |
| --- | --- | --- | --- |
| Capital Cost | CAPEX | USD/kW or USD/kWh | Overnight cost of building the plant (excluding cost escalation and interest during construction) normalised by the rated capacity of the plant.  USD/kWh can be used for energy storage. |
| Fixed O&M | OPEX_F | USD/kW/yr or USD/kWh/yr | Operation and maintenance costs which are a function of a plant's capacity, such as labour and insurance. USD/kWh/yr can be used for energy storage.  |
| Variable O&M | OPEX_V | USD/MWh | Operation and maintenance costs which are a function of operating hours (excluding fuel), such as maintenance. |
| Total O&M | OPEX_T | USD/kW/yr or USD/MWh | The sum of variable and fixed operating costs, excluding fuel inputs. |
| Fuel Price | FUEL_PRICE | USD/MWh | Cost of the fuel consumed, relative to the primary energy input (not including plant efficiency). |
| Efficiency | EFFICIENCY | % | The fraction of a fuel's lower heating value converted to net electricity. For batteries and pumped hydro, the fraction of charging energy returned as electricity over a complete round-trip cycle. |
| Construction Time | BUILDTIME | Years | Time to complete the project. Excludes pre-construction stages such as planning and permitting. |
| Lifetime | LIFETIME | Years | Time a plant is expected to operate, excluding end-of-life extensions. |
| Cost of Capital | WACC | % | Weighted average cost of capital used for discounting, in real terms, reflecting the split between equity and debt investments.  |


## Citation

Please cite this article when you use the GNESTE database:

L. Hatton, N. Johnson, L. Dixon, B. Mosongo, S. De Kock, A. Marquard, M. Howells, and I. Staffell (2024).  The Global and National Energy Systems Techno-Economic (GNESTE) Database: Cost and performance data for electricity generation and storage technologies.  Data in Brief.  [DOI:10.1016/j.dib.2024.110669](https://doi.org/10.1016/j.dib.2024.110669)


## License

[Creative Commons CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)
	
## Contact

Luke Hatton <[l.hatton23@imperial.ac.uk](mailto:l.hatton23@imperial.ac.uk?subject=GNESTE)>

Nathan Johnson <[nathan.johnson17@imperial.ac.uk](mailto:nathan.johnson17@imperial.ac.uk?subject=GNESTE)>

Iain Staffell <[i.staffell@imperial.ac.uk](mailto:i.staffell@imperial.ac.uk?subject=GNESTE)>
