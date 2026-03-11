# 🦞 Awesome OpenClaw Agents

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Stars](https://img.shields.io/github/stars/mergisi/awesome-openclaw-agents?style=social)](https://github.com/mergisi/awesome-openclaw-agents)
[![Agents](https://img.shields.io/badge/agents-103-blueviolet)](agents/)

> A curated collection of **103 production-ready AI agent templates** for the OpenClaw ecosystem. Every template is a copy-paste ready `SOUL.md` file.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:4F46E5,100:7C3AED&height=180&section=header&text=%F0%9F%A6%9E%20103%20OpenClaw%20Agent%20Templates&fontSize=36&fontColor=ffffff&fontAlignY=35" width="100%"/>
</p>

<div align="center">

### Don't want to set up Docker, VPS, or configs yourself?

**[Browse all 103 templates →](https://crewclaw.com/agents?utm_source=github&utm_medium=readme&utm_campaign=browse)** · **[Deploy in 60 seconds →](https://crewclaw.com/create-agent?utm_source=github&utm_medium=readme&utm_campaign=deploy)**

Pick a template. Customize the config. Get a full deploy package. No terminal required.

</div>

<div align="center">

📬 **Get weekly agent templates & tips** — new templates, deployment guides, and community highlights every Tuesday.

**[Subscribe to the newsletter →](https://docs.google.com/forms/d/e/1FAIpQLSeIqBjV1LXnR2qQqGSGa-48rAveAmpSKVqlzLqDK2d4D4aVWg/viewform)**

</div>

---

## Contents

- [Agent Templates](#agent-templates) (103 agents across 19 categories)
  - [Productivity](#productivity) · [Development](#development) · [Marketing](#marketing--content) · [Business](#business) · [Personal](#personal)
  - [DevOps](#devops) · [Finance](#finance) · [Education](#education) · [Healthcare](#healthcare) · [Legal](#legal) · [HR](#hr) · [Creative](#creative) · [Security](#security)
  - [E-Commerce](#e-commerce) · [Data](#data) · [SaaS](#saas) · [Real Estate](#real-estate) · [Freelance](#freelance) · [Moltbook](#-moltbook-new)
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

### 🧘 Personal

Your AI assistant for daily life.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [📅 Atlas](agents/personal/daily-planner/) | Schedule optimization, morning/evening reviews | When you want a structured daily routine with accountability | [View](agents/personal/daily-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📚 Scroll](agents/personal/reading-digest/) | Article summaries, weekly reading digest | When you have a reading backlog and need curated summaries | [View](agents/personal/reading-digest/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [💪 Iron](agents/personal/fitness-coach/) | Workouts, nutrition, progress reports | When you want a personal trainer that tracks everything | [View](agents/personal/fitness-coach/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🏠 Home Automation](agents/personal/home-automation/) | Smart home control via Telegram | When you want to control your smart home through chat | [View](agents/personal/home-automation/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [👨‍👩‍👧‍👦 Family Coordinator](agents/personal/family-coordinator/) | Shared calendar, meals, chore rotation | When your family needs a shared organizer and planner | [View](agents/personal/family-coordinator/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

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

### 💰 Finance

Making sense of the numbers.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🧾 Expense Tracker](agents/finance/expense-tracker/) | Expense categorization, budget alerts | When you need automated expense tracking and budget monitoring | [View](agents/finance/expense-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🧮 Invoice Manager](agents/finance/invoice-manager/) | Invoice creation, tracking, follow-ups | When invoices are getting lost and payments are late | [View](agents/finance/invoice-manager/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📈 Revenue Analyst](agents/finance/revenue-analyst/) | MRR analysis, churn, revenue forecasts | When you want automated revenue reports and forecasting | [View](agents/finance/revenue-analyst/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [🏦 Tax Preparer](agents/finance/tax-preparer/) | Receipt organization, deduction calculation | When tax season is approaching and you need to get organized | [View](agents/finance/tax-preparer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |
| [📉 Trading Bot](agents/finance/trading-bot/) | Portfolio tracking, sentiment, price alerts | When you want automated market monitoring and price alerts | [View](agents/finance/trading-bot/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=data-analyst) |

### 🎓 Education

Learning smarter, not harder.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🎓 Tutor](agents/education/tutor/) | Concept explanation, practice problems | When you need a patient tutor available 24/7 | [View](agents/education/tutor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [❓ Quiz Maker](agents/education/quiz-maker/) | Quiz generation, score tracking | When you want automated quizzes from your study material | [View](agents/education/quiz-maker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📖 Study Planner](agents/education/study-planner/) | Study schedules, reminders | When you need a structured study plan with daily reminders | [View](agents/education/study-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🔬 Research Assistant](agents/education/research-assistant/) | Paper search, summaries, citations | When you're doing research and need help finding papers | [View](agents/education/research-assistant/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🌍 Language Tutor](agents/education/language-tutor/) | Language learning, conversation practice | When you want daily language practice on your phone | [View](agents/education/language-tutor/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### 🏥 Healthcare

Taking care of what matters most.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🧘 Wellness Coach](agents/healthcare/wellness-coach/) | Daily check-ins, mental health, habits | When you want daily wellness reminders and mood tracking | [View](agents/healthcare/wellness-coach/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🥗 Meal Planner](agents/healthcare/meal-planner/) | Meal plans, nutrition tracking | When you need weekly meal plans based on your goals | [View](agents/healthcare/meal-planner/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |
| [🏋️ Workout Tracker](agents/healthcare/workout-tracker/) | Workout plans, progress tracking | When you want a workout plan that adapts to your progress | [View](agents/healthcare/workout-tracker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=fitness-coach) |

### ⚖️ Legal

Navigating the fine print.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [📜 Contract Reviewer](agents/legal/contract-reviewer/) | Contract review, risky clause detection | When you're reviewing contracts and need a second pair of eyes | [View](agents/legal/contract-reviewer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [✅ Compliance Checker](agents/legal/compliance-checker/) | Compliance monitoring, deadline tracking | When you need to stay on top of regulatory requirements | [View](agents/legal/compliance-checker/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📋 Policy Writer](agents/legal/policy-writer/) | Internal policies, terms of service | When you need to draft or update company policies | [View](agents/legal/policy-writer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

### 👥 HR

Building teams that work.

| Agent | Specialty | When to Use | SOUL.md | Deploy |
|-------|-----------|-------------|---------|--------|
| [🤝 Recruiter](agents/hr/recruiter/) | Resume screening, interview scheduling | When you're hiring and need faster candidate screening | [View](agents/hr/recruiter/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [🎒 Onboarding](agents/hr/onboarding/) | New hire setup, orientation guides | When new hires need a guided onboarding experience | [View](agents/hr/onboarding/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |
| [📊 Performance Reviewer](agents/hr/performance-reviewer/) | Feedback collection, review summaries | When it's review season and you need structured feedback | [View](agents/hr/performance-reviewer/SOUL.md) | [Deploy →](https://crewclaw.com/create-agent?role=personal-assistant) |

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

Pick any of the 103 templates above, or create a custom agent from scratch.

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
| [agents.json](agents.json) | Machine-readable index of all 100 agent templates |
| agent-validator | Validate SOUL.md syntax |
| mcp-tester | Test MCP server connections |
| [ProxyClaw](https://github.com/Iploop/proxyclaw) | Residential proxy skill — 2M+ IPs, 195+ countries, anti-bot bypass. `clawhub install proxyclaw` |

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
