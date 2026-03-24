---
title: Meta Attribution & Third-Party Tracking
skill: optimize-meta
usage: Load when user asks about post-iOS attribution, evaluates third-party tools (Triple Whale, Hyros, Northbeam), asks about view-through vs click-through attribution, or needs the reporting correlation method.
---

# Meta Attribution & Third-Party Tracking

## Post-iOS Attribution Reality

### Current Attribution Windows
| Setting | Window | Notes |
|---|---|---|
| **Standard (post-iOS)** | 7-day click, 1-day view | Default for all campaigns |
| **Pre-iOS (historical)** | 28-day click, 28-day view | No longer available; much more data was captured |

### Impact of Shorter Windows
- Campaigns have less time to accumulate optimization data
- Products with longer consideration periods lose more attributed conversions
- Learning phase is harder to exit (50 events in 7 days vs. 28 days)
- High-ticket products ($500+ CPA) are disproportionately affected

---

## Third-Party Tracking Tools

### The Major Players
| Tool | Strengths | Price Range |
|---|---|---|
| **Triple Whale** | LTV analysis, cross-channel attribution, first-party data | $$$ |
| **Hyros** | Call tracking, long-form funnel attribution | $$$ |
| **Northbeam** | Multi-touch attribution models, media mix modeling | $$$$ |
| **Google Analytics 4** | Free, cross-channel view, event-based | Free |

### What Third-Party Tools ARE Good For
- Lifetime value analysis across channels
- Understanding true attribution beyond platform self-reporting
- Business intelligence and cross-channel reporting
- Comparing platform-reported ROAS to actual business results
- Identifying which channels contribute to the customer journey

### What Third-Party Tools Are NOT Good For

**Optimization decisions.**

This is a critical distinction. Third-party events go to the PIXEL (for targeting/training) but NOT to the ad set's optimization event.

- If Triple Whale shows 5 sales but Ads Manager shows 2, **optimize based on 2** (what Facebook sees)
- Facebook optimizes campaigns using what IT reports, not what third parties report
- Making optimization decisions based on third-party data = gambling

**Quote from practitioner:** "I need to see what Facebook sees, because Facebook uses what IT sees for optimization."

### The Over-Reporting Problem
Despite claiming to "solve iOS," third-party tools do NOT solve the optimization data gap. They only help with reporting and analytics. The data they capture does not flow back to Meta's optimization engine.

---

## View-Through Attribution Caution

### The 30%+ Over-Report Issue
- View-through attribution (1-day view) credits Meta when someone SAW your ad and purchased within 24 hours
- This inflates reported ROAS by 30% or more in many accounts
- Someone may have seen your ad on Facebook but purchased because of a Google Search ad, email, or organic visit
- Meta still claims that conversion

### When View-Through is Legitimate
- Brand awareness campaigns where ad view genuinely influenced the purchase
- Retargeting campaigns where the reminder drove action
- Short purchase cycles (impulse products under $50)

### When View-Through is Misleading
- High-ticket products with long consideration periods
- Products where customers actively comparison-shop (Google Search first)
- Accounts with strong organic/email channels that would capture the sale regardless

### Recommendation
- Track both 7-day click and 1-day view separately
- For optimization decisions, weight click-through attribution more heavily
- For business reporting, acknowledge the view-through contribution but discount it

---

## The Reporting Correlation Method

### The Concept
Find the consistent ratio between what Meta Ads Manager reports and what your bank account shows. Use this ratio for all forward-looking decisions.

### How to Calculate
1. Pull Ads Manager ROAS for last 30 days
2. Pull actual revenue (bank/Shopify/payment processor) for same 30 days
3. Calculate actual ROAS: total revenue / total ad spend
4. Find the ratio: Ads Manager ROAS / Actual ROAS

### Example
| Source | Revenue | Spend | ROAS |
|---|---|---|---|
| Ads Manager | $18,000 | $10,000 | 1.8x |
| Bank Account | $30,000 | $10,000 | 3.0x |
| **Ratio** | | | 1.8 / 3.0 = **0.6x** |

In this example, Ads Manager reports 60% of actual ROAS.

### How to Use the Ratio
- To achieve 3.5x actual ROAS, target 3.5 x 0.6 = 2.1x in Ads Manager
- To hit break-even (1.6x actual), target 1.6 x 0.6 = 0.96x in Ads Manager
- **Optimize campaigns based on Ads Manager numbers** (what Facebook sees)
- **Evaluate BUSINESS based on actual numbers** (what the bank sees)

### Important Notes
- This ratio differs by account, country, and product
- Recalculate monthly as it can shift with seasonal patterns
- The ratio tends to be more favorable (higher actual vs. reported) for:
  - Accounts with strong organic traffic
  - Products with high repeat purchase rates
  - Accounts running email/SMS alongside paid ads

---

## Cross-Channel Attribution Problem

### The Double-Counting Issue
If you add all conversion value from all platforms, the total will EXCEED actual revenue:
- Meta takes credit for a sale
- Google takes credit for the same sale (user searched brand name after seeing Meta ad)
- Email takes credit for the same sale (user clicked email before purchasing)

### Solutions
1. **Third-party attribution tool** as single source of truth (Northbeam, Triple Whale)
2. **MER (Media Efficiency Ratio):** Total revenue / Total ad spend across all channels
3. **Blended ROAS:** Evaluate at the business level, not platform level
4. **Incrementality testing:** Turn off a channel for a set period, measure the actual revenue impact

### The MER Approach
- MER = Total Business Revenue / Total Marketing Spend (all channels)
- If MER is above your blended break-even target, marketing is profitable
- Do not obsess over individual channel ROAS -- optimize the portfolio
- Example: Meta shows 2x ROAS, Google shows 5x ROAS, MER is 3.5x = healthy overall

---

## Attribution Model Comparison

| Model | How It Works | Bias |
|---|---|---|
| **Last click** | 100% credit to last ad clicked | Over-credits bottom-funnel (brand search, retargeting) |
| **First click** | 100% credit to first ad clicked | Over-credits top-funnel (discovery campaigns) |
| **Linear** | Equal credit across all touchpoints | No differentiation between impactful and trivial touches |
| **Time decay** | More credit to recent touches | Similar to last-click bias but softer |
| **Position-based** | 40% first, 40% last, 20% middle | Better balance but arbitrary weighting |
| **Data-driven** | Uses ML to determine influence | Best option but requires significant data volume |

**Analogy:** Last click attribution is like blaming the tequila shot for your hangover while ignoring the 12 beers. It ignores everything that came before.

---

## Never Exclude Past Customers (Attribution Implications)

### Why This Matters for Attribution
- Excluding past customers removes the BEST data from your optimization chain
- A loyal repeat buyer provides better data for finding new similar customers than a first-time buyer
- iOS made this worse: less data + excluding customers = even less data for optimization

### The Case Study Proof
Same creatives, same targeting:
- Campaigns WITH exclusions: 2x+ higher cost per purchase
- Campaigns WITHOUT exclusions: dramatically better results
- Even in ASC campaigns, Meta ignores the "existing customer budget cap" setting and spends on existing customers anyway -- because Meta WANTS that data for optimization

### Exception
- If you sell a one-time product that can NEVER be repurchased, exclude purchases
- But NEVER exclude traffic or social media engagers -- that data is always valuable
