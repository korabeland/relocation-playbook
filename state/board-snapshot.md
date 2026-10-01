# Board snapshot

Snapshot date: `<YYYY-MM-DD of the last successful reconciliation, UTC>`

Coverage: `<for example: "all pages known to the assistant as of the snapshot date; pages the assistant has not seen may be missing">`

This is a dated copy of the task board. The board itself stays authoritative. Session close reconciles successful task writes and pages changed on or after the saved date (inclusive, from midnight UTC), before composing outputs. The date advances to the UTC date the board check began only if the change lookup and all returned page reads succeed, even when nothing changed. On any read failure, retain the last successful date and describe the gaps in Coverage. See `state/README.md`.

| Task | Status | Owner | Due | Phase |
|---|---|---|---|---|
| | | | | |

Counts: `<not started> not started, <in progress> in progress, <waiting> waiting, <done> done`
