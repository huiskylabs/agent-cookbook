# agent-cookbook

Agent-readable recipes for AI agents.

Each recipe is a directory of Markdown files. Point Codex, Claude Code, Cursor, or another coding agent at a recipe directory and ask it to set up or configure the pattern in your current workspace.

Example:

```text
setup/configure https://github.com/huiskylabs/agent-cookbook/tree/main/llm-wiki
```

## Recipes

- [`llm-wiki`](llm-wiki/) - a composable version of the LLM-maintained wiki pattern inspired by Andrej Karpathy's LLM Wiki gist.
- [`hermes-tweet-approval-gate`](hermes-tweet-approval-gate/) - an approval-gated X/Twitter workflow pattern for Hermes Tweet.

## Related Writing

- [Software Will Spread Before It Becomes Code](https://huisky.xyz/agentic-things/software-will-spread-before-it-becomes-code) - the article that uses `llm-wiki` as a demonstration of structured intent.
