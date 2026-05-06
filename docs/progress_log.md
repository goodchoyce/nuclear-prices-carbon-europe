# Progress log

A working log. Most recent entry first.

---

## 2026-05-06

**Documentation pass.**

- Updated `README.md` with research question, sub-questions, current status, vocabulary discipline section and a short caveats summary.
- Created this progress log.
- Drafted `docs/methodology.md`, `docs/source_notes.md`, `docs/glossary.md` and `docs/caveats.md`. These are queued for a follow-up commit.
- Decision: keep raw data uncommitted; commit small processed CSVs only when a downstream notebook or Power BI report depends on them.

**Not done.**

- No code changes.
- No new data loaded.
- No analytical claims added.

---

## 2026-05-05

**First dataset review notebook.**

Completed:

- Loaded Ember yearly electricity data.
- Filtered to Austria, United Kingdom, France, Germany, Czechia and Slovakia.
- Confirmed presence of Ember categories used downstream: Electricity generation, Power sector emissions, Capacity, Electricity demand, Electricity imports.
- Confirmed useful units: TWh, %, gCO₂/kWh, mtCO₂.
- Built latest-year generation mix table in TWh.
- Built generation share table for Nuclear, Hydro, Gas, Coal, Wind, Solar, Bioenergy, Other Fossil and Other Renewables.
- Built a key share summary (Nuclear, Hydro, Gas, Coal, Wind, Solar).
- Built a nuclear share ranking.
- Built a low-carbon vs fossil generation comparison.
- Added carbon intensity comparison from Ember.
- Loaded Eurostat household electricity price data (`nrg_pc_204`).
- Filtered household prices to band DC (2,500–4,999 kWh), all taxes and levies included, EUR, latest common period across all six countries.
- Built household price comparison table.
- Built combined country summary table joining generation shares, low-carbon share, fossil share, carbon intensity and household price (EUR/kWh).
- Exported processed CSVs for later use.

**Approximate findings (descriptive only, not causal).**

- France: high nuclear share, high low-carbon share, low carbon intensity.
- Slovakia: high nuclear share, high low-carbon share.
- Austria: zero nuclear share, high hydro share, high low-carbon share.
- United Kingdom: significant wind and gas share.
- Germany: high wind and solar but material coal and gas.
- Czechia: high nuclear but also high coal share.

**Open questions.**

- Do Ember generation periods and Eurostat price periods align closely enough for the joined summary?
- How should UK price data be handled if its latest common period is older than the Ember generation year?
- Should processed CSVs be committed, or kept ignored and regenerated from notebooks?

**Decisions taken.**

- Use Ember individual fuels (Subcategory = "Fuel") for shares, not "Aggregate fuel", to avoid double counting.
- Use 2024 as the latest full year; treat 2025 as preliminary.
- Country names follow Ember labelling ("United Kingdom", "Czechia").

---

## Backlog / parking lot

- Add Eurostat non-household electricity prices (`nrg_pc_205`).
- Add IAEA PRIS nuclear reactor status and capacity.
- Detailed time-period alignment check between Ember and Eurostat.
- UK price data special-case handling.
- Clean Power BI-ready processed tables.
- First Power BI dashboard prototype (only after the data layer is stable).
- ENTSO-E hourly volatility analysis (later phase).
- Cross-validate Ember carbon intensity against Electricity Maps (later phase).
- Methodology and limitations notes inside the notebook itself, not just `docs/`.
