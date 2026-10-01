# Shared folder and calendar setup

Notes for the optional shared folder and calendar used in the original setup. Identifiers are placeholders. Test each connection with a small action before you rely on it.

## Shared folder

The original kept the working copy of this kit in a private Drive folder that the household could open. The folder served two purposes: the assistant read and wrote files there, and the household read the outputs.

Layout in your private copy:

```text
<WORKSPACE_FOLDER>/
  AGENTS.md  PLAN.md  BACKLOG.md
  state/  templates/  workflows/
  Research/  Documents/  Weekly/  memory/  Job-Search/
```

Guidance:
- Use `Documents/` as the folder the other person opens. Put outputs they should read there, and nothing sensitive that they should not see.
- Keep the folder private. Give each person access one by one. Do not use a public link.
- A synced Drive folder can create conflict copies if two tools write the same file at once. This is why each file has one designated writer in `AGENTS.md`. The rule is a convention. If you ever see a copy with "conflict" in its name, resolve it by hand.
- Native spreadsheets and documents may appear in a synced folder as small pointer files with no content. The assistant cannot read those through the file system. If you want it to use one, export it to a file.
- The original could read a shared spreadsheet but not write into its cells. A table was handed over by pasting it in. Check what your setup allows.

## Calendar

Calendar reminders mirror selected entries in `state/deadlines.yaml`. They are a convenience. The deadline file stays the record.

How the original used it:
- Create a calendar shared with your household, called something like `Move`.
- Each mirrored deadline becomes an all-day event named `[MOVE] <what>`, with reminders a week ahead and a day ahead.
- The event reference returned by the calendar is stored in the deadline's `calendar_event` field.
- When a deadline is added, re-dated, completed, or dropped, session close shows the matching calendar change. It makes the change after a yes. A re-date updates the existing event. A done or dropped deadline deletes it.
- Mirror hard deadlines first. Mirror soft ones only if you want the nudge.

A reference stored in `calendar_event` shows that an event was created. It does not prove the event still exists or that a reminder fired. If a date matters, check the calendar itself.

Placeholders for your private copy:

```text
Calendar name:   <CALENDAR_NAME>
Calendar ID:     <CALENDAR_ID>
```

## Permissions

Give the assistant the least access that works. For the folder, that is read and write on the workspace folder only. For the calendar, that is create, update, and delete on the one calendar. Remember that the assistant asks before each write under the approval contract, and that you can say no.
