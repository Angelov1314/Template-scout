---
name: template-scout
description: Search GitHub for open-source project templates/boilerplates, score and rank them, and maintain a persistent URL registry for cross-session reuse.
triggers:
  - scout
  - template
  - boilerplate
  - scaffold
  - starter
  - find template
  - search github template
---

# Template Scout

Search GitHub and skill registries for open-source project templates, score them, and build a persistent registry that improves determinism across sessions.

## Commands

- **`/scout "description"`** — Search and display ranked results
- **`/scout save "category"`** — Search, rank, and persist to registry
- **`/scout list`** — List all saved registry categories
- **`/scout refresh "category"`** — Re-search and update a stale category
- **`/scout use "repo-url-or-name"`** — Clone a template into current directory

## Core Workflow

### Step 1: Check Registry First

Before any search, check if `~/.claude/template-registry/index.json` has a matching category. If found and `lastUpdated` is within 7 days, return cached results instead of re-searching.

```bash
cat ~/.claude/template-registry/index.json 2>/dev/null
cat ~/.claude/template-registry/<category>.json 2>/dev/null
```

### Step 2: Build Search Queries