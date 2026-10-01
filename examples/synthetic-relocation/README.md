# Synthetic relocation: Alex and Riley

Alex and Riley are invented. They are two adults and a cat, moving from "Country A" to "Country B" in March 2031. Nothing here describes a real household or real rules.

The example holds the state of the plan after about two weeks of use.

| File | What it shows |
|---|---|
| `PLAN.md` | A filled-in plan on a fixed-date timing model |
| `state/facts.yaml` | A confirmed fact, an assumption, and a recommendation, kept apart |
| `state/deadlines.yaml` | Hard and soft deadlines, including calendar references |
| `state/decisions.yaml` | One open decision and one decided |
| `state/research-queue.yaml` | Two finished and two queued research questions |
| `state/board-snapshot.md` | A dated task cache with a coverage note |
| `Research/shipping/ship-or-sell.md` | A short research file in the template layout |
| `Weekly/2031-01-18-session.md` | A session record, including a stale-agenda catch and a date correction |

Only one of the research files is included. The queue also lists a finished coverage question whose file is left out to keep the example small.

## One cycle, step by step

This is the loop the kit is built around, using the files above.

1. **Start.** The assistant reads the state files and notes the snapshot is four days old. It checks the board for pages changed on or after that date (inclusive, from midnight UTC) and finds one.
2. **Research.** Alex asks for "some research". The assistant takes the lowest-numbered queued entry, a question about shipping versus selling furniture, and writes `Research/shipping/ship-or-sell.md`. It proposes a follow-up date and an assumption to record, and writes neither to `state/` yet.
3. **Decision.** Alex and Riley choose to sell the large items and ship the rest. The decision moves from open to decided.
4. **Close.** The assistant updates the decisions file, flips the queue entry to done, and adds the deadline that came out of the research. It shows the board and calendar changes, waits for a yes, and applies the approved writes. It then reconciles successful task writes and changed pages into the snapshot before composing the next agenda. All board reads succeed, so it advances the checkpoint to the UTC date the board check began. It shares the agenda only after review and approval, appends the session record, and reports which surfaces were updated.

The session record shows the result.
