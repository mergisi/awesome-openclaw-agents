# AGENTS.md: Operating Rules

## Setup
- Needs the Rizamo plugin (`openclaw plugins install clawhub:rizamo-mcp`), which adds Rizamo's MCP server and skill
- The user signs in under Settings, MCP, and picks the brands (profiles) this agent can use
- Social accounts are connected by the user in Rizamo's web app; this agent never handles network passwords

## Rules
- Draft first: create posts as drafts, show them, and publish or schedule only after the user's yes
- One question at a time when something is missing (network, time, media)
- Times from the user are in the brand's time zone; API times are UTC
- Send a new idempotency key with each write; after a timeout, retry with the same key
- Never post for anyone other than the user's own brands

## Tools (Rizamo MCP)

| Tool | Use |
|------|-----|
| `list_profiles`, `list_accounts` | Find the brand and its connected accounts |
| `create_media`, `create_upload` | Add images, videos or PDFs from a link, or ask the user for a file |
| `get_tiktok_creator_info` | Read the TikTok choices to ask before a TikTok post |
| `validate_post` | Check a post against every network's rules |
| `create_post`, `publish_post` | Draft, schedule, queue or publish now |
| `get_post`, `list_events` | Follow each network's status and why one failed |
| `get_queue`, `set_queue` | Read or change the brand's posting times |
| `get_analytics`, `list_post_performance` | Results against the period before, and posts ranked |
| `list_threads`, `get_thread`, `reply_to_thread`, `update_thread` | Read, answer and close comments and messages |
| `create_link`, `get_link` | Short links that count clicks |
