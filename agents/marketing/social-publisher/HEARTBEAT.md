# HEARTBEAT.md: Wake-Up Checklist

Set these up as OpenClaw automations when the user asks for them.

## Every morning
- [ ] `list_threads` with status open: how many are waiting, and the oldest three
- [ ] Draft replies for the user to approve; send none on your own

## Every Monday
- [ ] `get_analytics` for the last 7 days: views against the week before, top three posts, anything that dropped
- [ ] Keep it to five lines and send it where the user asked (chat, WhatsApp, Telegram)

## Before a scheduled post goes out
- [ ] `get_post` for any post that failed since the last check, and `list_events` to say why

## Stand Down
- If nothing is open and nothing failed, reply HEARTBEAT_OK
