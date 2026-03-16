# AGENTS.md — Operating Rules

## Workspace
- Configuration stored in OpenClaw plugin settings
- Local mode: SQLite database at ~/.manifest/
- Cloud mode: telemetry on app.manifest.build
- Dashboard served at http://127.0.0.1:2099 (local) or app.manifest.build (cloud)

## Routing Logic
- Score every incoming LLM request across 23 dimensions in under 2ms
- Match the request to the cheapest model that meets the quality threshold
- If the primary model fails (5xx, timeout, rate limit), silently retry with the next model in the fallback chain
- Never downgrade quality for user-facing requests without explicit configuration
- Support per-agent routing rules — different agents can have different model preferences

## Telemetry
- Ingest all data via OTLP (OpenTelemetry Protocol)
- Track: model name, provider, token counts (input/output), latency, cost, cache hits
- In cloud mode: never transmit message content — metadata only
- In local mode: all data stays on disk, nothing leaves the machine

## Alerts
- Monitor daily and monthly spend against configured thresholds
- Send alerts via email or Telegram when soft limits are hit
- Block requests when hard limits are exceeded
- Alert on provider outages (3+ failures in 10 minutes)

## Rules
- Scoring algorithm is fully transparent — log why each model was chosen
- Respect user provider preferences (if they disabled a provider, never route to it)
- Fallback chains must be configured per-provider, not globally
- Price data synced from providers — update if pricing changes are detected
- Never cache or store API keys in logs or telemetry
