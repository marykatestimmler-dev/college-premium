# The College Premium

Five charts and the data behind them, on one question: **what has a bachelor's degree been worth in the American labor market over the last fifty years, and is that changing?**

Built by Mary Kate Stimmler (Berkeley Haas; Stanford CASBS) with Claude as research and engineering partner. Every number in every chart traces to a public federal source listed below. The CSVs in `data/` are the exact series the charts draw.

## The charts

Open any file in `charts/` in a browser. Each page is self-contained (no build step, no dependencies beyond Google Fonts) and has a Chart / Table toggle so the underlying numbers are one click away.

| Chart | What it shows | Window | Data |
|---|---|---|---|
| **The Straight Line** | Share of adults 25+ with a bachelor's degree or higher. Rises about half a point a year, straight through six recessions. | 1975–2023 | `attainment_age_25_plus.csv` |
| **Coming of Age** | Same measure, but only for 25–29 year olds, so each point is one generation rather than the whole adult population. | 1940–2024 | `attainment_age_25_29.csv` |
| **The Credentialed Majority** | Bachelor's+ share of the *labor force* 25+, monthly. Crosses 45% in 2025. | 1992–2026 | `labor_force_share_bachelors_plus_monthly.csv` |
| **The Credential Gap** | Unemployment for bachelor's+ vs. high-school-only workers, monthly, with the fed funds rate on a companion panel. | 1992–2026 | `unemployment_by_education_monthly.csv` |
| **Diminishing Returns** | The college wage premium at Fed benchmark years, and the 2019→2025 reversal in recent-graduate unemployment. | 1980–2025 | `college_wage_premium_benchmarks.csv`, `recent_graduate_unemployment_2019_vs_2025.csv`, `young_graduate_labor_market_indicators.csv` |

## What the data says

**Attainment rose steadily for fifty years.** In 1975 about one adult in seven held a bachelor's degree (13.9%). In 2023 it was nearly two in five (38.3%). The increase averages 0.51 percentage points a year. The series fell year-over-year exactly once since annual reporting began in 1985 (2022, by 0.2 points). Recessions, presidential transitions, and technology shifts are not visible in the line.

**The wage premium doubled, then plateaued.** Bachelor's-degree workers out-earned high-school-only workers by about 39% in 1980 and 79% in 2000. Since 2000 the premium has been flat, ending slightly below its peak (roughly 77%). This is the striking part: the supply of graduates nearly tripled and the price the market paid for them did not fall. But because tuition and student debt rose over the same period while the premium did not, the *net* return to a degree has narrowed even though the headline premium stayed high.

**The unemployment gap persists.** Workers 25+ with a bachelor's degree have been unemployed at roughly half to two-thirds the rate of high-school-only workers every month since 1992 (July 2026: 2.7% vs. 4.0%). The gap widens in every recession.

**The erosion, where it exists, is at the entrance.** Young college graduates (age 22–27) used to be unemployed about 5 points less often than young high-school graduates. That gap fell to 2.4 points in March 2024, the lowest since the late 1970s, and sat at 2.5 points in mid-2025. Recent graduates' unemployment (4.6% in Jan–Jul 2025) rose above the rate for all workers (4.2%), a reversal from 2019, while established graduates 28+ stayed at 2.4%. About 42% of recent graduates were underemployed in 2026 Q2. The mechanism, per the Cleveland Fed, is a fall in young graduates' job-finding rate (47% monthly in 1976–2000 to 37% in 2025) while high-school graduates' rate held steady.

The honest one-line summary: **the degree still pays, and pays most in bad times, but its payoff stopped growing around 2000 and the fast start it used to buy young graduates has largely disappeared.**

## Sources

All series are from U.S. federal statistical agencies or Federal Reserve research.

- **Attainment, adults 25+** (The Straight Line): U.S. Census Bureau, Current Population Survey, Annual Social and Economic Supplement, as published in National Center for Education Statistics, *Digest of Education Statistics*, [Table 104.10](https://nces.ed.gov/programs/digest/d23/tables/dt23_104.10.asp). 1975 and 1980 are the table's benchmark years; annual from 1985.
- **Attainment, ages 25–29** (Coming of Age): same survey, NCES *Digest* [Table 104.20](https://nces.ed.gov/programs/digest/d24/tables/dt24_104.20.asp). Benchmark years before 2005, annual from 2005.
- **Labor force share** (The Credentialed Majority): Bureau of Labor Statistics via FRED, civilian labor force levels 25+, seasonally adjusted: [LNS11027662](https://fred.stlouisfed.org/series/LNS11027662) (bachelor's+), [LNS11027689](https://fred.stlouisfed.org/series/LNS11027689) (some college/associate), [LNS11027660](https://fred.stlouisfed.org/series/LNS11027660) (HS only), [LNS11027659](https://fred.stlouisfed.org/series/LNS11027659) (less than HS). Share = bachelor's+ ÷ sum of the four.
- **Unemployment by education** (The Credential Gap): BLS via FRED, unemployment rate 25+, seasonally adjusted: [LNS14027662](https://fred.stlouisfed.org/series/LNS14027662) (bachelor's+), [LNS14027660](https://fred.stlouisfed.org/series/LNS14027660) (HS only). Fed funds: [FEDFUNDS](https://fred.stlouisfed.org/series/FEDFUNDS). Recession dates: NBER.
- **Wage premium benchmarks** (Diminishing Returns): Federal Reserve Bank of Minneapolis, [What happened to the college wage premium?](https://www.minneapolisfed.org/article/2025/what-happened-to-the-college-wage-premium) (2025).
- **Recent-graduate unemployment, 2019 vs 2025**: Federal Reserve Bank of St. Louis, [Recent College Grads Bear Brunt of Labor Market Shifts](https://www.stlouisfed.org/on-the-economy/2025/aug/recent-college-grads-bear-brunt-labor-market-shifts) (Aug 2025).
- **Young-graduate unemployment gap and job-finding rates**: Federal Reserve Bank of Cleveland, [Are Young College Graduates Losing Their Edge in the Job Market?](https://www.clevelandfed.org/publications/economic-commentary/2025/ec-202514-are-young-college-graduates-losing-their-edge-in-the-job-market) (Economic Commentary 2025-14).
- **Recent-graduate unemployment and underemployment, 2026 Q2**: Federal Reserve Bank of New York, [The Labor Market for Recent College Graduates](https://www.newyorkfed.org/research/college-labor-market).
- **College employment premium (EPOP)**: Federal Reserve Bank of New York, Liberty Street Economics, [The College Economy](https://libertystreeteconomics.newyorkfed.org/2025/05/the-college-economy-educational-differences-in-labor-market-outcomes/) (May 2025).

## Caveats worth knowing

- **Definition change in 1992.** Before 1992 the Census asked about "four or more years of college"; from 1992 it asks about degrees earned. NCES publishes the two as one continuous series and so do we, but a purist would draw a faint seam at 1992.
- **The wage-premium line is three points, not a series.** The Minneapolis Fed article gives benchmark values for 1980, 2000 and 2023. The chart connects them to show trajectory and says so in its method note. The Economic Policy Institute's regression-adjusted premium (a different measure with a lower level) shows the same 2000s–2010s plateau, which is why we are comfortable with the shape. Anyone wanting an annual line should pull EPI's State of Working America data or the CPS microdata directly.
- **"Recent graduate" is defined differently by different Feds.** St. Louis uses age 23–27 with a bachelor's; Cleveland uses 22–27; New York uses 22–27 with a bachelor's only. The CSVs record which definition each figure uses.
- **October 2025 is blank** in the two monthly BLS series because BLS did not publish that month. It is left empty rather than interpolated.
- **2024 attainment (25+)** is not in the table we used. The Census 2024 release reports 40.1% of women and 37.1% of men 25+ with a bachelor's or higher; we did not compute a combined figure from those.

## How this was made

This project was built in a series of working sessions between a social scientist and Claude (Anthropic's AI assistant, running in Claude Cowork). The division of labor, roughly:

- **The human** set the questions, chose which premium to test (wage vs. employment protection), decided the recent-graduate angle should be central, chose the time window, rejected a first draft of the Labor Day write-up as "boring" and redirected it toward what was actually remarkable in the data, and made every editorial call.
- **Claude** ran the searches, read the Fed papers, pulled and cross-checked the series, pushed back where the ask was ambiguous (the word "premium" means two different things), flagged where it could not get annual data and refused to interpolate it, built the charts as hand-written SVG in a shared design system, rendered them headlessly to check the output, and assembled this repository.

Two practices we would recommend to anyone doing similar work with an AI assistant. First, insist on a *method note on the chart itself* saying exactly what the data is and is not; it keeps both parties honest. Second, when the assistant cannot get a clean series, make it say so rather than smooth over the gap. The three-point wage-premium line in Diminishing Returns is uglier than an annual one would be, and it is also true.

## Repository layout

```
charts/   five self-contained HTML pages, one per chart
data/     every series as CSV, with a column naming the source where the data is hand-entered
```

## License

Code and chart pages: MIT (see `LICENSE`). Data from U.S. federal agencies is in the public domain. Federal Reserve Bank research is quoted under fair use; please cite the original papers, linked above, if you reuse those figures.
