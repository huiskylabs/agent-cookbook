# LLM Wiki Recipe

This recipe describes a local, agent-maintained wiki inspired by Andrej Karpathy's LLM Wiki pattern.

Give this directory to a coding agent and ask it to set up an LLM wiki in your current workspace.

```text
setup llm-wiki
```

Or point the agent at the public URL:

```text
setup https://github.com/huiskylabs/agent-cookbook/tree/main/llm-wiki
```

## The Pattern

An LLM wiki is not just a folder of notes. It is a compounding knowledge system:

```text
raw sources -> compiled wiki -> progressive context -> agent behavior protocol
```

The pattern can be factored into four universal ideas, plus one minimal implementation:

1. [Compounding knowledge](01-compounding-knowledge.md)
2. [Raw vs compiled knowledge](02-raw-vs-compiled-knowledge.md)
3. [Progressive disclosure](03-progressive-disclosure.md)
4. [Behavior protocol](04-behavior-protocol.md)
5. [Minimal Markdown implementation](05-minimal-markdown-implementation.md)

Use the first four files to understand the reusable ideas. They do not contain setup instructions or usage guidance. Use the fifth file to create the smallest practical version.

## Setup Intent

When asked to set up this recipe, follow [Minimal Markdown implementation](05-minimal-markdown-implementation.md).

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
- load relevant pages progressively instead of loading everything;
- keep the behavior rules in `AGENTS.md` so future agents can follow them.

Ask before adding extra tools, databases, plugins, or automation.

## Reuse

Examples of partial reuse:

- research workflow: use compounding knowledge + raw vs compiled knowledge + progressive disclosure;
- repo memory: use progressive disclosure + behavior protocol;
- personal notes: use compounding knowledge + behavior protocol;
- team docs: use raw vs compiled knowledge + behavior protocol.
