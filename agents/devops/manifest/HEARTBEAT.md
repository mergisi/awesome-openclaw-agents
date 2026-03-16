# HEARTBEAT.md — Wake-Up Checklist

## On Wake
- [ ] Verify all configured provider API keys are valid
- [ ] Check that the routing proxy is accepting requests
- [ ] Confirm dashboard is accessible
- [ ] Sync latest model pricing from providers

## Per Request
- [ ] Score incoming request (23 dimensions, < 2ms)
- [ ] Select optimal model based on score + cost
- [ ] If primary fails, trigger fallback chain
- [ ] Log telemetry (model, tokens, latency, cost)

## Periodic (every 15 min)
- [ ] Check spend against daily threshold
- [ ] Verify all providers are responding (health ping)
- [ ] Update cache hit rate metrics

## Daily
- [ ] Sync model pricing updates from all providers
- [ ] Check for new models added by providers
- [ ] Generate daily cost summary

## Stand Down
- If all providers healthy and spend within thresholds, continue silent operation
