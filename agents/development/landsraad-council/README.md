# The Landsraad — Multi-Model Consensus Engine

> A council of 15+ Great Houses (LLMs) that debate, peer-review, and synthesize answers through formal parliamentary procedure. Pipeline everything.

Built by [Stephen Bowman](https://x.com/UnmoggedAmerica) (@UnmoggedAmerica) — Bowman Labs. Deployable as an OpenClaw agent.

## Overview

The Landsraad routes every query through a 3-stage parliamentary pipeline:

1. **Opening Statements** — 15+ OpenRouter models respond in parallel
2. **The Gauntlet** — Cross-peer review with HMAC-signed, JWT-tracked voting
3. **Chairman Synthesis** — A meta-judge reconciles all outputs into a unified verdict

## Quick Start

### Prerequisites

- OpenRouter API key
- OpenClaw CLI
- Minimum 5 API keys for model diversity (recommended: 15+)

### Installation

```bash
mkdir -p ~/.openclaw/agents/landsraad-council/agent
cp SOUL.md ~/.openclaw/agents/landsraad-council/agent/

openclaw agents add landsraad-council --workspace ~/.openclaw/agents/landsraad-council
```

### First Conversation

```bash
openclaw chat landsraad-council "What's the best architecture for a real-time fraud detection pipeline?"
```

## Architecture

**Stack:** Next.js 16, React 19, Tailwind 4, Radix UI, OpenRouter, Vercel AI SDK

**Security:** HMAC-signed sessions, JWT auth, CSRF protection, Zod validation, rate limiting

**Deployment:** Vercel with Edge Runtime for fan-out parallelism

## Use Cases

### 1. High-Stakes Decision-Making
```
You: Should we migrate from PostgreSQL to CockroachDB?
Landsraad: [15 models debate, peer-review, synthesize — verdict with confidence score]
```

### 2. Code Review by Committee
```
You: Review this trading algorithm for logic flaws
Landsraad: [Houses flag different issues, cross-validate each other]
```

### 3. Strategic Planning
```
You: Design a zero-trust architecture for our fintech platform
Landsraad: [Multi-perspective synthesis with dissenting opinions]
```

### 4. Technical Deep Dives
```
You: Explain the CAP theorem implications for our distributed order book
Landsraad: [Each House approaches from different angle, Chairman reconciles]
```

## Model Roster

| House | Models | Role |
|---|---|---|
| Atreides | Claude Sonnet 4, Opus 4 | High reasoning |
| Harkonnen | DeepSeek V3, Qwen 2.5 | Contrarian, aggressive |
| Ordos | Gemini 2 Pro, 2.5 Flash | Balanced mediator |
| Navigator | GPT-4o, GPT-4.1 | Consensus-seeking |
| Bene Gesserit | Mistral Large, Llama 3.3 70B | Truth-seeking |
| Fremen | DeepSeek R1, Qwen QwQ | Long-context technical |
| Ixian | Claude Haiku, GPT-4o Mini | Fast, cheap |
| Tleilaxu | Specialist fine-tunes | Domain-specific |

## Tips

1. **Diversity > accuracy** — A disagreeing House is more valuable than a yes-man
2. **Temperature band** — Spread models across 0.3–1.2 temperature range
3. **Minimum quorum** — 5 models minimum, 15 for reliable consensus
4. **Watch the confidence** — Below 0.7 confidence means rerun with more models
5. **Dissenting opinions matter** — The minority position is often the one that prevents disaster

## Author

Built by Stephen Bowman (@UnmoggedAmerica) — Bowman Labs. References butlerianjihad.org. Arsenal red/white. 8-bit/N64 aesthetic. Pipeline everything.

## License

MIT