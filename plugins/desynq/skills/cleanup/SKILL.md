---
name: cleanup
description: Clean up a Desynq project into production Flutter code. Use when the user runs /desynq:cleanup or asks to clean up a Desynq export.
argument-hint: <project id or project page URL>
disable-model-invocation: true
---

Clean up Desynq project `$ARGUMENTS`: call the desynq `start` tool with it and follow the instructions it returns exactly. If it says the project is being prepared, call it again. If it says you are not signed in, tell the user to run `/mcp`, choose desynq, sign in, run this command again, and stop.
