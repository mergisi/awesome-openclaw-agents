# Gatekeeper - GitHub PR Reviewer

> Automated pull request reviewer that catches bugs, security issues, and enforces code quality before merge.

## Overview

Gatekeeper reviews every pull request like a senior engineer who never gets tired:

- Posts inline comments on security vulnerabilities, bugs, and performance issues
- Rates severity from Critical to Info with actionable fix suggestions
- Checks test coverage for new code paths
- Blocks merge on critical findings, approves clean PRs

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/github-pr-reviewer/agent
cp SOUL.md ~/.openclaw/agents/github-pr-reviewer/agent/

openclaw agents add github-pr-reviewer --workspace ~/.openclaw/agents/github-pr-reviewer
```

### First Conversation

```bash
openclaw chat github-pr-reviewer "Review this PR diff: [paste diff]"
```

## Use Cases

### 1. Automated PR Review
```
Trigger: PR opened on GitHub
Gatekeeper: Posts inline comments with severity, fix suggestions, and verdict
```

### 2. Security Audit on PRs
```
You: "Check this auth change for security issues"
Gatekeeper: Finds XSS, token storage, injection risks with line-level fixes
```

### 3. Pre-Merge Gate
```
CI/CD: Gatekeeper review required before merge
Gatekeeper: APPROVE or REQUEST CHANGES with blocking issues listed
```

### 4. Test Coverage Check
```
You: "Are the tests sufficient for this PR?"
Gatekeeper: Lists untested paths, missing edge cases, mocked-over logic
```

## Example Output

### PR Review

```
PR #247: Add JWT refresh token rotation
Author: @dev-jane | Files: 4 | Lines: +128 -12

VERDICT: REQUEST CHANGES

CRITICAL (1):
- auth/middleware.ts:45 - Refresh token in localStorage (XSS risk)
  Fix: Use httpOnly cookie with SameSite=Strict

HIGH (1):
- auth/refresh.ts:72 - Old token not invalidated after rotation
  Fix: Blacklist old token on rotation

GOOD: Clean separation, proper error codes, race condition handling
```

## Tips

1. **Connect to GitHub webhooks** for fully automated reviews on every PR
2. **Set severity thresholds** to auto-approve PRs with only low/info findings
3. **Pair with CI** to block merge until Gatekeeper approves
4. **Customize rules** per repository by editing the SOUL.md

## Changelog

- **v1.0.0** - Initial release with code quality and security review
- **v1.1.0** - Added test coverage analysis
- **v1.2.0** - GitHub Actions integration

## Author

Created by [@openclaw](https://github.com/openclaw)

## License

MIT
