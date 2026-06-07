---
name: openclaw-debugger
description: Trigger when an OpenClaw agent is broken, silent, crashing, stuck, not responding, returning empty output, or the user says "my agent is down", "agent not working", "/openclaw-debugger". Walks through the standard OpenClaw 2026.4 diagnosis checklist and prints a report.
---

# OpenClaw Debugger

Diagnose a broken OpenClaw agent (Orion, Echo, Radar, or any custom agent from `awesome-openclaw-agents`). Produces a structured diagnosis report identifying the most likely root cause.

Compatible with OpenClaw 2026.4.11 and later. For deeper reference see `TROUBLESHOOTING.md` in this repo.

## When to use

- Agent returns empty output or times out
- `openclaw agent --agent <name> --message "..."` hangs
- Heartbeat dashboard shows the agent as stale
- Model provider errors (429, 401, connection refused)
- User says "openclaw is broken" / "agent is down" / "why is Orion not replying"

## Instructions

Work through the checklist in order. Stop at the first failing step and report it — no need to run later steps until that's fixed.

### 1. Gateway health

```bash
openclaw agent --status
```

- If the gateway is down, tell the user to run `openclaw gateway restart`.
- If it reports "port 18789 in use by another process", find and kill the stale process (`lsof -i :18789`).

### 2. Tail recent logs

```bash
tail -n 200 ~/.openclaw/logs/gateway.log
tail -n 200 ~/.openclaw/agents/<name>/logs/agent.log
```

Grep for `ERROR`, `PANIC`, `401`, `429`, `timeout`. The first error in the tail is usually the real cause — everything after is fallout.

### 3. Heartbeat status

```bash
cat ~/.openclaw/agents/<name>/heartbeat.json
```

- Check `last_seen` timestamp. More than 5 minutes old = worker crashed.
- If `status` is `starting` for more than 60s, the agent is stuck in init (usually a bad `SOUL.md` or missing env var).

### 4. Session file integrity

```bash
ls -la ~/.openclaw/agents/<name>/sessions/sessions.json
```

- If the file is >5 MB, sessions may be corrupt. Back it up and delete:
  ```bash
  mv ~/.openclaw/agents/<name>/sessions/sessions.json{,.bak}
  ```
- If the JSON is invalid (`python3 -m json.tool < sessions.json`), same fix.

### 5. Model provider reachability

Read `~/.openclaw/agents/<name>/SOUL.md` frontmatter to find the configured `model` and `provider`. Then:

- **Anthropic (Opus 4.6, Sonnet 4.6):** `echo $ANTHROPIC_API_KEY | head -c 10` — confirm key exists.
- **GLM-5.1 / Minimax M3:** check `~/.openclaw/providers.json` for the base URL and hit `/v1/models` with curl.
- **Gemma 4 local:** confirm Ollama or the local runtime is up (`curl localhost:11434/api/tags`).

A 401 means bad key. A 429 means you're rate limited — retry with exponential backoff or switch model. Connection refused on localhost means the local runtime crashed.

### 6. SOUL.md validity

Read the agent's `SOUL.md` and check:
- YAML frontmatter parses (must have `name`, `model`, `system_prompt` fields)
- `model` string matches one in `~/.openclaw/providers.json`
- No lingering Turkish prompts if the agent is supposed to respond in English (per repo rules)

## Output format

Print a diagnosis report like this:

```
OpenClaw Debugger — <agent-name>

[OK]     Gateway up (port 18789)
[OK]     Logs clean
[FAIL]   Heartbeat stale (last_seen 14 min ago)
[SKIP]   Session file
[SKIP]   Model provider
[SKIP]   SOUL.md

Root cause: worker process crashed ~14 min ago. Last log line:
  ERROR 2026-04-13T08:41:02 panic: model provider returned 401

Fix:
  1. Export a fresh ANTHROPIC_API_KEY
  2. openclaw gateway restart
  3. openclaw agent --agent <name> --message "ping"
```

Keep it terse. The user wants a fix, not an essay.

## Example invocations

- `/openclaw-debugger orion`
- "My Echo agent is stuck — debug it"
- "Why is `openclaw agent --agent radar` timing out?"
