# Four Fits Growth Diagnostic — SKILL.md

A structured AI skill for diagnosing which of Brian Balfour's Four Fits are working and which are broken. Built to be used as a SKILL.md file with Claude or any LLM that supports system-level skill injection.

## What This Is

[Brian Balfour](https://brianbalfour.com) (founder of Reforge, ex-VP of Growth at HubSpot) argued that Product Market Fit is not enough. You need four fits aligned to build a sustainable, high-growth company:

| Fit | The Question |
|---|---|
| **Market <> Product** | Are you solving a problem people are actively trying to fix, or one they just tolerate? |
| **Product <> Channel** | Does your product naturally spread through your acquisition channel, or are you forcing it? |
| **Channel <> Model** | Can your revenue per customer pay for how you're acquiring them? |
| **Model <> Market** | Is your market large enough to support your pricing model at the volume you need? |

This skill turns that framework into an interactive diagnostic. It scrapes the user's website, asks targeted intake questions, runs a structured interview across all four fits, and produces a scored summary with a clear bottleneck and prioritized next steps.

## How to Use

Drop `SKILL.md` into your Claude Code project skills folder, or paste it as a system prompt before starting a diagnostic conversation.

**The skill will:**
1. Ask for a website URL and scrape it automatically to pre-populate context
2. Ask targeted gap-fill questions (retention, CAC, LTV, growth trend)
3. Include a meta question about recent changes — the most common root cause of a broken fit
4. Run through all four fits with Green / Yellow / Red scoring
5. Produce a structured diagnosis: bottleneck, evidence, prioritized actions, and downstream risk

## Why the Meta Question Matters

Fits break when something changes. A pricing increase, a channel shift, a move upmarket, or a new competitor can silently break Channel-Model or Model-Market fit while the product looks fine. The meta question surfaces that lag before it becomes invisible.

## Sources

- Brian Balfour, ["Why Product Market Fit Isn't Enough"](https://brianbalfour.com/essays/product-market-fit-isnt-enough)
- Brian Balfour, [Four Fits Framework Overview](https://brianbalfour.com/four-fits-growth-framework)
- Reforge Blog, ["The Four Fits: A Growth Framework for the AI Era"](https://www.reforge.com/blog/four-fits-growth-framework)

## License

MIT — use it, fork it, improve it. If you extend the skill, consider sharing your version.
