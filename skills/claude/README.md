# Claude Skills — Claude Code

Skills for [Claude Code](https://claude.com/claude-code) — invoked via `/skill-name` slash commands or automatic triggers based on the description.

## How to install

Copy any skill folder into `~/.claude/skills/`:

```bash
cp -r skill-name ~/.claude/skills/
```

The skill is immediately available. Invoke with `/skill-name` or let Claude trigger it automatically based on the description.

## Format

Each skill is a single Markdown file with YAML frontmatter:

```markdown
---
name: skill-name
description: When to trigger this skill
---

# Instructions

What the skill should do...
```

## Skills

| Skill | Description | Source |
|-------|-------------|--------|
| [mmx-cli](https://github.com/MiniMax-AI/cli) | Generate text, images, video, speech, and music via MiniMax AI | MiniMax-AI/cli |

Add yours via PR.
