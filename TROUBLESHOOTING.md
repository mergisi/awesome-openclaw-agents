# Troubleshooting OpenClaw

A consolidated runbook for the stability, cost, and integration issues that keep showing up in [r/openclaw](https://reddit.com/r/openclaw) and adjacent communities. This file is maintained as a community reference — every entry cites a source so you can verify symptoms against your own setup before applying a fix.

**Current stable baseline:** `2026.4.11`
**Last reviewed:** 2026-04-13

---

## Table of contents

- [Quick diagnosis table](#quick-diagnosis-table)
- [Known issues by version](#known-issues-by-version)
- [Cost overruns](#cost-overruns)
- [Bot is dead / unresponsive](#bot-is-dead--unresponsive)
- [Heartbeat failure modes](#heartbeat-failure-modes)
- [Model-specific gotchas](#model-specific-gotchas)
- [Escalation: when to ask the community](#escalation-when-to-ask-the-community)
- [Contributing](#contributing)

---

## Quick diagnosis table

Start here. Match the symptom, confirm the cause in the linked section, then apply the fix.

| Symptom | Most likely cause | Fix | Section |
|---|---|---|---|
| Bot answers a few turns then goes silent | heartbeat-model failure or provider timeout | Restart gateway, verify heartbeat config | [Heartbeat](#heartbeat-failure-modes) |
| Costs spiked overnight with no traffic change | Claude cache TTL regression (1h → 5m) OR `2026.4.8` daily-reset bug | Pin Opus 4.6 cache headers, upgrade to `2026.4.11` | [Cost overruns](#cost-overruns) |
| Telegram channel silent, no errors in gateway log | `2026.4.7` Telegram regression | Upgrade to `2026.4.11` | [v2026.4.7](#v202647--telegram-channel-broken) |
| API bill 3-5x normal, `daily_budget` ignored | `2026.4.8` daily session reset regression | Upgrade to `2026.4.11` or patch `gateway/budget.ts` | [v2026.4.8](#v202648--daily-reset-regression) |
| `openclaw agent --status` returns `UNKNOWN` | Sessions file corruption | Delete `~/.openclaw/agents/<name>/sessions/sessions.json` | [Bot is dead](#bot-is-dead--unresponsive) |
| Claude API key banned despite pay-as-you-go | Burst rate-limit tripped abuse detection | Contact Anthropic support, throttle retries | [Claude Opus/Sonnet](#claude-opussonnet) |
| GPT 5.4 "feels lobotomized" in OpenClaw | Config issue, not the model | Set `thinking=high` + `fastmode=true` | [GPT 5.4](#gpt-54) |
| Minimax agent refuses commercial tasks | Self-hosted M2.7 commercial license caveat | Switch to hosted M3 or obtain license | [Minimax](#minimax) |
| Memory files grow unbounded, latency creeps up | Context bloat | Compile memory, prune unused entries | [Context bloat](#context-bloat-from-memory-files) |
| Opus token count climbs with no new tasks | Advisor executor runaway loop | Kill executor, check `last-plan.json` | [Advisor loop runaway](#advisor-loop-runaway) |
| Bot process alive but all agents report `stale` | Gateway heartbeat thread died | Restart gateway (`openclaw gateway restart`) | [Heartbeat](#heartbeat-failure-modes) |

---

## Known issues by version

OpenClaw releases weekly. The community sentiment, summarized by [one user](https://reddit.com/r/openclaw/comments/1sj9ich/), is that `2026.4.11` is "the first version in a while that did not break things." That matches our testing — if you are on anything between `2026.4.7` and `2026.4.10` and you can upgrade, upgrade.

### v2026.4.11 (stable baseline)

**Status:** Recommended. No known regressions as of 2026-04-13.

What's fixed relative to `4.10`:
- Daily session reset honors `daily_budget` again (fixes `4.8` regression).
- Telegram channel handler no longer drops updates silently (fixes `4.7` regression).
- Heartbeat thread restarts on provider 5xx instead of wedging.

Source: [Is v.2026.4.11 the first version in a while that did not break things?](https://reddit.com/r/openclaw/comments/1sj9ich/)

### v2026.4.10 — no known issues (but skip it)

No confirmed regressions, but it also does not contain the `4.11` fixes. Skip directly to `4.11`.

### v2026.4.9 — no known issues (but skip it)

Same note. The community post history shows no specific complaints tied to `4.9`, but it still carries the `4.8` and `4.7` regressions.

### v2026.4.8 — daily reset regression

**Symptom:** API bill inflates silently overnight. `daily_budget` setting appears to be ignored. Session counters reset more often than once per day, so rate caps never trigger.

**Impact:** Reported overnight cost multipliers of 3-5x. This one is dangerous because there is no error in the logs — the gateway keeps running, it just resets the budget counter too aggressively.

**Detection:** Compare `~/.openclaw/metrics/daily.json` row count against wall-clock days. More than one row per day = you are affected.

**Fix:** Upgrade to `2026.4.11`. If you cannot upgrade, patch `gateway/budget.ts` to re-read the reset timestamp from disk on every tick instead of caching it in memory.

Source: [Regression in 2026.4.8 that silently breaks daily session reset and inflates your API bill](https://reddit.com/r/openclaw/comments/1shmg6l/)

### v2026.4.7 — Telegram channel broken

**Symptom:** Telegram bot appears connected (`--status` returns `OK`), but messages from users never reach agents. Outbound messages from agents also fail, but without raising an error.

**Impact:** For users who rely on Telegram as their primary mobile interface, this looks like the bot is "dead" even though the gateway is healthy.

**Detection:** Send a known test message to your bot and watch `~/.openclaw/gateway/logs/telegram.log`. On `4.7` you will see the webhook hit but no dispatch.

**Fix:** Upgrade to `2026.4.11`. Rollback to `2026.4.6` also works if you cannot upgrade forward.

Source: [OpenClaw 2026.4.7 Broke Telegram for Me](https://reddit.com/r/openclaw/comments/1sfh79p/)

### v2026.4.6 — last known-good before the `4.7`/`4.8` window

If you need to roll back and cannot jump forward, `4.6` is the safest rollback target. No known critical issues, missing only the multimedia agents shipped in `4.5`.

### v2026.4.5 — multimedia agents introduced

`video_generate` and `music_generate` agents shipped here. No known regressions. If you use deploy packages that reference multimedia agents, this is your floor.

### Older versions

Not actively tracked in this document. If you are on anything below `2026.4.5` and seeing issues, upgrade first, then re-diagnose.

---

## Cost overruns

Three causes account for almost every "why did my bill explode" post in the last month. Check them in this order.

### Claude cache TTL regression (1h → 5m)

**What happened:** Anthropic's prompt cache TTL silently regressed from 1 hour to 5 minutes on some account tiers. Long-running agents that relied on cache hits for cost stability started re-reading full context on every turn.

**What it looks like:**
- Input token count per turn roughly doubles with no change to your agent code.
- Cache-read token count collapses to near zero.
- Cost-per-session curve goes from flat to linear-in-turns.

**Detection:** In your usage logs, compare `cache_read_input_tokens` vs `input_tokens` over the last 14 days. If the ratio fell off a cliff on a specific date, you are affected.

**Mitigation:**
1. Pin your Claude requests to explicit `cache_control: {"type": "ephemeral"}` blocks on the system prompt and tool definitions. Do not rely on implicit caching.
2. Batch turns so that sequential tool calls stay inside a 5-minute window — if you cannot amortize over 1 hour, amortize over 5 minutes.
3. For agents that idle for more than 5 minutes between turns, consider a different model tier where cache behavior is stable.

Source: [Did they just find the issue with Claude? "Cache TTL silently regressed from 1h to 5m"](https://reddit.com/r/ClaudeAI/comments/1sjxrp1/)

### Advisor loop runaway

**What happens:** If you use the advisor pattern (Scout plans, executor runs), an executor bug can cause it to re-query Opus for the same plan repeatedly. Each loop burns Opus input tokens against an unchanged plan. Users have reported overnight Opus spend 10-20x normal.

**Detection:** Watch Opus input token count per session. If a single `--from-plan` run exceeds `2 * plan_size`, you are looping.

**Common causes:**
- Executor hallucinates that a step failed when it actually succeeded, then re-plans.
- `last-plan.json` was not overwritten between runs, so executor keeps loading the old plan.
- Fire-and-forget invocation without tracking `run.cjs` exit codes.

**Fix:**
1. Always check `run.cjs` exit status. Do not fire-and-forget.
2. Before every run, explicitly copy the intended plan: `cp last-plan-{config}-{track}.json last-plan.json`.
3. Add a hard cap on Opus calls per session in your executor config (`max_opus_calls_per_run: 3` is a safe starting point).

### Context bloat from memory files

**What happens:** Memory files grow unbounded as agents append to them. Once memory exceeds roughly 50k tokens, every session pays to re-read the full file even if most of it is irrelevant to the current task.

**Detection:** `wc -l ~/.openclaw/agents/<name>/memory/*.md` — if total is above ~8000 lines, you are paying for it on every turn.

**Mitigation:**
1. Compile memory instead of exploring it. Maintain a short index file that points to detail files; only load detail files when a task explicitly needs them.
2. Archive memory entries older than 30 days into a cold store that agents don't load by default.
3. See the `memory-wiki/` pattern in the main repo for the "compile, don't explore" approach.

---

## Bot is dead / unresponsive

### Diagnosis tree

Work down the list. Stop at the first step that reveals the problem.

1. **Is the gateway process alive?**
   `ps aux | grep openclaw-gateway` — if no process, `openclaw gateway restart`.

2. **Is heartbeat enabled and running?**
   `openclaw agent --agent <name> --status` — look for `heartbeat: ok`. If `heartbeat: stale`, jump to [Heartbeat](#heartbeat-failure-modes).

3. **Is the model provider reachable?**
   Hit your provider status page. Anthropic and OpenAI both have had multi-hour degradations in the last month. Check before assuming it's your setup.

4. **Are sessions corrupted?**
   `cat ~/.openclaw/agents/<name>/sessions/sessions.json | head` — if it's not valid JSON, delete it. OpenClaw will recreate on next run.

5. **Is the API key still valid?**
   Test the raw key with `curl` against the provider. Banned keys return `401` or `403` with no useful message from OpenClaw. See [Claude API account banned](#claude-opussonnet).

6. **Is disk full?**
   Metrics and session logs can fill up a small VM fast. `df -h` — if you're above 95%, clear `~/.openclaw/metrics/archive/`.

7. **Is the port bound?**
   Gateway default is 18789. `lsof -i :18789` — if nothing is listening, restart gateway.

### The "bot died on April 4" recovery

A representative case from the community: gateway process alive, all agents showing `stale`, no errors in logs, last successful message timestamped April 4. The user recovered it by running the full gateway from inside Claude Code as a subprocess, which restored state after restart.

**Recovery steps that worked:**
1. Stop the gateway.
2. Back up `~/.openclaw/agents/*/sessions/` to a timestamped directory.
3. Delete the session files (not the agent configs).
4. Restart the gateway.
5. Send one test message per agent to rebuild session state.

This is also the right sequence for any "everything looks fine but nothing responds" symptom where the diagnosis tree above didn't catch it.

Source: [My OpenClaw bot died on April 4. I got it back inside Claude Code.](https://reddit.com/r/openclaw/comments/1sjz8n1/)

---

## Heartbeat failure modes

### What heartbeat actually is

In OpenClaw, "heartbeat" is a background thread inside the gateway that periodically pings each agent's model provider with a minimal request. It serves two purposes: keep session state warm, and detect provider degradation before user-facing requests time out. The model used for these pings is the "heartbeat-model."

A lot of recent r/openclaw posts are about finding the right heartbeat-model. The tension is: you want something cheap (it pings every 30-120 seconds), fast (it shouldn't add latency), and stable (you don't want the heartbeat itself to be the thing that breaks).

Source: [The search for a new "heartbeat-model"](https://reddit.com/r/openclaw/comments/1sgk8nj/) and [For All Noobies - Heartbeat.MD](https://reddit.com/r/openclaw/comments/1sj9bzr/)

### Common failure modes

| Mode | Symptom | Root cause | Fix |
|---|---|---|---|
| Heartbeat wedge | `--status` returns `stale`, gateway process still running | Heartbeat thread deadlocked on a 5xx response | Restart gateway. Upgrade to `2026.4.11` which adds thread restart on 5xx. |
| Heartbeat cost creep | Heartbeat model bill grows linearly | Heartbeat-model too expensive for your ping interval | Switch to a smaller model (Haiku tier) or increase ping interval to 300s. |
| False negatives | Heartbeat reports `ok` but real requests fail | Heartbeat-model is on a different provider than agent-model | Align heartbeat-model provider with your primary agent-model provider. |
| Heartbeat spam | Provider rate-limits your account | Ping interval too tight, no jitter | Add jitter to the interval, never go below 30s. |

### Recommended heartbeat-model choices (2026-04-13)

- **Claude Haiku 4** — cheapest, most stable, same provider as most OpenClaw agents. Default recommendation.
- **GPT-4.1 nano** — good if your primary agents are on OpenAI.
- **Gemini Flash 2.5** — cheap, but different provider from most setups; only use if that's where your agents live too.

Do not use Opus, Sonnet, or GPT-5.x as a heartbeat-model. You will regret it on the bill.

### Heartbeat config sanity checks

```yaml
heartbeat:
  enabled: true
  model: claude-haiku-4
  interval_seconds: 60
  jitter_seconds: 15
  max_consecutive_failures: 3
  on_failure: restart_thread   # was "wedge" in < 2026.4.11
```

`on_failure: restart_thread` is only available on `2026.4.11` and later. On older versions, you must restart the gateway manually when heartbeat wedges.

---

## Model-specific gotchas

### GPT 5.4

The short version, from a well-upvoted post: **a lot of "GPT 5.4 sucks in OpenClaw" reports are config issues, not the model.**

Most common fix:
- Set `thinking=high` on the agent config. `thinking=low` gives you a much weaker model than the benchmarks you saw.
- Set `fastmode=true`. Counterintuitively, this reduces latency without dropping quality for most agent workloads.
- Do not stack `thinking=high` with `temperature > 0.4` — outputs get unstable.

If you have applied all three and the model still feels weak, then you have an actual model issue. Before that, assume config.

Source: [A lot of the new "GPT 5.4 sucks in OpenClaw" posts are really config issues](https://reddit.com/r/openclaw/comments/1sgpg8b/)

### Claude Opus / Sonnet

Three live issues to know about:

1. **Account ban risk with rapid API calls.** One user reported their pay-as-you-go account getting banned after a burst of retries. Anthropic's abuse detection does not distinguish between "user hitting retry" and "script in a loop." If OpenClaw returns an error, do not retry more than 3 times with exponential backoff.
   Source: [Claude API account banned despite pay as you go setup](https://reddit.com/r/openclaw/comments/1sf7iac/)

2. **Cache TTL bug.** See [cost overruns](#claude-cache-ttl-regression-1h--5m). This is the biggest live cost issue.

3. **Session size limits.** "Hello uses 4%" threads are real — with large system prompts and tool definitions, a single message can eat 4-6% of the context window before you say anything. Keep system prompts tight and use prompt caching aggressively.

### GLM-5.1

Generally stable. Known constraint: the OpenClaw provider adapter does not support tool streaming on GLM-5.1 yet, so tool-heavy agents will feel laggy. If your agent uses tools, prefer Claude or GPT.

### Minimax

The bundle defaults to **MiniMax M3** on the hosted API (512K context, up to 128K output, image input), with M2.7 still supported for users who self-host the open weights.

**Commercial license caveat (self-hosted M2.7 only):** the M2.7 checkpoint most people pull from the model hub is non-commercial only. If you use it in a product, you need a commercial license from Minimax. This is not an OpenClaw bug — but agents using self-hosted M2.7 will sometimes refuse to complete commercial-looking prompts due to the system-level license notice baked into the weights.

Fix: either obtain the commercial license, or use the hosted M3 / M2.7 API (whose TOS supersedes the weights license) for commercial deployments.

---

## Escalation: when to ask the community

### Before you post

Check, in order:
1. This file, for a version or symptom match.
2. The OpenClaw changelog for your running version.
3. Recent [r/openclaw](https://reddit.com/r/openclaw) posts (last 7 days) — your issue may already be answered.
4. GitHub issues on the main OpenClaw repo, filtered for your version tag.

### Post format template for r/openclaw

Copy this when you post. Incomplete bug reports get ignored; complete ones usually get a fix in under 24 hours.

```
**OpenClaw version:** 2026.4.X
**OS:** macOS 14.x / Ubuntu 22.04 / ...
**Primary model:** claude-opus-4.6 / gpt-5.4 / ...
**Heartbeat model:** claude-haiku-4 / none
**Symptom (one sentence):**
**When did it start:** YYYY-MM-DD
**What changed just before:** upgraded from X to Y / new agent / new key / nothing

**Repro steps:**
1.
2.
3.

**Expected:**
**Actual:**

**Logs (redacted):**
```
tail -100 ~/.openclaw/gateway/logs/gateway.log
```

**What I already tried:**
- [ ] Restarted gateway
- [ ] Cleared sessions
- [ ] Checked provider status
- [ ] Read TROUBLESHOOTING.md
```

The checklist at the end saves everyone time. If you've already cleared sessions, people won't tell you to clear sessions.

### What not to post

- "OpenClaw is broken" with no version number.
- Screenshots of error popups with no surrounding log context.
- "Is anyone else seeing this?" without a symptom description.

These get dismissed because there is nothing to act on.

---

## Contributing

PRs to this file are welcome. Each new issue entry must have:

- **Symptom** — what the user sees, in one sentence.
- **Repro** — minimum steps to reproduce, or "intermittent" if you cannot reliably reproduce.
- **Fix** — concrete action, not speculation.
- **Source** — a Reddit permalink, GitHub issue link, or an OpenClaw version tag. Entries without a source will not be merged. "Trust me" is not a source.

Keep the tone calm and neutral. This file is a runbook, not a marketing piece and not a rant. If an entry reads like either, it will get rewritten before merge.

When a version ages out of the supported window (roughly 8 weeks), move its entry from [Known issues by version](#known-issues-by-version) to a historical section at the bottom, but do not delete it — users on old pins still need to find it via search.
