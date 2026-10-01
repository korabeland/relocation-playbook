# Session end (the session scribe)

Run at the end of every session, solo or shared. There is no shared-only gate. Skipping the close after solo work let a shared agenda go stale in the original project, which is the reason this workflow exists in this form. See `docs/case-study.md`.

Approval contract: see `AGENTS.md`. Writing the files assigned to session close in the ownership table is allowed without asking. Any board write, calendar write, or shared page write is drafted, shown, and written only after a yes. If a yes is withheld, leave that surface unchanged and list it in the final report as not updated.

## 0. Did anything change?

If the session was only discussion or reading, with no decisions, facts, deadlines, or tasks touched, say "no state changes this session". Skip to step 6, which still records that the records were checked. Otherwise do all the steps below.

## 1. Update the state files

Update only what changed:
- `state/deadlines.yaml`: new, moved, completed, or dropped deadlines.
- `state/facts.yaml`: newly confirmed or corrected facts. Set `confidence` honestly. A fact you inferred is an `assumption` until it is checked.
- `state/decisions.yaml`: open new questions, and for decided ones set `status`, `decided_as`, and any reference to a longer record.
- `state/research-queue.yaml`: set `status: done` where the `output` file now exists. Add new queue entries the user agreed to.
- `state/contingencies.md`: if a scenario was filled in or triggered.

Never edit a record to say something the user did not confirm in the session.

## 2. Draft board and calendar changes

If the session produced task changes, new tasks, or a logged decision for the board, show the exact changes and wait for a yes. Write only the approved ones.

If a deadline was added or re-dated, show the matching calendar creation or update. See `docs/drive-and-calendar-setup.md`. Write only after a yes, and store the returned event reference in `calendar_event`. For a completed or dropped deadline, tell the user to delete its reminder themselves; never delete it.

## 3. Reconcile the board snapshot

After the approved task writes, reconcile `state/board-snapshot.md` before composing any outputs. Include the returned values from every successful task write this session, including new tasks and writes from other workflows. Exclude declined or failed writes.

Note the UTC date when the board check begins. Find task pages changed on or after the saved snapshot date (inclusive, from midnight UTC), fetch those pages, and update their rows and counts. If the snapshot is empty or has no date, establish its initial coverage from the board before setting a checkpoint. Do not attempt an unconfirmed bulk read. Update the coverage note to describe what was read.

Advance the snapshot date to the date the check began only when the change lookup and every returned page read succeeded, even if no pages changed. If any read fails, retain the last successfully reconciled date and describe the unread pages in the coverage note. Successfully read rows and successful task writes can still be reflected, but the snapshot remains partially stale. Retaining the checkpoint ensures the next check includes unseen changes; inclusive queries also include edits later on the same day.

## 4. Compose the next-session agenda from the records

Compose it from `state/`, not from memory of the conversation:
- What we decided last time: three to five plain-language bullets, from the records that changed.
- Action items, split by person, from open deadlines and the reconciled snapshot. If board reconciliation was incomplete, flag task status as unverified and say which information could not be read.
- Next session topics: two to four, each with one sentence on why now.
- Decisions needed: every `open` entry in `state/decisions.yaml`, written as question, options, and recommendation. Leave out entries marked `private`.

Show it to the user. After a yes, save it to the household agenda page or copy the approved file from owner-only `Documents/` to the separate shared output location. Do not publish an unreviewed agenda.

## 5. Save a session record

For a session where state changed, append a separately numbered session section to `Weekly/YYYY-MM-DD-session.md`, labeled solo or shared. Create the file for the first session that day; preserve all earlier sections when adding another. Each section has four short parts: topics discussed, decisions made, tasks updated, next steps. Keep it scannable. It is a reference log and not a transcript. Keep the record owner-only; share only a reviewed, approved copy.

## 6. Update the memory index

If the assistant has a persistent memory feature, or you keep `memory/`, refresh the index so it matches what was actually saved. Update the last-checked date and session number, active action items, recent decisions, and rows for new research files. Prune finished items. Do not store detail the records already hold.

On a session with no changes, still update the last-checked date and change nothing else.

## 7. Ask the after-action question

Ask the user one closing question: "Where did this process fall short today, and which steps were busywork?" Note the answer in the session record, or in memory if the assistant has it. If it shows a problem to fix in the kit, tell the user. Ask this even after a no-change session.

## 8. Report honestly

End with a short report that names each surface and what happened to it: updated, left unchanged because nothing changed, or not updated and why (declined, failed, could not be read). If something failed partway, say exactly which surfaces are current and which are stale, for example: "State files and the snapshot are current. The agenda page was not written, so the household copy is stale until the next session." Never let a partial failure read as a clean close.
