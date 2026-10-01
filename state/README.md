# state/

Small structured files that hold the facts, deadlines, and decisions of the move in one place each. Prose surfaces such as agendas, weekly summaries, and shared pages are composed from these files by the assistant at session close. They are not edited first and backfilled later. That order is the fix for a failure described in `docs/case-study.md`: the same fact written in several places drifts apart.

"Composed by the assistant" means exactly that. There is no program that renders these views. The assistant reads the files and writes the summary by following `workflows/session-end.md`.

The YAML records ship empty, with a commented example of one entry. The Markdown files contain prompts to fill in. Synthetic filled-in records are in `examples/synthetic-relocation/state/`.

## Files

### `deadlines.yaml`

Dated obligations. Fields:

| Field | Meaning |
|---|---|
| `id` | Short slug that stays the same across edits |
| `what` | One-line description |
| `due` | `YYYY-MM-DD` |
| `hardness` | `hard` for legal, booked, or fixed dates. `soft` for self-imposed ones that can slip a few days without real consequence |
| `owner` | `me`, `partner`, `both`, or your own labels |
| `unblocks` | What finishing this clears, or `null` |
| `calendar_event` | Calendar event reference once mirrored, otherwise `null` |
| `status` | `open`, `done`, or `dropped` |
| `visibility` | `household` or `private` (see below) |
| `note` | Optional, used sparingly |

### `facts.yaml`

Things you know or are relying on. Fields:

| Field | Meaning |
|---|---|
| `id`, `fact` | Slug and a one-line, self-contained statement |
| `confidence` | `confirmed` (checked against an official or primary source), `assumption` (believed but not checked), or `recommendation` (advice you are following but have not validated) |
| `source` | Where it was established: a session, a research file, an official page, a person |
| `verified_on` | `YYYY-MM-DD` last checked. Use `null` for an assumption that has never been checked |
| `verify_by` | Date after which the fact should be rechecked. A fact about a fixed future event can simply expire on the day of that event. Facts about a current snapshot, such as a rate or a balance, need an earlier date because they decay faster |
| `visibility` | `household` or `private` |

`verified_on` records that someone looked. It does not make the fact certain. An inference stays an `assumption` until you confirm it.

### `decisions.yaml`

Open questions waiting for a call. Fields: `id`, `question`, `options` (a list), `recommendation`, `status` (`open` or `decided`), `opened_on`, `decided_as` (`null` until a choice is made, then the outcome in one line), and `decision_log_ref` (a pointer to a longer record, if you keep one, otherwise `null`).

The session summary's "Decisions needed" section is composed from every `open` entry here, in plain language rather than raw fields.

### `research-queue.yaml`

Prioritized research questions. Fields: `id`, `topic`, `why` (the brief), `priority` (lowest number first), `status` (`queued` or `done`), and `output` (the path where the finished file goes). The research workflow takes the lowest-numbered queued entry when you ask it to "do some research" with no topic. Session close flips `status` to `done` after the output file exists.

### `contingencies.md`

Pre-mortem prompts: scenario, owner, first move. It is Markdown because a person should be able to read it quickly on a bad day. It is written for you to fill in. It is not advice about any country.

### `board-snapshot.md`

A dated copy of the task board: task, status, owner, due, phase. It does not contain Trigger values; trigger activation reads those from the board regardless of edit date. Session start reads the cache and fetches task pages changed on or after its date (inclusive, from midnight UTC). Session close reconciles successful task writes and changed pages before composing outputs, updating rows and counts.

The snapshot date is the last successful reconciliation checkpoint. Advance it to the UTC date the board check began only after the change lookup and all returned page reads succeed. On a failed read, keep the previous date and note the gaps in Coverage, even if some rows were updated. Inclusive queries catch later edits on the checkpoint day. An empty snapshot needs initial board coverage before a checkpoint is set. The coverage note describes known pages and read failures; a cache can still miss pages the assistant has not seen.

## Who writes what

One designated writer per file. This is a convention, not a lock. Nothing prevents a second tool or person from editing a file, so check the date and content before trusting it.

See the file ownership table in `AGENTS.md` for the designated writers, including who adds research queue entries and changes their status.

## The visibility field

- `household` means suitable to show the people who are moving together. It does not mean suitable for a public repository. Treat everything in your live instance as private.
- `private` means held back from anything another household member will read, such as a shared summary. Use it for one person's individual matters, for example a personal job search, or for any item the household has not agreed to surface.

Before composing anything another person will read, filter out `private` entries. Keep the workspace root owner-only; visibility labels filter outputs but do not restrict direct file access. Share only reviewed, approved copies in a separate household output location.
