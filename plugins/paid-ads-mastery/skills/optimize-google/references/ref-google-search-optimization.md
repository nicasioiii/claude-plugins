---
title: Google Search Campaign Optimization
skill: optimize-google
usage: Load when user asks about Search campaign performance, needs Quality Score improvement, asks about bidding strategy progression, or needs negative keyword management guidance.
---

# Google Search Campaign Optimization

## Search Term Report Management

### Frequency by Campaign Maturity
| Campaign Age | Check Frequency |
|---|---|
| First 2-4 weeks | Daily |
| Established (4+ weeks) | Weekly |
| Mature (3+ months) | Bi-weekly |

### What to Exclude
1. **Unrelated terms** -- terms completely irrelevant to your product/service
2. **Too-broad terms** -- single-word or very generic queries that waste budget
3. **High-spend / no-conversion terms** -- terms that have spent 1.5-2x target CPA with zero conversions
4. **High CPC terms** -- terms where CPC makes profitable conversion mathematically impossible

### Negative Keyword Best Practices
- Use **phrase match negatives** to block entire categories of irrelevant terms
- Create **negative keyword lists** to apply across multiple campaigns
- Review and update negatives monthly -- search behavior evolves
- Do NOT over-negate: sometimes a surprising term converts; check conversion data before excluding

---

## Quality Score Optimization Playbook

### Quality Score Components (1-10 Scale)
1. **Expected Click-Through Rate** (most weight) -- are people clicking your ad?
2. **Ad Relevance** -- does ad match the query intent? Keywords in the copy?
3. **Landing Page Experience** -- page speed, content relevance, keyword alignment

### Quality Score Targets
| Score | Status | Action |
|---|---|---|
| 8-10 | Excellent | Maintain; minor optimization only |
| 7 | Good | Target level; address any below-average components |
| 5-6 | Below average | Actively optimize; paying more than necessary |
| 1-4 | Poor | Urgent fix required; significantly overpaying |

### CPC Impact of Quality Score
**Formula:** Actual CPC = (Ad Rank below you / Your Quality Score) + $0.01
- Position 1 with QS 10 might pay $1.61
- Position 2 with QS 4 might pay $3.01
- Higher QS = lower CPC for the same position

### Prioritization Formula
**Priority Score = (10 - Quality Score) x Impressions**
Sort descending. Work on the highest-priority keyword/ad group first.
Fix ONE theme, validate, replicate. Never work on dozens simultaneously.

---

## Three-Phase Sequential Quality Score Process

### Phase 1: Ad Relevance (Fix First)
**If Ad Relevance = Below Average --> STOP. Fix this before anything else.**

Root cause: structural misalignment between keywords and ad copy.

**Ad Relevance SOP:**
1. Check if target keyword appears in at least one headline
2. Check if keyword intent matches ad messaging
3. Review ad group structure -- are keywords too diverse for one ad?
4. If ad group has >20 keywords with varied intent, split into tighter groups
5. Ensure ad copy speaks to the specific search intent, not generic benefits

**Timeline:** 7-14 days for Google to reassess after changes.

### Phase 2: Expected CTR (Fix Second)
**If Expected CTR = Below Average --> Fix after Ad Relevance passes.**

Root cause: ad copy is not compelling enough to earn clicks.

**Expected CTR SOP:**
1. Strengthen calls to action (be specific: "Get Free Quote Today" not "Learn More")
2. Add value propositions that differentiate from competitors
3. Include social proof in headlines ("Trusted by 10K+ Customers")
4. Use all available ad extensions (sitelinks, callouts, structured snippets, images)
5. Test emotional vs. rational messaging approaches
6. Ensure headlines are benefit-focused, not feature-focused

**Timeline:** 7-21 days for Google to reassess.

### Phase 3: Landing Page Experience (Fix Third)
**If Landing Page Experience = Below Average --> Fix after CTR passes.**

Root cause: page does not deliver on the ad's promise.

**Landing Page Experience SOP:**
1. Check page load speed (use PageSpeed Insights -- target under 3 seconds)
2. Verify mobile-friendliness (most Google traffic is mobile)
3. Ensure headline matches ad copy (message match)
4. Verify Core Web Vitals pass (LCP, FID, CLS)
5. Check that conversion action is obvious above the fold
6. Confirm content directly addresses the search intent
7. Google uses conversion rate as a proxy for good LPE -- if CVR is high, LPE should be fine

**Timeline:** 14-30 days for Google to reassess.

### Definition of Done
- All three QS components = Average or Above Average
- Quality Score >= 7/10 (stable for 14+ days)
- CPC stabilized or decreased
- Impression Share (Rank) improved without bid inflation

---

## Bidding Strategy Progression

### The Progression Path
1. **Start:** Enhanced CPC (Manual CPC + Enhanced option) OR Max Conversions / Max Conversion Value
2. **After 30 conversions in 30 days:** Switch to Target CPA or Target ROAS
3. **Set initial target** close to what campaign is already achieving
4. **Optimize gradually:** 10% adjustments, 1-2 times per week (never more than 20% at once)

### When to Use Target CPA vs. Target ROAS
| Scenario | Bid Strategy | Why |
|---|---|---|
| High LTV, repeat purchases | Target CPA | Get more customers cheaply; LTV justifies aggressive CPA |
| Low LTV, one-time purchases | Target ROAS | Need profitability on each transaction |
| Lead generation | Target CPA (then VBB) | Volume first, then optimize for value |
| E-commerce, varying margins | Target ROAS (then POAS) | Revenue first, then optimize for profit |

### Manual CPC Still Valid For
- Brand campaigns (often outperforms automated)
- Very low volume accounts where smart bidding cannot learn
- New campaigns with zero historical data
- Highly controlled experiments

### Portfolio Bid Strategies
- Combine multiple campaigns to share conversion data
- Useful when individual campaigns cannot hit the 50 conversion/month threshold
- Smart bidding learns across the combined dataset

---

## RSA Optimization

### Key Principle: 6-8 Headlines, NOT 15
- 15-headline RSA = up to 2,730 three-headline combinations
- Most ad groups never accumulate enough impressions for Google to learn
- Limit to 6-8 headlines for faster learning and cleaner data

### Asset Performance Analysis
- DO NOT use Google's "Low/Good/Best" labels as primary metric (they are CTR-driven)
- Calculate CPI (Conversions Per Impression) or RPI (Revenue Per Impression) manually
- Identify "Silent Killers": high impression share but low conversion rate -- remove these first

### The Iteration Loop
1. **Templatize:** Create RSA template with consistent headline type assignments
2. **Aggregate:** Pull performance data across ad group clusters
3. **Diagnose:** Plot assets on performance quadrants (Winners / Hidden Gems / Silent Killers / Underperformers)
4. **Iterate:** Replace underperformers, scale winners, test new variations

---

## Search Campaign Optimization Checklist

### Weekly Tasks
- [ ] Review search term report, add negatives
- [ ] Check Quality Score trends on top keywords
- [ ] Monitor bid strategy performance (actual CPA/ROAS vs. target)
- [ ] Review RSA asset performance ratings
- [ ] Check impression share lost (budget vs. rank)

### Bi-Weekly Tasks
- [ ] Pause high-spend / low-conversion keywords
- [ ] Break underperforming keywords into own ad groups for targeted optimization
- [ ] Review close variant matching (exact match now behaves like phrase match)
- [ ] Adjust bid targets by 5-10% if needed

### Monthly Tasks
- [ ] Full Quality Score audit
- [ ] Negative keyword list review and expansion
- [ ] Ad copy refresh (test new messaging angles)
- [ ] Landing page alignment check
- [ ] Competitor ad review
