# Manifest

> Open-source AI gateway for OpenClaw — intelligent model routing across 300+ models, automatic fallbacks, and real-time cost tracking.

## Overview

[Manifest](https://github.com/mnfst/manifest) is an OpenClaw plugin that intercepts every LLM request and routes it to the most cost-effective model using a 23-dimension scoring algorithm (< 2ms). It supports 300+ models across 12 providers, provides automatic fallbacks when a model fails, and serves a real-time dashboard to monitor costs and usage.

Instead of sending every query to the same expensive model, Manifest scores each request and picks the cheapest model that meets the quality bar — saving up to 70% on AI costs with zero code changes.

## Use Cases

| Request | Output |
|---------|--------|
| Install Manifest on OpenClaw | One-command setup, instant routing |
| Route simple tasks to cheap models | Automatic — no config needed |
| Handle provider outages | Silent fallback to next provider |
| Track AI spending per agent | Real-time dashboard at localhost:2099 |
| Set a monthly budget cap | Usage limits with email/Telegram alerts |
| Use local models with Ollama | Full offline routing, no cloud needed |

## Quick Start

```bash
openclaw plugins install manifest
```

Cloud mode (default) — dashboard from anywhere, telemetry on Manifest platform.

For local mode (all data stays on your machine):
```bash
openclaw plugins install manifest --local
```

Dashboard: [http://127.0.0.1:2099](http://127.0.0.1:2099)

## Supported Providers

| Provider | Models | Notes |
|----------|--------|-------|
| OpenAI | GPT-4o, GPT-4o-mini, o1, o3 | Full support |
| Anthropic | Claude Opus, Sonnet, Haiku | Prompt caching |
| Google Gemini | 2.5 Pro, Flash | Prompt caching |
| DeepSeek | DeepSeek-V3, R1 | Reasoning models |
| Mistral | Large, Small, Codestral | EU hosting |
| xAI | Grok | — |
| Qwen | Qwen 2.5 | — |
| MiniMax | — | — |
| Kimi (Moonshot) | — | — |
| Amazon Nova | — | — |
| Z.ai (Zhipu) | — | — |
| OpenRouter | 200+ models | Aggregator |
| Ollama | Any local model | Fully offline |

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Manifest routing identity and behavior |
| AGENTS.md | Operating rules for the routing proxy |
| HEARTBEAT.md | Health check and monitoring checklist |
| WORKING.md | Initial setup state |
| README.md | This file |

## Links

- **GitHub:** [github.com/mnfst/manifest](https://github.com/mnfst/manifest)
- **Website:** [manifest.build](https://manifest.build)
- **Dashboard:** [app.manifest.build](https://app.manifest.build)
- **Docs:** [manifest.build/docs](https://manifest.build/docs)
- **Discord:** [discord.gg/FepAked3W7](https://discord.gg/FepAked3W7)

## Author

Created by [@SebConejo](https://github.com/SebConejo) — [Manifest](https://github.com/mnfst/manifest) (MIT License)
