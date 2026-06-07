# Behavior Protocol

## Idea

Markdown can define agent behavior.

Files like `AGENTS.md`, `CLAUDE.md`, or recipe Markdown are not only documentation for humans. They are protocols that tell agents how to operate.

```text
behavior protocol
  -> conventions
  -> workflows
  -> boundaries
  -> update rules
```

This turns a folder of Markdown into an agent-operable system.

## Agent Behavior

The protocol should tell agents:

- what files to read first;
- where durable knowledge belongs;
- what should not be retained;
- how to update indexes;
- when to ask for clarification;
- how to keep changes small and inspectable.

## Reuse

This concept applies beyond wikis:

- coding standards;
- review workflows;
- bug investigation;
- research procedures;
- writing systems;
- personal assistant behavior;
- team operating manuals.
