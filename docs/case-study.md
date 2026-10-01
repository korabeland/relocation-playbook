# Using AI to Coordinate an International Relocation

I used an AI assistant to help coordinate an international relocation across logistics, research, household decisions, and deadlines. As the plan changed, the system exposed a weakness: important facts were scattered across notes and shared pages. I redesigned the workflow around structured records and a consistent session close, so the next conversation could start from a clearer picture.

This is a case study about the process. It is not about the household. Every example below is invented, and I have left out the names, places, employers, providers, and figures of the real move. I also leave out how the move turned out. The plan kept changing after the period described here, and I would rather describe what the method did than claim an outcome.

## What I am claiming, and what I am not

I am claiming that an assistant working from a small set of plain files was useful for research, drafting, and keeping a changing plan visible. I am also claiming that the first version of the system failed in a specific, fixable way, and that I changed it.

I am not claiming that it saved a measured amount of time, that it prevented missed deadlines, or that it ran by itself. I did not measure any of those things. Everything the assistant did, it did while I was in the conversation. The scheduled agents in my original design were never built. See [design-history.md](design-history.md) for those ideas.

## 1. The coordination problem

A move between countries is many problems that depend on each other: leaving a home, setting up a new one, work and income, health coverage, identity documents, tax administration, shipping, selling things, and the people involved. A change in one area ripples into others. A shifted travel date affects coverage start dates, the notice on a lease, the timing of a sale, and the money you need on a given week.

The hard part was not any one question. It was keeping the whole picture consistent as it moved.

## 2. The first system

I started simple and kept the parts separate by job.

```text
   Strategy            Tasks                 Knowledge              Continuity
   PLAN.md      Task board (Notion)    Research/, Documents/     memory index
   phases,        status, owner,        options, drafts,         a short list of
   constraints    phase, due            shared outputs           pointers
        \              |                      |                      /
         \_____________|______________________|_____________________/
                                  |
                          the assistant reads these
                          at the start of a session
```

The plan held strategy and constraints. A task board held tasks. A folder held research and outputs that the people I was moving with could open. A short memory index told the assistant where things were.

Each session worked like this: the assistant read the plan and the board, we worked through questions together, it researched and drafted, and I approved any changes to outside services. Short weekly reviews gave us a rhythm for making decisions rather than reconstructing the situation each time.

## 3. What the assistant actually handled

Within that structure it did these jobs:

- **Research.** It compared options for administrative, financial, healthcare, and shipping questions, and wrote them up with options, a recommendation, and what was uncertain.
- **Drafting.** It prepared checklists, comparison tables, and drafts of documents. It never sent or submitted anything.
- **Budget and sale planning.** It helped structure a scenario budget around four buckets: exit, travel, one-time setup, and recurring costs. It helped plan a household sale by separating the date an item is listed from the date it is handed over.
- **Task proposals.** It suggested new tasks, status changes, and dependencies, which I approved before anything was written to the board.
- **Session records.** It summarized each session and tracked decisions.

At one review, a session record shows three independent research questions running in parallel while we worked through the rest of the agenda. I am relying on that record. I did not keep a separate trace of how the jobs ran.

I treated its research as a lead to check, not as advice. Rules, fees, and eligibility change, and answers depended on my circumstances at the time they were written.

## 4. The plan kept changing

Early on, the plan waited for events. Some triggers narrowed the window without fixing it, and others, like booking travel, fixed the date. At one point I stopped waiting. A review changed the planning from "wait for a trigger" to "back-plan from a date". Once travel was booked, the date locked.

Later, a change in work circumstances shifted the income and coverage assumptions, which touched the budget, the timing of other tasks, and the coverage plan. Each change landed as several questions at once. This is where keeping facts in one place started to matter.

## 5. What broke

Several things went wrong, and they are the most useful part of this story.

**A stale shared agenda.** The shared agenda page was refreshed only after weekly reviews. Solo sessions in between changed the plan without updating it. After several weeks of this, the agenda no longer matched the work. Here is an invented illustration of the mechanism.

```text
Agenda page, written after the review on Monday:
  Open: "Decide notice date on the current home."

Wednesday, a solo session:
  The notice was given. The session ended without a close.

Next review, Monday:
  Agenda page still says: "Decide notice date on the current home."
```

The agenda was not wrong because anyone was careless. The process only refreshed it in one kind of session.

**Facts in several places.** A shipping-date estimate in the memory index disagreed with the due date on the board. Two deadlines on the board were missing from the condensed list in memory. When the same fact lives in three places, it drifts.

**Expensive starts.** Early feedback was that starting a session was too costly. The assistant read a lot each time. A cached copy of the board, and a rule to fetch only changed pages, came out of that.

**Integration limits.** The connector to the task board could not read the whole board in one query on my plan. Reading pages one at a time was slow. A shared spreadsheet could be read but not written, so I handed a table over by pasting it in. These are observations of my setup at the time, not facts about those products today.

**Contradictory rules.** My operating contract said in one place that the assistant could write to files it owned, and in another that it must always ask before modifying anything. Shorter workflows did not repeat the newer approval step at all. In this kit I wrote one approval contract and pointed every workflow at it.

**Auditing the auditor.** I asked the assistant to review the system and list gaps. It was useful, and it was also wrong in one place. It said a certain topic appeared nowhere in the earlier work. Older research and an early session record already covered it, though too shallowly for how my circumstances had changed. The better conclusion was that the earlier treatment needed to be deeper, not that it was absent. I now check an assistant's audit against older evidence before acting on it.

**Overconfident fields.** One entry in my "verified facts" file said, in its own text, that it was an unconfirmed inference. A field named "verified" had invited me to trust it. This is why the kit separates confirmed facts from assumptions and recommendations, and why a review date does not make a fact certain.

## 6. The redesign

After the stale-agenda problem became clear, I rebuilt the foundation around a few small structured records.

- **Facts** with a source, a review date, and a "check again by" date, plus a confidence label.
- **Deadlines** with a hard or soft marker and an owner.
- **Open decisions** with options and a recommendation.
- **A research queue** with priorities, so "do some research" has an answer.
- **A cached task board** with a date and a note on how complete it is.
- **A session close that runs after every session**, solo or shared, and composes the shared agenda from those records instead of from memory of the conversation.

The close also ends with an honest report of which surfaces were updated and which were not. If a write to an outside service fails partway, it says exactly what is current and what is stale.

I also designated one writer per file. It is a convention that makes edits predictable. Nothing enforces it, and I did not treat it as proof that conflicts could not happen.

Here is an invented fact with provenance, next to an assumption that must not be mistaken for it.

```yaml
- id: notice-period
  fact: "The current lease requires 60 days written notice."
  confidence: confirmed
  source: "Lease clause, read in session"
  verified_on: 2031-01-10
  verify_by: 2031-01-15
  visibility: household

- id: sea-freight-time
  fact: "Sea freight takes about six weeks."
  confidence: assumption
  source: "A general FAQ. Not a quote."
  verified_on: null
  verify_by: 2031-01-25
  visibility: household
```

And an invented deadline correction, as it would show up at close:

```text
The memory index listed a booking as due 1 February.
The board task said 25 January.
The board is authoritative for tasks.
The index was corrected. The deadline record already matched.
```

## 7. What the redesign showed

Two small results are worth reporting.

The first reconciliation after the redesign caught a wrong date and some missing obligations. And work queued in the research queue produced two new research files and updated the records.

That is the extent of what I can say. The redesign is not proof that drift ended. Later snapshots still showed some retired tasks, a marked duplicate, and overlapping entries. A completed deadline recorded in one place was not yet reflected in an earlier snapshot. One of my own working documents had a summary that disagreed with its own category counts. A system like this reduces the chance of drift. It does not remove the need to look.

I also cannot show that preparation took less time, or that anything was caught that would otherwise have been missed beyond the examples above.

## 8. What remains unproven, and what you can reuse

Unproven, because I never built them:
- A scheduled morning check on the records
- A weekly run that prepares a brief
- A text-message capture channel
- A recurring audit of the plan
- An arrival concierge that drafts documents for review

They are described, labeled as ideas, in [design-history.md](design-history.md). Treat them as design notes, not features.

What is reusable is the interactive method:

1. Separate strategy, tasks, knowledge, and continuity.
2. Keep facts, deadlines, and decisions in small structured records, and compose summaries from them.
3. Mark how sure you are, and when you will check again.
4. Run one close at the end of every session, and have it say what it did not update.
5. Keep one approval rule: draft, show, then write after a yes.
6. Check an assistant's research and its audits against what you already knew.

The kit in this repository is those procedures, restated for any pair of countries. Start with the [README](../README.md) and the [adoption guide](adoption.md).
