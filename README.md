# UK Airport Drop-Off Charges

Verified drop-off ("kiss and fly") and pick-up charges at 23 UK airports.

For each airport: the fee at the zone nearest the terminal, the free/included time window, overstay penalties, how you pay, and the free or cheaper alternative the airport keeps (with walk/shuttle detail). Every row is verified against the airport's own published charges and carries the date it was checked. The full dataset is re-verified quarterly and after any reported change.

Key facts as of 2026-08-17: the average fee across the 22 charging airports is £6.93; Gatwick and Stansted are joint-highest at £10; Cornwall Newquay is the only airport tracked with free terminal drop-off; at nearly every airport the same charge applies to pick-ups (Manchester charges £100 for pick-ups attempted in the drop-off zone).

Maintained independently by Airport Drop-Off Charges (https://airportdropoffcharges.co.uk); not affiliated with any airport. Licence: CC BY 4.0 — free to reuse with attribution to airportdropoffcharges.co.uk. Live data endpoints, an embeddable widget and an MCP server are documented at https://airportdropoffcharges.co.uk/ai/.

## Files

| File | Format | Contents |
|---|---|---|
| `data/airports.json` | JSON | Full dataset incl. metadata, per-airport notes, coordinates and rail links |
| `data/airports.csv` | CSV | Flat core table, one row per airport |

## CSV columns

| Column | Type | Description |
|---|---|---|
| `airport` | string | Airport name |
| `iata` | string | IATA code |
| `region` | string | UK region |
| `fee_gbp` | number | Drop-off fee in GBP at the zone nearest the terminal (0 = free) |
| `free_minutes` | integer | Minutes included in the fee (0 = charge per entry, no window) |
| `window_note` | string | Plain-English description of the charge window |
| `overstay` | string | What staying beyond the window costs |
| `free_alternative` | string | Name of the airport's free/cheaper drop-off option ('None' if none published) |
| `alt_detail` | string | Detail of the free alternative (free period, walk/shuttle transfer) |
| `verified` | date | Date this row was checked against the airport's own site |
| `verification` | string | 'official' = confirmed on the airport's own website on that date |
| `source` | string | URL of the airport's official page |

## Live versions of this data

- Comparison site & per-airport guides: https://airportdropoffcharges.co.uk
- JSON endpoint (CORS-enabled): https://airportdropoffcharges.co.uk/data/airports.json
- Embeddable widget: https://airportdropoffcharges.co.uk/embed/
- MCP server for AI tools: https://airportdropoffcharges.co.uk/mcp (docs: https://airportdropoffcharges.co.uk/connect/)

## Licence & attribution

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Reuse freely — credit
**Airport Drop-Off Charges (airportdropoffcharges.co.uk)** with a link.

## Corrections

Charges change without notice. Spotted an error? Email hello@airportdropoffcharges.co.uk —
corrections are made visibly and dated. Last full review: **2026-08-17**.
