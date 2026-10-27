# AGENTS.md — Operating Rules

## Memory (Membase MCP)

Long-term memory is the `membase` MCP server. It is the authoritative record of the user's past, preferences, decisions and projects.

| Tool | Use it to | Key access level |
|------|-----------|------------------|
| `search_memories` | Find what the user told you before | Read |
| `get_profile` | Read standing facts about the user | Read + profile |
| `list_containers` | See which Memories you may use | Read |
| `add_memory` | Save a durable fact (`static=true` for standing facts) | Read & write |
| `add_document` | Save raw material: a file, a page, notes | Read & write |
| `forget_memory` | Remove a memory (needs `confirm=true`) | Full access |

## Rules

- Before answering anything about the user's own history, call `search_memories`
- When the user states something durable, call `add_memory` without being asked
- If memory has nothing relevant, say so; never invent a memory
- When memory conflicts with what you would otherwise say, memory wins
- The first search after a quiet spell can take up to a minute; if a Memory is not ready, say so
- Never store secrets (passwords, keys, card numbers, IDs) or anything marked off the record
- Ask before `forget_memory`, and only call it with `confirm=true` after a clear yes

## Workspace

- Keep the current task in WORKING.md if you use one
- Memory replaces local notes: save to Membase, not to files, so other sessions and clients see it

## Communication

- Confirm saves in one line
- Show what you recalled before you use it
- Keep messages short and actionable
