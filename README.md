# solar-tracker

Live data tracker for *Same Sun, Different Fates* — a comparative study of solar energy transitions across 11 countries.

**→ [View tracker](https://logigorus.github.io/solar-tracker/)**

---

## What it tracks

One row per case country with the latest available values for:

| Column | Source | Notes |
|---|---|---|
| Electricity access % | World Bank Indicators | Latest year available |
| GDP per capita (USD) | World Bank Indicators | Latest year available |
| Renewable % of final energy | World Bank Indicators | Latest year available |
| Solar PV installed capacity (MW) | IRENA STAT | 2023 |
| Solar PV CAGR | IRENA STAT | Since first recorded year |
| Renewable % of electricity generation | Ember Global Electricity Review | Latest year available |
| V-Dem Electoral Democracy Index | V-Dem Institute v15 | 2023, scale 0–1 |
| WGI Rule of Law | World Bank WGI source=3 | 2023, scale ≈ −2.5 to +2.5 |

## Case countries

11 countries across four regions, covering three research subprojects:

| Country | Region | Pathway | Subproject |
|---|---|---|---|
| Uzbekistan | Central Asia | Fossil-to-Solar | Solo article |
| Kazakhstan | Central Asia | Resource Trap | Book |
| Kenya | East Africa | Leapfrog | Book |
| Mexico | Latin America | Middle Ground | Book |
| Slovenia | EU/CEE | EU Leader | WPSA paper |
| Slovakia | EU/CEE | EU Laggard | WPSA paper |
| Serbia | EU/CEE | Candidate Pressure | WPSA paper |
| Croatia | EU/CEE | EU Accelerator | WPSA paper |
| Senegal | West Africa | Pioneer | WPSA paper |
| Mali | West Africa | Low Capacity | WPSA paper |
| Ghana | West Africa | Emerging Market | WPSA paper |

## How it's generated

`index.html` is produced by `tracker_generator.py` in the companion research repo (`~/solar-research/scripts/`). The script reads processed CSVs from `~/solar-research/data/processed/{country}/`, builds a self-contained HTML page, and commits + pushes here. A macOS launchd agent runs it every Sunday at 09:00.

Data is collected by four automated scripts (news, World Bank/IRENA, Ember, PDF reports) and one manual script (democracy/governance scores from Polity5, WGI, and V-Dem v15).

## Data sources

- [World Bank Indicators API](https://datahelpdesk.worldbank.org/knowledgebase/articles/889392)
- [IRENA STAT](https://www.irena.org/Data/Downloads/IRENASTAT)
- [Ember Global Electricity Review](https://ember-energy.org/data/)
- [V-Dem Institute v15](https://v-dem.net/data/the-v-dem-dataset/)
- [World Bank WGI](https://info.worldbank.org/governance/wgi/)
- [Polity5](https://www.systemicpeace.org/polityproject.html) (coverage ends 2018)
