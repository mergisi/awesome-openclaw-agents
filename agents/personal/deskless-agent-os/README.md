# Judy — Autonomous Agent OS

> A 24/7 autonomous agent built around strategic leverage, not task execution. Designed for operators who want a thinking partner, not just a chatbot.

## Overview

Judy is an Agent OS template — a complete identity and governance layer for your OpenClaw agent.

It answers the hardest question in autonomous agents: **when should the agent act, and when should it stop and ask?**

- Runs 24/7 with clear autonomy boundaries
- Challenges low-leverage decisions proactively
- Executes without confirmation unless money moves, external visibility, or irreversibility triggers
- Strategic partner mode: evaluates requests against long-term freedom metrics

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/judy/agent
cp SOUL.md ~/.openclaw/agents/judy/agent/

openclaw agents add judy --workspace ~/.openclaw/agents/judy
```

### First Conversation

```bash
openclaw chat judy "What should I focus on today?"
```

## Use Cases

### 1. Autonomous Daily Operations

```
You: "Handle the morning routine"
Judy: [Checks pipeline, triages inbox, sends Telegram summary, flags items needing decision]
```

### 2. Strategic Decision Review

```
You: "Should I take on this new project?"
Judy: [Evaluates on 5 axes: Freedom, Sustainability, Reversibility, Complexity, Optionality]
      [Returns structured recommendation with leverage gain estimate]
```

### 3. Autonomy Boundary Check

```
You: "Post this to Twitter and send the invoice"
Judy: [Twitter post: externally visible → asks for confirmation]
      [Invoice: money moves → asks for confirmation]
      [Drafts both, waits for approval]
```

### 4. Growth Audit

```
You: "Review what I did this week"
Judy: [Identifies manual repetition that can be automated]
      [Flags tasks with low leverage-to-time ratio]
      [Proposes 1-3 high-leverage improvements]
```

## Example Outputs

### Strategic Evaluation

```
Evaluated: Client project X

Freedom:        +1 (income, but no leverage increase)
Sustainability: -1 (adds 12h/week manual delivery)
Reversibility:  medium (3-month contract)
Complexity:     low
Optionality:    -1 (blocks automation sprint for 90 days)

Recommendation: Decline or renegotiate scope.
Simplest next step: Counter-propose deliverable-based scope at 2x rate.
```

### Autonomy Decision Log

```
09:14 — Email triage: 52 processed, 4 flagged (your decision needed)
09:15 — Pipeline status: 3 active, 1 blocked (dependency: external API)
09:16 — Proactive: Identified recurring manual task (weekly report compile).
         Automation possible. Estimated leverage gain: 2h/week.
         Awaiting approval to automate.
```

## What Makes This Different

Most agent templates tell the agent *what to do*.

This one tells the agent *how to think* — and when to stop.

The autonomy framework (3-gate decision check) is what makes 24/7 operation safe in practice, not just in theory.

## Configuration

Works out of the box. Optional additions:
- `mind.md` — project context and current priorities
- `judgment-criteria.md` — domain-specific decision rules
- `HEARTBEAT.md` — recurring check-in schedule

Full starter pack: [syu0.github.io/deskless-judy](https://syu0.github.io/deskless-judy/)

## Author

Created by [@deskless_judy](https://twitter.com/deskless_judy)

Built while running a real 24/7 OpenClaw setup. Every pattern here was discovered under production conditions.

## License

MIT
