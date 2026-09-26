# Desynq for Claude Code

Turn a [Desynq](https://trydesynq.web.app) Figma export into clean, production
Flutter code, checked screen by screen against your design.

Available on Desynq paid plans.

## Install

In Claude Code:

```
/plugin marketplace add buildwithme65-ux/desynq-plugins
/plugin install desynq@desynq
```

## Use

Run every project from one folder, so Claude Code asks you to trust a folder
only once, and start Claude Code in auto mode:

```
mkdir -p ~/Desynq && cd ~/Desynq && claude --permission-mode auto
```

Then, in Claude Code:

```
/desynq:cleanup <project id>
```

The first time, Claude Code asks you to sign in: run `/mcp`, choose **desynq**,
and sign in with your Desynq account. After that a run goes from start to
finish on its own: the plugin pre-approves its own tools and never stops to ask
you anything. Any guesses it made (button actions, routes) are listed at the end.

### Updating

Third-party marketplaces don't update on their own. To get a new version:

```
/plugin marketplace update desynq
```
