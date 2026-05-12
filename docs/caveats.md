# Caveats

A single canonical place for the limitations of this analysis. Update as new datasets are added.

---

## Data scope

- Generation mix is **domestic generation**, not consumption. Imports and exports are not netted out.
- Carbon intensity here is **power-sector only**, not economy-wide.
- Household prices are **retail, all taxes and levies included** — they include VAT, network costs, levies and policy choices that are not generation costs.
- Yearly national averages are coarse. They cannot speak to short-term price spikes, hour-by-hour mix changes, or grid stability.

---

## Period alignment

- Ember generation is yearly; Eurostat prices are half-yearly. Joins map a Eurostat half-year to its calendar year.
- The latest common period across all six countries can be shorter than each country's individual latest period. Use the shorter window for cross-country comparisons.
- 2025 Ember rows exist but should be treated as preliminary.
- UK price coverage may end earlier than other countries — check before joining.

---

## Country comparability

- The six countries differ in geography, market design, interconnection, fiscal policy and history. Comparisons are illustrative, not controlled.
- Austria's hydro share is partly a function of Alpine geography and reservoir build-out. Not directly replicable elsewhere.
- France's nuclear-dominated mix reflects decades of central-state programme decisions; the model is not portable to a country starting from a different position.
- Germany's series shows a structural break around 2022–2023 (nuclear phase-out, coal reduction). Trend interpretation should reflect that.
- Czechia and Slovakia are smaller systems with high nuclear and significant coal exposure; their electricity prices reflect Central European wholesale dynamics.
- The UK is geographically and electrically less interconnected than Continental peers; price formation differs.

---

## Regional mapping caveats

- A UK regional carbon-intensity map will not necessarily show the carbon intensity of electricity consumed by each household or business in that region.
- Electricity grid regions may not match counties, local authorities or ITL/NUTS regions.
- A spatial join can make the map easier to read, but it can also create false precision if the source data and boundary geography do not align.
- Local generation is not the same as local consumption. Electricity can move across regions.
- Carbon intensity varies by time of day and season. A map based on annual or daily averages should not be read as a real-time grid view.

## Methodological

- Generation is reported in TWh; capacity is reported in GW. They are not interchangeable.
- "Aggregate fuel" Ember rows must not be summed alongside "Fuel" rows.
- Bioenergy is treated as low-carbon at the power-sector boundary; lifecycle emissions are non-zero.
- The Ember reported "Total Generation" is used only as a reconciliation check, not as a primary metric.

---

## Inferential

- This project reports **associations**, not causation.
- A high nuclear share alongside a low carbon intensity is consistent with several explanations (nuclear, hydro, low coal share, electricity trade) and does not by itself attribute the carbon outcome to nuclear.
- Cross-country price comparisons are not a like-for-like comparison of the cost of producing electricity. They include policy and tax choices.
- No statement here should be read as "Country X proves" or "Country Y disproves" anything about nuclear power.

---

## Known unknowns

- Consumption-based carbon intensity (planned cross-check with Electricity Maps).
- Hourly price and mix volatility (planned ENTSO-E phase).
- Industrial / non-household price comparisons (planned via `nrg_pc_205`).
- Reactor-level fleet age and outage exposure (planned via IAEA PRIS).
