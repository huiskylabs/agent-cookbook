# Agent Instructions

This repository is an agent cookbook: a collection of agent-readable recipe directories.

## Repository Model

Each recipe should be a directory with a `README.md`.

Use this split when a recipe has both abstract concepts and concrete setup steps:

```text
recipe-name/
  README.md
  ideas/
  setups/
```

- `ideas/` contains isolated universal ideas.
- `setups/` contains concrete setup instructions.
- `README.md` is the entry point that explains the recipe shape and points to the relevant setup.

## Idea Files

Idea files should stay pure.

They should explain:

- the idea;
- why it matters.

They should not include:

- setup instructions;
- agent behavior rules;
- usage guidance;
- composition advice;
- implementation details.

Do not tell downstream agents how to use an idea inside the idea file itself.

## Setup Files

Setup files are where concrete instructions belong.

They may include:

- files and folders to create;
- starter file contents;
- agent behavior rules;
- minimal workflows;
- checks for a successful setup.

Prefer the smallest useful setup. Do not add databases, plugins, scripts, automation, or extra tooling unless the recipe needs them.

## Editing Rules

- Keep recipes small and readable.
- Avoid turning the cookbook into a framework.
- Preserve source attribution when a recipe is inspired by a public idea, article, gist, or project.
- If a recipe is meant to be executable by an agent, test it from a blank scratch workspace before calling it ready.
- When testing a setup, verify that a future agent can continue from the generated files without rereading the cookbook.

## Pull Request Checklist

Before opening or updating a PR, confirm:

- recipe links work;
- idea files contain no setup or usage guidance;
- setup files are concrete enough to run from scratch;
- the recipe can be explained clearly in one or two sentences;
- no private data, secrets, tokens, credentials, or personal context were added.
