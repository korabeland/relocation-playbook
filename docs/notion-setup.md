# Task board setup (Notion)

The original setup kept tasks in a Notion database. This page describes it generically. All identifiers are placeholders. There is no export or provisioning script, so you build the board yourself, by hand. Notes about what the assistant could and could not do through a connector are historical observations of one setup. Test your own before relying on them.

Other task tools could work, but only this one has been tried.

## 1. Create the database

Create a database called `Relocation Tasks`, with these properties.

| Property | Type | Values |
|---|---|---|
| Task | Title | |
| Phase | Select | A Foundation, B Ready, C Hold, D Locked, E Landing |
| Status | Select | Not Started, In Progress, Waiting, Done |
| Owner | Select | Your own labels, for example `me`, `partner`, `both` |
| Trigger | Select | None, Soft Lock, Hard Lock |
| Category | Select | Finance and Tax, Healthcare, Family and Dependants, Transport, Admin, Logistics |
| Due | Date | |

Match these with `AGENTS.md`. If you rename a value, rename it in both places and in `PLAN.md`.

Use `templates/task-page.md` as the page body template.

## 2. Optional pages

These were useful in the original setup, and you can create them if you want them. None is required.

- **Dashboard.** A page showing the board filtered by Phase and Status, for the people who prefer a visual view.
- **Decision log.** A table of numbered decisions with date, decision, outcome, and notes. `decision_log_ref` in `state/decisions.yaml` can point at a number here.
- **Next session page.** The agenda composed at session close from `state/`. The assistant drafts it, you approve it, and then it is written.

## 3. Placeholders to fill in your private copy

Keep these in your private working copy only. Never commit them to a shared repository.

```text
Tasks database:      <TASKS_DATABASE_URL>
Decision log:        <DECISION_LOG_URL>
Next session page:   <NEXT_SESSION_PAGE_URL>
Dashboard page:      <DASHBOARD_URL>
```

## 4. Connect the assistant

Give the assistant access to the workspace through whatever connection your assistant supports. Grant it access to only the pages it needs. Test with a harmless read, then a harmless write on a test task. Confirm each kind of operation works before building a habit around it.

## 5. What to expect

In the original setup, the connector had limits that shaped the design:
- Reading the whole board in one structured query was not available on that workspace's plan. Reading single pages and searching worked, which is why the board snapshot exists.
- Reading each page one at a time was slow and costly, which is why session start reads the snapshot and fetches task pages changed on or after its checkpoint date (inclusive, from midnight UTC). Failed reads retain the old checkpoint at session close. Trigger activation also reads matching tasks regardless of edit date because Trigger is not cached.

Your workspace may behave differently. If bulk reads work for you, you can simplify. Keep the snapshot anyway if you want a dated copy you can compare against.

## 6. Writes need approval

Every write to the board follows the approval contract in `AGENTS.md`: draft in chat, show the exact change, then write after a yes.
