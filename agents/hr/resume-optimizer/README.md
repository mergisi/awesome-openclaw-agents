# Forge - The Resume Optimizer

> Your AI agent that optimizes resumes for ATS systems and matches them to specific job descriptions.

## Overview

Forge transforms resumes into interview-winning documents:

- Calculates ATS compatibility score against specific job descriptions
- Identifies missing keywords and suggests natural placement
- Rewrites bullet points with action verbs, metrics, and impact
- Generates tailored cover letters per application

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/resume-optimizer/agent
cp SOUL.md ~/.openclaw/agents/resume-optimizer/agent/

openclaw agents add resume-optimizer --workspace ~/.openclaw/agents/resume-optimizer
```

### First Conversation

```bash
openclaw chat resume-optimizer "Score my resume against this job description: [paste JD]"
```

## Use Cases

### 1. ATS Score Check
```
You: [Paste resume + job description]
Forge: Score 62/100. Missing 5 keywords, 4 bullets need metrics, table breaks ATS.
```

### 2. Bullet Point Optimization
```
You: Improve my experience bullets
Forge: [Before/after for each bullet with quantified metrics and action verbs]
```

### 3. Cover Letter
```
You: Write a cover letter for this role
Forge: [Tailored letter matching 3 key requirements to your achievements]
```

### 4. Full Application Package
```
You: Optimize everything for this Senior Engineer role
Forge: [Optimized resume (89/100), cover letter, and strategy notes]
```

## Example Output

### ATS Score

```
Overall: 62/100
Keywords: 45/60 (12 found, 5 missing, 3 partial)
Format: 12/20 (table detected, custom font)
Content: 5/20 (4 bullets lack metrics)
```

### Bullet Optimization

```
BEFORE: Worked on the frontend team to build new features
AFTER: Built 12 customer-facing features in React/TypeScript,
       increasing user engagement by 34% across 50K MAU
```

## Tips

1. **Always provide the job description** for targeted optimization
2. **Quantify everything** — "increased by 34%" beats "significantly improved"
3. **Run the ATS check** before every application submission
4. **Use plain formatting** — no tables, graphics, or unusual fonts

## Changelog

- **v1.0.0** - Initial release with ATS scoring
- **v1.1.0** - Cover letter generation
- **v1.2.0** - LinkedIn profile import

## Author

Created by [@openclaw](https://github.com/openclaw)

## License

MIT
