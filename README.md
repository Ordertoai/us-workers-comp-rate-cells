# US Workers Compensation Rate Cells Dataset

**13,833 NCCI class code × US state rate cells** sourced from state insurance department filings and rating-bureau publications.

Each row: an occupation classification (NCCI class code) + state combination, with the filed workers comp insurance rate per $100 of payroll.

This is the open-data dataset powering [wcclasscode.com](https://wcclasscode.com) — the free workers comp rate database operated by Ordertoai LLC.

## Files

- `rate-cells.csv` — 13,833 rows, CSV format with header row, ~1.8 MB
- `rate-cells.json` — same data, JSON array, ~4.5 MB

## Schema

| Column | Type | Description |
|---|---|---|
| `code` | string | NCCI class code (e.g., "5403", "8810", "9079") |
| `occupation_primary` | string | Primary occupation classification name (NCCI Scopes manual) |
| `industry` | string | Higher-level industry grouping (construction, manufacturing, retail, etc.) |
| `state` | string | 2-letter US state code (e.g., "CA", "NY", "TX") |
| `state_name` | string | Full state name |
| `rate` | number | Filed rate per $100 of payroll, decimal |
| `rate_type` | string | Filing type: "loss cost", "base rate", "advisory", etc. |
| `effective_date` | string | When the rate took effect (YYYY-MM-DD) |
| `rating_authority` | string | Authority that filed the rate (NCCI, WCIRB for CA, NYCIRB for NY, etc.) |
| `is_top_50_code` | boolean | Whether this is in the top 50 most-common codes nationally |
| `state_is_indep_bureau` | boolean | True if state uses its own rating bureau (CA, NY, PA, NJ, etc.) |
| `state_is_monopolistic` | boolean | True if state has monopolistic-fund coverage (OH, WA, ND, WY) |

## State coverage

All 50 states + DC. Coverage varies by state because some states file fewer class codes than NCCI's national set:

- California (WCIRB): 498 codes filed
- Alabama (NCCI): 612 codes
- Alaska: 616 codes
- ... (full distribution in `rate-cells.csv`)

## Use cases

- Building a workers comp premium estimator
- Comparing rates across states for a specific occupation
- Analyzing rate trends + filing patterns
- Industry-level rate analysis
- Academic / regulatory research

## License

CC BY 4.0 — free to use, modify, redistribute with attribution to [wcclasscode.com](https://wcclasscode.com).

## See it live

Browse the full database (with calculators, settlement charts, EMR explainers, and state-by-state coverage) at **[wcclasscode.com](https://wcclasscode.com)**.

## Methodology

Rates are sourced from:
- State Department of Insurance public filings
- NCCI Scopes Manual (public)
- Independent rating bureau publications (WCIRB, NYCIRB, PCRB, NJCRIB, WCRIBMA, etc.)
- AM Best public ratings

Verified on a quarterly cycle. The full methodology, source citations, and confidence audit are at:
- https://wcclasscode.com/methodology/
- https://wcclasscode.com/sources/

## Maintainer

This dataset is operated by **Ordertoai LLC** (Texas LLC). Site: [wcclasscode.com](https://wcclasscode.com). Wikidata: [Q139714089](https://www.wikidata.org/wiki/Q139714089).

## Not legal or insurance advice

This data is provided for informational purposes only. Verify rates with your state's rating bureau or department of insurance before pricing a binding insurance quote. See [the full disclaimer](https://wcclasscode.com/disclaimer/).

## Versions

| Version | Date | Cells | Notes |
|---|---|---|---|
| 1.0 | 2026-05-12 | 13,833 | Initial public release |
