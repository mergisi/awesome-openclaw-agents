---
name: model-cost-compare
description: Trigger when the user asks which model to use, wants to compare model costs, says "what's cheapest for this task", "should I use Opus or Sonnet", "can a smaller model handle this", or "/model-cost-compare". Estimates token cost across Opus 4.6, Sonnet 4.6, GLM-5.1, Minimax M3, and local Gemma 4, then recommends the cheapest model capable of the task.
---

# Model Cost Compare

Given a task description (and optionally a rough prompt / input size), estimate the cost of running it on each available model tier and recommend the cheapest one that can actually do the job.

## When to use

- "Which model should I use for X?"
- "Is it worth running this on Opus or will Sonnet do?"
- "Can I offload this to a local model?"
- "/model-cost-compare — classify 10k support tickets"

## Pricing table (indicative — always flag as "check provider docs")

Use these rough figures. They are **not** exact; confirm before quoting real numbers to the user.

| Model | Tier | Input ($/1M tok) | Output ($/1M tok) | Context | Strengths |
|---|---|---|---|---|---|
| Opus 4.6 (1M) | Frontier | ~$15 | ~$75 | 1M | Agentic, long-context, hard reasoning |
| Sonnet 4.6 | Mid | ~$3 | ~$15 | 400k | Everyday coding, agents, drafting |
| GLM-5.1 | Budget hosted | ~$0.60 | ~$2.20 | 256k | Cheap bulk work, decent reasoning |
| Minimax M3 | Budget hosted | ~$0.60 | ~$2.40 | 512k | Agentic SWE, long-context, image input |
| Gemma 4 (local) | On device | $0 marginal | $0 marginal | 32k | Free but slow, weak at multi-step logic |

> Indicative pricing as of OpenClaw 2026.4.11. Check the provider docs before billing decisions.

## Instructions

1. Parse the user's task. Extract:
   - **Task type:** reasoning, extraction, classification, drafting, translation, agentic tool use, long-context synthesis.
   - **Input size estimate:** in tokens. If the user says "10k tickets averaging 500 tokens", that's 5M input tokens. If unknown, ask for a rough size.
   - **Output size estimate:** short label? full essay? JSON record?
   - **Volume:** one-off or batch?
2. Rule out incapable models. Use this capability floor:
   - Agentic multi-tool flows with long reasoning → Opus or Sonnet only.
   - Structured extraction / classification with clear schema → any tier, including Gemma 4 local.
   - Long-context synthesis (>400k tokens) → Opus only.
   - Privacy-sensitive data that cannot leave the machine → Gemma 4 local only.
3. For each surviving model, compute:
   ```
   cost = (input_tokens / 1_000_000) * input_price
        + (output_tokens / 1_000_000) * output_price
   ```
   Multiply by volume. Show your arithmetic so the user can sanity-check.
4. Print the comparison as a Markdown table sorted cheapest first. Bold the recommended row.
5. End with a one-line recommendation: `Recommended: <model> — <1-sentence reason>`.

## Output example

Input: "Classify 10,000 customer support emails into 5 categories. Avg 400 input tokens, 20 output tokens."

```
Total tokens: 4M input, 200k output

| Model       | Input cost | Output cost | Total   | Capable? |
|-------------|-----------:|------------:|--------:|---------:|
| **Gemma 4** |     $0.00  |      $0.00  |  $0.00  |   yes    |
| Minimax M3  |     $2.40  |      $0.48  |  $2.88  |   yes    |
| GLM-5.1     |     $2.40  |      $0.44  |  $2.84  |   yes    |
| Sonnet 4.6  |    $12.00  |      $3.00  | $15.00  |   yes    |
| Opus 4.6    |    $60.00  |     $15.00  | $75.00  |   overkill |

Recommended: Gemma 4 local — classification with a fixed 5-label schema is trivial for on-device models and costs nothing.
```

## Anti-patterns

- Don't recommend Opus by default "just to be safe". If Sonnet can do it, say so.
- Don't recommend a local model for agentic tool-use loops — they spiral.
- Always flag prices as approximate.

## Example invocations

- `/model-cost-compare classify 10k support tickets into 5 buckets`
- "What's the cheapest model that can draft 200 SEO meta descriptions a day?"
- "Should I use Opus or Sonnet for this 800k-token codebase review?"
