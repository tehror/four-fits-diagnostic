# Four Fits Growth Diagnostic

A Claude Code skill for diagnosing which of Brian Balfour's Four Fits are working and which are broken. Built for the [Agent Skills](https://skills.sh) ecosystem.

## Install

```bash
npx skills add tehror/four-fits-diagnostic
```

Or install directly to a specific agent:

```bash
npx skills add tehror/four-fits-diagnostic -a claude-code
```

## What This Skill Does

[Brian Balfour](https://brianbalfour.com) (founder of Reforge, ex-VP of Growth at HubSpot) argued that Product Market Fit is not enough. You need four fits aligned to build a sustainable, high-growth company:

| Fit | The Question |
|---|---|
| **Market <> Product** | Are you solving a problem people are actively trying to fix, or one they just tolerate? |
| **Product <> Channel** | Does your product naturally spread through your acquisition channel, or are you forcing it? |
| **Channel <> Model** | Can your revenue per customer pay for how you're acquiring them? |
| **Model <> Market** | Is your market large enough to support your pricing model at the volume you need? |

This skill turns that framework into an interactive diagnostic. Once activated, it will:

1. Ask for your website URL and scrape it automatically to pre-populate context
2. Ask targeted gap-fill questions (retention, CAC, LTV, growth trend)
3. Run a meta question about recent changes — the most common root cause of a broken fit
4. Score each fit Green / Yellow / Red
5. Name the primary bottleneck with prioritized next steps and downstream risks

## When It Activates

The skill activates when you say things like:
- "Why isn't my product growing?"
- "Run a four fits diagnostic"
- "Our CAC is too high"
- "We have PMF but growth is stalling"
- "Audit our go-to-market strategy"

## Structure

```
skills/
└── four-fits/
    └── SKILL.md
```

## Sources

- Brian Balfour, ["Why Product Market Fit Isn't Enough"](https://brianbalfour.com/essays/product-market-fit-isnt-enough)
- Brian Balfour, [Four Fits Framework Overview](https://brianbalfour.com/four-fits-growth-framework)
- Reforge Blog, ["The Four Fits: A Growth Framework for the AI Era"](https://www.reforge.com/blog/four-fits-growth-framework)

## License

MIT
