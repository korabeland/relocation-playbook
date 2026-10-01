# Session start

Use at the start of a working session. There are two kinds. A shared review has other household members present. A solo session is you and the assistant. If it is unclear which one it is, ask.

Approval contract: see `AGENTS.md`. Reading is always allowed. Nothing in this workflow writes to the board, the calendar, or `PLAN.md`.

## Both kinds: load the picture

1. Read `state/board-snapshot.md`, `state/deadlines.yaml`, `state/decisions.yaml`, and `state/facts.yaml`. Note the snapshot date.
2. Read `PLAN.md` and `BACKLOG.md`.
3. Check the board for task pages changed on or after the snapshot date (inclusive, from midnight UTC), even if the date is today. If the snapshot is empty or undated, establish initial coverage from the board without an unconfirmed bulk read. Use successfully read pages for this session and report anything you could not read; do not treat unread task status as current. Session close alone saves the reconciliation checkpoint, retaining its prior date on any read failure.
4. Say in one or two sentences what changed since the last session and what is overdue or due within two weeks. Flag any fact past its `verify_by` date.

## Solo session

After step 4, ask what the user wants to work on. If they do not know, suggest the top item from the priorities in `AGENTS.md`. Work. End with `workflows/session-end.md`.

## Shared review

In a shared review, people who are not following the technical details are in the room. Use plain language throughout. No tool names, no jargon, no file names.

5. Compare the last session's action items with what happened. List three groups without judgment: done, still open, and new since last time.
6. Show the agenda that session close composed last time. It is a starting point from records, not the final word. Ask: "Here is what we planned to cover. Want to change or add anything?" Wait for an answer.
7. Take topics one at a time. For each, say what it is and why it is on the agenda, give the relevant status or findings, ask for a decision, and note action items as you go.
8. When the agenda is done or time is up, move straight into `workflows/session-end.md`. It does not need a separate request.

The agenda is a suggestion. If the agenda looks stale compared with the records in `state/`, say so and work from the records.
