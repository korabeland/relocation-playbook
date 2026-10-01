# Budget structure

A way to organize a relocation budget so that scenarios can be compared. This is a design explanation. It is not a spreadsheet file, and it contains no figures. Build the workbook in your own private copy and keep real amounts out of anything you share.

## Four buckets

Group every expected cost into one of four buckets.

| Bucket | What goes in it | Examples |
|---|---|---|
| Exit | Costs of leaving the origin | Breaking a lease, final bills, selling fees, storage, cleaning |
| Travel | Getting people, pets, and goods there | Flights, shipping, pet transport, temporary stays on the way |
| One-time setup | Costs that happen once on arrival | Deposits, furniture, a vehicle, registration fees, initial supplies |
| Recurring | Costs that continue each month | Rent, coverage premiums, transport, childcare, subscriptions |

## Expense list

One row per expected cost. Suggested columns:

| Column | Meaning |
|---|---|
| Item | What the cost is |
| Bucket | One of the four |
| Amount | In your planning currency |
| Currency | Set the currency and the rate source in one place |
| When | The month it falls in |
| Certainty | `quoted`, `estimated`, or `guess` |
| Note | Where the number came from |

Certainty is the useful column. It stops a guess from looking like a quote.

## Scenarios

Build two or three scenarios from the same list rather than separate sheets. A scenario is a set of choices, for example "ship everything", "sell the large items", or "arrive before the new role starts" versus "arrive after". The summary computes each bucket's total per scenario and the runway left at departure and at arrival.

Keep formulas simple, in one summary area, so any adult in the household can check them. State the exchange-rate assumption at the top and date it.

## Open questions sheet

A third sheet lists what would change the numbers: quotes not yet received, rules not yet confirmed, decisions not yet made. Each row points at the `state/decisions.yaml` entry or research question that will settle it.

## Before sharing a workbook

A workbook carries more than its visible cells: comments, hidden sheets, document properties, and links. Do not share a populated workbook. Share only a blank structure built from scratch.
