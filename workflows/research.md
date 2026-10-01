# Research

Use when the user asks you to research a topic, or says "do some research" without naming one.

Approval contract: see `AGENTS.md`. Writing the research file is allowed without asking. Adding a research summary to a task page on the board is a board write and needs a yes first. This workflow never edits `state/research-queue.yaml`. Session close does that.

## 0. No topic given

Read `state/research-queue.yaml`. Pick the queued entry (`status: queued`) that has the smallest `priority` number. Treat its `why` as the brief and its `output` as the path to write to. Skip an entry whose `output` file already exists, and tell the user, because it probably needs a status change at session close. If a topic was given, ignore the queue.

## 1. Gather

Use whatever search tools the assistant has. Prefer official and primary sources. Note the date you read each source. If you cannot reach a source, say so rather than filling the gap from memory.

## 2. Check the situation

Read the facts in `state/facts.yaml` and the constraints in `PLAN.md` that the answer depends on. If the research rests on an assumption, name it. Rules, fees, and eligibility depend on the household's circumstances, so write down the circumstances you assumed.

## 3. Save the findings

Write the file at the queue's `output` path, or at `Research/<area>/<topic>.md` for an ad hoc topic, using `templates/research-file.md`.

## 4. Offer follow-ups

List, in chat, any facts to add, deadlines to create, decisions to open, or tasks to create. These are proposals. They enter `state/` at session close and reach the board only after approval.

If the user wants the findings on a task page, draft the short summary and the link, show it, and write it after a yes.

## 5. Present

Give a concise summary: the top three to five options with pros and cons, a recommendation, and what is uncertain. Say plainly what you could not confirm. Do not present research as legal, tax, or medical advice.

If this came from the queue, mention that its status needs to change to `done` at session close.
