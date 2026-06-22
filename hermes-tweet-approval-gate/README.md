# Hermes Tweet Approval Gate Recipe

This recipe configures a workspace pattern for using [Hermes Tweet](https://github.com/Xquik-dev/hermes-tweet) with explicit human approval before any X/Twitter write action.

Give this directory to a coding agent and ask it to set up the approval gate in your current workspace.

```text
setup/configure hermes-tweet-approval-gate
```

Or point the agent at the public URL:

```text
setup/configure https://github.com/huiskylabs/agent-cookbook/tree/main/hermes-tweet-approval-gate
```

## The Pattern

The workflow separates social media work into 4 phases:

```text
read evidence -> draft options -> show action payload -> wait for approval
```

The pattern is intentionally small. It does not add a scheduler, queue, database, or publishing bot. It only gives future agents enough local rules to keep Hermes Tweet read-first and approval-gated.

## Setup Intent

When asked to set up this recipe, follow [Minimal Approval Gate](setups/minimal-approval-gate.md).

The expected starter structure is:

```text
AGENTS.md
social/
  hermes-tweet-approval-gate.md
```

Then configure the agent behavior:

- keep `XQUIK_API_KEY` in the runtime, never in prompts or Markdown;
- keep `HERMES_TWEET_ENABLE_ACTIONS` unset or false by default;
- use read-only Hermes Tweet tools before drafting;
- show the exact JSON payload before any write;
- publish only after explicit same-turn human approval.

Ask before adding scripts, automation, background monitors, or credential storage.
