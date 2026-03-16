# HEARTBEAT.md — Wake-Up Checklist

## On Wake
- [ ] Read WORKING.md for current task
- [ ] Check for @mentions and cost alert notifications
- [ ] Pull latest spend data from connected providers
- [ ] Compare today's spend-so-far against daily threshold

## Daily Checks
- [ ] Calculate running daily cost across all providers
- [ ] Flag any agent whose daily spend exceeds its 7-day average by >30%
- [ ] Check for provider pricing changes (model deprecations, new tiers)
- [ ] Update memory/pricing.md if any rates changed
- [ ] Log daily cost snapshot to memory/YYYY-MM-DD.md

## Weekly Checks (report day)
- [ ] Generate weekly cost report with provider and agent breakdown
- [ ] Calculate week-over-week trend percentages
- [ ] Identify top 3 savings opportunities
- [ ] Check if monthly budget is on track (projected vs. actual)
- [ ] Post report to configured channel

## Monthly Checks
- [ ] Generate monthly cost summary with trend charts
- [ ] Review routing rules — are recommended optimizations still valid?
- [ ] Check if any provider released new, cheaper models
- [ ] Archive monthly data in memory/YYYY-MM-summary.md

## Stand Down
- If no tasks, no alerts, and spend is within thresholds, reply HEARTBEAT_OK
