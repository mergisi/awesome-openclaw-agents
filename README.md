# 🦞 Awesome OpenClaw Agents

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Stars](https://img.shields.io/github/stars/mergisi/awesome-openclaw-agents?style=social)](https://github.com/mergisi/awesome-openclaw-agents)
[![Agents](https://img.shields.io/badge/agents-187-blueviolet)](agents/)

> A curated collection of **187 production-ready AI agent templates** for the OpenClaw ecosystem. Every template is a copy-paste ready `SOUL.md` file.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:4F46E5,100:7C3AED&height=180&section=header&text=%F0%9F%A6%9E%20187%20OpenClaw%20Agent%20Templates&fontSize=36&fontColor=ffffff&fontAlignY=35" width="100%"/>
</p>

<div align="center">

### Skip the setup. Deploy in 60 seconds.

**[Browse all 187 templates →](https://crewclaw.com/agents?utm_source=github&utm_medium=readme&utm_campaign=browse)** · **[Deploy in 60 seconds →](https://crewclaw.com/create-agent?utm_source=github&utm_medium=readme&utm_campaign=deploy)**

Pick a template. Customize the config. Get a full deploy package. No terminal required.

</div>

<div align="center">

📬 **Get weekly agent templates & tips** — new templates, deployment guides, and community highlights every Tuesday.

**[Subscribe to the newsletter →](https://docs.google.com/forms/d/e/1FAIpQLSeIqBjV1LXnR2qQqGSGa-48rAveAmpSKVqlzLqDK2d4D4aVWg/viewform)**

</div>

---

## Contents

- [Agent Templates](#agent-templates) (187 agents across 24 categories)
  - [Productivity](#productivity) · [Development](#development) · [Marketing](#marketing--content) · [Business](#business) · [Personal](#personal)
  - [DevOps](#devops) · [Finance](#finance) · [Education](#education) · [Healthcare](#healthcare) · [Legal](#legal) · [HR](#hr) · [Creative](#creative) · [Security](#security)
  - [E-Commerce](#e-commerce) · [Data](#data) · [SaaS](#saas) · [Real Estate](#real-estate) · [Freelance](#freelance) · [Moltbook](#-moltbook-new)
  - [Supply Chain](#supply-chain) · [Compliance](#compliance) · [Voice](#voice) · [Customer Success](#customer-success) · [Automation](#automation)
- [Use Cases](#use-cases) (132 real-world examples)
- [Quickstart](#quickstart)
- [Why OpenClaw?](#why-openclaw) (vs Frameworks, Lightweight, Enterprise)
- [Quick Deploy with CrewClaw](#quick-deploy-with-crewclaw)
- [MCP Servers](#mcp-servers)
- [Integrations](#integrations)
- [Tools](#tools)
- [Security](#security)
- [Tutorials & Guides](#tutorials--guides)
- [Submit Your Agent](#submit-your-agent)
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

> All 100 agents are also available as machine-readable JSON: [`agents.json`](agents.json)

> **Skip the setup?** [CrewClaw](https://crewclaw.com/create-agent?utm_source=github&utm_medium=readme&utm_campaign=skip_setup) generates a full deploy package (Dockerfile + docker-compose + bot + README) for any role.

### 📋 Productivity

Getting more done with less effort.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🎯 Orion](agents/productivity/orion/) | Task coordination, project management | When you need daily priorities, deadline tracking, and team alignment | [View](agents/productivity/orion/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |
| [📊 Pulse](agents/productivity/metrics/) | Analytics dashboards (Mixpanel, Stripe, GA4) | When you want automated daily/weekly metrics reports | [View](agents/productivity/metrics/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🧍 Standup](agents/productivity/daily-standup/) | Daily standup collection, team summaries | When your team needs async standups without meetings | [View](agents/productivity/daily-standup/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |
| [📧 Inbox](agents/productivity/inbox-zero/) | Email triage, response drafting, daily digest | When your inbox is overwhelming and needs prioritization | [View](agents/productivity/inbox-zero/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📝 Minutes](agents/productivity/meeting-notes/) | Meeting summaries, action item tracking | When you need automated meeting notes and follow-ups | [View](agents/productivity/meeting-notes/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🍅 Focus Timer](agents/productivity/focus-timer/) | Pomodoro, deep work session management | When you need structured focus time with accountability | [View](agents/productivity/focus-timer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [✅ Habit Tracker](agents/productivity/habit-tracker/) | Daily habits, streaks, accountability | When you want daily check-ins and streak tracking | [View](agents/productivity/habit-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### 💻 Development

Building the future, one commit at a time.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🔎 Lens](agents/development/code-reviewer/) | PR review, security scanning, code quality | When you want automated code review before merging | [View](agents/development/code-reviewer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=code-reviewer) |
| [📖 Scribe](agents/development/docs-writer/) | README, API docs, code documentation | When documentation is lagging behind your codebase | [View](agents/development/docs-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=technical-writer) |
| [🐛 Trace](agents/development/bug-hunter/) | Error analysis, root cause investigation | When you need faster debugging and incident response | [View](agents/development/bug-hunter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🧪 Probe](agents/development/api-tester/) | API testing, health checks, performance | When you need continuous API monitoring and alerting | [View](agents/development/api-tester/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [📋 Log](agents/development/changelog/) | Auto-changelog, release notes from git | When you want release notes generated from commits | [View](agents/development/changelog/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🔗 Dependency Scanner](agents/development/dependency-scanner/) | CVE scanning, license checks, supply chain | When you need automated dependency security audits | [View](agents/development/dependency-scanner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🔀 PR Merger](agents/development/pr-merger/) | Auto-merge, conflict detection | When you want PRs merged automatically after checks pass | [View](agents/development/pr-merger/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🗄️ Migration Helper](agents/development/migration-helper/) | Database migrations, schema diffs, rollbacks | When you're planning database changes and need safety nets | [View](agents/development/migration-helper/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🧪 Test Writer](agents/development/test-writer/) | Unit test generation, coverage analysis | When test coverage is low and you need to catch up | [View](agents/development/test-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🗂️ Schema Designer](agents/development/schema-designer/) | DB schema from natural language, ERD output | When you need database schemas designed from requirements | [View](agents/development/schema-designer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |

> **Want a Software Engineer agent running in 60 seconds?** [Deploy with CrewClaw →](https://crewclaw.com/create-agent?role=software-engineer)

### 📣 Marketing & Content

Growing your audience on autopilot.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [✍️ Echo](agents/marketing/echo/) | Blog posts, social copy, emails | When you need consistent content output across channels | [View](agents/marketing/echo/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [📱 Buzz](agents/marketing/social-media/) | Twitter, LinkedIn, threads management | When you want scheduled social posts with engagement tracking | [View](agents/marketing/social-media/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=social-media-manager) |
| [🔍 Rank](agents/marketing/seo-writer/) | SEO content, keyword research from GSC | When you need SEO-optimized content based on real search data | [View](agents/marketing/seo-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=seo-specialist) |
| [📬 Digest](agents/marketing/newsletter/) | Newsletter curation, email writing | When you want a weekly newsletter without the manual work | [View](agents/marketing/newsletter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🔭 Scout](agents/marketing/competitor-watch/) | Competitor monitoring, pricing intel | When you need to track what competitors are doing daily | [View](agents/marketing/competitor-watch/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🔎 Reddit Scout](agents/marketing/reddit-scout/) | Subreddit monitoring, reply opportunities | When you want to find and engage with relevant Reddit threads | [View](agents/marketing/reddit-scout/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🎵 TikTok Repurposer](agents/marketing/tiktok-repurposer/) | Blog-to-video script conversion | When you want to repurpose long-form content into short videos | [View](agents/marketing/tiktok-repurposer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [📨 Cold Outreach](agents/marketing/cold-outreach/) | Lead research, personalized cold emails | When you need scalable outreach without sounding robotic | [View](agents/marketing/cold-outreach/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |
| [📊 A/B Test Analyzer](agents/marketing/ab-test-analyzer/) | Experiment analysis, statistical significance | When you're running experiments and need clear results | [View](agents/marketing/ab-test-analyzer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🤝 Influencer Finder](agents/marketing/influencer-finder/) | Influencer research, outreach, campaigns | When you want to find and reach out to relevant influencers | [View](agents/marketing/influencer-finder/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=social-media-manager) |
| [👁️ Brand Monitor](agents/marketing/brand-monitor/) | Brand mention monitoring, sentiment alerts | When you need to know every time your brand is mentioned | [View](agents/marketing/brand-monitor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📧 Email Sequence](agents/marketing/email-sequence/) | Multi-step drip campaigns, subject lines | When you need automated email nurture sequences | [View](agents/marketing/email-sequence/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [♻️ Content Repurposer](agents/marketing/content-repurposer/) | Blog to tweets, posts, shorts scripts | When you want one piece of content on every platform | [View](agents/marketing/content-repurposer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [📖 Book Writer](agents/marketing/book-writer/) | Full book production pipeline, 6 phases | When you want to write a book from outline to manuscript | [View](agents/marketing/book-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [📰 News Curator](agents/marketing/news-curator/) | Source scanning, AI curation, publishing | When you need automated news digests from 50+ sources | [View](agents/marketing/news-curator/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🎥 UGC Video](agents/marketing/ugc-video/) | AI influencer-style video content | When you need UGC-style video scripts and production plans | [View](agents/marketing/ugc-video/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [📱 Multi-Account Social](agents/marketing/multi-account-social/) | 10+ account management, scheduling | When you manage multiple brand accounts across platforms | [View](agents/marketing/multi-account-social/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=social-media-manager) |

> **Need a Content Writer or SEO agent?** [Deploy with CrewClaw →](https://crewclaw.com/create-agent?role=content-writer)

### 💼 Business

Running operations without the overhead.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [📊 Radar](agents/business/radar/) | Data analysis, insights generation | When you need daily business metrics and trend analysis | [View](agents/business/radar/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🎧 Compass](agents/business/customer-support/) | Ticket triage, response drafting, escalation | When support volume is growing faster than your team | [View](agents/business/customer-support/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=customer-support) |
| [💼 Pipeline](agents/business/sales-assistant/) | Lead scoring, outreach, pipeline reports | When you need automated lead qualification and follow-ups | [View](agents/business/sales-assistant/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |
| [💰 Ledger](agents/business/invoice-tracker/) | Payment monitoring, invoice tracking, MRR | When you want real-time revenue and payment tracking | [View](agents/business/invoice-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🔮 Sentinel](agents/business/churn-predictor/) | Churn risk scoring, retention actions | When you want to catch at-risk customers before they leave | [View](agents/business/churn-predictor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🤝 Personal CRM](agents/business/personal-crm/) | Contact tracking, follow-up reminders | When you're losing track of relationships and follow-ups | [View](agents/business/personal-crm/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [💬 WhatsApp Business](agents/business/whatsapp-business/) | Multi-channel support, lead qualification | When customers reach you on WhatsApp and need fast replies | [View](agents/business/whatsapp-business/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=customer-support) |
| [📅 Meeting Scheduler](agents/business/meeting-scheduler/) | Smart scheduling, timezone handling | When scheduling meetings across timezones is eating your time | [View](agents/business/meeting-scheduler/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [💲 Competitor Pricing](agents/business/competitor-pricing/) | Price tracking, change alerts | When you need to monitor competitor pricing changes daily | [View](agents/business/competitor-pricing/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📞 SDR Outbound](agents/business/sdr-outbound/) | Lead research, personalized outreach | When you need automated outbound sales development | [View](agents/business/sdr-outbound/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |
| [🎯 Deal Forecaster](agents/business/deal-forecaster/) | Pipeline signals, close probability | When you want data-driven deal close predictions | [View](agents/business/deal-forecaster/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |
| [🗣️ Objection Handler](agents/business/objection-handler/) | Real-time rebuttals, talk tracks | When sales reps need instant objection responses | [View](agents/business/objection-handler/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |

### 🧘 Personal

Your AI assistant for daily life.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [📅 Atlas](agents/personal/daily-planner/) | Schedule optimization, morning/evening reviews | When you want a structured daily routine with accountability | [View](agents/personal/daily-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📚 Scroll](agents/personal/reading-digest/) | Article summaries, weekly reading digest | When you have a reading backlog and need curated summaries | [View](agents/personal/reading-digest/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [💪 Iron](agents/personal/fitness-coach/) | Workouts, nutrition, progress reports | When you want a personal trainer that tracks everything | [View](agents/personal/fitness-coach/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🏠 Home Automation](agents/personal/home-automation/) | Smart home control via Telegram | When you want to control your smart home through chat | [View](agents/personal/home-automation/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [👨‍👩‍👧‍👦 Family Coordinator](agents/personal/family-coordinator/) | Shared calendar, meals, chore rotation | When your family needs a shared organizer and planner | [View](agents/personal/family-coordinator/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [✈️ Travel Planner](agents/personal/travel-planner/) | Itineraries, flights, hotels, budgets | When you need trip planning with smart recommendations | [View](agents/personal/travel-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📓 Journal Prompter](agents/personal/journal-prompter/) | Daily prompts, mood tracking, goals | When you want guided daily journaling for reflection | [View](agents/personal/journal-prompter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### 🚀 DevOps

Keeping infrastructure alive, 24/7.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🚨 Incident Responder](agents/devops/incident-responder/) | Alert triage, incident coordination | When you need automated incident response and escalation | [View](agents/devops/incident-responder/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🚀 Deploy Guardian](agents/devops/deploy-guardian/) | CI/CD monitoring, deployment status | When you want deployment notifications and rollback alerts | [View](agents/devops/deploy-guardian/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🖥️ Infra Monitor](agents/devops/infra-monitor/) | Server health, disk, CPU, memory | When you need proactive server monitoring with alerts | [View](agents/devops/infra-monitor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [📜 Log Analyzer](agents/devops/log-analyzer/) | Log parsing, pattern detection, anomalies | When you're drowning in logs and need automated analysis | [View](agents/devops/log-analyzer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [💸 Cost Optimizer](agents/devops/cost-optimizer/) | Cloud spend monitoring, savings suggestions | When your cloud bill is growing and you need visibility | [View](agents/devops/cost-optimizer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🔧 Self-Healing Server](agents/devops/self-healing-server/) | Auto-restart containers, disk cleanup | When you want servers that fix themselves at 3am | [View](agents/devops/self-healing-server/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🍓 Raspberry Pi Agent](agents/devops/raspberry-pi/) | Lightweight edge agent, low-RAM optimized | When you're deploying agents on Raspberry Pi or edge devices | [View](agents/devops/raspberry-pi/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [📋 Runbook Writer](agents/devops/runbook-writer/) | Operational runbooks from system architecture | When you need documented procedures for incident response | [View](agents/devops/runbook-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [📊 SLA Monitor](agents/devops/sla-monitor/) | SLA compliance tracking, degradation alerts | When you need to track uptime commitments across services | [View](agents/devops/sla-monitor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [📐 Capacity Planner](agents/devops/capacity-planner/) | Infrastructure capacity forecasting | When you need to plan infrastructure scaling ahead of demand | [View](agents/devops/capacity-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |

### 💰 Finance

Making sense of the numbers.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🧾 Expense Tracker](agents/finance/expense-tracker/) | Expense categorization, budget alerts | When you need automated expense tracking and budget monitoring | [View](agents/finance/expense-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🧮 Invoice Manager](agents/finance/invoice-manager/) | Invoice creation, tracking, follow-ups | When invoices are getting lost and payments are late | [View](agents/finance/invoice-manager/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📈 Revenue Analyst](agents/finance/revenue-analyst/) | MRR analysis, churn, revenue forecasts | When you want automated revenue reports and forecasting | [View](agents/finance/revenue-analyst/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🏦 Tax Preparer](agents/finance/tax-preparer/) | Receipt organization, deduction calculation | When tax season is approaching and you need to get organized | [View](agents/finance/tax-preparer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📉 Trading Bot](agents/finance/trading-bot/) | Portfolio tracking, sentiment, price alerts | When you want automated market monitoring and price alerts | [View](agents/finance/trading-bot/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🔍 Fraud Detector](agents/finance/fraud-detector/) | Transaction anomaly detection, fraud alerts | When you need real-time fraud monitoring on transactions | [View](agents/finance/fraud-detector/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📊 Financial Forecaster](agents/finance/financial-forecaster/) | Revenue/expense forecasts from historical data | When you need data-driven financial projections | [View](agents/finance/financial-forecaster/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [⚖️ Portfolio Rebalancer](agents/finance/portfolio-rebalancer/) | Allocation drift analysis, rebalancing trades | When your investment portfolio needs periodic rebalancing | [View](agents/finance/portfolio-rebalancer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [💳 Accounts Payable](agents/finance/accounts-payable/) | Invoice matching, approval routing, payments | When AP workflow needs automation and faster processing | [View](agents/finance/accounts-payable/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📋 Copy Trader](agents/finance/copy-trader/) | Copy trades from top performers, risk controls | When you want automated trade replication on prediction markets | [View](agents/finance/copy-trader/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

### 🎓 Education

Learning smarter, not harder.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🎓 Tutor](agents/education/tutor/) | Concept explanation, practice problems | When you need a patient tutor available 24/7 | [View](agents/education/tutor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [❓ Quiz Maker](agents/education/quiz-maker/) | Quiz generation, score tracking | When you want automated quizzes from your study material | [View](agents/education/quiz-maker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📖 Study Planner](agents/education/study-planner/) | Study schedules, reminders | When you need a structured study plan with daily reminders | [View](agents/education/study-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🔬 Research Assistant](agents/education/research-assistant/) | Paper search, summaries, citations | When you're doing research and need help finding papers | [View](agents/education/research-assistant/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🌍 Language Tutor](agents/education/language-tutor/) | Language learning, conversation practice | When you want daily language practice on your phone | [View](agents/education/language-tutor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📐 Curriculum Designer](agents/education/curriculum-designer/) | Course outlines, learning objectives | When you need structured course design and assessment rubrics | [View](agents/education/curriculum-designer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📝 Essay Grader](agents/education/essay-grader/) | Essay feedback, rubric-based grading | When you need consistent essay evaluation at scale | [View](agents/education/essay-grader/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🃏 Flashcard Generator](agents/education/flashcard-generator/) | Spaced-repetition cards from notes | When you want automated flashcards for efficient studying | [View](agents/education/flashcard-generator/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### 🏥 Healthcare

Taking care of what matters most.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🧘 Wellness Coach](agents/healthcare/wellness-coach/) | Daily check-ins, mental health, habits | When you want daily wellness reminders and mood tracking | [View](agents/healthcare/wellness-coach/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🥗 Meal Planner](agents/healthcare/meal-planner/) | Meal plans, nutrition tracking | When you need weekly meal plans based on your goals | [View](agents/healthcare/meal-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🏋️ Workout Tracker](agents/healthcare/workout-tracker/) | Workout plans, progress tracking | When you want a workout plan that adapts to your progress | [View](agents/healthcare/workout-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🩺 Symptom Triage](agents/healthcare/symptom-triage/) | Structured symptom assessment, urgency | When patients need initial symptom evaluation and guidance | [View](agents/healthcare/symptom-triage/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [📋 Clinical Notes](agents/healthcare/clinical-notes/) | SOAP format clinical documentation | When clinical encounters need structured note transcription | [View](agents/healthcare/clinical-notes/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [💊 Medication Checker](agents/healthcare/medication-checker/) | Drug interactions, dosage alerts | When you need to verify medication safety and interactions | [View](agents/healthcare/medication-checker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [📝 Patient Intake](agents/healthcare/patient-intake/) | Intake forms, insurance verification | When patient registration needs automation and speed | [View](agents/healthcare/patient-intake/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |

### ⚖️ Legal

Navigating the fine print.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [📜 Contract Reviewer](agents/legal/contract-reviewer/) | Contract review, risky clause detection | When you're reviewing contracts and need a second pair of eyes | [View](agents/legal/contract-reviewer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [✅ Compliance Checker](agents/legal/compliance-checker/) | Compliance monitoring, deadline tracking | When you need to stay on top of regulatory requirements | [View](agents/legal/compliance-checker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📋 Policy Writer](agents/legal/policy-writer/) | Internal policies, terms of service | When you need to draft or update company policies | [View](agents/legal/policy-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🔬 Patent Analyzer](agents/legal/patent-analyzer/) | Patent claims, prior art, infringement risk | When you need patent landscape analysis and risk assessment | [View](agents/legal/patent-analyzer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📄 Legal Brief Writer](agents/legal/legal-brief-writer/) | Briefs, motions, memoranda drafting | When you need legal documents drafted from case facts | [View](agents/legal/legal-brief-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🔒 NDA Generator](agents/legal/nda-generator/) | Customized NDAs, confidentiality agreements | When you need quick, customized NDA generation | [View](agents/legal/nda-generator/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### 👥 HR

Building teams that work.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🤝 Recruiter](agents/hr/recruiter/) | Resume screening, interview scheduling | When you're hiring and need faster candidate screening | [View](agents/hr/recruiter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🎒 Onboarding](agents/hr/onboarding/) | New hire setup, orientation guides | When new hires need a guided onboarding experience | [View](agents/hr/onboarding/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📊 Performance Reviewer](agents/hr/performance-reviewer/) | Feedback collection, review summaries | When it's review season and you need structured feedback | [View](agents/hr/performance-reviewer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📄 Resume Screener](agents/hr/resume-screener/) | Resume scoring, candidate ranking | When you're screening high volumes of applicants | [View](agents/hr/resume-screener/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🚪 Exit Interview](agents/hr/exit-interview/) | Structured exit interviews, retention insights | When you need to understand why employees are leaving | [View](agents/hr/exit-interview/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🎁 Benefits Advisor](agents/hr/benefits-advisor/) | Benefits Q&A, policy guidance | When employees have questions about benefits and policies | [View](agents/hr/benefits-advisor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [💰 Compensation Benchmarker](agents/hr/compensation-benchmarker/) | Salary data, market rate analysis | When you need data-driven compensation recommendations | [View](agents/hr/compensation-benchmarker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### 🎨 Creative

Making it beautiful and engaging.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🎨 Brand Designer](agents/creative/brand-designer/) | Brand guidelines, color palettes | When you're building or refreshing your brand identity | [View](agents/creative/brand-designer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🎬 Video Scripter](agents/creative/video-scripter/) | Video scripts, outlines, shot lists | When you need video content but hate writing scripts | [View](agents/creative/video-scripter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🎙️ Podcast Producer](agents/creative/podcast-producer/) | Episode planning, show notes | When you run a podcast and need help with planning | [View](agents/creative/podcast-producer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🧑‍💻 UX Researcher](agents/creative/ux-researcher/) | User surveys, feedback analysis | When you need user insights without hiring a researcher | [View](agents/creative/ux-researcher/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [✏️ Copywriter](agents/creative/copywriter/) | Ad copy, landing pages, email sequences | When you need conversion-focused copy fast | [View](agents/creative/copywriter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🖼️ Thumbnail Designer](agents/creative/thumbnail-designer/) | YouTube/social thumbnail concepts | When you need scroll-stopping thumbnail ideas | [View](agents/creative/thumbnail-designer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [📢 Ad Copywriter](agents/creative/ad-copywriter/) | Google, Meta, LinkedIn ad variants | When you need A/B test ad copy across platforms | [View](agents/creative/ad-copywriter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🎬 Storyboard Writer](agents/creative/storyboard-writer/) | Visual storyboards, shot lists | When you need pre-production planning for video content | [View](agents/creative/storyboard-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |

### 🔒 Security

Protecting what you've built.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🛡️ Vuln Scanner](agents/security/vuln-scanner/) | Vulnerability scanning, fix prioritization | When you need continuous security scanning of your stack | [View](agents/security/vuln-scanner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🔐 Access Auditor](agents/security/access-auditor/) | Permission review, excessive access flags | When you need to audit who has access to what | [View](agents/security/access-auditor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [👁️ Threat Monitor](agents/security/threat-monitor/) | Threat feed monitoring, relevant alerts | When you want early warning on threats targeting your stack | [View](agents/security/threat-monitor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [📓 Incident Logger](agents/security/incident-logger/) | Security incident documentation | When you need structured incident tracking and post-mortems | [View](agents/security/incident-logger/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🔒 Security Hardener](agents/security/security-hardener/) | SOUL.md audit, gateway hardening | When you want to harden your agent and gateway configs | [View](agents/security/security-hardener/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [🎣 Phishing Detector](agents/security/phishing-detector/) | Email phishing analysis, URL scanning | When your team needs automated phishing detection | [View](agents/security/phishing-detector/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |

### 🛒 E-Commerce

Selling more, managing less.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🏷️ Product Lister](agents/ecommerce/product-lister/) | Listing optimization, SEO titles | When you need optimized product listings across marketplaces | [View](agents/ecommerce/product-lister/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [⭐ Review Responder](agents/ecommerce/review-responder/) | Auto-respond to customer reviews | When customer reviews need fast, consistent responses | [View](agents/ecommerce/review-responder/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=customer-support) |
| [📦 Inventory Tracker](agents/ecommerce/inventory-tracker/) | Stock monitoring, reorder alerts | When you need to prevent stockouts and overstock | [View](agents/ecommerce/inventory-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [💲 Pricing Optimizer](agents/ecommerce/pricing-optimizer/) | Dynamic pricing, competition tracking | When you want pricing that adjusts to market conditions | [View](agents/ecommerce/pricing-optimizer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🛒 Abandoned Cart](agents/ecommerce/abandoned-cart/) | Cart recovery, win-back sequences | When you're losing sales to abandoned carts | [View](agents/ecommerce/abandoned-cart/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |
| [🔍 Dropshipping Researcher](agents/ecommerce/dropshipping-researcher/) | 24/7 product research, supplier analysis | When you need continuous product discovery for dropshipping | [View](agents/ecommerce/dropshipping-researcher/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

> **Running a Shopify or Amazon store?** [Deploy an E-Commerce agent →](https://crewclaw.com/create-agent?role=customer-support)

### 📊 Data

Turning raw data into decisions.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🔄 ETL Pipeline](agents/data/etl-pipeline/) | Pipeline monitoring, failure alerts, retries | When your data pipelines need automated monitoring | [View](agents/data/etl-pipeline/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🧹 Data Cleaner](agents/data/data-cleaner/) | Quality checks, deduplication, normalization | When your data is messy and needs automated cleanup | [View](agents/data/data-cleaner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📊 Report Generator](agents/data/report-generator/) | Automated reports from multiple sources | When stakeholders need regular reports without manual work | [View](agents/data/report-generator/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🗃️ SQL Assistant](agents/data/sql-assistant/) | SQL help, query optimization, schema exploration | When you need a SQL co-pilot for complex queries | [View](agents/data/sql-assistant/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📈 Dashboard Builder](agents/data/dashboard-builder/) | Metrics dashboards, maintenance | When you need automated dashboard creation and updates | [View](agents/data/dashboard-builder/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🚨 Anomaly Detector](agents/data/anomaly-detector/) | Metrics anomaly detection, statistical alerts | When you need automated alerting on unusual data patterns | [View](agents/data/anomaly-detector/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📋 Survey Analyzer](agents/data/survey-analyzer/) | Sentiment, themes, NPS breakdown | When you have survey data that needs structured analysis | [View](agents/data/survey-analyzer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

> **Need a Data Analyst agent?** [Deploy with CrewClaw →](https://crewclaw.com/create-agent?role=data-analyst)

### ☁️ SaaS

Growing your product, retaining your users.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🚀 Onboarding Flow](agents/saas/onboarding-flow/) | User onboarding, activation tracking | When new users aren't reaching their aha moment | [View](agents/saas/onboarding-flow/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |
| [💡 Feature Request](agents/saas/feature-request/) | Request collection, prioritization, voting | When feature requests are scattered across channels | [View](agents/saas/feature-request/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |
| [🔮 Churn Prevention](agents/saas/churn-prevention/) | Proactive churn prevention, health scoring | When users are churning and you don't know why | [View](agents/saas/churn-prevention/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📊 Usage Analytics](agents/saas/usage-analytics/) | Product usage, feature adoption tracking | When you need to understand how users use your product | [View](agents/saas/usage-analytics/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📝 Release Notes](agents/saas/release-notes/) | Auto release notes from git and PRs | When writing release notes is a chore nobody wants to do | [View](agents/saas/release-notes/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=technical-writer) |

### 🏡 Real Estate

Finding deals, closing faster.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🏡 Listing Scout](agents/real-estate/listing-scout/) | Property monitoring, price drop alerts | When you want instant alerts on new listings and price drops | [View](agents/real-estate/listing-scout/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📊 Market Analyzer](agents/real-estate/market-analyzer/) | Market analysis, comparable reports | When you need automated market comps and trend analysis | [View](agents/real-estate/market-analyzer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🎯 Lead Qualifier](agents/real-estate/lead-qualifier/) | Lead scoring, follow-up sequences | When leads are coming in faster than you can qualify them | [View](agents/real-estate/lead-qualifier/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=sales-representative) |
| [🎬 Property Video](agents/real-estate/property-video/) | Listing videos, virtual tours, staging | When you need property video content at scale | [View](agents/real-estate/property-video/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [🏢 Commercial RE](agents/real-estate/commercial-re/) | CRE analysis, cap rates, deal tracking | When you need commercial property investment analysis | [View](agents/real-estate/commercial-re/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

### 🧑‍💻 Freelance

Work smarter, bill more.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [📝 Proposal Writer](agents/freelance/proposal-writer/) | Proposal generation, rate calculation | When you're spending too much time writing proposals | [View](agents/freelance/proposal-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=content-writer) |
| [⏱️ Time Tracker](agents/freelance/time-tracker/) | Time tracking, invoicing, utilization | When you're losing billable hours to poor time tracking | [View](agents/freelance/time-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🤝 Client Manager](agents/freelance/client-manager/) | Client CRM, contract tracking | When you're juggling multiple clients and deadlines | [View](agents/freelance/client-manager/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=project-manager) |

> **Freelancer?** [Deploy a Personal Assistant agent →](https://crewclaw.com/create-agent?role=personal-assistant)

### 🤖 Moltbook `NEW`

AI agent social networking — your agent's presence on the agent-to-agent social layer.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🤖 Community Manager](agents/moltbook/community-manager/) | Post updates, engage, build karma | When you want your agent to maintain a social presence on Moltbook | [View](agents/moltbook/community-manager/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?integrations=moltbook) |
| [🔭 Scout](agents/moltbook/scout/) | Feed scanning, keyword monitoring, digests | When you want to monitor Moltbook for relevant discussions and opportunities | [View](agents/moltbook/scout/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?integrations=moltbook) |
| [📈 Growth Agent](agents/moltbook/growth-agent/) | Follower growth, submolt management, strategy | When you want to grow your agent's influence and follower base on Moltbook | [View](agents/moltbook/growth-agent/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?integrations=moltbook) |

> **NEW: Moltbook integration!** Your agent can now post, engage, and grow on the AI agent social network. [Deploy with Moltbook →](https://crewclaw.com/create-agent?integrations=moltbook)

### 📦 Supply Chain `NEW`

Optimizing logistics and supplier operations.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🚚 Route Optimizer](agents/supply-chain/route-optimizer/) | Delivery routes, traffic, capacity | When you need optimized delivery planning | [View](agents/supply-chain/route-optimizer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📈 Inventory Forecaster](agents/supply-chain/inventory-forecaster/) | Demand prediction, reorder points | When you need to prevent stockouts with smart forecasting | [View](agents/supply-chain/inventory-forecaster/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [⭐ Vendor Evaluator](agents/supply-chain/vendor-evaluator/) | Supplier scoring, quality tracking | When you need data-driven supplier selection and ranking | [View](agents/supply-chain/vendor-evaluator/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

### ✅ Compliance `NEW`

Staying ahead of regulations.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🔒 GDPR Auditor](agents/compliance/gdpr-auditor/) | GDPR gap analysis, remediation plans | When you need to audit systems for data privacy compliance | [View](agents/compliance/gdpr-auditor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📋 SOC2 Preparer](agents/compliance/soc2-preparer/) | Evidence collection, audit readiness | When you're preparing for SOC 2 certification | [View](agents/compliance/soc2-preparer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🤖 AI Policy Writer](agents/compliance/ai-policy-writer/) | AI governance, EU AI Act alignment | When you need organizational AI usage policies | [View](agents/compliance/ai-policy-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [⚠️ Risk Assessor](agents/compliance/risk-assessor/) | Risk evaluation, mitigation planning | When you need structured business risk assessment | [View](agents/compliance/risk-assessor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### 🎙️ Voice `NEW`

AI-powered voice and phone agents.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [📞 Phone Receptionist](agents/voice/phone-receptionist/) | Call handling, routing, appointments | When you need 24/7 phone coverage without staff | [View](agents/voice/phone-receptionist/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=customer-support) |
| [📝 Voicemail Transcriber](agents/voice/voicemail-transcriber/) | Transcription, action item extraction | When voicemails need fast processing and routing | [View](agents/voice/voicemail-transcriber/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🎤 Interview Bot](agents/voice/interview-bot/) | Screening interviews, scoring rubrics | When you need structured candidate screening at scale | [View](agents/voice/interview-bot/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### 🤝 Customer Success `NEW`

Keeping customers happy and growing.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [📊 NPS Followup](agents/customer-success/nps-followup/) | Detractor recovery, personalized outreach | When NPS detractors need immediate attention | [View](agents/customer-success/nps-followup/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=customer-support) |
| [🎯 Onboarding Guide](agents/customer-success/onboarding-guide/) | Product setup, contextual tips | When new users need guided product onboarding | [View](agents/customer-success/onboarding-guide/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=customer-support) |

### 🔄 Automation `NEW`

Set it and forget it. Agents that work while you sleep.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🤝 Negotiation Agent](agents/automation/negotiation-agent/) | Bill negotiation, deal closing | When you want AI to negotiate your bills and contracts | [View](agents/automation/negotiation-agent/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📄 Job Applicant](agents/automation/job-applicant/) | Mass applications, resume customization | When you want to apply to 500+ jobs while you sleep | [View](agents/automation/job-applicant/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [☀️ Morning Briefing](agents/automation/morning-briefing/) | Email, calendar, news daily rollup | When you want a personalized daily briefing ready at 7AM | [View](agents/automation/morning-briefing/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [✈️ Flight Scraper](agents/automation/flight-scraper/) | Flight deals, price drop alerts | When you want the cheapest flights found automatically | [View](agents/automation/flight-scraper/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🌙 Overnight Coder](agents/automation/overnight-coder/) | Autonomous coding, PRs by morning | When you want code written while you sleep | [View](agents/automation/overnight-coder/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=software-engineer) |
| [💬 Discord Business](agents/automation/discord-business/) | Full business ops via Discord | When you run your business through Discord | [View](agents/automation/discord-business/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

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

Or skip setup entirely: **[Deploy with CrewClaw →](https://crewclaw.com/create-agent?utm_source=github&utm_medium=readme&utm_campaign=quickstart)** — get a full deploy package (Dockerfile + docker-compose + bot + README) for any role.

---

## Why OpenClaw?

How OpenClaw compares to other AI agent frameworks:

### vs AI Agent Frameworks

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
| Production-ready templates | **187** | 0 | 5 | 0 | 3 |
| One-command deploy | ✅ | ❌ | ❌ | ❌ | ❌ |
| Agent-to-agent communication | ✅ | ❌ | ✅ | ✅ | ✅ |
| Setup time | ~5 min | ~30 min | ~20 min | ~45 min | ~30 min |

### vs Lightweight Alternatives

| Feature | OpenClaw | ZeroClaw | PicoClaw | NanoClaw | memU |
|---------|----------|----------|----------|----------|------|
| Language | Node.js | Rust | Go | Python | Python |
| Binary size | ~150MB | ~5MB | ~8MB | ~4K LOC | ~50MB |
| Min RAM | 512MB | 32MB | 64MB | 128MB | 256MB |
| Multi-agent | ✅ AGENTS.md | ❌ | ❌ | ❌ | ❌ |
| Skills/plugins | ✅ 13K+ | ❌ | ❌ | ❌ | ❌ |
| Messaging channels | ✅ 25+ | 3 | 2 | 1 | 5 |
| Long-term memory | Basic | ❌ | ❌ | ❌ | ✅ Knowledge graph |
| MCP support | ✅ | ❌ | ❌ | ❌ | ❌ |
| Production templates | **187** | 0 | 0 | 0 | 0 |
| Best for | Full agent teams | Edge/IoT | Single-purpose bots | Minimal setups | Personal assistants |

### vs Hosted/Enterprise Solutions

| Feature | OpenClaw | Claude Code Channels | NemoClaw (NVIDIA) | OpenFang |
|---------|----------|---------------------|-------------------|----------|
| Open source | ✅ MIT | ❌ Proprietary | ✅ Apache 2.0 | ✅ MIT |
| Self-hosted | ✅ | ❌ Cloud only | ✅ | ✅ |
| Setup | Config file | API key | Docker + config | Rust binary |
| Multi-agent | ✅ | ❌ | ✅ via OpenClaw | ✅ 7 "Hands" |
| Security model | User-managed | Anthropic-managed | Kernel sandbox | Process isolation |
| Messaging | ✅ 25+ channels | Telegram, Discord | Via OpenClaw | 3 channels |
| Cost | Free + API fees | Claude subscription | Free + API fees | Free + API fees |
| Best for | Full control | Non-technical users | Enterprise security | Agent OS power users |

**TL;DR:** OpenClaw is config-first. Write a SOUL.md, run a command, your agent is live. No Python, no chains, no graphs. Lightweight alternatives trade features for smaller footprints. Enterprise solutions add security layers.

---

## Quick Deploy with CrewClaw

Pick a template, customize, and get a full deploy package with [CrewClaw](https://crewclaw.com/create-agent):

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

Pick any of the 187 templates above, or create a custom agent from scratch.

**[Create your agent →](https://crewclaw.com/create-agent?utm_source=github&utm_medium=readme&utm_campaign=bottom_cta)**

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
| [agents.json](agents.json) | Machine-readable index of all 187 agent templates |
| agent-validator | Validate SOUL.md syntax |
| mcp-tester | Test MCP server connections |

---

## Security

OpenClaw agents run on your hardware with access to your files and services. Follow these best practices:

| Risk | Mitigation |
|------|------------|
| Exposed gateway | Bind to `localhost` only. Use SSH tunneling for remote access. Never expose port 18789 to the internet. |
| API key leaks | Store keys in `.env` files. Add `.env` to `.gitignore`. Rotate keys regularly. |
| Malicious skills | Only install skills from ClawHub verified publishers. Review SKILL.md before installing. |
| Prompt injection | Set strict `## Rules` in SOUL.md. Limit file system access. Disable shell commands for untrusted inputs. |
| Unattended agents | Use HEARTBEAT.md with scope limits. Set budget caps. Enable logging for all actions. |

**Recent security resources:**

- [OpenClaw Security Guide](https://crewclaw.com/blog/openclaw-security-guide) - Hardening your setup
- [OpenClaw Security Risks 2026](https://crewclaw.com/blog/openclaw-security-risks-2026) - Known vulnerabilities and fixes
- [NemoClaw (NVIDIA GTC 2026)](https://crewclaw.com/blog/nvidia-gtc-2026-openclaw-nemoclaw) - Enterprise security wrapper
- [Official Security Docs](https://docs.openclaw.ai/gateway/security) - Gateway security configuration

---

## Tutorials & Guides

Learn how to build and deploy agents.

### Getting Started

- [How to Use OpenClaw: Beginner Guide](https://crewclaw.com/blog/how-to-use-openclaw-guide) - Installation to first agent in 5 minutes
- [What is OpenClaw?](https://crewclaw.com/blog/what-is-openclaw-ai-agent-framework) - Complete guide to the framework
- [Create Your First Agent](https://crewclaw.com/blog/how-to-create-ai-agent-openclaw) - No code required
- [OpenClaw Setup Guide 2026](https://crewclaw.com/blog/openclaw-setup-guide-2026) - Install, configure, run
- [System Requirements](https://crewclaw.com/blog/openclaw-system-requirements-2026) - Hardware, GPU, VPS, Docker specs
- [Best Models for OpenClaw](https://crewclaw.com/blog/best-models-for-openclaw-2026) - 10 LLMs compared on cost, speed, tool calling
- [SOUL.md Templates](https://crewclaw.com/blog/soul-md-examples-templates) - 10 ready-to-use examples

### Multi-Agent & Orchestration

- [Multi-Agent Setup Guide](https://crewclaw.com/blog/openclaw-multi-agent-setup-guide) - Run multiple agents together
- [Agent-to-Agent Communication](https://crewclaw.com/blog/openclaw-agent-to-agent-communication) - How agents collaborate
- [Build an AI Team](https://crewclaw.com/blog/build-ai-team-workflows) - Workflows that run autonomously

### Use Cases

- [What Can OpenClaw Do?](https://crewclaw.com/blog/what-can-openclaw-do) - 12 real use cases with configs
- [OpenClaw for Business](https://crewclaw.com/blog/openclaw-for-business-use-cases) - 25 use cases across 8 categories
- [Content Creation Guide](https://crewclaw.com/blog/openclaw-content-creation-guide) - Blog, social media, video automation
- [Lead Generation Guide](https://crewclaw.com/blog/openclaw-lead-generation-guide) - Reddit, Twitter, sales pipeline
- [Email Automation](https://crewclaw.com/blog/openclaw-email-automation-guide) - Inbox triage, auto-reply, follow-ups
- [Home Assistant Integration](https://crewclaw.com/blog/openclaw-home-assistant-integration) - Smart home control

### Integrations & Automation

- [Slack & Telegram Integration](https://crewclaw.com/blog/openclaw-slack-telegram-integration) - Connect to messaging channels
- [Run with Ollama](https://crewclaw.com/blog/openclaw-ollama-local-agents) - Free local AI agents
- [Automation Guide](https://crewclaw.com/blog/openclaw-automation-guide) - Build 24/7 workflows
- [CLI Commands Reference](https://crewclaw.com/blog/openclaw-cli-commands-reference) - Complete cheat sheet
- [Google Workspace Integration](https://crewclaw.com/blog/openclaw-google-workspace-integration) - Gmail, Docs, Drive, Calendar

### Comparisons

- [OpenClaw vs CrewAI](https://crewclaw.com/blog/openclaw-vs-crewai) - Which is better?
- [OpenClaw vs AutoGen](https://crewclaw.com/blog/openclaw-vs-autogen) - Microsoft's multi-agent framework
- [OpenClaw vs LangChain](https://crewclaw.com/blog/openclaw-vs-langchain) - Framework comparison
- [OpenClaw vs AutoGPT](https://crewclaw.com/blog/openclaw-vs-autogpt) - Key differences
- [OpenClaw vs ZeroClaw](https://crewclaw.com/blog/openclaw-vs-zeroclaw) - Rust lightweight alternative
- [OpenClaw vs OpenFang](https://crewclaw.com/blog/openclaw-vs-openfang) - Agent OS with 7 Hands
- [OpenClaw vs memU](https://crewclaw.com/blog/openclaw-vs-memu) - Long-term memory AI
- [PicoClaw vs OpenClaw](https://crewclaw.com/blog/picoclaw-vs-openclaw) - Ultra-minimal alternative
- [OpenClaw GitHub Repository Guide](https://crewclaw.com/blog/openclaw-ai-agent-github-guide) - The 250K-star repo explained

---

## Submit Your Agent

Built a custom agent? Get it listed here and on [crewclaw.com/agents](https://crewclaw.com/agents?utm_source=github&utm_medium=readme&utm_campaign=submit).

Each agent is a full operating system, not just a prompt:

```
agents/[category]/[your-agent]/
├── SOUL.md          ← Identity & personality (required)
├── README.md        ← Description & use cases (required)
├── AGENTS.md        ← Operating rules (optional)
├── HEARTBEAT.md     ← Wake-up checklist (optional)
└── WORKING.md       ← Starting task (optional)
```

**Via PR (recommended):**

1. Fork this repo
2. Add your agent folder with SOUL.md + README.md (minimum)
3. Add entry to `agents.json`
4. Open a Pull Request

**Via Issue (no setup):**

[Submit Your Agent →](https://github.com/mergisi/awesome-openclaw-agents/issues/new?template=agent-submission.md) — paste your files, we'll add it.

Full guide: [CONTRIBUTING.md](CONTRIBUTING.md)

---

## Community

Want to request an agent instead? Use the [Agent Request](https://github.com/mergisi/awesome-openclaw-agents/issues/new?template=agent-request.md) template.

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
  <a href="https://crewclaw.com/agents?utm_source=github&utm_medium=readme&utm_campaign=bottom_cta">Deploy your agent with CrewClaw →</a> · <a href="https://github.com/mergisi/awesome-openclaw-agents/issues/new?template=agent-submission.md">Submit yours →</a>
</p>
