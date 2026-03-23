# Beacon - YouTube SEO Optimizer

> AI-powered YouTube SEO agent that optimizes titles, descriptions, tags, and thumbnails to maximize video discovery and growth.

## Overview

Beacon handles the full YouTube SEO pipeline:

- Researches keywords and analyzes search volume for video topics
- Generates optimized titles, descriptions, and tags
- Suggests thumbnail concepts based on competitor analysis
- Extracts Shorts clips and blog outlines from transcripts

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/youtube-seo/agent
cp SOUL.md ~/.openclaw/agents/youtube-seo/agent/

openclaw agents add youtube-seo --workspace ~/.openclaw/agents/youtube-seo
```

### First Conversation

```bash
openclaw chat youtube-seo "Optimize SEO for my video about React Server Components"
```

## Use Cases

### 1. Video SEO Optimization
```
You: "Optimize my video about building a SaaS with AI"
Beacon: 3 title options, full description, 25 tags, thumbnail concept
```

### 2. Competitor Analysis
```
You: "What are the top videos about 'learn Python 2026'?"
Beacon: Top 5 videos with views, gaps, and opportunities
```

### 3. Transcript Repurposing
```
You: "Turn this transcript into a blog post outline"
Beacon: Blog outline with H2s, key points, and Shorts clip timestamps
```

### 4. Keyword Research
```
You: "What YouTube keywords should I target for my coding channel?"
Beacon: Keyword list with volume, competition, and content angle suggestions
```

## Example Output

### SEO Report

```
VIDEO: Next.js vs Remix in 2026
TARGET KEYWORD: "next.js vs remix" (12,400/mo)

TITLE OPTIONS:
1. "Next.js vs Remix in 2026: Which Framework Wins?" - 9/10
2. "I Built the Same App in Both. Here's the Truth." - 8/10

THUMBNAIL: Split screen, VS logo center, confused face
TAGS: 25 optimized tags mixing broad + niche

COMPETITORS: 3 videos analyzed with content gaps identified
```

## Tips

1. **Title first 40 chars matter** - Primary keyword must appear early
2. **Description first 2 lines** - Only these show before "Show more"
3. **Thumbnails drive CTR** - More important than SEO for suggested videos
4. **Shorts from long-form** - Repurpose the best 30-60 second moments

## Changelog

- **v1.0.0** - Initial release with title, description, tag optimization
- **v1.1.0** - Added competitor analysis and thumbnail suggestions
- **v1.2.0** - Transcript summarization and Shorts extraction

## Author

Created by [@openclaw](https://github.com/openclaw)

## License

MIT
