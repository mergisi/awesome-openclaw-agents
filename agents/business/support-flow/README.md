# SupportFlow — The Complete Support Agent

A production-ready customer support agent for e-commerce and SaaS businesses. Handles first-contact resolution, returns, troubleshooting, and escalation — with memory of past interactions.

## Use Cases

- **E-commerce:** Shipping questions, returns, order issues, product troubleshooting
- **SaaS:** Account help, billing questions, feature how-tos, bug triage
- **Service businesses:** FAQ responses, appointment issues, complaint intake

## What Makes This Different

Unlike minimal support prompts, SupportFlow is a complete operating configuration:

- **Knowledge base structure** — Shipping, returns, and product-issue sections ready to customize
- **Escalation rules** — Knows exactly when to hand off to a human (threats, legal issues, refunds >$500, security concerns)
- **Memory schema** — Tracks order history, past issues, communication preferences per customer
- **Heartbeat tasks** — Checks unanswered tickets, reviews escalations, monitors social mentions every 2 hours
- **Multi-channel ready** — Email, web chat, Telegram configurations included
- **Boundaries** — Won't over-promise refunds, won't share customer data, won't invent product specs

## Quick Start

```bash
# Copy the SOUL.md into your agent workspace
cp agents/business/support-flow/SOUL.md ~/.openclaw/workspace/SOUL.md

# Register the agent
openclaw agents add ./SOUL.md

# Start it
openclaw agent start support-flow
```

## Customization

Edit the Knowledge Base section with your actual business policies:
- Shipping timelines and carriers
- Return windows and conditions
- Refund processing times
- Product-specific troubleshooting steps

The escalation thresholds ($500 refund limit, etc.) are defaults — adjust for your business.

## Source

Part of the [BizClaw](https://cyberleo986.github.io/bizclaw-site/) template library. This is the free template — paid templates cover lead qualification, appointment booking, and research workflows.