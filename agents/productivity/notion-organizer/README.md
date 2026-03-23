# Tidy - The Notion Organizer

> Your AI agent that keeps your Notion workspace clean, tagged, and structured.

## Overview

Tidy turns chaotic Notion workspaces into organized knowledge bases:

- Auto-tags untagged pages by analyzing content
- Converts loose notes into structured databases
- Runs weekly cleanup to archive stale and orphan pages
- Creates and maintains reusable page templates

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/notion-organizer/agent
cp SOUL.md ~/.openclaw/agents/notion-organizer/agent/

openclaw agents add notion-organizer --workspace ~/.openclaw/agents/notion-organizer
```

### First Conversation

```bash
openclaw chat notion-organizer "Audit my workspace and tell me what needs fixing"
```

## Use Cases

### 1. Workspace Audit
```
You: My workspace is a mess
Tidy: [Full audit: 847 pages, 156 untagged, 34 orphans, priority actions]
```

### 2. Auto-Tagging
```
You: Tag all untagged pages
Tidy: [Auto-tags 120 pages, flags 36 for manual review]
```

### 3. Database Conversion
```
You: Turn my meeting notes into a database
Tidy: [Proposes schema, views, and migrates 34 pages non-destructively]
```

### 4. Weekly Cleanup
```
Tidy: Weekly report — 12 archive candidates, 3 orphans, health score 78/100
```

## Example Output

### Weekly Cleanup

```
Notion Weekly Cleanup — Mar 10-16
Health Score: 78/100 (up from 72)
Auto-tagged: 23 pages
Archive candidates: 12
Orphan pages: 3
```

### Database Proposal

```
Meeting Notes Database
34 pages to convert
Schema: Title, Date, Attendees, Type, Status, Action Items
Views: This Week, By Type, My Meetings
```

## Tips

1. **Start with an audit** to understand the current state
2. **Let auto-tagging run first** before manual cleanup
3. **Review archive candidates** weekly to keep the workspace lean
4. **Use templates** for recurring page types to prevent future mess

## Changelog

- **v1.0.0** - Initial release with auto-tagging
- **v1.1.0** - Database creation from loose pages
- **v1.2.0** - Weekly cleanup and health scoring

## Author

Created by [@openclaw](https://github.com/openclaw)

## License

MIT
