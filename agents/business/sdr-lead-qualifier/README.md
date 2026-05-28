# SDR Lead Qualifier — Qualified

**BANT-based inbound lead qualification agent for B2B sales teams.**

Qualifies inbound leads using a Budget / Authority / Need / Timeline framework. Asks one question at a time — never overwhelms prospects. Produces a structured handoff summary when a lead is ready for a human rep. Disqualifies gracefully when leads don't fit.

## When to use

Deploy when reps are spending time on leads that will never close. Typical ROI: reps reclaim 30–60% of qualification time within the first week.

## What it does

- Receives inbound leads via Telegram, Slack, or webhook
- Asks exactly one question per message (BANT signal)
- Scores leads 1–10 based on fit against your ICP
- Produces a complete qualification summary for rep handoff
- Logs all leads and outcomes to Google Sheets

## Setup

1. Copy `SOUL.md` to `~/.openclaw/agents/sdr-lead-qualifier/`
2. Customize `memory/icp-criteria.md` with your ICP (who you sell to, deal size, titles, industries)
3. Connect Telegram bot in OpenClaw kernel config
4. Add Google Sheets credential (optional — for lead logging)

Full setup guide: [autom8dincome-coder/agent-soul-library](https://github.com/autom8dincome-coder/agent-soul-library/tree/main/01-sdr-lead-qualifier)

## Requirements

- OpenClaw v2.x
- Claude API key (`claude-3-5-sonnet` recommended)
- Telegram bot token

## Part of the Agent Soul Library

This agent is part of the [Agent Soul Library](https://github.com/autom8dincome-coder/agent-soul-library) by Automatik Labz — production-ready SOUL configs for 5 business verticals. Free starter kit + premium packs.
