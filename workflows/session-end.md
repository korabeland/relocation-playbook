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

## 2. Reconcile the board snapshot

Compare `state/board-snapshot.md` with the board. Find pages changed after the snapshot date, fetch only those, and update their rows. Set the snapshot date to today, even when nothing changed. Update the coverage note if you found pages that were missing. If you could not read the board, say so in the coverage note.

## 3. Draft board and calendar changes

If the session produced task changes, new tasks, or a logged decision for the board, show the exact changes and wait for a yes. Write only the approved ones.

If a deadline was added, re-dated, completed, or dropped, show the matching calendar change (create, update, or delete a reminder). See `docs/drive-and-calendar-setup.md`. Write only after a yes, and store the returned event reference in `calendar_event`.

## 4. Compose the next-session agenda from the records

Compose it from `state/`, not from memory of the conversation:
- What we decided last time: three to five plain-language bullets, from the records that changed.
- Action items, split by person, from open deadlines and the snapshot.
- Next session topics: two to four, each with one sentence on why now.
- Decisions needed: every `open` entry in `state/decisions.yaml`, written as question, options, and recommendation. Leave out entries marked `private`.

Show it to the user. After a yes, save it where the household reads it (a page on the board, or a file in `Documents/`). Do not publish an unreviewed agenda.

## 5. Save a session record

For a session where state changed, write `Weekly/YYYY-MM-DD-session.md` with four short parts: topics discussed, decisions made, tasks updated, next steps. Keep it scannable. It is a reference log and not a transcript.

## 6. Update the memory index

If the assistant has a persistent memory feature, or you keep `memory/`, refresh the index so it matches what was actually saved. Update the last-checked date and session number, active action items, recent decisions, and rows for new research files. Prune finished items. Do not store detail the records already hold.

On a session with no changes, still update the last-checked date and change nothing else.

## 7. Ask the after-action question

Ask the user one closing question: "Where did this process fall short today, and which steps were busywork?" Note the answer in the session record, or in memory if the assistant has it. If it shows a problem to fix in the kit, tell the user. Ask this even after a no-change session.

## 8. Report honestly

End with a short report that names each surface and what happened to it: updated, left unchanged because nothing changed, or not updated and why (declined, failed, could not be read). If something failed partway, say exactly which surfaces are current and which are stale, for example: "State files and the snapshot are current. The agenda page was not written, so the household copy is stale until the next session." Never let a partial failure read as a clean close.
