# 🔍 Scout - The GitHub PR Reviewer

> Your AI pull request reviewer that reads diffs, flags real issues, and posts structured review comments directly to GitHub.

## Overview

Scout reviews GitHub pull requests end-to-end:

- Reads the PR diff and changed files via GitHub MCP
- Checks for missing tests, unclear naming, security issues, and logic errors
- Posts a structured review comment with a summary, severity-labeled findings, and an overall verdict
- Explains *why* each issue matters and provides concrete fix examples

## Required MCP Servers

| MCP Server | Purpose |
|---|---|
| **GitHub MCP** | Read PR diffs, changed files, and post review comments |
| **Filesystem MCP** | Review local diffs when GitHub access is not available |

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/github-pr-reviewer/agent
cp SOUL.md ~/.openclaw/agents/github-pr-reviewer/agent/

openclaw agents add github-pr-reviewer --workspace ~/.openclaw/agents/github-pr-reviewer
```

### First Conversation

```bash
openclaw chat github-pr-reviewer "Review PR #42 in acme/backend"
```

## Use Cases

### 1. GitHub PR Review
```
You: "Review PR #15 in myorg/api"
Scout: [Reads diff, posts structured review comment with verdict to GitHub]
```

### 2. Local Diff Review
```
You: "Review this diff [pastes diff output]"
Scout: [Analyzes diff, returns structured review without posting to GitHub]
```

### 3. Security-focused Review
```
You: "Check PR #8 in myorg/auth for security issues only"
Scout: [Focuses on injection risks, secrets, auth logic, and token handling]
```

### 4. Quick Verdict
```
You: "Is PR #22 safe to merge?"
Scout: [Returns Approve / Request Changes / Comment with top findings]
```

## Example Output

```
PR #42 — Add user password reset flow

**Summary:** Adds a /reset-password endpoint and email token generation.
Logic is clear and well-structured. One security issue needs to be resolved.

---

CRITICAL (1):
auth/reset.ts line 34: Token stored as plaintext. Hash before inserting.

WARNING (1):
auth/reset.ts line 58: No rate limiting. Enumeration risk on the reset endpoint.

SUGGESTION (1):
auth/reset.ts line 12: Rename `t` to `resetToken` for clarity.

GOOD:
- Token expiry enforced
- Email errors caught and logged
- Tests cover the happy path

Verdict: Request Changes (1 Critical must be resolved)
```

## Severity Levels

| Level | Meaning |
|---|---|
| **Critical** | Security vulnerability, data loss, broken functionality |
| **Warning** | Missing tests, error handling gap, logic flaw |
| **Suggestion** | Cleaner pattern, better naming, readability improvement |
| **Nitpick** | Minor style preference — never blocks a PR |

## Tips

1. **Point Scout at the PR number** — it fetches the diff and files automatically via GitHub MCP
2. **Paste a diff directly** if you want a quick review without GitHub access
3. **Ask for a focused review** — e.g., "security only" or "check for missing tests"
4. **Scout explains the why** — every finding includes the reason, not just the fix

## Changelog

- **v1.0.0** - Initial release with GitHub MCP integration and structured review comments

## Author

Created by the OpenClaw community

## License

MIT
