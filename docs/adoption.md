# Adoption guide

How to turn this kit into your own working relocation workspace. Plan for a first session of about an hour.

## Before you start

- You need an AI assistant that can read and write files in a folder you control, and follow written instructions. The original ran in a terminal assistant. Other assistants may work, but only the original setup has been tried.
- Decide whether you will use outside services. A Notion task board, a shared Drive-style folder, and a calendar make up the full setup described here. The folder, plan, state files, templates, and session workflows work on their own. Without a task board the loop is simpler, and without a shared folder you will share outputs another way.
- Decide who else is moving with you and what they should see. Sharing with your household is not the same as publishing, and your working copy should never be public.

## 1. Make a private working copy

Copy the kit's files into a new folder only you and your household can reach, such as a private Drive folder. The kit repository stays the clean template. Your folder is the live instance. Keep the two separate so that your dates, finances, and documents never reach a repository.

If you put your working copy under version control, keep it in a private repository of its own, and check what you commit. `.gitignore` in this kit excludes common local files and document formats, but it cannot know what is sensitive to you.

You do not need Git to run the plan.

## 2. Fill in the plan

Open `PLAN.md` with your assistant and work through it section by section. Say where you are moving from and to, what must be preserved, and what is flexible. Choose the timing model: a window with triggers, or a fixed date. Do not copy assumptions from the example. The example assumes two adults and a cat, and yours may be different.

Look at `examples/synthetic-relocation/PLAN.md` for how a filled-in plan reads.

## 3. Set up the task board

Follow `docs/notion-setup.md`, or decide to keep tasks in `state/board-snapshot.md`. The second option is a variation the original never ran, so expect to adjust the workflows' wording. Record your choice in the `[TASK_BOARD]` line in `AGENTS.md`.

## 4. Connect the assistant

Give the assistant access to the folder and, if you use them, to the board and the calendar. Set its permissions yourself and explicitly. Allow only what you are comfortable with. Do not import another person's assistant configuration.

Fill in `[CONNECTED_SERVICES]` in `AGENTS.md`. See `docs/drive-and-calendar-setup.md`.

If your assistant has a memory feature, confirm how it works and where it stores data. See `memory/README.md`.

## 5. Seed the records

Add a handful of entries, no more:
- Five or so facts in `state/facts.yaml`, each with a source and a review date. Mark each as `confirmed`, `assumption`, or `recommendation`. Be strict.
- Any dated obligations you already know of in `state/deadlines.yaml`, marked hard or soft.
- Open decisions in `state/decisions.yaml`, with options.
- Two or three research questions in `state/research-queue.yaml`.
- A first set of tasks on the board, then an initial `state/board-snapshot.md` with its date and a coverage note.

Start with an empty `BACKLOG.md`. Do not bulk-load a large backlog.

## 6. Run one full cycle

Run a shared review or a solo session:
1. Start with `workflows/session-start.md`.
2. Agree priorities.
3. Research one question using `workflows/research.md`.
4. Make or record a decision.
5. Close with `workflows/session-end.md`.

Then check that the records, the snapshot, the agenda, and the memory index agree with what was actually saved. The close should say which surfaces were updated and which were not. If it reports a clean close and something is stale, treat that as a bug in your setup.

`examples/synthetic-relocation/README.md` walks through the same cycle on an invented household.

## 7. Keep a rhythm

- Hold short shared reviews at the interval your plan sets.
- Close solo sessions the same way you close shared ones. Skipping the close was the main cause of drift in the original project.
- Recheck facts when they pass their review date. Revise the plan when circumstances change, and record the change.
- Mirror important deadlines to a calendar if you use one, after approving each change.

## Things to watch

- **Drift.** The same fact stored in two places will disagree sooner or later. Write it in `state/` first and compose prose from it.
- **Stale caches.** The board snapshot is a copy. Its date tells you how much to trust it.
- **Overconfident records.** A date in `verified_on` shows that someone looked. It does not prove the fact is still true.
- **Assistant audits.** If you ask the assistant to review its own system and it reports gaps, check those claims against earlier work before acting on them.
- **Outdated research.** Rules and fees change, and your own circumstances change. Reread old research when either happens.
- **Integration limits.** Services differ in what an assistant can read or write. Test each integration with a small action before you depend on it.

## What this kit does not do

It does not run on a schedule, send messages, give legal, tax, or medical advice, or submit anything for you. Those ideas are in `docs/design-history.md` as future ideas only.
