---
name: cleanup
description: Clean up a Desynq project into production Flutter code. Use when the user runs /desynq:cleanup or asks to clean up a Desynq export.
argument-hint: <project id or project page URL>
disable-model-invocation: true
---

Clean up Desynq project `$ARGUMENTS`.

1. Call the desynq `start` tool with that project. If it says the project is being prepared, call it again. If it says you are not signed in, tell the user to run `/mcp`, choose desynq, sign in, run this command again, and stop.
2. Run the `desynq-sync init …` command it gives you, then work inside that folder.
3. Make one task per build group so the user can follow progress.
4. Hand the plan to the `desynq:planner` agent. It writes the theme and shared widgets.
5. Build the groups in the order `start` lists them, each with the agent named beside it. Give the agent the project id, the folder and the group's screen names. Do not build screens yourself. Mark each task done as its agent reports.
6. When every group is done, call `finish` and give the user its summary in a few lines.

Keep messages to the user short: what is being worked on and what passed.
