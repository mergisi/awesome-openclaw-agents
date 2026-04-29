# ✦ Faro - LinkedIn Brand Strategist & Social Seller

> AI agent that positions B2B founders on LinkedIn and converts attention into qualified pipeline.

## Overview

Faro combines a **Brand Director** (content strategy, voice, pillars) with a **Social-Selling AE** (warm outreach, ICP targeting, discovery booking) into one OpenClaw agent. Built on the 2026 algorithm rules: dwell time, saves + sends, document carousels, and warm-only outreach (14.6% reply rate vs 1.7% cold).

Unlike generic "LinkedIn AI writers," Faro enforces scope discipline (one brand, one ICP), executes a 7-step outreach funnel, and tracks the only metric that matters: qualified discovery calls per month.

## Quick Start

```bash
mkdir -p ~/.openclaw/agents/faro/agent
cp SOUL.md ~/.openclaw/agents/faro/agent/
openclaw agents add faro --workspace ~/.openclaw/agents/faro
```

Then create a `USER.md` describing the founder, the brand being sold, the ICP, and the offers. Faro reads it and runs.

## Use Cases

| Request | Output |
|---------|--------|
| "Draft 3 posts for next week" | 3 drafts × 3 hook variants + carousel slide outline |
| "Find 50 ICP prospects" | Sales Nav search + trigger column + DM angle per prospect |
| "Audit my LinkedIn profile" | Full diagnostic + headline A/B/C + About rewrite (<2,600 chars) |
| "Why did this post flop?" | Algorithm-2026 analysis + pattern capture for memory |
| "Book me discovery calls" | Warm-outreach pipeline tracker, status per prospect |
| "Validate my 4 pillars" | Pillar critique + 30 seed-ideas per pillar (120 posts backlog) |
| "Write a contrarian post on X" | Bold-contrarian hook + body + close + carousel optional |

## Example

```
You: "Founder of a B2B SaaS for mid-market HR. Position me on LinkedIn."

Faro:
WEEK-1 PLAN

Profile audit (issues found):
  - Headline reads "CEO at Acme | Building the future of HR" — generic, low-CTR
  - About is 4 paragraphs of feature-talk, zero hook
  - Banner is default LinkedIn blue
  - Featured section: empty

Headline A/B/C proposal:
  A) "I help mid-market HR teams cut hiring time 40% with AI. CEO Acme."
  B) "Mid-market HR is broken. We're fixing time-to-hire. CEO Acme."
  C) "Mid-market HR teams: stop losing candidates to Big Tech. CEO Acme · 40% faster hiring."

Recommended: C (specific number, named ICP, named pain).

4 Pillars (proposed):
  1. HR Hiring Reality Check (contrarian, what's broken)
  2. Customer Cases (anonymized wins with numbers)
  3. Frameworks (interview rubrics, comp benchmarks, hiring loops)
  4. POV vs Big HR Tech (Workday, Greenhouse, Lever takes)

Pilot posts (drafted, 3 hooks each):
  Post 1 hook A: "Most HR tech promises 'AI-powered'. Almost none actually saves time."
  Post 1 hook B: "I audited 12 HR platforms. Only 2 cut hiring time. Here's why."
  Post 1 hook C: "Workday isn't your problem. Your interview loop is."
  [...]

50 ICP prospects identified (CSV ready).
Analytics baseline: 432 followers, 3 posts/30d avg, 12 likes median, 0 saves tracked.

ONE question: which headline (A/B/C) do you want to ship today?
```

## Files

| File | Purpose |
|------|---------|
| `SOUL.md` | Faro's identity, voice rules, algorithm knowledge, 7-step funnel |
| `README.md` | This guide |

## Recommended Companion Files (create in your workspace)

Faro works best with these workspace files (described in `SOUL.md`):

- `USER.md` — the founder + brand being positioned
- `MEMORY.md` — published posts, metrics, leads, decisions
- `content/pillars.md` — your 4 pillars × 30 seed ideas
- `icp/profile.md` — Primary/Secondary/Tertiary ICP
- `outbound/playbook.md` — detailed 7-step funnel
- `frameworks/algorithm-2026.md` — LinkedIn algo cheat sheet

A reference implementation for a real founder use case is available at: [github.com/pabesfu/faro](https://github.com/pabesfu/faro)

## Methodology Sources

- [Justin Welsh — LinkedIn Operating System](https://learn.justinwelsh.me/linkedin)
- LinkBoost State of LinkedIn 2026
- Edelman-LinkedIn B2B Thought Leadership Impact Report 2025
- [OpenClaw Dreaming docs](https://docs.openclaw.ai/concepts/dreaming)

## Author

[Pablo Estrada](https://github.com/pabesfu) · Founder, [Catalizadora.ai](https://catalizadora.ai/)
