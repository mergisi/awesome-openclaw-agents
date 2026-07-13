# MiniMax M-Series Agent Configs

Drop-in OpenClaw configuration for the hosted `MiniMax-M3` and `MiniMax-M2.7` models. The directory name is retained so existing links to the original bundle continue to work.

## Supported Models

| Model ID | Context window | Input modalities | Thinking |
|----------|----------------|------------------|----------|
| `MiniMax-M3` | 1,000,000 tokens | Text, image, video | `adaptive` or `disabled` |
| `MiniMax-M2.7` | 204,800 tokens | Text | Always on |

Both model IDs are available through the OpenAI-compatible and Anthropic-compatible APIs in the global and China service regions.

## Quick Start

1. Get an API key from the official documentation for your service region:
   - Global: https://platform.minimax.io/docs
   - China: https://platform.minimaxi.com/docs

2. Copy the example environment file and select one endpoint from each protocol family:

```bash
cp configs/minimax-m2.7/.env.example .env
```

| Region | OpenAI-compatible base URL | Anthropic-compatible base URL |
|--------|----------------------------|-------------------------------|
| Global | `https://api.minimax.io/v1` | `https://api.minimax.io/anthropic` |
| China | `https://api.minimaxi.com/v1` | `https://api.minimaxi.com/anthropic` |

The Anthropic-compatible base URL must end in `/anthropic`. Compatible clients append `/v1/messages` when they send a Messages API request.

3. Register the protocol you want OpenClaw to use:

```bash
set -a
source .env
set +a

# OpenAI-compatible provider
openclaw provider add minimax \
  --api-key "$MINIMAX_API_KEY" \
  --base-url "$MINIMAX_BASE_URL"

# Anthropic-compatible provider
openclaw provider add minimax-anthropic \
  --api-key "$MINIMAX_API_KEY" \
  --base-url "$MINIMAX_ANTHROPIC_BASE_URL"
```

4. Copy the agent bundle and run it:

```bash
cp configs/minimax-m2.7/SOUL.md ~/.openclaw/agents/swe-agent/SOUL.md
openclaw agent --agent swe-agent --message "Find and fix the failing tests in this repo"
```

The included `SOUL.md` defaults to `minimax/MiniMax-M3`. To use the second model, change the model line to `minimax/MiniMax-M2.7`. For the Anthropic-compatible registration, use the `minimax-anthropic` provider prefix with either model ID.

## Pricing

Prices below are in USD per million tokens. MiniMax-M3 pricing depends on the request's service tier and input length, so do not flatten it to one rate.

### MiniMax-M3

| Service tier | Input length | Input | Output | Cache read |
|--------------|--------------|------:|-------:|-----------:|
| Standard | Up to 512,000 tokens | 0.30 | 1.20 | 0.06 |
| Standard | More than 512,000 tokens | 0.60 | 2.40 | 0.12 |
| Priority | Up to 512,000 tokens | 0.45 | 1.80 | 0.09 |
| Priority | More than 512,000 tokens | 0.90 | 3.60 | 0.18 |

### MiniMax-M2.7

| Input | Output | Cache read | Cache write |
|------:|-------:|-----------:|------------:|
| 0.30 | 1.20 | 0.06 | 0.375 |

## Thinking and Modalities

`MiniMax-M3` accepts text, image, and video input. Set `thinking` to `adaptive` for reasoning or `disabled` for a direct response. The OpenAI-compatible API enables thinking when the field is omitted, while the Anthropic-compatible API disables it when omitted.

`MiniMax-M2.7` accepts text input and always uses thinking; a request cannot disable it.

## Official References

- Global model and context documentation: https://platform.minimax.io/docs/api-reference/text-openai-api
- Global pricing: https://platform.minimax.io/docs/guides/pricing-paygo
- Global Anthropic-compatible setup: https://platform.minimax.io/docs/api-reference/text-anthropic-api
- China OpenAI-compatible setup: https://platform.minimaxi.com/docs/api-reference/text-openai-api
- China Anthropic-compatible setup: https://platform.minimaxi.com/docs/api-reference/text-anthropic-api

## Files in This Bundle

- `SOUL.md` - software engineering agent defaults for MiniMax-M3
- `.env.example` - model selection and all supported regional base URLs
