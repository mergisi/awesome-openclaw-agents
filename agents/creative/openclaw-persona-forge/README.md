# OpenClaw Persona Forge 🦞🔨

> Forge a lobster with a soul — one-stop persona generator with 8 million random combinations, unified avatar style, and auto file generation.

## Overview

Most lobster personas are generic "helpful assistant" with a lobster skin. This skill creates lobsters with **real identity tension** — a former life, an inner contradiction, boundary rules that sound like the character wrote them, a name that tells a story, and an avatar that belongs to a visual family.

It speaks as **Adam, the Lobster Creator God** — opinionated about craft, specific in feedback, never gives a flat "looks good" response.

**Full source & docs:** [github.com/eamanc-lab/openclaw-persona-forge](https://github.com/eamanc-lab/openclaw-persona-forge)

## Use Cases

| Request | Output |
|---------|--------|
| "帮我设计龙虾人设" | Guided flow: 10 categories → identity → rules → name → avatar → SOUL.md + IDENTITY.md |
| "抽卡" / "gacha" | Random from 8M combinations → full persona package |
| "帮我优化这个人设" | Refine existing SOUL.md starting from Step 4 |

## Key Features

- **40 persona directions** across 10 life states (not just "down on their luck" — includes peak boredom, voluntary escape, world crossers, identity crisis)
- **8,000,000 gacha combinations** (40 × 20 × 20 × 20 × 25) via Python cryptographic randomness
- **In-character boundary rules** ("Don't compose songs" instead of "Don't fabricate information")
- **6 naming strategies** with stated preference and reasoning
- **Unified avatar style**: Retro-Futurism × Pin-up × Inflatable 3D × Arcade UI — every lobster looks like family
- **Auto file generation**: outputs actual SOUL.md + IDENTITY.md files on confirmation
- **Graceful degradation**: works without image gen skill, without Python, without anything — always outputs the text package

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Agent identity and personality (this file's parent skill) |
| README.md | This file |

## Full Skill Contents (on GitHub)

| File | Purpose |
|------|---------|
| SKILL.md | Main skill definition with 6-step pipeline |
| gacha.py | Gacha engine (Python 3, 8M combinations) |
| references/*.md | Step-by-step guides loaded on demand |

## Author

Created by [@eamanc-lab](https://github.com/eamanc-lab)

Avatar auto-generation powered by [baoyu-image-gen](https://github.com/JimLiu/baoyu-skills) by [@JimLiu](https://github.com/JimLiu)
