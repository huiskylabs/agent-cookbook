# Minimal Approval Gate Setup

## Goal

Create the smallest useful workspace pattern for approval-gated X/Twitter work with Hermes Tweet.

Use Markdown rules only. Do not add scripts, daemons, queues, databases, or new credential stores unless the user asks.

## Prerequisites

- [Hermes Agent](https://hermes-agent.nousresearch.com) is installed.
- Hermes Tweet is installed as a Hermes Agent plugin.
- `XQUIK_API_KEY` is available in the runtime environment.
- `HERMES_TWEET_ENABLE_ACTIONS` stays unset or false until a publishing session is approved.

## Create This Structure

```text
AGENTS.md
social/
  hermes-tweet-approval-gate.md
```

## `AGENTS.md`

Create or update `AGENTS.md` with this behavior block.

If `AGENTS.md` already exists, merge these rules into it instead of replacing unrelated project instructions.

```markdown
# Agent Instructions

This workspace uses Hermes Tweet for approval-gated X/Twitter work.

## Hermes Tweet Approval Gate

For X/Twitter monitoring, drafting, or publishing tasks:

1. Start with read-only Hermes Tweet tools.
2. Summarize evidence with source URLs, tweet IDs, or account handles.
3. Draft no more than 3 candidate posts or replies.
4. Before any write, show the exact JSON action payload.
5. Ask a direct approval question after showing the payload.
6. Do not write unless the user gives explicit approval in the same turn.
7. If an auth, policy, or permission error occurs, stop and report it. Do not retry writes.

## Boundaries

- Keep `XQUIK_API_KEY` in the runtime environment only.
- Do not paste credentials, tokens, cookies, or private runtime values into prompts or Markdown.
- Keep `HERMES_TWEET_ENABLE_ACTIONS` unset or false except during an approved publishing session.
- Turn the action gate off again after publishing.
- Ask before adding scripts, background jobs, monitors, or automation.
```

## `social/hermes-tweet-approval-gate.md`

Create a local runbook with this content:

````markdown
# Hermes Tweet Approval Gate

Use this file when planning X/Twitter work with Hermes Tweet.

## Default Flow

1. Read evidence.
2. Summarize what matters.
3. Draft options.
4. Show the exact JSON action payload.
5. Ask for same-turn approval.
6. Publish only after explicit approval.

## Prompt Skeleton

```text
Use Hermes Tweet for this X/Twitter task.

Goal:
- Monitor:
- Audience:
- Voice:
- Claims or links to avoid:

Rules:
- Use read-only tools first.
- Cite source URLs, tweet IDs, or account handles.
- Draft at most 3 options.
- Show the exact JSON action payload before any write.
- Stop for approval before publishing.
- Do not retry writes after auth, policy, or permission errors.

Output:
- Evidence
- Drafts
- Recommended payload
- Approval question
```

## Done Check

- No credentials were written to files.
- The action gate was off before drafting.
- The payload was shown before publishing.
- The user approved in the same turn as the payload.
- The action gate was turned off after publishing.
````

## Done Check

After setup, confirm:

- `AGENTS.md` contains the approval gate rules;
- `social/hermes-tweet-approval-gate.md` exists;
- no secrets, tokens, cookies, or private runtime values were added;
- no scripts, automation, background monitors, or credential stores were added;
- a future agent can run the flow from the local runbook without rereading this cookbook.
