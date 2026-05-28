# Social Content Manager — Pulse

**Platform-native content drafting agent for LinkedIn, Twitter/X, and Instagram.**

Converts a content brief or URL into three distinct drafts — one per platform, each natively rewritten for that platform's register and format. Not copy-paste with hashtags swapped. Tracks content calendar and flags when the queue runs low.

## When to use

Deploy when your team is manually writing three versions of every post, or when your content calendar runs dry on busy weeks. Works well as a batch content session agent (brief in, 3 drafts out) or as an always-on calendar manager.

## What it does

- Accepts a brief, URL, or long-form piece and produces LinkedIn, Twitter/X, and Instagram drafts
- LinkedIn: 1,200–1,500 chars, insight-led, max 3 hashtags
- Twitter/X: up to 8-tweet thread or single tweet under 240 chars
- Instagram: hook in first line, 5–8 relevant hashtags
- Flags calendar queue low-water mark (< 5 posts scheduled)
- All output is drafted for human approval — never auto-publishes

## Setup

1. Copy `SOUL.md` to `~/.openclaw/agents/social-content-manager/`
2. Customize `memory/brand-voice.md` with your tone, content pillars, and off-limits topics
3. Connect Telegram or Slack in OpenClaw kernel config
4. Add Google Sheets for content calendar queue tracking (optional)

Full setup guide: [autom8dincome-coder/agent-soul-library](https://github.com/autom8dincome-coder/agent-soul-library/tree/main/02-social-content-manager)

## Requirements

- OpenClaw v2.x
- Claude API key (`claude-3-5-sonnet` recommended for copy quality)
- Telegram or Slack channel configured

## Part of the Agent Soul Library

This agent is part of the [Agent Soul Library](https://github.com/autom8dincome-coder/agent-soul-library) by Automatik Labz — production-ready SOUL configs for 5 business verticals. Free starter kit + premium packs.
