# Relocation Playbook

Relocation Playbook turns an AI assistant into a chief of staff for an international move.

Moving countries means dozens of interdependent moving parts (visas, money, shipping, healthcare, housing, jobs, family logistics), and plans change weekly. The usual result is facts scattered across notes, chats, and spreadsheets, so nobody is sure what is current. This kit gives you and your assistant one shared system that keeps the move straight.

This repository holds the reusable kit only. It is not anyone's live relocation record. You keep your own working copy somewhere private and fill it in with your own countries, dates, and people.

**Status: private while under review.** This kit is released under the MIT License; see `LICENSE`.

## What this is

Everything here is a set of instructions and templates that an assistant follows during a conversation, working inside a folder of plain files. There is no program to install, no scheduler, and no service this repository runs for you. No coding is needed.

What it gives you:

- **One source of truth.** Facts, deadlines, open decisions, and research questions live in a few small structured records. Agendas and summaries are composed from them by the assistant, so nothing drifts in a forgotten note.
- **It knows how sure it is.** Each fact is marked confirmed, assumption, or recommendation, with its source and the date it was last checked.
- **Every session closes properly.** Solo or shared, the assistant ends by updating the records, proposing task board and agenda changes for your yes, and reporting anything it did not manage to update.
- **Life events reshape the plan.** When an offer lands or flights get booked, one workflow finds the affected tasks and proposes moving them forward, and helps you re-date from the new date. Deadlines are marked hard (legal or booked) or soft (self-imposed).
- **Research on tap.** Say "do some research" and the assistant takes the next priority question from a queue and writes up what it finds, with sources.
- **You stay in charge.** The assistant drafts and proposes, and you say yes before anything outside the folder changes. It never deletes items in your other services.
- **Built for households.** Every record is labeled household or private, an unlabeled record counts as private, and a personal job search stays separate from shared planning.

What you get: fill-in templates, eight step-by-step routines, a small invented example household, setup guides for Notion, Google Drive, and Calendar, and a case study.

Why trust it: it was used in one real relocation, and the case study is honest about that. It leads with what broke and why the system was rebuilt, and says plainly what was never built or measured.

What it is not: an app, an autopilot, or legal or tax advice for any particular country.

## What is in the kit

| Part | What it does |
|---|---|
| `AGENTS.md` | The operating contract: reading order, what the assistant may do alone, what needs your approval, and which file has which writer. |
| `CLAUDE.md` | Optional one-line router for assistants that look for that filename. |
| `PLAN.md` | Prompts for your strategy: situation, constraints, phases, triggers, and weekly rhythm. |
| `BACKLOG.md` | A quick-capture inbox, empty. |
| `state/` | Small structured records: facts with provenance, deadlines, open decisions, a research queue, contingency prompts, and a cached task board. |
| `templates/` | Task page, research file, and weekly summary layouts. |
| `workflows/` | Eight procedures the assistant follows: capture, backlog processing, research, documents, trigger activation, weekly summary, session start, session end. |
| `Research/`, `Documents/`, `Weekly/`, `memory/`, `Job-Search/` | Folder guides that say what goes where and who may see it. |
| `examples/` | A small invented household, plus a blank budget structure and a blank sale-list schema. |
| `docs/` | Adoption guide, setup notes for Notion, Drive, and Calendar, the case study, and design history. |

## What has and has not been tried

Be clear about what you are adopting.

| Piece | Honest status |
|---|---|
| The folder layout, plan, backlog, state records, templates, and session workflows | Used in one real relocation, then restated here in general wording. |
| The Notion task board and Calendar reminders | Used in the same setup. Setup notes here are written fresh with placeholders and have not been exercised by anyone else. |
| The synthetic example in `examples/` | Written for this kit. It shows the shapes of the records, not a tested run by another household. |
| Scheduled agents, text-message intake, recurring audits, an arrival concierge | Never built. See `docs/design-history.md` for the future ideas. |

The kit makes no claim about time saved or missed deadlines avoided. See the case study for what the original process did and did not show.

## How to adopt it

The short version. The full guide is `docs/adoption.md`.

1. Copy this kit into a private working folder your assistant can read and write. Keep that copy separate from this repository so personal data never lands here.
2. Fill in `PLAN.md` with your own origin, destination, constraints, and a target window or fixed date.
3. Create the required task board from `docs/notion-setup.md`. The board is authoritative; `state/board-snapshot.md` is only a cache.
4. Seed a few facts, deadlines, decisions, and research questions using the schemas in `state/README.md`.
5. Run one review session using `workflows/session-start.md`, research one question, and close with `workflows/session-end.md`.
6. Repeat on a short rhythm, and close solo sessions the same way you close shared ones.

## What you need

- An AI assistant that can read and write files in a folder you control. The original ran in a terminal assistant; any assistant that follows the instructions in `AGENTS.md` should work, though only the original setup has been tried.
- A task board set up using `docs/notion-setup.md`.
- Optional: a separate Drive-style shared folder for approved outputs your household reads, and a calendar for deadline reminders.
- No programming is required.

## Privacy

Your working copy will hold sensitive material: identity documents, finances, health, tax, and housing. Keep it private. `docs/adoption.md` explains how to separate the shareable kit from your live instance, and `.gitignore` excludes the usual local files. Sharing a record with your household is not the same as publishing it.

## Where to start reading

1. `docs/case-study.md` for the story and the lessons.
2. `AGENTS.md` for the contract the assistant follows.
3. `examples/synthetic-relocation/` for what filled-in records look like.
