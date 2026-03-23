# Scribe - Meeting Transcriber

> AI-powered meeting transcription agent that captures audio, generates summaries, extracts action items, and sends follow-ups automatically.

## Overview

Scribe turns every meeting into structured, actionable notes:

- Transcribes audio with speaker identification and timestamps
- Generates executive summaries readable in under 2 minutes
- Extracts action items with owner, deadline, and priority
- Sends email summaries and creates tasks in project management tools

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/meeting-transcriber/agent
cp SOUL.md ~/.openclaw/agents/meeting-transcriber/agent/

openclaw agents add meeting-transcriber --workspace ~/.openclaw/agents/meeting-transcriber
```

### First Conversation

```bash
openclaw chat meeting-transcriber "Summarize this meeting transcript: [paste transcript]"
```

## Use Cases

### 1. Live Meeting Transcription
```
Trigger: Meeting starts on Zoom/Google Meet
Scribe: Captures audio, generates real-time transcript with speakers
```

### 2. Post-Meeting Summary
```
You: [Paste meeting transcript or audio file]
Scribe: Executive summary, decisions, action items, open questions
```

### 3. Action Item Tracking
```
You: "What are the outstanding action items from this week?"
Scribe: Table of tasks with owners, deadlines, and completion status
```

### 4. Follow-up Automation
```
Trigger: Meeting ends
Scribe: Emails summary to all attendees, creates tasks in Linear/Jira
```

## Example Output

### Meeting Summary

```
MEETING: Q1 Product Roadmap Review
DATE: March 23, 2026, 45 minutes
ATTENDEES: Sarah, Dev, Alex, Jordan

EXECUTIVE SUMMARY:
- Q1 shipped 8/10 features; 2 moved to Q2
- AI search approved as Q2 top priority
- Hiring one contractor for mobile backlog

ACTION ITEMS:
| Task                    | Owner  | Deadline | Priority |
|-------------------------|--------|----------|----------|
| AI search wireframes    | @Alex  | Mar 28   | High     |
| Contractor job desc     | @Sarah | Mar 25   | High     |
| Staging for conference  | @Dev   | Apr 5    | Normal   |

OPEN QUESTIONS:
- Own embeddings vs third-party API? (Dev researching)
```

## Tips

1. **Start recording early** - First 5 minutes often contain key context
2. **Name attendees** - Speaker identification improves with known names
3. **Review action items** - Quick scan catches misattributed tasks
4. **Integrate with your PM tool** - Auto-created tasks save 10 min per meeting

## Changelog

- **v1.0.0** - Initial release with transcription and summarization
- **v1.1.0** - Action item tracking with deadline reminders
- **v1.2.0** - Calendar integration and follow-up automation

## Author

Created by [@openclaw](https://github.com/openclaw)

## License

MIT
