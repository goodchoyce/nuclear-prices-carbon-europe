# Source notes

Per-dataset notes on access, vintage, licence, expected file path and known quirks. Update vintages when you re-download.

---

## Ember Electricity Data Explorer (yearly)

- **Use.** Generation by fuel, demand, power-sector emissions, carbon intensity.
- **URL.** https://ember-energy.org/data/electricity-data/
- **File expected.** `data/raw/ember/ember_yearly_electricity_data.csv`
- **Granularity.** Country × year, long format.
- **Key columns.** Area, ISO 3 code, Year, Area type, Category, Subcategory, Variable, Unit, Value.
- **Vintage.** See download timestamp on the file in `data/raw/ember/`.
- **Licence.** CC-BY 4.0 (verify on the page at download time).
- **Quirks.**
  - "Aggregate fuel" rows (Renewables, Fossil, Wind and Solar, etc.) overlap with individual fuel rows. Do not sum across both.
  - "Country or economy" Area type filter is required to drop regional aggregates.
  - 2025 rows exist but should be treated as preliminary.

---

## Eurostat `nrg_pc_204` — household electricity prices

- **Use.** Household electricity prices by consumption band, biannual.
- **URL.** https://ec.europa.eu/eurostat/databrowser/view/nrg_pc_204/
- **File expected.** `data/raw/eurostat/eurostat_nrg_pc_204_household_prices.csv`
- **Granularity.** Country × half-year × consumption band × tax treatment × currency.
- **Filters used in this project.**
  - Consumption band: DC (2,500–4,999 kWh).
  - Taxes: all taxes and levies included.
  - Currency: EUR.
  - Period: latest common half-year across all six countries.
- **Vintage.** See download timestamp on the file in `data/raw/eurostat/`.
- **Licence.** Eurostat re-use policy (free re-use with attribution).
- **Quirks.**
  - UK coverage may end earlier than other countries; check before joining.
  - Czechia values are in EUR via Eurostat conversion from CZK; reported price levels can move with the EUR/CZK rate.
  - Half-year codes are `S1` and `S2`; map carefully when joining to Ember yearly data.

---

## Eurostat `nrg_pc_205` — non-household electricity prices

- **Use.** Industrial / business electricity prices, biannual.
- **URL.** https://ec.europa.eu/eurostat/databrowser/view/nrg_pc_205/
- **File expected.** `data/raw/eurostat/eurostat_nrg_pc_205_non_household_prices.csv`
- **Status.** Planned. Same band-and-currency caveats as `nrg_pc_204`.

---

## IAEA PRIS — Power Reactor Information System

- **Use.** Reactor-level operational status, capacity (MWe), first criticality, permanent shutdown.
- **URL.** https://pris.iaea.org/
- **File expected.** `data/raw/iaea_pris/iaea_pris_country_nuclear_status.csv`
- **Granularity.** Reactor or country aggregate, depending on export.
- **Vintage.** See download timestamp on the file in `data/raw/iaea_pris/`.
- **Licence.** IAEA terms of use; attribution required.
- **Quirks.**
  - Status codes (Operational, Long Term Shutdown, Permanent Shutdown, Under Construction) need explicit handling.
  - "Net" vs "gross" capacity matters; pick one and stick with it.

---

## ENTSO-E Transparency Platform (later phase)

- **Use.** Hourly generation and day-ahead prices for volatility analysis.
- **URL.** https://transparency.entsoe.eu/
- **Access.** Requires an API token.
- **Storage.** Do not commit token. Use `.env` (already in `.gitignore`).
- **Quirks.** Country boundaries are bidding zones; not always 1:1 with countries (e.g. Germany–Luxembourg historically combined).

---

## Electricity Maps (later phase)

- **Use.** Consumption-based carbon intensity for cross-validation.
- **URL.** https://www.electricitymaps.com/
- **Quirks.** Differs from Ember by including imports; expect divergence and document it.

---

## Kaggle (prototyping only)

- Used only for early prototyping. Not citable as final evidence. Do not commit Kaggle CSVs.
