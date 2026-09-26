---
name: cleanup
description: Clean up a Desynq project into production Flutter code. Use when the user runs /desynq:cleanup or asks to clean up a Desynq export.
argument-hint: <project id or project page URL>
disable-model-invocation: true
---

Clean up Desynq project `$ARGUMENTS`. You are the lead: you own every shared file and never build a screen yourself.

**Every step you take re-reads this whole chat — keep the lead to about 25 steps.** Big steps, no exploring, no screenshots of your own.

1. Call the desynq `start` tool. If it says the project is being prepared, call it again. If it says you are not signed in, tell the user to run `/mcp`, choose desynq, sign in, run this command again, and stop.
2. Naming, once, before download: call `naming`, look at both images once, then call `names` with one `old<TAB>new` line for every asset it lists. Name by meaning, never numbers.
3. Run the `desynq-sync init …` command from `start`; work inside that folder from now on.
4. Shared files, in one pass: the theme, shared widgets, routes and shell are already seeded. Adapt colours, font family, header, nav and button look to the design; replace every `TODO(seed)`; name every colour `naming` listed into AppColors. For each batch call `pack` with `missing: true` and add what it lists. Create one placeholder view per screen (a StatelessWidget returning `const SizedBox()`) and register every screen in `test/screens_list.dart`, so the project compiles while builders write. Run `desynq-sync`.
5. Make one task per batch. Start one `desynq:builder` agent per batch from `start`, ALL AT ONCE in the background. Give each: the project id, the folder, its screens, and the placeholder file and class for each. Then wait for their reports; do nothing else meanwhile.
6. For each 3-line report: fix what it lists in shared files (a token, a widget), sync. Any screen not PASS for a reason other than keyboard or harness: SendMessage the fix back to that builder; never fix a screen here. Then call `look` once for the batch with `width: 200` and check every icon and label is right. Mark the task done.
7. When every batch is done, call `finish` and give the user its summary in a few lines, plus every route or button action you had to guess.

Keep messages to the user short: what is being worked on and what passed.
