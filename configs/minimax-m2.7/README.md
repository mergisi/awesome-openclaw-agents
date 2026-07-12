# MiniMax-M3 Agent Configs

Drop-in OpenClaw configs for **MiniMax-M3** — MiniMax's long-context hosted model for agentic coding and multimodal-adjacent workflows.

## Why MiniMax-M3

The short version: if you care about long-horizon agent workflows and want an OpenAI-compatible or Anthropic-compatible hosted endpoint, MiniMax-M3 is the current MiniMax option to try.

Key provider parameters:

- **Context window:** 1,000,000 tokens
- **Pricing:** $0.60/M input, $2.40/M output
- **Cache read pricing:** $0.12/M input
- **Thinking modes:** adaptive or disabled

MiniMax exposes separate global and China-region API hosts, plus Anthropic-compatible paths for Claude-style clients.

## Quick Start

1. Get an API key from the MiniMax platform docs for your region:
   - Global: https://platform.minimax.io/docs
   - China: https://platform.minimaxi.com/docs

2. Register the provider with OpenClaw. For the global OpenAI-compatible endpoint:

```bash
openclaw provider add minimax \
  --api-key $MINIMAX_API_KEY \
  --base-url https://api.minimax.io/v1
```

For Claude-style clients, use the Anthropic-compatible base URL instead:

```bash
openclaw provider add minimax-anthropic \
  --api-key $MINIMAX_API_KEY \
  --base-url https://api.minimax.io/anthropic
```

China-region base URLs are `https://api.minimaxi.com/v1` and `https://api.minimaxi.com/anthropic`.

3. Copy the agent bundle:

```bash
cp configs/minimax-m2.7/SOUL.md ~/.openclaw/agents/swe-agent/SOUL.md
```

4. Run it:

```bash
openclaw agent --agent swe-agent --message "Find and fix the failing tests in this repo"
```

## Model IDs

| Model ID | Context | Good For |
|----------|---------|----------|
| `MiniMax-M3` | 1M | Default hosted model for long-context agent workflows. |

Set it in your `SOUL.md` front matter as `Model: minimax/MiniMax-M3`. Use `thinking=adaptive` for hard tasks and disable thinking for latency-sensitive routing.

## About `mmx-cli`

MiniMax also ships their own CLI called `mmx-cli` that wraps the same API with a different agent loop. **This is a separate tool from OpenClaw.** If you see posts saying "MiniMax works great with mmx-cli but breaks in OpenClaw," that's usually because the poster was comparing two different agent harnesses, not two different models. This bundle targets OpenClaw's loop, not `mmx-cli`.

## Cost Comparison (July 2026)

| Model | Input | Output | Cache read | Notes |
|-------|-------|--------|------------|-------|
| Claude Opus 4.6 | $15 | $75 | — | If you can get access. |
| Claude Sonnet 4.6 | $3 | $15 | — | Still the price-performance baseline. |
| **MiniMax-M3 (hosted)** | **$0.60** | **$2.40** | **$0.12** | 1M context. |

## Gotchas When Migrating From Claude

1. **Endpoint shape matters.** Configure Anthropic-compatible clients with a base URL ending in `/anthropic`; the client appends `/v1/messages` for requests.

2. **Long contexts still need budgets.** MiniMax-M3 supports a 1M-token context window, but long agent sessions can still run up cost. Set a max-steps cap in your OpenClaw config if you care about runaway spend.

3. **Thinking mode is configurable.** Use adaptive thinking for complex planning and disable it for latency-sensitive or deterministic routing tasks.

4. **Multimodal tools are separate capabilities.** MiniMax also offers speech, voice clone, image, video, video-agent, and music APIs; wire those as OpenClaw tools rather than treating them as chat model features.

## Related Docs

- Global docs: https://platform.minimax.io/docs/api-reference/api-overview
- China docs: https://platform.minimaxi.com/docs/api-reference/api-overview

## Files in This Bundle

- `SOUL.md` — agentic SWE agent tuned for MiniMax-M3's long tool chains
- `.env.example` — env vars for hosted OpenAI-compatible and Anthropic-compatible endpoints
