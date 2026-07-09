# Advisor-Hybrid Agent Config

A two-tier OpenClaw setup: an expensive **Advisor** model plans and reviews, a cheap **Executor** model runs the work. Based on Anthropic's official "Advisor Strategy" pattern, adapted for OpenClaw 2026.4.11.

> Anthropic announced the Advisor Strategy for the Claude Platform on April 8, 2026. This config ports the same idea to local and self-hosted OpenClaw agents — use Opus 4.6 as the advisor, and Sonnet 4.6 / GLM-5.1 / MiniMax-M3 / local Gemma as the executor.

## What is the Advisor Pattern?

```
          ┌────────────────────┐
          │   User / Trigger   │
          └─────────┬──────────┘
                    │ task
                    ▼
        ┌───────────────────────┐
        │  Executor (cheap)     │    runs tool calls,
        │  Sonnet 4.6 / GLM-5.1 │    writes code, edits
        │  /Gemma local         │    files, drives the loop
        └────┬─────────────▲────┘
             │             │
    "I'm stuck / about to  │  compact
     do something risky"   │  checklist
             ▼             │
        ┌───────────────────────┐
        │  Advisor (expensive)  │    plans, reviews,
        │  Opus 4.6             │    flags risk,
        │                       │    never executes
        └───────────────────────┘
```

The Advisor is a **planner and reviewer**. It sees a summary of the task, returns a compact checklist, and then steps out of the loop. The Executor does all the tool calls, file edits, and iteration. The Executor calls the Advisor **at critical decision points only** — not every step.

Reddit threads on r/openclaw suggest roughly 60–80% cost savings vs. running Opus end-to-end, for tasks where the executor model is competent enough to follow a plan without hand-holding.

## When to Use It

| Scenario | Use Advisor-Hybrid? |
|----------|---------------------|
| Long refactors across many files | Yes — Opus plans, Sonnet edits |
| Research + synthesis (50+ sources) | Yes — Opus picks strategy, GLM-5.1 reads |
| One-shot "write me a function" | No — single Sonnet call is cheaper |
| Deeply novel / research-level problems | No — use Opus end-to-end |
| Cron jobs and batch work | Yes — cost dominates quality tradeoff |
| Interactive pair-programming | Maybe — latency of two-hop matters |

Rule of thumb: if the task has **planning complexity** but **execution is mechanical**, hybrid wins. If both planning and execution are hard, run a single Opus session.

## How OpenClaw Wires Two Agents Together

OpenClaw's `agent` CLI already supports agent-to-agent calls — any agent can invoke another via the `openclaw agent` command inside its own session. The advisor-hybrid config uses that mechanism: the Executor has a documented instruction to shell out to the Advisor when it hits a checkpoint.

Two SOUL.md files live in this directory:

| File | Agent | Model | Role |
|------|-------|-------|------|
| `ADVISOR.md` | `advisor-opus` | opus-4.6 | Plans, reviews, flags risk. Never executes. |
| `EXECUTOR-SOUL.md` | `executor-hybrid` | sonnet-4.6 (or GLM-5.1 / Gemma) | Does the work. Consults advisor at checkpoints. |

The Executor SOUL is written in the **Orion style** (structured markdown system prompt with Identity / Responsibilities / Behavioral Guidelines) so it slots into any existing OpenClaw setup without reformatting.

## Setup Walkthrough

### 1. Install both agents

```bash
# Create the two agent directories
mkdir -p ~/.openclaw/agents/advisor-opus
mkdir -p ~/.openclaw/agents/executor-hybrid

# Copy the SOUL files
cp configs/advisor-hybrid/ADVISOR.md       ~/.openclaw/agents/advisor-opus/SOUL.md
cp configs/advisor-hybrid/EXECUTOR-SOUL.md ~/.openclaw/agents/executor-hybrid/SOUL.md
```

### 2. Configure models

Edit `~/.openclaw/agents/advisor-opus/config.json`:

```json
{
  "model": "anthropic/claude-opus-4-6",
  "max_tokens": 4096,
  "tools": []
}
```

Note `"tools": []` — the advisor has **no tool access by design**. It can only return text.

Edit `~/.openclaw/agents/executor-hybrid/config.json`:

```json
{
  "model": "anthropic/claude-sonnet-4-6",
  "max_tokens": 8192,
  "tools": ["bash", "edit_file", "read_file", "openclaw_agent"]
}
```

Swap `claude-sonnet-4-6` for `glm-5.1`, `MiniMax-M3`, or an Ollama model if you want a cheaper executor. The `openclaw_agent` tool is what lets the executor call the advisor.

### 3. Test the handshake

```bash
openclaw agent --agent executor-hybrid --message "Refactor utils/parser.js to use async/await"
```

You should see the executor call `openclaw agent --agent advisor-opus` once at the start (for a plan), then run its edits, then optionally call the advisor again at the end for a review.

### 4. Wire into cron / triggers

For batch jobs, trigger the executor directly — it'll pull the advisor in as needed:

```bash
# Daily refactor pass
0 6 * * * openclaw agent --agent executor-hybrid --message "Run weekly tech-debt cleanup from tech-debt.md"
```

## Cost Math

Sample scenario: **1000 planning-heavy tasks/day**, average task = 15K input tokens + 3K output tokens.

### Opus-only baseline

| Item | Tokens | Rate (2026.4) | Cost |
|------|--------|---------------|------|
| Input  | 15K × 1000 = 15M  | $15 / M  | $225 |
| Output | 3K  × 1000 = 3M   | $75 / M  | $225 |
| **Daily** | | | **$450** |
| **Monthly** | | | **~$13,500** |

### Advisor-Hybrid (Opus advisor + Sonnet executor)

Assume the advisor is called **twice per task** on average (plan + review), ~2K input / ~500 output each time. The executor handles the rest.

| Item | Tokens | Rate (2026.4) | Cost |
|------|--------|---------------|------|
| Advisor input  | 4K × 1000 = 4M   | $15 / M  | $60 |
| Advisor output | 1K × 1000 = 1M   | $75 / M  | $75 |
| Executor input  | 15K × 1000 = 15M | $3 / M   | $45 |
| Executor output | 3K  × 1000 = 3M  | $15 / M  | $45 |
| **Daily** | | | **$225** |
| **Monthly** | | | **~$6,750** |

Roughly half the cost in this scenario. Swap the executor for GLM-5.1 or MiniMax-M3 and the executor line drops another order of magnitude — community reports on Reddit cite 60–80% total savings at that point.

**Rates above are illustrative** — always check live pricing before budgeting real workloads.

## Gotchas

- **Don't let the executor ping the advisor on every step.** The cheapest way to ruin the economics is to turn "consult advisor at checkpoints" into "consult advisor before every tool call." The Executor SOUL explicitly bounds this — read it before you tune it.
- **Batch advice requests.** If the executor is about to do five related things, it should ask the advisor *once* with a 5-item checklist, not five times.
- **Advisor has no tools.** Give it read-only context in the prompt. If you give it tools, it stops being an advisor and starts being a second executor — costs spike.
- **Context window matters.** When the executor asks for advice, it should send a *compact summary* of state (what's been tried, what failed), not a raw transcript. Dumping 50K tokens of history into Opus every checkpoint kills the savings.
- **Don't use hybrid for trivial tasks.** The two-hop overhead isn't worth it for "rename this variable."
- **Local executors drift more.** GLM-5.1 and Gemma executors benefit from more-frequent advisor checkpoints than Sonnet 4.6. Tune checkpoint frequency per model.
- **Logging.** Log every advisor call with token counts. Community reports of "hybrid didn't save me money" almost always trace back to unbounded advisor calls nobody noticed.

## Related Work

- **Anthropic Advisor Strategy announcement** — official launch for the Claude Platform, April 2026 (see r/ClaudeAI top post "We're bringing the advisor strategy to the Claude Platform").
- **r/openclaw community thread** — "Running agents on a cheap model + using Claude Code as an 'advisor' on your subscription" — early adaptation of the pattern to OpenClaw, where this config started.
- **@akshay_pachaar OpenClaw-RL** — related work on reinforcement-learning a small executor against a larger critic. Different training-time approach, same "big brain advises, small brain executes" intuition.

## See Also

- `configs/ollama/README.md` — if you want the executor to run fully local
- `agents/productivity/orion/SOUL.md` — the style the Executor SOUL is modeled on
