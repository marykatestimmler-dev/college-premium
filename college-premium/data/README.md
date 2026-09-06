# Data

Every CSV here is the exact series its chart draws. Column names carry units. Empty cells are months the source agency did not publish (October 2025 in the two monthly BLS files); nothing is interpolated.

| File | Rows | Source |
|---|---|---|
| `attainment_age_25_plus.csv` | 41 (1975, 1980, then annual 1985–2023) | Census CPS via NCES Digest Table 104.10 |
| `attainment_age_25_29.csv` | 28 (benchmark years 1940–2000, annual 2005–2024) | Census CPS via NCES Digest Table 104.20 |
| `labor_force_share_bachelors_plus_monthly.csv` | 415 months, Jan 1992–Jul 2026 | BLS via FRED, computed from LNS11027662 / 689 / 660 / 659 |
| `unemployment_by_education_monthly.csv` | 415 months, Jan 1992–Jul 2026 | BLS via FRED LNS14027662, LNS14027660; FEDFUNDS |
| `college_wage_premium_benchmarks.csv` | 3 benchmark years | Minneapolis Fed (2025), hand-entered, source in row |
| `recent_graduate_unemployment_2019_vs_2025.csv` | 4 groups | St. Louis Fed (Aug 2025), hand-entered, source in row |
| `young_graduate_labor_market_indicators.csv` | 11 indicators | Cleveland Fed EC 2025-14, NY Fed, hand-entered, source in row |

Full citations with links are in the top-level README.
