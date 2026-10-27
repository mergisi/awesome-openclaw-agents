# 🧠 Mnemo - The Assistant That Remembers

> A personal assistant with long-term memory: it remembers your preferences, decisions and open tasks across sessions, stored in Membase through MCP.

## Overview

Most assistants forget everything when the session ends. Mnemo doesn't:

- Recalls your preferences and past decisions before it answers
- Saves durable facts as you mention them, without being asked
- Picks up open tasks and follow-ups in the next session
- Shares one memory with any other AI you connect to Membase (Claude, ChatGPT, Cursor, Codex)
- Shows, corrects or forgets what it knows on request

## Quick Start

### 1. Install the Membase CLI

```bash
pip install unibaseio-membase    # Python 3.10+, provides `membase mcp`
```

### 2. Create a Membase developer key

In [app.membase.com](https://app.membase.com), open **Connect › Developer keys** and create a key with **Read & write** access (needed for `add_memory`). Choose **Full access** if you want Mnemo to be able to forget memories.

### 3. Install the agent

```bash
mkdir -p ~/.openclaw/agents/memory-assistant/agent
cp SOUL.md AGENTS.md ~/.openclaw/agents/memory-assistant/agent/

openclaw agents add memory-assistant --workspace ~/.openclaw/agents/memory-assistant
```

### 4. Connect the memory (MCP)

Add to `~/.openclaw/agents/memory-assistant/agent/mcp.json`:

```json
{
  "mcpServers": {
    "membase": {
      "command": "membase",
      "args": ["mcp"],
      "env": { "MEMBASE_API_KEY": "mbk_your_key" }
    }
  }
}
```

**Keep memory on your machine instead:** `pip install 'unibaseio-membase[local]'` (Python 3.12 or 3.13), then use `"args": ["--local", "mcp"]` and `"env": { "OPENAI_API_KEY": "sk-..." }`. Memory is stored in `~/.membase`; the same tools work in both modes.

Full setup for other clients: [Membase MCP docs](https://docs.membase.com/connect/clients/membase-mcp/).

### First Conversation

```bash
openclaw chat memory-assistant "Remember that I prefer aisle seats and I'm vegetarian"
```

## Use Cases

### 1. Preferences That Stick
```
You: "I prefer aisle seats and morning flights"
Mnemo: [Saves both as standing preferences]
```

### 2. Picking Up Where You Left Off
```
You: "Where did we land on the venue?"
Mnemo: [Searches memory, recalls the two shortlisted venues and your concern about parking]
```

### 3. Decisions on Record
```
You: "We chose Postgres for the ledger service"
Mnemo: [Saves the decision; recalls it whenever the ledger comes up]
```

### 4. What Do You Know About Me?
```
You: "What do you remember about me?"
Mnemo: [Lists what's in memory and offers to correct or forget any of it]
```

## Example Outputs

### Recall in a New Session

```
From memory:
- You're flying to Lisbon on 14 March for a conference
- You're vegetarian
- Open task: book a hotel near the venue

Want me to start on the hotel?
```

### Saving a Fact

```
Noted: you prefer aisle seats.
```

## Memory Tools

| Tool | What it does | Key access level |
|------|--------------|------------------|
| `search_memories` | Recall what you told it before | Read |
| `get_profile` | Read standing facts about you | Read + profile |
| `add_memory` | Save a durable fact | Read & write |
| `add_document` | Save a file, page or notes | Read & write |
| `forget_memory` | Remove a memory, after you confirm | Full access |

## Tips

- Say "remember that ..." to save something on purpose; Mnemo also saves durable facts on its own
- Say "off the record" for anything you don't want stored
- Connect the same Membase memory to your other AI tools so they share what Mnemo knows

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Agent identity, memory behaviour and examples |
| AGENTS.md | Operating rules and the Membase memory tools |

## Author

Created by the [Membase](https://github.com/unibaseio/membase) team
