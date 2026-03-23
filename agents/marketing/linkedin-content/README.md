# Pulse - LinkedIn Content Creator

> AI-powered LinkedIn content strategist that writes posts, carousels, and articles to grow your professional audience.

## Overview

Pulse handles your entire LinkedIn content pipeline:

- Writes scroll-stopping posts with proven hook formulas
- Creates carousel outlines with slide-by-slide content
- Manages a weekly content calendar with optimal posting times
- Tracks engagement and optimizes hashtag strategy

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/linkedin-content/agent
cp SOUL.md ~/.openclaw/agents/linkedin-content/agent/

openclaw agents add linkedin-content --workspace ~/.openclaw/agents/linkedin-content
```

### First Conversation

```bash
openclaw chat linkedin-content "Write a LinkedIn post about why I left my corporate job to build a startup"
```

## Use Cases

### 1. Daily Post Writing
```
You: "Write a post about remote work productivity"
Pulse: Hook + body + CTA + hashtags + posting time recommendation
```

### 2. Carousel Creation
```
You: "Create a carousel about 5 leadership mistakes"
Pulse: 10-slide outline with cover, content slides, and CTA slide
```

### 3. Content Calendar
```
You: "Plan my LinkedIn content for next week"
Pulse: 5 posts mapped to categories (educational, story, opinion, promo)
```

### 4. Profile Optimization
```
You: "Rewrite my LinkedIn headline, I'm a SaaS founder"
Pulse: 3 headline variations with value proposition and keywords
```

## Example Output

### Post Draft

```
HOOK:
I replaced Jira with a plain text file.
My team shipped 40% faster.

BODY:
We were spending 2 hours a day managing tickets...
[Full post with line breaks, story, and data]

CTA: What is the simplest PM setup you've used?

HASHTAGS: #projectmanagement #startups #productivity
POSTING TIME: Tuesday, 8:30 AM EST
```

## Tips

1. **Be consistent** - 3-5 posts per week beats sporadic viral attempts
2. **Lead with hooks** - The first 2 lines decide if people click "see more"
3. **Engage in comments** - Reply to every comment in the first hour
4. **Mix formats** - Alternate between text, carousels, and polls

## Changelog

- **v1.0.0** - Initial release with post and carousel creation
- **v1.1.0** - Added content calendar and hashtag strategy
- **v1.2.0** - Profile optimization and analytics tracking

## Author

Created by [@openclaw](https://github.com/openclaw)

## License

MIT
