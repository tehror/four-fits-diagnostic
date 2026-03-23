# SKILL: Four Fits Growth Diagnostic

## Purpose

Run a structured diagnostic interview to identify which of Brian Balfour's Four Fits are working and which are broken. Balfour developed this framework at HubSpot (as VP of Growth) and turned it into the foundation of Reforge. The core insight: Product Market Fit is not enough. You need all four fits aligned to build a sustainable, high-growth company.

**Source:** Brian Balfour, "Why Product Market Fit Isn't Enough" — https://brianbalfour.com/essays/product-market-fit-isnt-enough

---

## When to Trigger This Skill

Use this skill when the user:
- Asks why their product is not growing despite good retention or user satisfaction
- Wants to audit their go-to-market strategy
- Is hitting a growth plateau
- Is confused about which channel, pricing, or market to focus on
- Mentions phrases like "we have PMF but growth is stalling," "our CAC is too high," or "we don't know where to invest next"

---

## The Four Fits (Framework Summary)

The framework has four interconnected fits. Each depends on the others. If one breaks, the whole system struggles.

```
MARKET --> PRODUCT --> CHANNEL --> MODEL --> MARKET (loop)
```

| Fit | The Question | Breaks When... |
|---|---|---|
| **Market <> Product** | Are you solving a problem people are *actively trying to fix*, not just tolerating? | Users churn, NPS is weak, organic referrals are rare, usage is shallow |
| **Product <> Channel** | Does your product naturally spread through the channels you're using, or are you forcing it? | CAC is rising, channel efficiency is falling, the product requires explanation the channel can't give |
| **Channel <> Model** | Can your revenue per customer pay for how you're acquiring them? | LTV/CAC ratio is below 3:1, CAC payback exceeds 12-18 months, you're in the "dead zone" |
| **Model <> Market** | Is your market large enough to support your pricing model at the volume you need? | Total addressable market caps out before you reach target revenue, pricing drives away key segments |

**The "Dead Zone" (Channel-Model):** The most common silent killer. Your price is too high for free/viral channels to work, but too low for expensive paid or outbound channels to be profitable. The product still works. Users like it. But growth flatlines.

---

## Interview Protocol

### Step 1: Gather Product Context

#### 1a: Scrape the Website First

Before asking any questions, ask the user for their website URL. Then use the `web_fetch` tool to retrieve and read the homepage and, if available, the pricing page and about/team page.

**Prompt to user:**
```
Before we dive into questions, share your website URL (and your pricing page URL if it's separate).
I'll read them first so you don't have to explain the basics.
```

**What to extract from the website:**
- Product category and core value proposition (what problem does it claim to solve?)
- Target customer (who is the messaging written for?)
- Pricing model and tiers (if pricing page is public)
- Key differentiators or positioning language
- Any social proof signals: customer logos, testimonials, case studies, G2/Capterra badges
- Distribution signals: "Free trial," "Request a demo," "Get started free," "Talk to sales" — these reveal the intended acquisition motion

**After scraping, confirm your read with the user:**
```
Based on your site, here's what I'm working with:
- Product: [summary]
- Target customer: [who]
- Pricing model: [what you found, or "not public"]
- Acquisition motion: [self-serve / sales-led / hybrid, based on CTA language]

Correct anything I got wrong, then we'll fill in the gaps I couldn't get from the site.
```

This confirmation step is important. Websites often lag behind reality — the pricing page may be outdated, the ICP may have shifted, or the CTA may not reflect actual acquisition strategy.

---

#### 1b: Fill the Gaps with Direct Questions

After scraping and confirming, ask only for what the website couldn't answer. Prompt gently — not all users will have all of this.

```
Now fill in what I couldn't get from your site:

1. What is your average revenue per customer? (MRR or ACV per account)
2. What does your retention look like? (Churn rate, D30/D90 retention, NPS if known)
3. What is your approximate CAC (cost to acquire a customer)?
4. How large is your current customer base or DAU/MAU?
5. What does your growth curve look like over the past 6 months? (Flat, growing, spikey, declining)
6. What is your estimated total addressable market?
7. What changed recently? (New pricing, new channel, new market, new competitor, new leadership)
   This is the most important question. If something shifted in the last 6-12 months, say what it was.

Share whatever you have. Rough numbers and gut reads are fine.
```

**Note on question 7 (the meta question):** This is not optional. Fits break when something changes, and teams often don't connect the change to the symptom. A pricing increase, a channel shift, a move upmarket, or a new competitor can silently break Channel-Model or Model-Market fit while the product itself looks fine. If the user skips this, ask it directly before moving to the diagnostic.

---

### Step 2: Run the Four Fits Diagnostic

After gathering context, work through each fit in order. For each one:
- Ask the one core diagnostic question
- Probe with 2-3 follow-up questions
- Assign a status: **Green (working)**, **Yellow (shaky)**, or **Red (broken)**
- Note the evidence

Do not skip fits even if one seems obviously broken. All four interact.

---

#### Fit 1: Market <> Product

**Core question:** Are you solving a problem people are actively trying to fix, or one they just tolerate?

**Probe questions:**
- When users stop using your product, what do they say? What do they switch to, or do they just go back to doing it manually?
- Do new users find you, or do you have to find them?
- When you ask your best users "what would happen if this product disappeared tomorrow?" — what do they say?
- Is your NPS or retention curve flattening to a meaningful floor, or continuing to decline?

**Green signals:**
- Strong NPS (50+), unprompted referrals, users describe the product as essential
- Retention curve flattens (not trending to zero)
- Direct/organic traffic is a meaningful share of acquisition
- Users switch from a worse alternative, not from "nothing"

**Yellow signals:**
- NPS is neutral (20-40), occasional churn, users engaged but not evangelizing
- Retention declining slowly
- Growth exists but is fragile or channel-dependent

**Red signals:**
- NPS is low or volatile, high churn
- Users say "it's nice to have" or "we stopped using it after the trial"
- Growth only happens with active push (campaigns, discounts, sales calls)
- Users can't clearly articulate what problem it solves

---

#### Fit 2: Product <> Channel

**Core question:** Does your product naturally spread through the channel you're relying on, or are you forcing it?

**Probe questions:**
- What is your primary acquisition channel today? How did you choose it?
- Does your product have a short time-to-value (minutes/hours vs. days/weeks)?
- Do your users have a natural reason to share or invite others?
- Is your product complex enough that it needs a human to explain it, or can it be understood from a landing page?
- Are your channel metrics (CTR, conversion rate, CAC) getting better, flat, or worse over time?

**Channel-Product fit rules of thumb:**
- **Viral/Product-Led:** Works when product has quick time-to-value, broad value proposition, network effect, and low friction to share. (Slack, Dropbox, Figma)
- **Content/SEO:** Works when buyers research before buying, problem is well-defined and searchable, trust matters. (HubSpot, Moz)
- **Paid Acquisition:** Works when LTV is high enough to absorb CAC, market is large and targetable, conversion funnel is tight.
- **Outbound/Sales:** Works when ACV is $5K+, buyers are identifiable, and the problem requires a consultative sale.
- **Partnerships:** Works when partner already has the customer relationship and your product extends their value.

**Green signals:**
- Channel efficiency is improving or stable
- The channel matches the product's natural distribution behavior
- CAC is not rising faster than LTV

**Yellow signals:**
- Channel works but is expensive or fragile (single-channel dependency)
- Product requires more explanation than the channel allows
- Experimenting with multiple channels without a clear winner

**Red signals:**
- Primary channel CAC is rising with no sign of improvement
- Product requires demos/calls to convert but you're relying on self-serve
- Virality is hoped for but not designed into the product

---

#### Fit 3: Channel <> Model

**Core question:** Can your revenue per customer pay for how you're acquiring them?

**This is the most common silent killer.** The product works. Users like it. But growth flatlines because the math doesn't close.

**Probe questions:**
- What is your CAC in your primary channel?
- What is your LTV (or best estimate)?
- What is your CAC payback period? (CAC / monthly gross margin per customer)
- If you use a freemium model, what is your free-to-paid conversion rate?
- If you use outbound/sales, what is your ACV?

**The Dead Zone diagnostic:**
- Price is too high for free/viral channels to work efficiently (usually >$25-50/month consumer, >$200/month SMB)
- Price is too low to support paid acquisition or an outbound sales team (usually <$500-1,000 ACV for sales, <$50 LTV for paid)
- If both are true simultaneously: you are in the dead zone.

**Benchmarks to apply:**
- LTV/CAC ratio: 3:1 or better = healthy. Below 2:1 = warning. Below 1:1 = critical.
- CAC payback period: Under 12 months = good. 12-18 months = watch carefully. Over 18 months = investigate.
- Freemium conversion: 2-5% is typical. Below 1% may indicate a model-channel mismatch.

**Green signals:**
- LTV/CAC > 3:1, payback under 12 months
- Model matches channel cost structure
- Freemium converts at meaningful rate, or sales team closes at sufficient ACV

**Yellow signals:**
- LTV/CAC between 2-3:1, payback 12-18 months
- Model works but is fragile to price changes or CAC increases
- Channel efficiency declining, narrowing the margin

**Red signals:**
- LTV/CAC below 2:1 or you don't know what it is
- CAC payback exceeds 18 months
- Freemium converts below 1% or sales team closes deals below their cost to operate
- You're stuck between channels: too expensive for free, too cheap for paid

---

#### Fit 4: Model <> Market

**Core question:** Is your market large enough to support your pricing model at the volume you need?

**Probe questions:**
- What is your best estimate of the total addressable market (number of potential customers)?
- At your current pricing, how many customers would you need to hit your revenue target?
- Does your pricing reflect what your best customers perceive the value to be, or was it set based on cost or competition?
- Are there segments of your market that can't afford your pricing? Are there segments where your pricing feels cheap?
- Is your market growing, flat, or shrinking?

**The math test:**
```
Revenue Target / ACV = Customers Needed
Customers Needed / TAM = % of Market Required
```
If you need more than 5-10% of a defined market to hit your target, your market may be too small or your price too low.

**Example (from Balfour's SaaS analysis):**
- Marketo: Enterprise, high ACV, outbound sales, small addressable count but high revenue per customer
- HubSpot: Mid-market, medium ACV, content + inside sales, larger pool, sustainable math
- Mailchimp: SMB/Consumer, freemium/low ACV, virality, massive volume required — only works because TAM is enormous

**Green signals:**
- Math works: TAM * reasonable penetration rate > revenue target
- Pricing feels like fair value to customers (not a discount, not a stretch)
- Market is growing and your pricing model scales with it

**Yellow signals:**
- Market is defined but penetration math is tight
- Pricing is under pressure from competitors
- Customers push back on price but still buy

**Red signals:**
- Market is too small for your model to hit scale
- Pricing is misaligned with perceived value (too high = churn, too low = can't reinvest in growth)
- Niche market with no expansion path

---

#### Meta Question: Have the Fits Recently Changed?

Run this before synthesis. It often unlocks the diagnosis faster than any metrics.

**Ask:**
- Has anything changed in the last 6-12 months? (Pricing, channel strategy, target market, team structure, competitive landscape)
- If yes: what changed, and when did you first notice growth being affected?

**Why this matters:**

Balfour's core point is that the fits are always evolving, and when one breaks you cannot simply change one element. You have to revisit all four. But teams rarely connect the change to the symptom because there's a lag — a pricing change in Q1 may not show up in CAC or churn data until Q3.

**Common change-to-symptom patterns to watch for:**

| What Changed | Fit Most Likely Broken | Symptom That Shows Up Later |
|---|---|---|
| Raised prices | Channel <> Model | CAC payback extends, conversion drops |
| Moved upmarket (SMB to Mid-Market) | Product <> Channel + Model <> Market | Self-serve stops working, sales cycle lengthens |
| Shifted primary channel (e.g., SEO to paid) | Channel <> Model | CAC spikes, payback period explodes |
| Added a new product line | Market <> Product | Messaging confusion, ICP fragmentation |
| New well-funded competitor enters | Model <> Market | Pricing pressure, TAM effectively shrinks |
| Lost a key distribution partner | Product <> Channel | Growth flatlines despite good retention |

If the user identifies a recent change, map it to the table above and prioritize that fit in the diagnostic. The other fits may be fine — or they may have been destabilized downstream. Check them all anyway.

---


After completing all four fits, produce a summary in this format:

```
FOUR FITS DIAGNOSTIC SUMMARY
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Fit 1: Market <> Product       [GREEN / YELLOW / RED]
Fit 2: Product <> Channel      [GREEN / YELLOW / RED]
Fit 3: Channel <> Model        [GREEN / YELLOW / RED]
Fit 4: Model <> Market         [GREEN / YELLOW / RED]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

LIKELY BOTTLENECK: [name the primary broken fit and explain why]

WHY IT MATTERS NOW: [connect this to the symptoms the user described]

WHAT TO INVESTIGATE FIRST: [2-3 concrete, prioritized actions]

WATCH OUT FOR: [one downstream fit that may break if you fix the primary one incorrectly]
```

---

### Step 4: Deliver Action Priorities

After the summary, provide prioritized next steps. Frame them as experiments or questions to answer, not directives. The fits evolve — you cannot fix one in isolation without revisiting the others.

**Prioritization rules:**
1. Fix Market <> Product first. If users don't need it, nothing else works.
2. Fix Product <> Channel second. If the channel can't distribute the product, growth never compounds.
3. Fix Channel <> Model third. If the math doesn't close, growth burns cash until it stops.
4. Model <> Market is often a strategic reset — address it if the first three are green but you're still capped.

---

## Key Principles to Apply Throughout

- **Market first, product second.** Balfour deliberately flips "Product Market Fit" to "Market Product Fit." The problem exists before the product does. Starting with the product is putting the cart before the horse.
- **Channels do not mold to products. Products are built to fit channels.** You cannot force a product through a channel that doesn't match its natural distribution behavior.
- **The fits are always evolving.** When one breaks, you cannot change just one element. You have to revisit all four.
- **All four fits influence each other.** A price change affects Channel-Model fit. A channel change affects Product-Channel fit. Never diagnose in isolation.
- **The product death cycle is a symptom, not a cause.** Feature launches that produce spikes followed by flatlines usually indicate a broken Channel or Model fit, not a product problem.

---

## Reference: Balfour's Email Marketing Comparison

This table from Balfour's SaaS talk illustrates how all four fits must align — and how three $2B+ companies can serve the same category with completely different configurations:

| Company | Product | Market | Model | Channel |
|---|---|---|---|---|
| Marketo | Heavily customizable email | Enterprise | High ACV | Outbound sales |
| HubSpot | All-in-one email | Mid-market | Medium ACV | Content + inside sales |
| Mailchimp | Simple, touchless email | SMB/Consumer | Freemium, low ACV | Virality |

None of these configurations is universally "better." Each works because the four fits are internally consistent.

---

## Sources

- Brian Balfour, "Why Product Market Fit Isn't Enough" — https://brianbalfour.com/essays/product-market-fit-isnt-enough
- Brian Balfour, Four Fits Framework Overview — https://brianbalfour.com/four-fits-growth-framework
- Reforge Blog, "The Four Fits: A Growth Framework for the AI Era" — https://www.reforge.com/blog/four-fits-growth-framework
- Brian Balfour at SaaSFest 2016 (slides) — Channel-Model dead zone illustration
