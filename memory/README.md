# memory

Continuity between conversations. An assistant starts each conversation without remembering the last one, so the workspace keeps a short index for it to read.

This kit does not depend on any particular memory service. Pick one of these:

1. **Use the assistant's own memory feature, if it has one.** Keep what it stores to a short index of pointers, as described in `AGENTS.md`.
2. **Keep an index file here.** Create `memory/index.md` in your private copy. It lists the last-checked date, the active action items, recent decisions, and a table of completed research with file paths. Keep it under about 100 lines.
3. **Use neither.** The records in `state/` and `Weekly/` already carry most of the continuity. Session start reads them every time.

Topic notes that grow too long for the index go in this folder as separate files, linked from the index. An example is a note on how your budget is structured, with the pointer in the index and the numbers in your private budget workbook.

Rules:
- Store pointers and one-line summaries, not findings.
- Prune on every update.
- Reflect what was actually saved, not drafts.
- Keep real figures and identifiers out of anything you share. This folder is private.
