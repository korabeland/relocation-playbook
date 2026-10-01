# Trigger activation

Use when the user reports an event that moves the plan, such as an offer being accepted or travel being booked. Triggers are defined in `PLAN.md`.

Approval contract: see `AGENTS.md`. Changing task status on the board needs a yes first. Edits to `PLAN.md` need a yes. Changes to `state/` happen at session close.

1. Identify the trigger from `PLAN.md`: is it a soft lock (narrows the window) or a hard lock (fixes the date)? If it is not listed, say so and ask whether to add it.
2. Find affected tasks on the authoritative board by searching or filtering for the matching Trigger value across all task pages, regardless of edit date. Read the matching pages to confirm Trigger and current Status before selecting the batch. The snapshot has no Trigger field and cannot establish this list. Use supported searches and individual page reads; do not attempt an unconfirmed bulk read. If matching tasks cannot be found or read, report the gap and do not present the batch as complete.
3. Draft the batch change: tasks to move from Not Started to In Progress or another status. Show the whole list and wait for a yes. One yes covers the list you showed.
4. Present priorities: the top five tasks to act on this week, and why.
5. If the trigger changes the timing, propose the edit to `PLAN.md`, including the timing model if it switches from window-led to date-led. Show it and wait for a yes. If the date locks, list the deadlines that need to be added or re-dated.
6. Remind the user that the facts, deadlines, and decisions this changed are recorded at session close.

If the plan switches to date-led, expect a stretch of re-dating. Do the highest-risk dates first.
