# LLM Wiki Recipe

This recipe describes a local, agent-maintained wiki inspired by Andrej Karpathy's LLM Wiki pattern.

Inspiration: [Andrej Karpathy's LLM Wiki gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

Give this directory to a coding agent and ask it to set up or configure an LLM wiki in your current workspace.

```text
setup/configure llm-wiki
```

Or point the agent at the public URL:

```text
setup/configure https://github.com/huiskylabs/agent-cookbook/tree/main/llm-wiki
```

## The Pattern

An LLM wiki is not just a folder of notes. It is a compounding knowledge system:

```text
raw sources -> compiled wiki -> progressive context
```

The pattern is split into isolated ideas and concrete setups:

```text
ideas/
  01-compounding-knowledge.md
  02-evidence-vs-synthesis.md
  03-progressive-context.md

setups/
  minimal-markdown.md
```

The `ideas/` files contain only universal ideas. They do not contain setup instructions, usage guidance, or composition advice.

The `setups/` files describe concrete ways to instantiate the ideas.

## Setup Intent

When asked to set up this recipe, follow [Minimal Markdown](setups/minimal-markdown.md).

The expected starter structure is:

```text
wiki/
  index.md
  sources/
    README.md
  notes/
    README.md
  synthesis/
    README.md
AGENTS.md
```

Then configure the agent behavior:

- store raw source references separately from synthesized notes;
- update the wiki when new sources or useful conclusions arrive;
- use `wiki/index.md` as the starting point for context loading;
- load context progressively instead of loading everything;
- keep the behavior rules in `AGENTS.md` so future agents can follow them.

Ask before adding extra tools, databases, plugins, or automation.
