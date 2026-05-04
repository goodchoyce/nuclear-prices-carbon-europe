# Nuclear, Prices and Carbon: European Power Mix Analysis

A Python and Power BI energy analytics project investigating nuclear power, electricity prices, carbon intensity and generation mix across selected European electricity systems.

## Why did I start this project?

I started this project while I was in Austria, around the time the IAEA Conference on Nuclear and Radiation Regulation was taking place in Vienna.

This is influenced by Hans Rosling and Gapminder: data should be used to challenge assumptions, explain complex global issues clearly, and avoid turning messy realities into simple slogans.

My parnter and I had a discussion about nuclear power as it is not only a technical question. It depends on regulation, safety, public trust, long-term governance and whether countries have the institutions to manage it properly.

At the same time, I was hearing more conversations about energy prices and whether people might become more open to nuclear if they thought it could bring bills down.

So this project is not here to argue for or against nuclear power. It is here to test the data properly.

## Main question

**Are nuclear-heavy European electricity systems associated with cheaper, cleaner or less volatile electricity, and what does Austria’s non-nuclear model reveal?**

## Countries included

| Country | Why it is included |
|---|---|
| Austria | Non-nuclear case study with high hydro generation |
| United Kingdom | Relevant to UK energy policy, nuclear, wind and gas exposure |
| France | Nuclear-heavy benchmark |
| Germany | Nuclear phase-out comparison |
| Czechia | Nuclear-using neighbour of Austria |
| Slovakia | Nuclear-using neighbour of Austria |

## What I am comparing

- nuclear share of electricity generation
- renewable share
- fossil fuel share
- gas share
- hydro share
- household electricity prices
- non-household electricity prices
- carbon intensity
- price volatility, if the data supports it

## Data sources

| Source | Use |
|---|---|
| Ember Electricity Data Explorer | Generation mix, demand, emissions and carbon intensity |
| Eurostat `nrg_pc_204` | Household electricity prices |
| Eurostat `nrg_pc_205` | Non-household electricity prices |
| IAEA PRIS | Nuclear reactor status and capacity |
| ENTSO-E Transparency Platform | Hourly generation, prices, load and cross-border flows |
| Electricity Maps | Carbon intensity validation where useful |
| Kaggle | Fast prototyping only, checked against official sources before final claims |

Raw datasets are kept local and are not committed to this repository.

## Tools

| Tool | Purpose |
|---|---|
| Python | Data cleaning and analysis |
| pandas | Data transformation |
| Jupyter Notebook | Exploratory analysis |
| Power BI | Dashboard design |
| Git and GitHub | Version control and portfolio evidence |
| Markdown | Documentation |

## Planned dashboard

1. Executive summary
2. Generation mix by country
3. Nuclear, renewables, gas and hydro comparison
4. Electricity price comparison
5. Carbon intensity comparison
6. Price volatility and energy security
7. Austria case study
8. Methodology and caveats

## Method

The first version will stay simple:

1. Load Ember electricity data.
2. Filter to Austria, United Kingdom, France, Germany, Czechia and Slovakia.
3. Calculate nuclear, renewable, fossil, gas and hydro shares.
4. Add Eurostat household and non-household electricity prices.
5. Verify nuclear status using IAEA PRIS.
6. Compare generation mix, prices and carbon intensity.
7. Build a Power BI dashboard with clear caveats.
8. The analysis is also influenced by Hans Rosling and Gapminder: use clear visuals, challenge assumptions, and stay honest about what the data can and cannot prove.

## Caveats

There should be no claim that nuclear power automatically makes electricity cheaper.

Electricity prices are affected by many things:

- gas prices
- taxes and levies
- network costs
- subsidies
- market design
- demand
- imports and exports
- interconnectors
- national policy choices

Austria also needs careful interpretation. Its low-carbon electricity system depends heavily on hydro resources, which other countries cannot simply copy.

The aim: show patterns clearly, not to pretend one chart settles the debate.

## Current status

Early-stage project setup.

Completed:

- project folder created
- Git repository initialised
- raw data folders created
- Ember, Eurostat and IAEA PRIS files started locally
- `.gitignore` set up to keep raw data and large files out of Git
- initial documentation scaffold created

Next steps:

1. Finalise documentation.
2. Load Ember data in the first notebook.
3. Inspect columns and country coverage.
4. Create the first country comparison table.
5. Add Eurostat price data.
6. Build first exploratory charts.
7. Start the Power BI dashboard.

## Why this matters for my portfolio

- energy-sector data interpretation
- Python and pandas data cleaning
- Power BI dashboard design
- time-series analysis
- data quality checks
- documentation
- regulatory and governance awareness
- clear communication of limitations
- passion for data awareness 