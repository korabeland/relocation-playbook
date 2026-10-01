# Weekly summary

Use when the user asks for this week's summary.

Approval contract: see `AGENTS.md`. Writing the file in `Weekly/` is allowed without asking. A summary that another household member will read is shown to the user first.

1. Read `state/board-snapshot.md`, `state/deadlines.yaml`, and `state/decisions.yaml`. Check the board for task pages changed on or after the snapshot date (inclusive, from midnight UTC), even if the date is today. If the snapshot is empty or undated, establish initial coverage without an unconfirmed bulk read. Use successfully read pages for the summary, flag unread task status as unverified, and report read failures. Session close alone saves the reconciliation checkpoint, retaining its prior date on any read failure.
2. Compose `Weekly/YYYY-MM-DD.md` with `templates/weekly-summary.md`, from those records.
3. Leave out any entry marked `private`, unless the reader is the person it belongs to.
4. Keep it readable in two minutes. Plain language, no tool names.
5. Show the user the summary and mention any entry you left out as private.

This workflow summarizes. It does not change `state/`. Changes happen at session close.
