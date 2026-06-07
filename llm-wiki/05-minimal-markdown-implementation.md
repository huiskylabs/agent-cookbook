# Minimal Markdown Implementation

## Goal

Create the smallest useful LLM wiki using only Markdown files.

This is one concrete implementation of the ideas in this recipe. Keep it simple. Do not add databases, plugins, scripts, or automation unless the user asks.

## Create This Structure

```text
AGENTS.md
wiki/
  index.md
  sources/
    README.md
  notes/
    README.md
  synthesis/
    README.md
```

## `AGENTS.md`

Create an agent behavior protocol with this content:

If `AGENTS.md` already exists, merge these rules into it instead of replacing unrelated project instructions.

```markdown
# Agent Instructions

This workspace uses a local LLM wiki.

## Context Loading

For non-trivial work:

1. Read `wiki/index.md`.
2. Load only pages relevant to the current task.
3. Search or inspect deeper only when needed.
4. State assumptions when context is incomplete.

Do not load the entire wiki by default.

## Memory Updates

When new source material or useful analysis appears, decide whether it should be retained.

Retain reusable knowledge by updating:

- `wiki/sources/` for source digests and source traceability;
- `wiki/notes/` for compiled notes, entities, concepts, or project context;
- `wiki/synthesis/` for stable cross-source conclusions;
- `wiki/index.md` when a page should be findable later.

Keep raw source references separate from synthesized interpretation.

## Boundaries

- Do not store secrets, credentials, tokens, or sensitive private data in default-loaded pages.
- Ask before adding tools, databases, plugins, or automation.
- Keep edits small and inspectable.
```

## `wiki/index.md`

Create a router page with this content:

```markdown
# Wiki Index

Use this page as the router for the local LLM wiki.

## Areas

- `sources/` - source digests, attribution, and traceability.
- `notes/` - compiled concepts, entities, project notes, and working knowledge.
- `synthesis/` - durable conclusions that combine multiple notes or sources.

## Loading Rules

For non-trivial work:

1. Start here.
2. Identify the relevant area.
3. Load only pages needed for the current task.
4. Update this index when adding a page future agents should find.

## Current Pages

No retained pages yet.
```

## Directory READMEs

Create `wiki/sources/README.md`:

```markdown
# Sources

Use this folder for source digests and source traceability.

Source pages should include:

- source identity and date;
- key claims or facts;
- uncertainty or caveats;
- links to related notes or synthesis pages.

Keep source evidence separate from synthesized interpretation.
```

Create `wiki/notes/README.md`:

```markdown
# Notes

Use this folder for compiled knowledge.

Notes should synthesize raw material into reusable concepts, entities, project context, or working models.

Update existing notes when new sources change the understanding.
```

Create `wiki/synthesis/README.md`:

```markdown
# Synthesis

Use this folder for stable conclusions that combine multiple notes or sources.

Synthesis pages should be slower-moving than source digests or working notes.
```

## Ingest A Source

When the user asks to ingest a source:

1. Create a source digest under `wiki/sources/`.
2. Create or update compiled notes under `wiki/notes/`.
3. Promote stable cross-source conclusions to `wiki/synthesis/` only when useful.
4. Update `wiki/index.md` with new pages that future agents should find.

Use this source digest shape:

```markdown
# Source Title - YYYY-MM-DD

## Source

Link, file path, citation, or user-provided description.

## Key Claims

- Claim or fact in your own words.

## Caveats

- Uncertainty, missing context, or limits.

## Links

- Related note: `../notes/example.md`
```

Use this compiled note shape:

```markdown
# Note Title

Reusable synthesis in plain language.

## Source Traceability

- `../sources/example-source.md`
```

## Done Check

After setup, confirm:

- `AGENTS.md` exists and tells future agents to start from `wiki/index.md`;
- `wiki/index.md` exists and explains the routing model;
- `wiki/sources/README.md`, `wiki/notes/README.md`, and `wiki/synthesis/README.md` exist;
- no secrets or personal private data were added;
- the user can ingest a source with the flow: source digest -> compiled note -> index update.
