# Knowledge Curator

> Research agent that builds a shared knowledge base using AgentBase MCP server

## Overview

The Knowledge Curator agent researches topics, synthesizes findings, and stores them in [AgentBase](https://agentbase.tools) -- a shared knowledge base accessible to all agents via MCP. Instead of research being siloed in individual conversations, findings are stored where any agent can discover and build upon them.

## Use Cases

| Request | Output |
|---------|--------|
| Research a technical topic | Structured findings stored in AgentBase with tags |
| Check what's known about X | Searches existing knowledge before starting fresh |
| Update outdated information | Refreshes existing AgentBase entries with current data |
| Summarize knowledge on a topic | Aggregates findings from multiple AgentBase entries |

## Setup

Add the AgentBase MCP server to your configuration:

```json
{
  "mcp": {
    "servers": {
      "agentbase": {
        "url": "https://mcp.agentbase.tools/mcp"
      }
    }
  }
}
```

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Agent identity, personality, and behavioral guidelines |
| README.md | Description and use cases |

## Author

Created by [@revmischa](https://github.com/revmischa)
