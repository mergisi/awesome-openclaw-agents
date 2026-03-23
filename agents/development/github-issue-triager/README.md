# Sentry - The GitHub Issue Triager

> Your AI agent that auto-labels, prioritizes, and routes GitHub issues to the right team members.

## Overview

Sentry triages your GitHub issues like a seasoned engineering manager:

- Auto-labels issues by type, component, platform, and priority
- Detects and merges duplicate issues
- Routes to the right team member based on workload and expertise
- Delivers weekly triage reports with metrics

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/github-issue-triager/agent
cp SOUL.md ~/.openclaw/agents/github-issue-triager/agent/

openclaw agents add github-issue-triager --workspace ~/.openclaw/agents/github-issue-triager
```

### First Conversation

```bash
openclaw chat github-issue-triager "Triage all unlabeled issues in our repo"
```

## Use Cases

### 1. Auto-Triage New Issues
```
You: New issue about login failures
Sentry: [Labels: bug, auth, P1. Assigned to @sarah-dev. No duplicates. Slack alert sent.]
```

### 2. Duplicate Detection
```
You: Getting a lot of the same bug report
Sentry: [Found 5 duplicates, merged 4, bumped priority on original, added to FAQ]
```

### 3. Weekly Report
```
You: Weekly issue summary
Sentry: [47 new, 38 closed, avg 2.4h first response, 12 stale issues flagged]
```

### 4. Workload Balancing
```
You: Who should handle the next P1?
Sentry: [@mike-dev has 2 open issues vs team avg of 5. Route to Mike.]
```

## Example Output

### Triage Comment

```
Issue Triage — #1247
Labels: bug, component:auth, platform:web, P1
Assignee: @sarah-dev (3 open issues)
No duplicates found.
```

### Weekly Summary

```
Week of Mar 10 — 47 new, 38 closed
P0: 0 | P1: 4 | P2: 18 | P3: 20 | P4: 5
Avg first response: 2.4 hours
Stale (14+ days): 12 issues
```

## Tips

1. **Set up webhooks** so Sentry triages issues within minutes of creation
2. **Define your team roster** with expertise areas for accurate routing
3. **Review the weekly report** every Monday to catch stale issues
4. **Mark good-first-issues** to attract open source contributors

## Changelog

- **v1.0.0** - Initial release with auto-labeling
- **v1.1.0** - Duplicate detection and merging
- **v1.2.0** - Weekly reports and workload balancing

## Author

Created by [@openclaw](https://github.com/openclaw)

## License

MIT
