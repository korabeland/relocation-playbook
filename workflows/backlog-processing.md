# Backlog processing

Use when the user asks you to process `BACKLOG.md`. This is manual. Nothing processes the backlog on its own.

Approval contract: see `AGENTS.md`. Creating tasks is a board write and needs a yes first. Clearing processed lines from `BACKLOG.md` is allowed once the board writes have been approved and done.

1. Read every item in `BACKLOG.md`.
2. For each item, check whether a similar task exists, first in `state/board-snapshot.md`, then on the board if the snapshot may be out of date.
3. Sort the items into three groups: new tasks, duplicates, and items that still need thinking.
4. Show the user the plan: for each new task, its title, Phase, Owner, Category, and Due if known. Wait for a yes. The user may edit or drop items.
5. Create the approved tasks on the board using `templates/task-page.md`.
6. Remove processed items from `BACKLOG.md`. Leave items that still need thinking, and say why.
7. Report in one line: how many items were processed, how many new tasks were created, how many duplicates were skipped, how many were left.

If a board write fails partway through, report exactly which tasks were created and which were not. Leave unprocessed items in the backlog. Never present a partial result as a clean one.
