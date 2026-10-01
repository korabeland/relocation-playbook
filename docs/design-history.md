# Design history

How the original system developed, what was built, and what was only discussed. The kit in this repository packages the built parts. This page holds the rest.

Labels used here:
- **Built:** used in the original relocation, then restated in this kit.
- **Future idea:** designed or discussed but never built. Not part of the kit, and not promised.

## What was built

The method grew in stages, over several months of real use.

1. **Plan, board, and folder.** A strategic plan, a task board, a folder of research and shared outputs, and a short memory index. A first review fixed ownership of research and set a numbered log of decisions.
2. **Templates and workflows.** Templates for tasks, research, and summaries. Workflows for capture, backlog, research, documents, triggers, and summaries.
3. **Budget and sale planning.** A scenario budget with four buckets, and a household sale plan that separated listing dates from handover dates.
4. **A longer session close.** The close step grew to include a memory refresh.
5. **Date-led planning.** A review changed the plan from waiting on triggers to planning back from a date.
6. **The foundation redesign.** After the stale-agenda finding: structured records for facts, deadlines, and decisions; a research queue; a cached task board; a session close that runs after every session; and calendar reminders mirrored from the deadline file.

The restated kit keeps stage 6 as its center.

## Observed lessons

- Prose copies of a fact drift. One record per fact, with prose composed from it, held up better.
- A session close that only runs after shared reviews leaves solo work unrecorded.
- A "verified" field can still hold an unverified claim. A confidence label helps.
- An assistant's audit of its own system needs checking. It can overstate gaps.
- Connector limits shaped the design. They were observations of one setup, and they may not hold elsewhere.
- Conflicting approval wording across files leads to inconsistent behavior. One contract, referenced everywhere, is simpler.

## What was not built: future ideas

The original design discussed a larger system. None of it was built, and none of it is in the kit. Do not treat any of it as a capability.

### Scheduled daily check (future idea)
A run each morning that reads the state files and sends a nudge only when something needs attention. It would have needed a scheduler and a messaging channel.

### Scheduled weekly run (future idea)
A run before each shared review that would prepare a brief, draft a household digest as an unsent draft, and complete one research question from the queue.

### Text-message capture (future idea)
A way for the other household member to send a short message that would be captured into a dated file for later processing.

### Recurring audit (future idea)
A monthly pass that would test the plan against a pre-mortem checklist, in the manner of a red team.

### Arrival concierge (future idea)
A role that would draft outbound documents into an approval outbox and, after arrival, help with the first weeks. It would never send anything without approval.

### Single-writer enforcement (future idea)
The ownership table is a convention. Making it structural would need tooling that was never written.

### Open design questions that were never settled
- How to detect an outage in a scheduled run.
- How to schedule runs around travel.
- Whether message capture is worth the added surface.

## Decisions about this kit

Choices made when restating the system as a general kit:
- The kit is for any pair of countries. Users fill in their own.
- It holds templates and a synthetic example. It does not hold the original household's records.
- Folder names for templates and workflows are simplified to `templates/` and `workflows/`.
- Owner and visibility labels are generic.
- The task board setup is described with placeholders and is required for the task workflows. Calendar reminders and a shared output folder are optional.
- The kit is released under the MIT License; see `LICENSE`.
- The live workspace stays private. This repository holds only the shareable kit.
