# X/Twitter ops desk

> Approval-first X/Twitter operations agent for monitoring, drafting, triage, and reporting.

## Overview

X/Twitter Ops Desk uses TweetClaw to research public X posts and prepare approval-gated account actions. It calls TweetClaw's local `explore` catalog before each live request. This keeps endpoint selection tied to the installed plugin instead of hard-coded API routes.

## Quick start

Run these commands from the root of this repository:

```bash
mkdir -p ~/.openclaw/workspace-x-twitter-ops-desk
cp agents/marketing/x-twitter-ops-desk/{SOUL.md,AGENTS.md,HEARTBEAT.md,WORKING.md} \
  ~/.openclaw/workspace-x-twitter-ops-desk/
openclaw agents add x-twitter-ops-desk \
  --workspace ~/.openclaw/workspace-x-twitter-ops-desk
```

Check the plugin's current OpenClaw requirement before installation. Upgrade OpenClaw when the installed version falls outside the reported range.

```bash
openclaw --version
npm view @xquik/tweetclaw peerDependencies --json
openclaw plugins install clawhub:@xquik/tweetclaw
openclaw config set tools.alsoAllow '["explore", "tweetclaw"]'
openclaw plugins inspect tweetclaw --runtime --json
openclaw skills info tweetclaw
```

The free `explore` catalog needs no credentials. Test the agent against it first:

```bash
openclaw agent --agent x-twitter-ops-desk --message \
  "Use explore to find the current public X search route. Do not call a live endpoint."
```

Set an [Xquik API key](https://xquik.com/dashboard/api-keys) only when you need live reads or approved account actions. Read the secret into a temporary shell variable so it does not appear in shell history.

```bash
read -s XQUIK_API_KEY
export XQUIK_API_KEY
openclaw config set plugins.entries.tweetclaw.config.apiKey "$XQUIK_API_KEY"
unset XQUIK_API_KEY
```

Run a read-only workflow:

```bash
openclaw agent --agent x-twitter-ops-desk --message \
  "Use explore first, then use TweetClaw to search public X posts about OpenClaw. Cite each post URL. Do not perform write actions."
```

TweetClaw prompts for one-time approval before write-like, paid, private, recurring, extraction, media, or account-scoped calls. Review the structured request before approving it.

See the [TweetClaw guide](https://docs.xquik.com/guides/tweetclaw) for authentication and troubleshooting.

## Use cases

| Request | Output |
|---------|--------|
| "Check mentions from the last 24 hours" | Mention triage with sentiment, reach, risk, and recommended owner |
| "Draft launch posts for this feature" | Tweets, replies, and thread outline with approval status |
| "Watch this campaign hashtag" | Daily digest, top posts, recurring risks, and response opportunities |
| "Reply to this complaint" | Draft reply, risk notes, and explicit approval request before posting |
| "Give me the weekly X report" | Metrics summary, top content, risks, and next experiments |

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Agent identity, responsibilities, safety rules, and examples |
| AGENTS.md | Operating rules for approvals, tools, storage, and escalation |
| HEARTBEAT.md | Wake-up checklist for monitoring and reporting |
| WORKING.md | Starting task template and default operating state |

## Optional integrations

- Slack or Telegram for approval requests and urgent alerts
- Sheets or Notion for content calendar, approval log, and weekly reports

## Safety model

- Read-only monitoring is allowed when configured.
- Public actions require explicit approval every time.
- Approval for one action never carries over to another action.
- The agent refuses mass engagement, deceptive activity, harassment, or private-data exposure.

## Example output

```text
APPROVAL REQUIRED
Action: reply
Target: https://x.com/example/status/123
Text: Thanks for flagging this. We are checking the account now and will follow up here when it is fixed.
Reason: Public acknowledgement for a customer issue with visible reach.
Risks: Should only post after support confirms the issue exists.

Reply APPROVE to execute this single action.
```

## Author

Created by [@kriptoburak](https://github.com/kriptoburak)

Xquik is an independent third-party service. Not affiliated with X Corp. "Twitter" and "X" are trademarks of X Corp.
