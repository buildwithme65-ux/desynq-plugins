---
name: cleanup
description: Clean up a Desynq project into production Flutter code. Use when the user runs /desynq:cleanup or asks to clean up a Desynq export.
argument-hint: <project id or project page URL>
disable-model-invocation: true
allowed-tools:
  - mcp__plugin_desynq_desynq__start
  - mcp__plugin_desynq_desynq__naming
  - mcp__plugin_desynq_desynq__names
  - mcp__plugin_desynq_desynq__pack
  - mcp__plugin_desynq_desynq__look
  - mcp__plugin_desynq_desynq__check
  - mcp__plugin_desynq_desynq__tune
  - mcp__plugin_desynq_desynq__status
  - mcp__plugin_desynq_desynq__finish
  - Bash(desynq-sync *)
  - Bash(desynq-sync)
  - Bash(dart analyze *)
  - Bash(dart format *)
  - Bash(flutter pub get *)
  - Bash(flutter pub get)
  - Read
  - Write
  - Edit
  - Glob
  - Grep
  - Agent
  - SendMessage
  - TaskCreate
  - TaskUpdate
  - TaskList
---

Clean up Desynq project `$ARGUMENTS`: call the desynq `start` tool with it and follow the instructions it returns exactly. Never stop to ask the user anything once the run starts: when something is unclear, pick the most likely answer and list it in the final summary. If it says the project is being prepared, call it again. If it says you are not signed in, tell the user to run `/mcp`, choose desynq, sign in, run this command again, and stop.
