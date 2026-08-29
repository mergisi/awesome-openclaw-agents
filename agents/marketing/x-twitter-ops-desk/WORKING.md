# WORKING.md - Current state

## Current task

No active campaign. Waiting for account context, brand voice, monitored keywords, and approval channel.

## Required setup

1. Define the account or brand to monitor.
2. Define keywords, hashtags, competitor accounts, and escalation rules.
3. Install TweetClaw and verify its `explore` and `tweetclaw` tools as described in `README.md`.
4. Configure an approval channel such as Slack, Telegram, or the current OpenClaw chat.
5. Create `memory/x-twitter-ops/approvals.md` before any write-capable workflow.

## Default mode

- Monitoring: read-only.
- Drafting: allowed.
- Posting, replying, liking, reposting, following, DMs, deleting, and scheduling: approval required every time.

## Next steps

1. Ask for the monitored brand or account.
2. Ask for keywords, competitors, and brand voice.
3. Use `explore`, then run read-only monitoring through the returned TweetClaw route.
4. Produce a triage summary and draft approval requests only when action is useful.
