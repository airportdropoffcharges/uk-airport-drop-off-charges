# UK Airport Drop-Off Charges

Verified drop-off ("kiss and fly") and pick-up charges at 29 UK airports.

For each airport: the fee at the zone nearest the terminal, the free/included time window, overstay penalties, how you pay, and the free or cheaper alternative the airport keeps (with walk/shuttle detail). Every row is verified against the airport's own published charges and carries the date it was checked. The full dataset is re-verified quarterly and after any reported change.

Key facts as of 2026-09-05: the average fee across the 27 charging airports is £6.51; Gatwick and Stansted are joint-highest at £10; Cornwall Newquay and Humberside are the only airports tracked with free terminal drop-off; where fees have risen the typical increase is 38%, with four rises and one brand-new charge recorded in 2026 alone (Liverpool went £6 to £7 on 1 September 2026). At most airports the same charge applies to pick-ups — but Manchester charges £100 for pick-ups attempted in the drop-off zone, Heathrow bans pick-ups from its drop-off zones, and Stansted's and East Midlands' express lanes are drop-off only.

The JSON also carries, per airport: where the drop-off zone physically is, per-terminal detail for multi-terminal airports, how and when to pay (methods, deadline, penalties), pick-up rules, Blue Badge arrangements and fee history. A dated public change log ships alongside as updates.json (mirrored live at https://airportdropoffcharges.co.uk/updates/). The CSV keeps the stable 12-column core.

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
corrections are made visibly and dated. Last full review: **2026-08-25**.
