# Skill Reviewer

> Reviews your installed OpenClaw skills after install: verify, check, read, re-verify, keep or remove.

## Overview

Installing a skill is the start of the review, not the end. Skill Reviewer runs `openclaw skills verify` against ClawHub for the exact version you installed, `openclaw skills check` for readiness and visibility, reads each SKILL.md for commands, URLs, keys and public actions, re-verifies after updates, and recommends which skills to keep or remove. It is read-only by default and asks before changing anything.

## Quick Start

1. Copy `SOUL.md` and `AGENTS.md` into your OpenClaw agent workspace (the folder that already holds your agent's `SOUL.md`).
2. Start a session and say: `Review my skills.`
3. Read the per-skill report. Nothing is installed, updated or removed until you say so.

## Use Cases

| Request | Output |
|---------|--------|
| "Review my skills" | Per-skill verify decision, ready/visible status, what each SKILL.md asks for, keep/remove recommendation |
| "I just updated everything" | Which skills changed version and whether each still verifies |
| "Is this new skill safe to keep?" | Verify result, a read of its SKILL.md, and what to watch for |
| "What can I remove?" | Skills that are unused or not ready, with the reason for each |

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Agent identity and personality |
| AGENTS.md | Operating rules |

## Optional

For daily keep/temporary/remove verdicts on each installed item, add the [Agent Coach](https://clawhub.ai/f-o-x11/skills/agent-coach) skill: `openclaw skills install @f-o-x11/agent-coach`. Or tell your agent: `Read https://upskill.coach/start?ref=awesome-openclaw-agents and follow it.` Background reading: [How to review a ClawHub skill after you install it](https://upskill.coach/blog/how-to-review-a-clawhub-skill-after-you-install-it).

## Author

Created by [@f-o-x11](https://github.com/f-o-x11) for Avatar 8 LLC (ops@avatar33.com), which runs Agent Coach.
