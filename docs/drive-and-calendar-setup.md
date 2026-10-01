# Shared folder and calendar setup

Notes for the optional shared folder and calendar used in the original setup. Identifiers are placeholders. Test each connection with a small action before you rely on it.

## Shared folder

Keep the live working copy accessible only to its owner and the assistant. Use a separate shared folder for reviewed, approved copies of household outputs. Sharing the workspace root would also expose private state, drafts, memory, research, and job-search notes.

Layout in your private copy:

```text
<WORKSPACE_FOLDER>/
  AGENTS.md  PLAN.md  BACKLOG.md
  state/  templates/  workflows/
  Research/  Documents/  Weekly/  memory/  Job-Search/
```

Guidance:
- Keep `Documents/` in the owner-only workspace as the place for drafts. After review and approval, copy selected outputs to the separate shared folder; do the same for any research or weekly record the household should read.
- Give household members access only to that shared folder, one by one. Do not share the workspace root or use a public link.
- A synced Drive folder can create conflict copies if two tools write the same file at once. This is why each file has one designated writer in `AGENTS.md`. The rule is a convention. If you ever see a copy with "conflict" in its name, resolve it by hand.
- Native spreadsheets and documents may appear in a synced folder as small pointer files with no content. The assistant cannot read those through the file system. If you want it to use one, export it to a file.
- The original could read a shared spreadsheet but not write into its cells. A table was handed over by pasting it in. Check what your setup allows.

## Calendar

Calendar reminders mirror selected entries in `state/deadlines.yaml`. They are a convenience. The deadline file stays the record.

How the original used it:
- Create a calendar shared with your household, called something like `Move`.
- Each mirrored deadline becomes an all-day event named `[MOVE] <what>`, with reminders a week ahead and a day ahead.
- The event reference returned by the calendar is stored in the deadline's `calendar_event` field.
- When a deadline is added or re-dated, session close shows the matching calendar creation or update and makes it after a yes. A re-date updates the existing event.
- When a deadline is done or dropped, tell the user to delete its reminder themselves. The assistant never deletes outside-service items.
- Mirror hard deadlines first. Mirror soft ones only if you want the nudge.

A reference stored in `calendar_event` shows that an event was created. It does not prove the event still exists or that a reminder fired. If a date matters, check the calendar itself.

Placeholders for your private copy:

```text
Calendar name:   <CALENDAR_NAME>
Calendar ID:     <CALENDAR_ID>
```

## Permissions

Give the assistant the least access that works: read and write on the owner-only workspace, and access to the separate shared output folder if you use it. For the calendar, allow creation and updates on the one calendar. Every outside-service write needs approval under the approval contract. Deletion is left to the user.
