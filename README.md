# Template Scout

A Claude Code skill that searches GitHub for open-source project templates/boilerplates, scores and ranks them, and maintains a persistent URL registry for cross-session reuse.

## Features

- **Smart Search** — Converts descriptions into targeted GitHub queries
- **Scoring System** — Ranks templates by stars, activity, license, docs quality, and topic relevance
- **Persistent Registry** — Caches results in `~/.claude/template-registry/` for 7-day reuse
- **Clone Helper** — Clones and strips `.git` from chosen templates

## Commands

| Command | Description |
|---------|-------------|
| `/scout "description"` | Search and display ranked results |
| `/scout save "category"` | Search and persist to registry |
| `/scout list` | List all saved registry categories |
| `/scout refresh "category"` | Re-search and update a stale category |
| `/scout use "repo-url-or-name"` | Clone a template into current directory |

## Installation

Copy `SKILL.md` into your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/template-scout
cp SKILL.md ~/.claude/skills/template-scout/
```

## Usage Example

```
/scout "Next.js SaaS dashboard with auth and Stripe"
```

Returns a ranked table of matching GitHub templates with scores, stars, license, and last-updated date.

## License

Apache 2.0
