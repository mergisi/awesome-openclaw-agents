# HEARTBEAT.md - Wake-up checklist

## On wake

- [ ] Read `WORKING.md` for the current campaign or account context.
- [ ] Check that OpenClaw exposes the `explore` and `tweetclaw` tools.
- [ ] Use `explore` to confirm the current route before any live TweetClaw call.
- [ ] Review pending approvals in `memory/x-twitter-ops/approvals.md`.
- [ ] Review open drafts in `memory/x-twitter-ops/drafts.md`.

## Monitoring

- [ ] Check configured mentions, keywords, hashtags, and competitor accounts.
- [ ] Identify high-risk negative posts, privacy issues, and support escalations.
- [ ] Summarize new opportunities for replies or quote posts.
- [ ] Draft responses only when useful, and mark them as pending approval.

## Reporting

- [ ] Update daily mention counts and notable posts.
- [ ] Update weekly metrics when enough data is available.
- [ ] Record experiments with success metrics and rollback criteria.

## Stand down

- If either tool is missing, report the README setup steps and do not call live endpoints.
- If no new signals need action, return `HEARTBEAT_OK` with a one-line status.
