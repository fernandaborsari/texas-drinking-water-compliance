# Texas Drinking Water Compliance Pipeline

> **Which public water systems in Texas violate drinking water regulations, what kinds of violations are most common, and how quickly are they resolved?**

An end-to-end data engineering project built on **Databricks Free Edition** with Python, PySpark, SQL and
Delta Lake, following the Medallion architecture (Bronze, Silver, Gold). It uses public data from the
US EPA Safe Drinking Water Information System (SDWIS), published through ECHO.

> **Scope note:** this project analyzes **regulatory compliance**. It does not claim that the water in any
> specific city is safe or unsafe. Violation data has known limitations and reporting delays.

## Scope (version 1)

- **Region:** Texas, USA (public water systems with `PWSID` starting with `TX`)
- **Period:** violations from 2021 to 2025 (five complete years)
- **Indicators:**
  1. Active water systems and population served, by system type and county
  2. Violations per year, with health-based violations shown separately
  3. Violations by category (contaminant limit, monitoring and reporting, treatment technique, other)
  4. Share of systems with at least one health-based violation, and the population they serve
  5. Violation status (resolved, addressed, unaddressed, archived)
  6. Time to return to compliance (median days)
  7. Ranking of counties and contaminants

## Project status

| Phase | Description | Status |
|---|---|---|
| 1 | Proof of concept: validate the source, explore the Texas data, first Bronze table | 🚧 In progress |
| 2 | Data engineering: Bronze, Silver and Gold layers, data quality checks | ⏳ Planned |
| 3 | Analytics: AI/BI dashboard and key findings | ⏳ Planned |
| 4 | Publication: final documentation and architecture diagram | ⏳ Planned |

## Data source

- **EPA ECHO – SDWA Data Download:** [download summary](https://echo.epa.gov/tools/data-downloads/sdwa-download-summary)
  (refreshed quarterly)

Raw data files are not stored in this repository. Instructions to reproduce the ingestion will be added
in the "How to run" section.

## Repository structure

```
notebooks/   Databricks notebooks (one per pipeline step)
src/utils/   Reusable Python functions
sql/         SQL queries for Gold tables and the dashboard
config/      Project configuration (period, state, file names)
docs/        Design decisions, data quality rules, data dictionary
images/      Architecture diagram and dashboard screenshots
tests/       Tests for transformation logic
```
