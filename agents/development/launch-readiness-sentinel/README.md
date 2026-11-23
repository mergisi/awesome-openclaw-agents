# Sentinel - Pre-Launch Security, DNS & Crawler Readiness Auditor

> Evidence-driven release gate agent that catches leaked frontend secrets, missing CSP/HSTS headers, broken SPF/DMARC DNS, and `llms.txt` gaps before production deploy.

## Overview

Sentinel is an OpenClaw development agent built for teams shipping web and SaaS releases:

- Audits `NEXT_PUBLIC_*` / `VITE_*` client bundle secret exposure, `.js.map` sourcemaps, and missing Supabase/Postgres RLS
- Generates framework-native Nonce CSP, HSTS, COOP, Permissions-Policy, and RFC 9116 `/.well-known/security.txt` configs
- Verifies SPF (`<= 10` DNS lookups), DKIM, DMARC (`p=quarantine`/`p=reject` + `rua`), and BIMI records
- Checks `/robots.txt` AI crawler rules, `/llms.txt`, and JSON-LD structured data

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/launch-readiness-sentinel/agent
cp SOUL.md ~/.openclaw/agents/launch-readiness-sentinel/agent/

openclaw agents add launch-readiness-sentinel --workspace ~/.openclaw/agents/launch-readiness-sentinel
```

### First Conversation

```bash
openclaw chat launch-readiness-sentinel "Run a 4-pillar pre-launch security, DNS, and crawler readiness audit on this Next.js repo and staging domain."
```
