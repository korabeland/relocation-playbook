# Relocation Playbook

A practical kit for using an AI assistant to coordinate a complex move between countries. It provides planning templates, research and document workflows, decision records, and session routines that keep changing facts and deadlines visible. The accompanying case study explains how the method evolved, including the problems that prompted its redesign.

This repository holds the reusable kit only. It is not anyone's live relocation record. You keep your own working copy somewhere private and fill it in with your own countries, dates, and people.

**Status: private while under review. A license will be chosen before any public release.** Until then, no reuse rights are granted.

## What this is

The method came from one real relocation planned with an AI assistant working inside a folder of plain files. The assistant read a strategic plan, a small set of structured records, and a quick-capture inbox. It then researched questions, drafted documents, proposed task changes, and closed every session by updating those records.

Everything here is a set of instructions and templates that an assistant follows during a conversation. There is no program to install, no scheduler, and no service this repository runs for you.

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
| Scheduled agents, text-message intake, recurring audits, an arrival concierge | Never built. They appear only in `docs/design-history.md`, labeled as future ideas. |

The kit makes no claim about time saved or missed deadlines avoided. See the case study for what the original process did and did not show.

## How to adopt it

The short version. The full guide is `docs/adoption.md`.

1. Copy this kit into a private working folder your assistant can read and write. Keep that copy separate from this repository so personal data never lands here.
2. Fill in `PLAN.md` with your own origin, destination, constraints, and a target window or fixed date.
3. If you use a task board, create it from `docs/notion-setup.md`. Without one, you can track tasks in `state/board-snapshot.md` directly, but the original setup never ran that way.
4. Seed a few facts, deadlines, decisions, and research questions in `state/`, each with a source and a review date.
5. Run one review session using `workflows/session-start.md`, research one question, and close with `workflows/session-end.md`.
6. Repeat on a short rhythm, and close solo sessions the same way you close shared ones.

## What you need

- An AI assistant that can read and write files in a folder you control. The original ran in a terminal assistant; any assistant that follows the instructions in `AGENTS.md` should work, though only the original setup has been tried.
- Optional: a Notion workspace for the task board, a Drive-style shared folder for outputs your household reads, and a calendar for deadline reminders.
- No programming is required.

## Privacy

Your working copy will hold sensitive material: identity documents, finances, health, tax, and housing. Keep it private. `docs/adoption.md` explains how to separate the shareable kit from your live instance, and `.gitignore` excludes the usual local files. Sharing a record with your household is not the same as publishing it.

## Where to start reading

1. `docs/case-study.md` for the story and the lessons.
2. `AGENTS.md` for the contract the assistant follows.
3. `examples/synthetic-relocation/` for what filled-in records look like.
