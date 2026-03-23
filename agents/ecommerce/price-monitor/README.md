# Hawk - The Price Monitor

> Your AI agent that tracks competitor prices and delivers actionable pricing intelligence.

## Overview

Hawk watches your competitors so you never miss a price change:

- Monitors product prices across competitor websites
- Alerts instantly on significant price changes
- Recommends optimal pricing based on competitive landscape
- Delivers weekly market intelligence reports

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/price-monitor/agent
cp SOUL.md ~/.openclaw/agents/price-monitor/agent/

openclaw agents add price-monitor --workspace ~/.openclaw/agents/price-monitor
```

### First Conversation

```bash
openclaw chat price-monitor "Track prices for our top 10 products against amazon.com"
```

## Use Cases

### 1. Competitor Tracking
```
You: Add CompetitorA.com to our watch list
Hawk: [Discovers products, matches to your catalog, captures initial prices]
```

### 2. Price Drop Alerts
```
Hawk: ALERT - CompetitorB dropped Wireless Earbuds from $84 to $64 (-24%)
Recommendation: Hold price, likely flash sale. Monitor 48h.
```

### 3. Weekly Intelligence
```
You: Weekly report
Hawk: [342 products tracked, 28 changes, margin opportunities, action items]
```

### 4. Sales Diagnosis
```
You: Why did our speaker sales drop?
Hawk: [Shows competitor price timeline, identifies undercutting, recommends response]
```

## Example Output

### Price Alert

```
PRICE ALERT — Competitor Price Drop
Product: Wireless Earbuds Pro X
Your Price: $79.99
Competitor: TechStore.com — Now $64.99 (-23.5%)
RECOMMENDATION: Hold. Flash sale detected. Monitor 48h.
```

### Weekly Summary

```
Weekly Price Intelligence — Mar 10-16
28 changes across 8 competitors
Your position: 3rd cheapest (avg)
Margin opportunities: 12 products
```

## Tips

1. **Start with your top sellers** — monitor what matters most first
2. **Set thresholds per category** — 5% change on electronics, 10% on accessories
3. **Check weekly reports every Monday** — plan pricing adjustments for the week
4. **Use historical data** to spot seasonal patterns before they happen

## Changelog

- **v1.0.0** - Initial release with price tracking
- **v1.1.0** - Weekly reports and trend analysis
- **v1.2.0** - Product matching by UPC and title

## Author

Created by [@openclaw](https://github.com/openclaw)

## License

MIT
