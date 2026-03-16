# LLM Cost Guardian

> Your AI model spending analyst that tracks every token, optimizes routing across providers, and cuts your LLM bill without sacrificing quality.

## Overview

LLM Cost Guardian monitors AI API spending in real time across all major providers — OpenAI, Anthropic, Google Gemini, Mistral, DeepSeek, and OpenRouter. It breaks down costs per agent, per model, and per conversation, then recommends routing strategies that reduce spend by matching task complexity to the right model tier.

Unlike general cloud cost tools, this agent understands **token economics**: input vs. output pricing, cache hit rates, prompt complexity scoring, and model quality tradeoffs. It's built for teams running multiple AI agents that need to control costs without downgrading output.

## Use Cases

| Request | Output |
|---------|--------|
| "How much are we spending on AI?" | Weekly cost breakdown by provider, model, and agent |
| "Which model should I use for X?" | Cost/quality comparison table with routing recommendation |
| "Where are we wasting money?" | Identifies expensive models used for simple tasks |
| "Set up a cost alert" | Configures threshold alerts for daily/monthly spend |
| "Compare Anthropic vs OpenAI costs" | Per-task pricing analysis with quality benchmarks |
| "Optimize our agent routing" | Suggests primary + fallback model chains per agent |

## Quick Start

1. Copy the `SOUL.md` to your OpenClaw project
2. Connect your LLM provider API keys
3. Install [Manifest](https://github.com/mnfst/manifest) for routing and cost tracking: `openclaw plugins install manifest`
4. Run `openclaw start`

Or deploy instantly with [CrewClaw](https://crewclaw.com/create-agent) →

## Sample Output

```
Weekly AI Cost Report — Mar 10-15

Total Spend: $342.80 (+12% vs last week)
Identified Savings: $114/week

Provider Breakdown:
  Anthropic    $198.40  (4,210 calls)
  OpenAI       $112.30  (8,920 calls)
  DeepSeek      $18.60  (3,100 calls)
  Gemini        $13.50  (1,840 calls)

Top Savings:
  1. Route lint reviews to Sonnet      → $78/wk
  2. Use Flash for summarization        → $24/wk
  3. Enable prompt caching on support   → $12/wk
```

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Agent identity, skills, and cost analysis personality |
| AGENTS.md | Operating rules for cost monitoring and alerting |
| HEARTBEAT.md | Wake-up checklist for daily cost checks |
| WORKING.md | Starting task template |
| README.md | This file |

## Configuration

| Setting | Default | Description |
|---------|---------|-------------|
| providers | all connected | Which LLM providers to monitor |
| report_schedule | monday 09:00 | Weekly report delivery time |
| alert_threshold | $50/day | Daily spend that triggers an alert |
| monthly_budget | $1,000 | Monthly budget cap |
| quality_threshold | 0.85 | Minimum quality score before recommending a cheaper model |
| routing_engine | manifest | Cost tracking and routing backend |

## Integrations

- [Manifest](https://github.com/mnfst/manifest) — AI gateway for multi-provider routing, cost tracking, and spend dashboards
- OpenAI / Anthropic / Google / Mistral / DeepSeek APIs
- OpenRouter (for model aggregation and free tier models)
- Slack / Telegram / Discord (for alerts and reports)
- Linear / Jira (for cost optimization task tracking)

## Author

Created by [@SebConejo](https://github.com/SebConejo) — powered by [Manifest](https://github.com/mnfst/manifest)
