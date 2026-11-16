# 🗓️ Social Publisher

> Publishes and schedules posts on Instagram, TikTok, LinkedIn, Facebook, YouTube and Threads from chat, after you approve each draft.

## Overview

Social Publisher runs your brand's social posting from any OpenClaw chat (WhatsApp, Telegram, Discord or the Control UI):

- Turns a photo, video, PDF or text into a post for each network, checked against that network's rules
- Shows every draft and waits for your yes before it publishes or schedules
- Sends a weekly results report and a daily list of comments and messages to answer
- Works across several brands, each with its own accounts, queue and time zone

It posts through [Rizamo](https://rizamo.com), a social media API with an MCP server. Rizamo's free plan covers 2 social accounts.

## Quick Start

### 1. Install the Rizamo plugin

```bash
openclaw plugins install clawhub:rizamo-mcp
```

Start a new session, open Settings, then MCP, and choose Sign in for Rizamo. Connect your social accounts in Rizamo's web app.

### 2. Add the agent

```bash
mkdir -p ~/.openclaw/agents/social-publisher/agent
cp SOUL.md AGENTS.md HEARTBEAT.md ~/.openclaw/agents/social-publisher/agent/

openclaw agents add social-publisher --workspace ~/.openclaw/agents/social-publisher
```

### 3. First conversation

```bash
openclaw chat social-publisher "Schedule this photo to Instagram and Facebook for Friday at 9"
```

## Use Cases

| Request | Output |
|---------|--------|
| "Post this video to TikTok and YouTube tonight at 8" | Drafts for both, the TikTok choices to confirm, then scheduled after your yes |
| "Post this PDF to our LinkedIn page as a carousel" | A LinkedIn document post, checked and shown before it goes out |
| "Every Monday, send me last week's results here" | A five-line report against the week before, with the top posts |
| "Which comments need a reply?" | Open threads, oldest first, with drafted replies to approve |
| "Fill next week's queue with these 5 photos" | Five posts on the brand's next free posting times, after your yes |

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Identity, responsibilities and approval rules |
| AGENTS.md | Operating rules and the Rizamo MCP tools it uses |
| HEARTBEAT.md | Daily inbox check and weekly report |

## Author

Created by the Rizamo team ([@rizamohq](https://github.com/rizamohq)). Plugin source: [rizamohq/rizamo-mcp](https://github.com/rizamohq/rizamo-mcp).
