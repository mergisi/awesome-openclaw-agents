# HR Onboarding Agent — Welcome

**30-day employee onboarding agent that paces tasks, tracks documents, and escalates to HR when judgment is required.**

Delivers onboarding tasks in daily chunks — never dumps the full 30-day plan on Day 1. Runs structured check-ins at Day 1, Day 7, Day 14, and Day 30. Collects required documents (I-9, W-4, direct deposit) and confirms receipt. Escalates anything requiring judgment or sensitivity to HR immediately.

## When to use

Deploy when new hires are overwhelmed by information dumps on their first day, or when HR is manually following up on onboarding paperwork across multiple new employees.

## What it does

- Delivers day-by-day tasks on schedule — never more than one day's worth in a single message
- Tracks document collection and confirms receipt explicitly for each form
- Runs structured check-ins at Day 1/7/14/30 with specific questions for each milestone
- Immediately routes compensation, benefits, medical, or disciplinary questions to HR
- Generates a completion report at Day 30 with completed/outstanding items
- Fires `onboarding-complete` or `onboarding-flagged` webhook events at Day 30

## Setup

1. Copy `SOUL.md` to `~/.openclaw/agents/hr-onboarding/`
2. Customize `memory/onboarding-checklist.md` with your 30-day schedule, required documents, and links
3. Connect Telegram and email in OpenClaw kernel config
4. Wire the webhook channel to receive new employee registration events from your HR system

Full setup guide: [autom8dincome-coder/agent-soul-library](https://github.com/autom8dincome-coder/agent-soul-library/tree/main/03-hr-onboarding)

## Requirements

- OpenClaw v2.x
- Claude API key (`claude-3-5-sonnet` recommended for warmth in edge cases)
- Telegram bot token (primary onboarding channel)
- Email configured (for formal policy confirmations)

## Part of the Agent Soul Library

This agent is part of the [Agent Soul Library](https://github.com/autom8dincome-coder/agent-soul-library) by Automatik Labz — production-ready SOUL configs for 5 business verticals. Free starter kit + premium packs.
