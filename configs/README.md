# OpenClaw Config Bundles

Drop-in agent configs for different model providers. Each folder is a self-contained bundle: a README with setup steps, a working `SOUL.md` example, and an `.env.example` for any required credentials.

## Available Bundles

| Bundle | Provider | Best For | Status |
|--------|----------|----------|--------|
| [ollama](./ollama) | Local Ollama | Private, offline, no API cost | Stable |
| [glm-5.1](./glm-5.1) | Zhipu GLM-5.1 | Opus 4.6 alternative, long-horizon coding | New |
| [minimax-m2.7](./minimax-m2.7) | MiniMax M3 (default) / M2.7 (229B) | Agentic SWE tasks, terminal workflows | New |
| [gpt-5.4](./gpt-5.4) | OpenAI GPT-5.4 | Reasoning-heavy tasks, Codex workflows | New |

## Which one should I pick?

- **You can't get on Claude right now** (Anthropic ban, quota exhausted, Alibaba resellers sold out) → start with **glm-5.1**. It's the closest drop-in for Opus 4.6 prompts and most community threads on r/openclaw rank it first.
- **You want open weights + the best agentic scores** → **minimax-m2.7** (the bundle now defaults to **MiniMax M3** on hosted API, with M2.7 still supported for self-hosters). Heavier to self-host, but SWE-Pro 56.22% is the highest open-weight number as of April 2026.
- **You already have an OpenAI key and want official support** → **gpt-5.4**. It needs prompt surgery coming from Claude, but the `thinking=high + fastmode=true` combo is solid once configured.
- **You want zero vendor lock-in, private data, no network** → **ollama**.

## Conventions

- Every bundle ships a minimal `SOUL.md` tuned to that model's strengths. Copy it to `~/.openclaw/agents/<name>/SOUL.md` and run `openclaw agent --agent <name> --message "..."`.
- `.env.example` lists the provider env vars. Copy to `.env` (or export in your shell) and fill in real values.
- OpenClaw 2026.4.11+ is required for the `openclaw provider add` command used in the GLM / MiniMax / GPT bundles.
