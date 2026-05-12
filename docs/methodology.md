# Methodology

Decisions taken, and why. Update as choices change.

---

## Country selection

Six countries chosen to span a wide range of nuclear exposure and generation mix:

- France — long-standing nuclear-dominated system.
- Slovakia — small system, high nuclear share.
- Czechia — high nuclear, also high coal.
- United Kingdom — significant wind and gas, declining nuclear.
- Germany — completed nuclear phase-out in April 2023.
- Austria — no nuclear since 1978, high hydro share.

Smaller European systems (Hungary, Belgium, Switzerland) and the Nordics were considered but excluded to keep the comparison legible. They are candidates for a later phase.

---

## Country naming

Names follow the Ember dataset's labelling. Other sources are mapped to these names:

- "United Kingdom" — not "UK", "Great Britain" or "GB".
- "Czechia" — not "Czech Republic" or "CZ".

A small mapping table in code converts ISO codes (GBR, CZE, DEU, AUT, FRA, SVK) where needed.

---

## Generation mix

- Source: Ember Electricity Data Explorer, yearly file.
- Filter: `Area type == 'Country or economy'`.
- For TWh by fuel: `Category == 'Electricity generation'`, `Subcategory == 'Fuel'`, `Unit == 'TWh'`.
- For shares (%): same filters with `Unit == '%'`.
- "Aggregate fuel" rows are excluded from any per-fuel sum to avoid double counting.
- "Total Generation" rows are used only for cross-checking that the sum of individual fuels reconciles.

---

## Low-carbon vs fossil

- Low-carbon: Nuclear + Hydro + Wind + Solar + Bioenergy + Other Renewables.
- Fossil: Coal + Gas + Other Fossil.
- This split follows Ember's "Clean / Fossil" aggregation. Bioenergy is treated as low-carbon at the power-sector level, with the standard caveat that lifecycle emissions are not zero.

---

## Carbon intensity

- Source: Ember `Power sector emissions` → `CO2 intensity` → `CO2 intensity` in `gCO₂/kWh`.
- This is generation-based: it reflects emissions from electricity produced inside the country, not electricity consumed there.
- Consumption-based carbon intensity (which would account for net imports) is a planned later cross-check using Electricity Maps.

---

## Planned UK regional carbon-intensity map

A planned extension will examine regional variation in UK electricity carbon intensity. The intended output is a map suitable for Power BI and/or Python visualisation.

The final geography will depend on data availability and boundary compatibility. Candidate geographies are:

- county or local authority boundary
- ITL/NUTS region
- electricity grid region or carbon-intensity region

The first data pass will not assume that administrative regions and electricity-system regions match. Where a spatial join is required, the join key and boundary file will be documented. If only grid-region data is available, the map will use grid regions rather than forcing the data onto county boundaries.

This extension will be descriptive. It will show regional variation in reported or estimated carbon intensity, but it will not claim causation.

## Time period

- Yearly series start in 2000.
- Trend charts and trend tables use 2024 as the latest full year.
- 2025 rows are excluded by default. Where included for a specific reason, they are clearly labelled as preliminary.

---

## Prices (Eurostat)

- Household: `nrg_pc_204`, band DC (2,500–4,999 kWh), all taxes and levies included, EUR per kWh, latest common half-year across the six countries.
- Non-household: `nrg_pc_205`, band selection to be decided in the next data pass.
- Prices are reported half-yearly; Ember generation is yearly. The join uses the calendar year of the chosen Eurostat half-year and notes the misalignment.

---

## Joins

When generation and prices are joined into a country summary table, the join key is `Country` only for cross-sectional comparisons, or `(Country, Year)` for time-series joins. Period misalignment is annotated in any chart or table that combines the two.

---

## What is not done in this project

- No regression analysis or causal inference.
- No grid-stability or hourly volatility analysis (planned later).
- No levelised cost of electricity (LCOE) modelling.
- No projection or forecasting.

Findings are presented as descriptive comparisons and associations, with caveats stated near each chart.
