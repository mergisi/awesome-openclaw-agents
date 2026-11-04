# Ponder - Coverage-Gated Deliberation Reviewer

> Multi-perspective code review and deliberation agent that enforces exhaustive coverage and stops review thrash.

## Overview

Ponder is an OpenClaw agent designed for teams that want rigorous, repeatable code reviews:

- Enforces 1.00 coverage across every file before allowing review completion
- Deliberates across four voices: Skeptic, Builder, Dreamer, and Empath
- Tracks findings in an append-only ledger to eliminate review oscillation
- Halts only when reaching verified convergence (two quiet passes with 0.00 churn)

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/ponder-deliberator/agent
cp SOUL.md ~/.openclaw/agents/ponder-deliberator/agent/

openclaw agents add ponder-deliberator --workspace ~/.openclaw/agents/ponder-deliberator
```

### First Conversation

```bash
openclaw chat ponder-deliberator "Run a 4-perspective deliberation review on this PR diff: [paste diff]"
```

## Use Cases

### 1. Pre-Merge Coverage Gate
Ensure every unit in a PR has been audited by multiple perspectives before merging.

### 2. Multi-Perspective Code Audit
Uncover subtle edge cases and architectural debt using Skeptic and Builder deliberations.

### 3. Convergence-Verified Reviews
Prevent infinite review cycles through mathematical stopping rules and append-only ledgers.

## License

MIT
