# Relocation plan

Fill this in with your assistant in the first session. Replace every prompt in angle brackets. Keep it short: this file states strategy and constraints, while tasks, facts, and deadlines live elsewhere (see `AGENTS.md`). Changes to this file need your approval.

Last reviewed: `<YYYY-MM-DD>`

## 1. Situation

- Who is moving: `<names or labels, and anyone depending on the move>`
- Moving from: `<country and region>`
- Moving to: `<country and region>`
- Why now: `<the reason in one or two sentences>`
- What the move must preserve: `<income, coverage, schooling, a career, a pet, a visa path, or other must-haves>`
- What is flexible: `<things you are willing to trade away>`

Do not assume anything about citizenship, dependants, housing, or employment. Write down what is true for you.

## 2. Timing model

Pick one and delete the other.

**Window-led.** `<earliest and latest acceptable move dates>`. The plan waits for specific events (triggers) before committing. See section 4.

**Date-led.** `<fixed target date>`, usually because travel or a lease is booked. Every task gets a due date back-planned from this one. A backstop date: `<latest acceptable date if the target slips>`.

You can start window-led and switch to date-led when something locks the date. If you switch, note the date and the reason here and in `state/decisions.yaml`, then re-date the open tasks.

## 3. Constraints

List the limits that shape every other choice.

| Area | Constraint | Source | Last checked |
|---|---|---|---|
| Work and income | `<for example: a notice period, remote-work limits, a gap between jobs>` | `<where you learned it>` | `<YYYY-MM-DD>` |
| Health coverage | `<what coverage exists at each stage>` | | |
| Money | `<a runway amount or a rule of thumb, kept in the private copy>` | | |
| Immigration and identity | `<visa, permits, passports, anything with a processing time>` | | |
| Housing | `<current lease or sale terms, and what you need at arrival>` | | |
| Family | `<schooling, childcare, care for relatives>` | | |
| Other | | | |

Anything with a fixed date also belongs in `state/deadlines.yaml`. Anything you have confirmed belongs in `state/facts.yaml` with its source.

## 4. Phases and triggers

Phases group the task board. Rename or drop any that do not fit.

| Phase | Meaning | Enters when |
|---|---|---|
| A Foundation | Research, paperwork that can start now, and no-regret preparation | Always open |
| B Ready | Everything prepared so a decision can be acted on quickly | `<condition>` |
| C Hold | Waiting on a trigger before spending or committing. Skip this phase in a date-led plan. | `<condition>` |
| D Locked | The date is fixed and tasks are back-planned from it | `<condition, such as booked travel>` |
| E Landing | Arrival and the first weeks | `<condition>` |

Triggers are events that move the plan. A soft lock narrows the window without fixing it (for example, an offer still under consideration). A hard lock fixes the date (for example, travel booked or a notice given). When a trigger happens, follow `workflows/trigger-activation.md`.

| Trigger | Type | What it activates |
|---|---|---|
| `<event>` | Soft Lock or Hard Lock | `<task categories or phases>` |

## 5. Responsibilities

Who owns what. Use the owner labels from the task schema in `AGENTS.md`.

- `<person or label>`: `<areas>`
- `<person or label>`: `<areas>`
- Shared: `<areas that need both people>`

Individual work that affects only one person, such as a personal job search, stays in that person's own area. Only its effects on timing, income, and coverage enter the shared plan. See `Job-Search/README.md`.

## 6. Weekly rhythm

- Shared review: `<day, length, who attends>`. Starts with `workflows/session-start.md`.
- Solo sessions: whenever you work with the assistant. They end with `workflows/session-end.md`, just like shared ones.
- Weekly summary: `<when you want one, and for whom>`.

## 7. Open questions

Questions you cannot answer yet. Move each into `state/decisions.yaml` once it has options.

- `<question>`
