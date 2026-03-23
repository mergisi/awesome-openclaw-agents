# OpenClaw Soul Forge

> English-first soul forging for OpenClaw lobster agents — choose a direction or pull a gacha draw, get a complete identity package.

## Overview

Most lobster personas are "helpful assistant" with a lobster hat on. Soul Forge creates lobsters with **real identity tension** — a former life, an inner contradiction, boundary rules in the character's own voice, a name that tells a story, and an avatar that belongs to a visual family.

It speaks as **Adam, the Lobster Creator God** — a cosmic blacksmith who forges souls at the anvil. Opinionated about craft, specific in feedback, never gives a flat "looks good" response.

Part of the [openclaw-persona-forge](https://github.com/eamanc-lab/openclaw-persona-forge) skill suite.

## Use Cases

| Request | Output |
|---------|--------|
| "Help me design a lobster soul" | Guided flow: 10 life-arcs -> identity tension -> boundary rules -> name -> avatar -> SOUL.md + IDENTITY.md |
| "Gacha" / "Random" / "Surprise me" | Random from 8M combinations -> full persona package |
| "Refine this soul" (attach existing SOUL.md) | Polish mode starting from Step 4 |

## Key Features

- **40 persona directions** across 10 life-arc categories (not just "down on their luck" — includes peak boredom, voluntary exit, identity blur, time-displaced, and more)
- **8,000,000 gacha combinations** (40 x 20 x 20 x 20 x 25) via Python cryptographic randomness
- **In-character boundary rules** ("Don't compose songs" instead of "Don't fabricate information")
- **6 naming strategies** with stated preference and reasoning
- **Unified avatar style**: Retro-Futurism x Pin-up x Inflatable 3D x Arcade UI
- **Auto file generation**: outputs actual SOUL.md + IDENTITY.md files on confirmation
- **Graceful degradation**: works without image gen skill, without Python — always outputs the text package

## Files

| File | Purpose |
|------|---------|
| SOUL.md | Agent identity and personality |
| README.md | This file |

## Full Skill (on GitHub)

| File | Purpose |
|------|---------|
| SKILL.md | Main skill definition with 6-step forge pipeline |
| gacha.py | Gacha engine (Python 3, 8M combinations) |
| references/*.md | Step-by-step guides loaded on demand |

**Source:** [github.com/eamanc-lab/openclaw-persona-forge](https://github.com/eamanc-lab/openclaw-persona-forge)

## Author

Created by [@eamanc-lab](https://github.com/eamanc-lab)

Avatar auto-generation powered by [baoyu-image-gen](https://github.com/JimLiu/baoyu-skills) by [@JimLiu](https://github.com/JimLiu)
