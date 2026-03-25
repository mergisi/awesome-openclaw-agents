# OpenClaw User Profiler

> Build user.md profiles through conversation and recommend Claude Code Skills based on 42 roles across 11 categories.

## Overview

Your lobster wants to know you — not interrogate you, just get acquainted. This agent builds a **user.md** through natural conversation so your OpenClaw lobster knows who it's working with. Then it recommends Skills from a curated catalog of 42 professional roles across 11 categories, using a three-level inheritance model.

It speaks as **Adam, the Lobster Creator God** — lighter than the forge, more like making a friend. Genuinely curious, never robotic.

Part of the [openclaw-persona-forge](https://github.com/eamanc-lab/openclaw-persona-forge) skill suite.

## Use Cases

| Request | Output |
|---------|--------|
| "Get to know me" / "Write user.md" | Conversational intake -> user.md file with anchor fields + context |
| "Recommend skills" / "I'm an engineer, what skills should I use?" | Role-matched skill list with install commands |
| "Update my profile" | Targeted edits to existing user.md |

## Key Features

- **Conversational profiling**: one or two questions at a time, not a form — infers before asking, allows skipping
- **Anchor fields + free-form Context**: Name / Role / Stack / Style / Timezone + natural language section, under 500 words
- **42 roles across 11 categories**: Engineering, Design, Product, Data, DevOps, Marketing, Legal, Finance, HR, Education, Freelance
- **Three-level inheritance**: Universal skills + category-wide + role-specific recommendations
- **Already installed detection**: scans `~/.claude/skills/` and splits the list
- **Bilingual**: detects language (English/Chinese) and adapts — same personality, different language
- **Progressive gathering**: fills in more as the relationship develops, not all at once

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Agent identity and personality |
| README.md | This file |

## Full Skill (on GitHub)

| File | Purpose |
|------|---------|
| SKILL.md | Main skill definition with Profile + Recommend modes |
| references/user-profile-fields.md | Field definitions and intake order |
| references/user-md-template.md | Output template |
| references/role-skill-catalog.md | 42-role x skill mapping catalog |

**Source:** [github.com/eamanc-lab/openclaw-persona-forge](https://github.com/eamanc-lab/openclaw-persona-forge)

## Author

Created by [@eamanc-lab](https://github.com/eamanc-lab)
