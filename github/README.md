# UK Airport Drop-Off Charges Dataset

Verified, dated drop-off and pick-up charges at 29 UK airports: the charge at the
zone nearest the terminal, how long it covers, what an overstay costs, how you pay, and the
airport's own free or cheaper alternative. Each figure is checked against the airport's own
published charges and dated. Free to reuse under CC BY 4.0.

Live, always-current version: https://airportdropoffcharges.co.uk/ (JSON: https://airportdropoffcharges.co.uk/data/airports.json, CSV: https://airportdropoffcharges.co.uk/data/airports.csv)

## At a glance (28 Oct 2026)

- **29 UK airports**, each checked between 25 Oct 2026 and 28 Oct 2026. 28 are confirmed on the airport's own website; Cardiff Wales is confirmed against published reports instead and labelled `secondary`.
- **Average charge £6.74** across the 27 airports that charge (median £7). Highest: London Gatwick and London Stansted at £10. Free at the terminal: Cornwall Newquay and Humberside.
- **Typical rise +28%** across 23 recorded rises. The largest is Belfast International's, £3 to £5 (+67%).
- Last full review 25 Oct 2026; data last updated 28 Oct 2026. Every change is logged at https://airportdropoffcharges.co.uk/updates/.

## Files

- `data/airports.csv`: one row per airport (the main table)
- `data/airports.json`: the full records, with payment rules, pick-up rules, Blue Badge terms, fee history and sources
- `data/updates.json`: the dated change log (fee changes and corrections)
- `datapackage.json`: Frictionless Data descriptor; `CITATION.cff`: how to cite
- Mirrors: GitHub (https://github.com/airportdropoffcharges/uk-airport-drop-off-charges), Kaggle (https://www.kaggle.com/datasets/airportdropoff/uk-airport-drop-off-charges-verified-2026), Hugging Face (https://huggingface.co/datasets/uk-airport-drop-off-charges/uk-airport-drop-off-charges)

### CSV columns (`airports.csv`)

| Column | Meaning |
|---|---|
| `airport` | Airport name. |
| `iata` | Three-letter IATA airport code, for example LHR. |
| `region` | UK nation or English region. |
| `fee_gbp` | The charge in pounds for the drop-off zone nearest the terminal. 0 means it is free. |
| `free_minutes` | The time allowance in minutes: how long the charge covers, or how long is free at an airport that doesn't charge. 0 means a charge per entry with no time allowance. The name is historical. |
| `window_note` | The charge and its time limit in plain English. |
| `overstay` | What a longer stay costs. |
| `free_alternative` | The airport's own free or cheaper place to drop off. In the CSV this is its name, or "None". In the JSON it is an object: exists, name, detail, transfer (how you get to the terminal from it) and, for some airports, allow (how much extra time to leave). |
| `alt_detail` | CSV only: a description of the free alternative. In the JSON this is free_alternative.detail. |
| `verified` | The date this airport's figures were last checked, as YYYY-MM-DD. |
| `verification` | official: confirmed on the airport's own website. secondary: confirmed against published comparisons instead. |
| `source` | The website the figures were checked against. |

### Extra fields in the JSON

The JSON has every CSV field plus these (not every airport has every field):

| Fields | Meaning |
|---|---|
| `payment` | How you pay, in a line. |
| `pay_type`, `pay_methods`, `pay_deadline`, `pay_penalty`, `pay_note` | Payment in detail: whether you pay at a barrier or afterwards (postpay), the ways to pay, the deadline, and what happens if you miss it. |
| `pay_url` | The official payment website, where there is one. |
| `dropoff_location` | Where the drop-off zone is. |
| `pickup_note` | The rules and cost for picking someone up. |
| `exemptions` | Blue Badge terms and other exemptions. |
| `previous_fee_gbp`, `previous_fee_year` | An earlier charge and the year it applied, for fee history. |
| `fee_changed` | The date the current charge took effect, where the airport publishes it (YYYY-MM-DD). |
| `autopay_auto`, `autopay_url` | Whether the operator says AutoPay charges each visit automatically (false where it doesn't say), and where to sign up for it. |
| `free_dropoff` | Where an airport runs a dedicated free drop-off area away from the terminal zone: its free minutes, where it is and the walk (Birmingham, Inverness). |
| `aka` | A former or alternative name people still search for (Teesside's 'Durham Tees Valley'). |
| `official_check` | The official page to check the charge on. |
| `terminals`, `terminals_note` | The zone at each terminal, at airports with more than one. |
| `rail_mode`, `rail`, `rail_source` | The rail or tram link to the airport, with its source. |
| `colour`, `colour_source` | A practical detail about the drop-off, with its source. |
| `fact`, `fact_source` | A notable fact about the airport, often from its history, with its source. |
| `lat`, `lon` | The airport's coordinates. |
| `note` | An extra remark about the record. |
| `machines_onsite` | True where an airport that charges afterwards also has pay machines on site. |

## How the data is checked

Every charge is read from the airport's own website and stamped with the date it was
checked (`verified`). Where the airport's page can't be read, the row is confirmed against
published reports and labelled `secondary`. All airports are re-checked every quarter and
after any reported change, and corrections are logged publicly. Full method:
https://airportdropoffcharges.co.uk/methodology/

Charges change without notice: check the airport's own page before you travel.

## Licence and citation

Creative Commons Attribution 4.0 (CC BY 4.0). Credit "airportdropoffcharges.co.uk".

Airport Drop-Off Charges, *UK Airport Drop-Off Charges Dataset*, updated 28 Oct 2026, airportdropoffcharges.co.uk. CC BY 4.0.

Corrections: hello@airportdropoffcharges.co.uk
