# 🦞 Awesome OpenClaw Agents

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Stars](https://img.shields.io/github/stars/mergisi/awesome-openclaw-agents?style=social)](https://github.com/mergisi/awesome-openclaw-agents)
[![Agents](https://img.shields.io/badge/agents-101-blueviolet)](agents/)

> A curated collection of **101 production-ready AI agent templates** for the OpenClaw ecosystem. Every template is a copy-paste ready `SOUL.md` file.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:4F46E5,100:7C3AED&height=180&section=header&text=%F0%9F%A6%9E%20101%20OpenClaw%20Agent%20Templates&fontSize=36&fontColor=ffffff&fontAlignY=35" width="100%"/>
</p>

<div align="center">

### Don't want to set up Docker, VPS, or configs yourself?

**[Deploy any agent in 60 seconds with CrewClaw →](https://crewclaw.com/create-agent)**

Pick a role. Customize the config. Get a full deploy package. No terminal required.

</div>

---

## Contents

- [Agent Templates](#agent-templates) (101 agents across 18 categories)
  - [Productivity](#productivity) · [Development](#development) · [Marketing](#marketing--content) · [Business](#business) · [Personal](#personal)
  - [DevOps](#devops) · [Finance](#finance) · [Education](#education) · [Healthcare](#healthcare) · [Legal](#legal) · [HR](#hr) · [Creative](#creative) · [Security](#security)
  - [E-Commerce](#e-commerce) · [Data](#data) · [SaaS](#saas) · [Real Estate](#real-estate) · [Freelance](#freelance)
- [Use Cases](#use-cases) (132 real-world examples)
- [Quickstart](#quickstart)
- [Why OpenClaw?](#why-openclaw) (Comparison)
- [Quick Deploy with CrewClaw](#quick-deploy-with-crewclaw)
- [MCP Servers](#mcp-servers)
- [Integrations](#integrations)
- [Tools](#tools)
- [Tutorials & Guides](#tutorials--guides)
- [Community](#community)

---

## Agent Templates

Ready-to-use SOUL.md templates for your AI agents. Copy the SOUL.md, register with `openclaw agents add`, and start the gateway.

```bash
# Quick start with any template
git clone https://github.com/mergisi/awesome-openclaw-agents.git
cd awesome-openclaw-agents/quickstart
npm install && cp ../agents/productivity/orion/SOUL.md ./SOUL.md
node bot.js
```

> All 101 agents are also available as machine-readable JSON: [`agents.json`](agents.json)

> **Skip the setup?** [CrewClaw](https://crewclaw.com/create-agent) generates a full deploy package (Dockerfile + docker-compose + bot + README) for any role. $29 one-time.

### Productivity

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🎯 Orion](agents/productivity/orion/) | Task coordinator and project manager | [View](agents/productivity/orion/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |
| [📊 Pulse](agents/productivity/metrics/) | Analytics dashboard agent (Mixpanel, Stripe, GA4) | [View](agents/productivity/metrics/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🧍 Standup](agents/productivity/daily-standup/) | Daily standup collector and team summarizer | [View](agents/productivity/daily-standup/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |
| [📧 Inbox](agents/productivity/inbox-zero/) | Email triage, response drafting, daily digest | [View](agents/productivity/inbox-zero/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📝 Minutes](agents/productivity/meeting-notes/) | Meeting summarizer and action item tracker | [View](agents/productivity/meeting-notes/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🍅 Focus Timer](agents/productivity/focus-timer/) | Pomodoro and deep work session manager | [View](agents/productivity/focus-timer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [✅ Habit Tracker](agents/productivity/habit-tracker/) | Daily habit tracking, streaks, accountability | [View](agents/productivity/habit-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### Development

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🔎 Lens](agents/development/code-reviewer/) | PR review, security scanning, quality assessment | [View](agents/development/code-reviewer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=code-reviewer) |
| [📖 Scribe](agents/development/docs-writer/) | README, API docs, and code documentation generator | [View](agents/development/docs-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=technical-writer) |
| [🐛 Trace](agents/development/bug-hunter/) | Error analysis, root cause investigation, debugging | [View](agents/development/bug-hunter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🧪 Probe](agents/development/api-tester/) | API endpoint testing, health checks, performance | [View](agents/development/api-tester/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [📋 Log](agents/development/changelog/) | Auto-changelog from git commits, release notes | [View](agents/development/changelog/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🔗 Dependency Scanner](agents/development/dependency-scanner/) | CVE scanning, license checks, supply chain security | [View](agents/development/dependency-scanner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🔀 PR Merger](agents/development/pr-merger/) | Auto-merge PRs when checks pass, conflict detection | [View](agents/development/pr-merger/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🗄️ Migration Helper](agents/development/migration-helper/) | Database migration assistant, schema diff, rollback plans | [View](agents/development/migration-helper/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🧪 Test Writer](agents/development/test-writer/) | Unit test generator, coverage analysis | [View](agents/development/test-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |

> **Want a Software Engineer agent running in 60 seconds?** [Deploy with CrewClaw →](https://crewclaw.com/create-agent?role=software-engineer)

### Marketing & Content

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [✍️ Echo](agents/marketing/echo/) | Content writer for blogs, social, emails | [View](agents/marketing/echo/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [📱 Buzz](agents/marketing/social-media/) | Social media manager for Twitter, LinkedIn, threads | [View](agents/marketing/social-media/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=social-media-manager) |
| [🔍 Rank](agents/marketing/seo-writer/) | SEO content writer with keyword research from GSC | [View](agents/marketing/seo-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=seo-specialist) |
| [📬 Digest](agents/marketing/newsletter/) | Weekly newsletter curator and email writer | [View](agents/marketing/newsletter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🔭 Scout](agents/marketing/competitor-watch/) | Competitor monitoring, pricing intel, market analysis | [View](agents/marketing/competitor-watch/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🔎 Reddit Scout](agents/marketing/reddit-scout/) | Subreddit monitoring, sentiment analysis, reply opportunities | [View](agents/marketing/reddit-scout/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🎵 TikTok Repurposer](agents/marketing/tiktok-repurposer/) | Convert blogs and podcasts into short-form video scripts | [View](agents/marketing/tiktok-repurposer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [📨 Cold Outreach](agents/marketing/cold-outreach/) | Lead research, personalized cold emails, outreach sequences | [View](agents/marketing/cold-outreach/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |
| [📊 A/B Test Analyzer](agents/marketing/ab-test-analyzer/) | Experiment results analysis, statistical significance | [View](agents/marketing/ab-test-analyzer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🤝 Influencer Finder](agents/marketing/influencer-finder/) | Influencer research, outreach, campaign tracking | [View](agents/marketing/influencer-finder/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=social-media-manager) |
| [👁️ Brand Monitor](agents/marketing/brand-monitor/) | Brand mention monitoring, sentiment alerts | [View](agents/marketing/brand-monitor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

> **Need a Content Writer or SEO agent?** [Deploy with CrewClaw →](https://crewclaw.com/create-agent?role=content-writer)

### Business

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [📊 Radar](agents/business/radar/) | Data analyst and insights generator | [View](agents/business/radar/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🎧 Compass](agents/business/customer-support/) | Support ticket triage, response drafting, escalation | [View](agents/business/customer-support/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=customer-support) |
| [💼 Pipeline](agents/business/sales-assistant/) | Lead scoring, outreach drafting, pipeline reports | [View](agents/business/sales-assistant/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |
| [💰 Ledger](agents/business/invoice-tracker/) | Payment monitoring, invoice tracking, MRR reports | [View](agents/business/invoice-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🔮 Sentinel](agents/business/churn-predictor/) | Churn risk scoring, retention actions, re-engagement | [View](agents/business/churn-predictor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🤝 Personal CRM](agents/business/personal-crm/) | Contact tracking, follow-up reminders, relationship health | [View](agents/business/personal-crm/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [💬 WhatsApp Business](agents/business/whatsapp-business/) | Multi-channel support, lead qualification | [View](agents/business/whatsapp-business/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=customer-support) |
| [📅 Meeting Scheduler](agents/business/meeting-scheduler/) | Smart scheduling, timezone handling, calendar optimization | [View](agents/business/meeting-scheduler/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [💲 Competitor Pricing](agents/business/competitor-pricing/) | Competitor price tracking, alerts on changes | [View](agents/business/competitor-pricing/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

### Personal

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [📅 Atlas](agents/personal/daily-planner/) | Daily schedule optimizer, morning plans, evening reviews | [View](agents/personal/daily-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📚 Scroll](agents/personal/reading-digest/) | Article summarizer, weekly reading digest | [View](agents/personal/reading-digest/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [💪 Iron](agents/personal/fitness-coach/) | Workout planner, nutrition tracker, progress reports | [View](agents/personal/fitness-coach/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🏠 Home Automation](agents/personal/home-automation/) | Smart home control via Telegram, Home Assistant | [View](agents/personal/home-automation/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [👨‍👩‍👧‍👦 Family Coordinator](agents/personal/family-coordinator/) | Shared calendar, meal planning, chore rotation | [View](agents/personal/family-coordinator/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📞 Vox](agents/personal/voice-assistant/) | Voice calling, SMS, call missions with transcription | [View](agents/personal/voice-assistant/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent) |

### DevOps

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🚨 Incident Responder](agents/devops/incident-responder/) | Monitors alerts, triages incidents, coordinates response | [View](agents/devops/incident-responder/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🚀 Deploy Guardian](agents/devops/deploy-guardian/) | Watches CI/CD pipelines, reports deployment status | [View](agents/devops/deploy-guardian/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🖥️ Infra Monitor](agents/devops/infra-monitor/) | Tracks server health, disk, CPU, memory usage | [View](agents/devops/infra-monitor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [📜 Log Analyzer](agents/devops/log-analyzer/) | Parses logs, finds patterns, alerts on anomalies | [View](agents/devops/log-analyzer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [💸 Cost Optimizer](agents/devops/cost-optimizer/) | Monitors cloud spend, suggests savings | [View](agents/devops/cost-optimizer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🔧 Self-Healing Server](agents/devops/self-healing-server/) | Auto-restart crashed containers, disk cleanup | [View](agents/devops/self-healing-server/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🍓 Raspberry Pi Agent](agents/devops/raspberry-pi/) | Lightweight edge agent optimized for Pi, low-RAM | [View](agents/devops/raspberry-pi/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |

### Finance

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🧾 Expense Tracker](agents/finance/expense-tracker/) | Categorizes expenses, tracks budgets, sends alerts | [View](agents/finance/expense-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🧮 Invoice Manager](agents/finance/invoice-manager/) | Creates, tracks, and follows up on invoices | [View](agents/finance/invoice-manager/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📈 Revenue Analyst](agents/finance/revenue-analyst/) | Analyzes revenue streams, MRR, churn, forecasts | [View](agents/finance/revenue-analyst/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🏦 Tax Preparer](agents/finance/tax-preparer/) | Organizes receipts, calculates deductions | [View](agents/finance/tax-preparer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📉 Trading Bot](agents/finance/trading-bot/) | Portfolio tracking, market sentiment, price alerts | [View](agents/finance/trading-bot/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

### Education

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🎓 Tutor](agents/education/tutor/) | Explains concepts, creates practice problems | [View](agents/education/tutor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [❓ Quiz Maker](agents/education/quiz-maker/) | Generates quizzes from content, tracks scores | [View](agents/education/quiz-maker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📖 Study Planner](agents/education/study-planner/) | Creates study schedules, sends reminders | [View](agents/education/study-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🔬 Research Assistant](agents/education/research-assistant/) | Finds papers, summarizes research, manages citations | [View](agents/education/research-assistant/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🌍 Language Tutor](agents/education/language-tutor/) | Language learning, conversation practice, grammar drills | [View](agents/education/language-tutor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### Healthcare

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🧘 Wellness Coach](agents/healthcare/wellness-coach/) | Daily check-ins, habit tracking, mental health tips | [View](agents/healthcare/wellness-coach/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🥗 Meal Planner](agents/healthcare/meal-planner/) | Creates meal plans, tracks nutrition | [View](agents/healthcare/meal-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🏋️ Workout Tracker](agents/healthcare/workout-tracker/) | Designs workout plans, tracks progress | [View](agents/healthcare/workout-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |

### Legal

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [📜 Contract Reviewer](agents/legal/contract-reviewer/) | Reviews contracts, flags risky clauses | [View](agents/legal/contract-reviewer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [✅ Compliance Checker](agents/legal/compliance-checker/) | Monitors compliance requirements, tracks deadlines | [View](agents/legal/compliance-checker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📋 Policy Writer](agents/legal/policy-writer/) | Drafts internal policies, terms of service | [View](agents/legal/policy-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### HR

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🤝 Recruiter](agents/hr/recruiter/) | Screens resumes, schedules interviews | [View](agents/hr/recruiter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🎒 Onboarding](agents/hr/onboarding/) | Guides new hires through setup | [View](agents/hr/onboarding/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📊 Performance Reviewer](agents/hr/performance-reviewer/) | Collects feedback, generates review summaries | [View](agents/hr/performance-reviewer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### Creative

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🎨 Brand Designer](agents/creative/brand-designer/) | Creates brand guidelines, color palettes | [View](agents/creative/brand-designer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🎬 Video Scripter](agents/creative/video-scripter/) | Writes video scripts, outlines, shot lists | [View](agents/creative/video-scripter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🎙️ Podcast Producer](agents/creative/podcast-producer/) | Plans episodes, writes show notes | [View](agents/creative/podcast-producer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🧑‍💻 UX Researcher](agents/creative/ux-researcher/) | User surveys, feedback analysis, reports | [View](agents/creative/ux-researcher/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [✏️ Copywriter](agents/creative/copywriter/) | Ad copy, landing pages, email sequences | [View](agents/creative/copywriter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🖼️ Thumbnail Designer](agents/creative/thumbnail-designer/) | YouTube/social thumbnail concepts and copy | [View](agents/creative/thumbnail-designer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |

### Security

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🛡️ Vuln Scanner](agents/security/vuln-scanner/) | Scans for vulnerabilities, prioritizes fixes | [View](agents/security/vuln-scanner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🔐 Access Auditor](agents/security/access-auditor/) | Reviews permissions, flags excessive access | [View](agents/security/access-auditor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [👁️ Threat Monitor](agents/security/threat-monitor/) | Monitors threat feeds, alerts on relevant threats | [View](agents/security/threat-monitor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [📓 Incident Logger](agents/security/incident-logger/) | Documents security incidents, tracks resolution | [View](agents/security/incident-logger/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🔒 Security Hardener](agents/security/security-hardener/) | Audit SOUL.md, scan skills, harden gateway config | [View](agents/security/security-hardener/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🎣 Phishing Detector](agents/security/phishing-detector/) | Email phishing analysis, URL scanning | [View](agents/security/phishing-detector/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |

### E-Commerce

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🏷️ Product Lister](agents/ecommerce/product-lister/) | Marketplace listing optimization, SEO titles | [View](agents/ecommerce/product-lister/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [⭐ Review Responder](agents/ecommerce/review-responder/) | Auto-respond to customer reviews across platforms | [View](agents/ecommerce/review-responder/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=customer-support) |
| [📦 Inventory Tracker](agents/ecommerce/inventory-tracker/) | Stock monitoring, reorder alerts, demand forecasting | [View](agents/ecommerce/inventory-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [💲 Pricing Optimizer](agents/ecommerce/pricing-optimizer/) | Dynamic pricing based on competition and demand | [View](agents/ecommerce/pricing-optimizer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🛒 Abandoned Cart](agents/ecommerce/abandoned-cart/) | Cart recovery messaging, win-back sequences | [View](agents/ecommerce/abandoned-cart/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |

> **Running a Shopify or Amazon store?** [Deploy an E-Commerce agent →](https://crewclaw.com/create-agent?role=customer-support)

### Data

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🔄 ETL Pipeline](agents/data/etl-pipeline/) | Data pipeline monitoring, failure alerts, retry logic | [View](agents/data/etl-pipeline/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🧹 Data Cleaner](agents/data/data-cleaner/) | Data quality checks, deduplication, normalization | [View](agents/data/data-cleaner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📊 Report Generator](agents/data/report-generator/) | Automated report generation from multiple sources | [View](agents/data/report-generator/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🗃️ SQL Assistant](agents/data/sql-assistant/) | SQL query helper, optimization, schema exploration | [View](agents/data/sql-assistant/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📈 Dashboard Builder](agents/data/dashboard-builder/) | Metrics dashboard creation and maintenance | [View](agents/data/dashboard-builder/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

> **Need a Data Analyst agent?** [Deploy with CrewClaw →](https://crewclaw.com/create-agent?role=data-analyst)

### SaaS

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🚀 Onboarding Flow](agents/saas/onboarding-flow/) | User onboarding optimization, activation tracking | [View](agents/saas/onboarding-flow/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |
| [💡 Feature Request](agents/saas/feature-request/) | Feature request collector, prioritizer, voter | [View](agents/saas/feature-request/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |
| [🔮 Churn Prevention](agents/saas/churn-prevention/) | Proactive churn prevention, health scoring | [View](agents/saas/churn-prevention/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📊 Usage Analytics](agents/saas/usage-analytics/) | Product usage analysis, feature adoption tracking | [View](agents/saas/usage-analytics/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📝 Release Notes](agents/saas/release-notes/) | Automated release notes from git commits and PRs | [View](agents/saas/release-notes/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=technical-writer) |

### Real Estate

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [🏡 Listing Scout](agents/real-estate/listing-scout/) | Property listing monitor, price drop alerts | [View](agents/real-estate/listing-scout/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📊 Market Analyzer](agents/real-estate/market-analyzer/) | Real estate market analysis, comp reports | [View](agents/real-estate/market-analyzer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🎯 Lead Qualifier](agents/real-estate/lead-qualifier/) | Real estate lead scoring, follow-up sequences | [View](agents/real-estate/lead-qualifier/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |

### Freelance

| Agent | Description | SOUL.md | Deploy |
|-------|-------------|---------|--------|
| [📝 Proposal Writer](agents/freelance/proposal-writer/) | Freelance proposal generator, rate calculator | [View](agents/freelance/proposal-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [⏱️ Time Tracker](agents/freelance/time-tracker/) | Project time tracking, invoicing, utilization | [View](agents/freelance/time-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🤝 Client Manager](agents/freelance/client-manager/) | Client relationship management, contract tracking | [View](agents/freelance/client-manager/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |

> **Freelancer?** [Deploy a Personal Assistant agent →](https://crewclaw.com/create-agent?role=personal-assistant)

---

## Use Cases

**132 verified real-world use cases** — what people are actually building with OpenClaw agents.

From developer workflows and DevOps automation to smart home control, crypto trading, robotics, and agents that modify their own code.

**[Browse all 132 use cases →](USE-CASES.md)**

Top categories: Personal Productivity (14) · Business Operations (11) · Developer Workflows (10) · Content Creation (10) · Ecosystem Tools (10)

---

## Quickstart

Get a working agent running in under 5 minutes with zero config:

```bash
git clone https://github.com/mergisi/awesome-openclaw-agents.git
cd awesome-openclaw-agents/quickstart
cp .env.example .env          # add your API key + Telegram token
cp ../agents/marketing/echo/SOUL.md ./SOUL.md
npm install && node bot.js    # your agent is live on Telegram
```

See the full [Quickstart Guide](quickstart/) with Docker support.

Or skip setup entirely: **[Deploy with CrewClaw →](https://crewclaw.com/create-agent)** (includes Dockerfile + docker-compose + bot + README). $29 one-time, yours forever.

---

## Why OpenClaw?

How OpenClaw compares to other AI agent frameworks:

| Feature | OpenClaw | AutoGPT | CrewAI | LangChain | MetaGPT |
|---------|----------|---------|--------|-----------|---------|
| Config-first (SOUL.md) | ✅ | ❌ | ❌ | ❌ | ❌ |
| No code required | ✅ | ❌ | ❌ | ❌ | ❌ |
| Telegram/Slack/Discord built-in | ✅ | ❌ | ❌ | ❌ | ❌ |
| Multi-agent orchestration | ✅ | ❌ | ✅ | ✅ | ✅ |
| MCP (Model Context Protocol) | ✅ | ❌ | ❌ | ❌ | ❌ |
| Self-hosted / local | ✅ | ✅ | ✅ | ✅ | ✅ |
| Heartbeat monitoring | ✅ | ❌ | ❌ | ❌ | ❌ |
| Works with Ollama (free) | ✅ | ✅ | ✅ | ✅ | ❌ |
| Production-ready templates | **100** | 0 | 5 | 0 | 3 |
| One-command deploy | ✅ | ❌ | ❌ | ❌ | ❌ |
| Agent-to-agent communication | ✅ | ❌ | ✅ | ✅ | ✅ |
| Setup time | ~5 min | ~30 min | ~20 min | ~45 min | ~30 min |

**TL;DR:** OpenClaw is config-first. Write a SOUL.md, run a command, your agent is live. No Python, no chains, no graphs.

---

## Quick Deploy with CrewClaw

Don't want to configure manually? [CrewClaw](https://crewclaw.com/create-agent) generates a complete deployment package for any agent:

```
Your CrewClaw package includes:
├── agents/your-agent/SOUL.md    # Agent configuration
├── Dockerfile                    # Container setup
├── docker-compose.yml            # One-command deploy
├── bot.js                        # Telegram bot (grammy)
├── .env.example                  # API keys template
├── package.json                  # Dependencies
└── README.md                     # Setup instructions
```

**$29 one-time. No subscription. Yours forever.**

Pick any of the 100 templates above, or create a custom agent from scratch.

[Create your agent →](https://crewclaw.com/create-agent)

---

## MCP Servers

Model Context Protocol servers to extend agent capabilities.

### Official

| Server | Description | Install |
|--------|-------------|---------|
| [@anthropic/mcp-server-fetch](https://github.com/anthropics/mcp-server-fetch) | Web fetching and browsing | `npx -y @anthropic/mcp-server-fetch` |
| [@anthropic/mcp-server-filesystem](https://github.com/anthropics/mcp-server-filesystem) | File system access | `npx -y @anthropic/mcp-server-filesystem` |

### Community

| Server | Description |
|--------|-------------|
| mcp-notion | Notion integration |
| mcp-google-calendar | Google Calendar access |
| mcp-github | GitHub operations |
| mcp-slack | Slack messaging |
| mcp-postgres | PostgreSQL queries |
| mcp-stripe | Stripe payments |
| mcp-shopify | Shopify store management |
| mcp-twitter | Twitter/X posting |
| mcp-discord | Discord bot integration |
| mcp-linear | Linear issue tracking |

---

## Integrations

Connect your agents to external services.

### Messaging

- **Telegram** - Chat with agents via Telegram (built-in to OpenClaw)
- **Slack** - Slack workspace connection (built-in to OpenClaw)
- **Discord** - Discord server bot (built-in to OpenClaw)
- **Email** - Email channel (built-in to OpenClaw)

### Automation

- **n8n** - n8n integration nodes
- **GitHub Actions** - CI/CD integration
- **Cron / pm2 / systemd** - Always-on agent scheduling

---

## Tools

Utilities and helpers for working with OpenClaw.

| Tool | Description |
|------|-------------|
| [openclaw CLI](https://crewclaw.com/blog/openclaw-cli-commands-reference) | Official CLI - complete command reference |
| [agents.json](agents.json) | Machine-readable index of all 100 agent templates |
| agent-validator | Validate SOUL.md syntax |
| mcp-tester | Test MCP server connections |

---

## Tutorials & Guides

Learn how to build and deploy agents.

### Getting Started

- [What is OpenClaw?](https://crewclaw.com/blog/what-is-openclaw-ai-agent-framework) - Complete guide to the framework
- [Create Your First Agent](https://crewclaw.com/blog/how-to-create-ai-agent-openclaw) - No code required
- [OpenClaw Setup Guide 2026](https://crewclaw.com/blog/openclaw-setup-guide-2026) - Install, configure, run
- [SOUL.md Templates](https://crewclaw.com/blog/soul-md-examples-templates) - 10 ready-to-use examples

### Multi-Agent & Orchestration

- [Multi-Agent Setup Guide](https://crewclaw.com/blog/openclaw-multi-agent-setup-guide) - Run multiple agents together
- [Agent-to-Agent Communication](https://crewclaw.com/blog/openclaw-agent-to-agent-communication) - How agents collaborate
- [Build an AI Team](https://crewclaw.com/blog/build-ai-team-workflows) - Workflows that run autonomously

### Integrations & Automation

- [Slack & Telegram Integration](https://crewclaw.com/blog/openclaw-slack-telegram-integration) - Connect to messaging channels
- [Run with Ollama](https://crewclaw.com/blog/openclaw-ollama-local-agents) - Free local AI agents
- [Automation Guide](https://crewclaw.com/blog/openclaw-automation-guide) - Build 24/7 workflows
- [CLI Commands Reference](https://crewclaw.com/blog/openclaw-cli-commands-reference) - Complete cheat sheet

### Comparisons

- [OpenClaw vs LangChain](https://crewclaw.com/blog/openclaw-vs-langchain) - Framework comparison
- [OpenClaw vs AutoGPT](https://crewclaw.com/blog/openclaw-vs-autogpt) - Key differences
- [OpenClaw vs CrewAI](https://crewclaw.com/blog/openclaw-vs-crewai) - Which is better?

---

## Community

### Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md).

#### How to Add an Agent

1. Fork this repository
2. Create folder: `agents/[category]/[agent-name]/`
3. Add `SOUL.md` and `README.md`
4. Update the main README table
5. Submit a Pull Request

Use the [Agent Request](https://github.com/mergisi/awesome-openclaw-agents/issues/new?template=agent-request.md) template to suggest new agents.

---

## Related Projects

- [🦞 CrewClaw](https://crewclaw.com) - Deploy AI agents with zero config. No Docker, no terminal.
- [OpenClaw](https://github.com/openclaw) - Official OpenClaw repository
- [Anthropic MCP](https://github.com/anthropics/mcp) - Model Context Protocol

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=mergisi/awesome-openclaw-agents&type=Date)](https://star-history.com/#mergisi/awesome-openclaw-agents&Date)

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to this work.

---

<p align="center">
  Made with 🦞 by the OpenClaw Community
  <br/>
  <a href="https://crewclaw.com/create-agent">Deploy your agent with CrewClaw →</a>
</p>
