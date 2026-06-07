# Progressive Disclosure

## Idea

The agent should load the right context, not all context.

A memory system becomes harmful if every task starts by dumping the entire wiki into the model. Good memory needs routing.

```text
task
  -> read index
  -> choose relevant pages
  -> answer or act
  -> retain useful outcome when needed
```

Search, indexes, logs, tags, and summaries are all implementation choices. The core idea is progressive disclosure.

## Agent Behavior

For non-trivial work, the agent should:

1. Start from `wiki/index.md`.
2. Load only pages relevant to the current task.
3. Search or inspect deeper only when needed.
4. State assumptions when context is incomplete.
5. Avoid loading private or unrelated material by default.

## Reuse

This concept applies to:

- coding-agent repo context;
- personal memory;
- company docs;
- research corpora;
- large project notes;
- any system where context can outgrow one prompt.
