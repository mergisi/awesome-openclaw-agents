# Ariadne Loop Steward

> OpenClaw agent template for writing verifier-driven development loops.

## Overview

Ariadne Loop Steward turns rough engineering work into a repeatable agent loop:
inspect the real state, act with a narrow scope, verify with observable
evidence, then decide whether to continue, stop, roll back, or ask a human.

It is useful when OpenClaw is coordinating coding work that must survive long
threads, handoffs, release gates, or repeated status reports.

## Use Cases

| Request | Output |
|---------|--------|
| "Turn this GitHub issue into an agent task" | Snapshot, loop steps, verifiers, rollback rules |
| "Make this release safe for an agent to finish" | Release loop with publish gates and readback checks |
| "Continue this long debugging thread" | Resumable handoff packet with current state and stop rules |
| "Review this agent's JSON reports" | Continue, stop, rollback, or needs-human decision |

## Quick Start

```bash
mkdir -p ~/.openclaw/agents/ariadne-loop-steward/agent
cp SOUL.md ~/.openclaw/agents/ariadne-loop-steward/agent/

openclaw agents add ariadne-loop-steward --workspace ~/.openclaw/agents/ariadne-loop-steward
openclaw chat ariadne-loop-steward "Turn this bug report into a verifier-driven repair loop"
```

## Optional CLI

The companion CLI can generate sample loop artifacts:

```bash
python -m pip install git+https://github.com/zhangzeyu99-web/ariadne-loop.git
ariadne-loop quickstart --output .ariadne/quickstart
```

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Agent identity and loop-writing behavior |
| AGENTS.md | Operating rules for loop construction |
| HEARTBEAT.md | Wake-up checklist for recurring loop supervision |
| WORKING.md | Starting task template |

## Related Project

- Ariadne Loop: https://github.com/zhangzeyu99-web/ariadne-loop
- Browser builder: https://zhangzeyu99-web.github.io/ariadne-loop/playground.html
- OpenClaw guide: https://zhangzeyu99-web.github.io/ariadne-loop/openclaw.html

## Author

Created by [@zhangzeyu99-web](https://github.com/zhangzeyu99-web).

## License

MIT
