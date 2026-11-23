# Claude Skills — Claude Code

Skills for [Claude Code](https://claude.com/claude-code) — invoked via `/skill-name` slash commands or automatically triggered by Claude based on each skill's `description` frontmatter.

Tested against Claude Code on Opus 4.6 and Sonnet 4.6 (OpenClaw 2026.4.11 ecosystem).

## Skills in this folder

| Skill | What it does | Install |
|---|---|---|
| [git-commit-writer](./git-commit-writer/) | Drafts an opinionated commit message from your staged diff, matching the repo's existing convention. | `cp -r skills/claude/git-commit-writer ~/.claude/skills/` |
| [openclaw-debugger](./openclaw-debugger/) | Walks the standard OpenClaw agent diagnosis checklist (gateway, logs, heartbeat, sessions, model provider) and prints a fix. | `cp -r skills/claude/openclaw-debugger ~/.claude/skills/` |
| [model-cost-compare](./model-cost-compare/) | Estimates token cost for a task across Opus 4.6, Sonnet 4.6, GLM-5.1, Minimax M3, and local Gemma 4, then recommends the cheapest capable model. | `cp -r skills/claude/model-cost-compare ~/.claude/skills/` |
| [excalidraw-architecture](./excalidraw-architecture/) | Generates or updates `docs/architecture.excalidraw` by surveying the codebase's entry points and data stores. Inspired by @bibryam. | `cp -r skills/claude/excalidraw-architecture ~/.claude/skills/` |
| [cost-optimizer](./cost-optimizer/) | Static audit of a project for the common Claude Code cost leaks — bloated CLAUDE.md, memory, cache-busting hooks, over-pinned Opus. | `cp -r skills/claude/cost-optimizer ~/.claude/skills/` |

## How invocation works

After copying a skill into `~/.claude/skills/`, it's immediately available. You can:

- **Explicit invocation:** type `/skill-name` followed by any arguments.
- **Auto-invocation:** just describe what you need in natural language. Claude reads every skill's `description` field and picks the matching one. That's why writing a precise, trigger-heavy description is the most important thing when authoring a skill.

## Format reference

Each skill lives in its own folder as `SKILL.md` — a single Markdown file with YAML frontmatter:

```markdown
---
name: skill-name
description: When to trigger this skill (one specific sentence — Claude auto-invokes based on this).
---

# Skill title

## When to use
- ...

## Instructions
Concrete steps. Can reference Bash, Read, Edit, Grep, Glob, Write.

## Example invocations
- `/skill-name arg`
- "Natural language trigger"
```

Keep skills between 80 and 200 lines. Longer than that and you're writing docs, not a skill.

## Contribute your own

Have a Claude Code skill that's earned its keep in your workflow? Open a PR:

1. Create `skills/claude/<your-skill-name>/SKILL.md` following the format above.
2. Add a row to the table in this README.
3. Include a "When to use" section with concrete trigger phrases — this is what makes auto-invocation work.
4. Keep it under 200 lines. If it's bigger, it probably wants to be split into multiple skills.

PRs welcome at [mergisi/awesome-openclaw-agents](https://github.com/mergisi/awesome-openclaw-agents).
