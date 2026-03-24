---
name: Google Campaign Optimization & Diagnostics
description: |
  MANDATORY TRIGGERS: User asks about Google Ads optimization, Shopping optimization, Search term reports, Quality Score, PMax optimization, Google bidding adjustments, POAS vs ROAS, break-even ROAS calculation, bottleneck analysis, Google campaign diagnostics, or unit economics for ads.
  FOR: Day-to-day Google campaign management, Shopping product/keyword optimization (7-14 day cycles), Search term report management, Quality Score optimization (3-phase sequential), PMax optimization levers, bidding strategy adjustments, bottleneck analysis, POAS implementation, and unit economics validation.
  Do NOT use for: Meta/Facebook campaign optimization (use optimize-meta). Initial Google campaign setup or structure (use strategy-google-ads). Google account or Merchant Center setup (use setup-google-ads). Creative testing methodology (use test-creative).
---

# Google Campaign Optimization & Diagnostics

## When to Read Reference Files

Load `ref-google-shopping-optimization.md` when:
- User asks about Shopping campaign performance
- User needs product-level or keyword-level optimization
- User asks about Shopping CTR targets or feed optimization

Load `ref-google-search-optimization.md` when:
- User asks about Search campaign performance
- User needs Quality Score improvement guidance
- User asks about bidding strategy progression or negative keywords

Load `ref-google-pmax-optimization.md` when:
- User asks about PMax campaign performance
- User needs PMax optimization levers or asset performance analysis
- User asks about brand exclusion or PMax scaling

Load `ref-google-unit-economics.md` when:
- User asks about break-even ROAS, POAS, or profitability
- User needs unit economics calculations (e-commerce, lead gen, or SaaS)
- User asks about bottleneck analysis or value-based bidding

---

## Universal Google Ads Optimization Principles

### The 30/30 Threshold
Switch from starter bidding (Enhanced CPC / Max Conversions) to Target CPA or Target ROAS after:
- **30 conversions in 30 days** per campaign
- Set initial target close to current performance
- Adjust gradually: no more than 20% change per week (recommended: 10% increments, 1-2x per week)

### The 20% Adjustment Rule
- Never change bids or targets by more than 20% at once
- Recommended cadence: 10% adjustments, 1-2 times per week
- Larger changes disrupt smart bidding's learned patterns
- This applies to: Target CPA, Target ROAS, manual bids, budgets

### Budget as Fuel, Bids as Steering Wheel
- Limited budget + High bids = Limited reach but premium positions (overpaying per click)
- High budget + Low bids = High reach potential but poor positioning (budget will not fully spend)
- Balanced approach = Optimal reach + optimal positioning

---

## Quick Diagnostic: Where Is the Problem?

### The Conversion Chain (Bottleneck Analysis)

```
Impressions --> Clicks --> Leads/Sales --> Revenue --> Profit
     |              |           |              |          |
    CTR           CVR      Close Rate    Deal Value   Margins
```

Output is always limited by the WEAKEST LINK in the chain. Identify which link is broken before optimizing.

| Bottleneck | Metric to Check | Solution Area |
|---|---|---|
| Not enough impressions | Impression Share, Search IS Lost (Budget/Rank) | Increase budget or bids |
| Impressions but no clicks | CTR | Improve ad copy, headlines, extensions |
| Clicks but no conversions | Conversion Rate | Fix landing page or offer |
| Conversions but not profitable | CPA / ROAS | Improve unit economics or bidding |
| Profitable but cannot scale | Budget, bid limits | Increase budget, test new campaigns |

---

## Shopping Optimization Quick Reference

### Optimization Frequency: Every 7-14 Days ONLY
- Never more frequently -- each optimization restarts campaign learning
- Expect results to tank for 2-3 days after any optimization
- Look at data for the 7-14 day window matching your optimization cycle

### Product Optimization Priority Order
1. **Exclude high-spend, zero-sale products** (spent 1.5-3x profit margin with no conversions)
2. **Exclude zero-click, high-impression products** (500+ impressions, zero clicks)
3. **Fix low-CTR products** (below 0.10-0.25%) via image > pricing > title changes
4. **Never touch products WITH sales** regardless of CTR

### Campaign CTR Target: 1%+
Below 1% = quality score drops, CPC increases, profitability spiral.

---

## Search Optimization Quick Reference

### Search Term Report Management
- Check DAILY for new campaigns (first 2-4 weeks)
- Check weekly for established campaigns
- Add negative keywords for: unrelated terms, too-broad terms, high spend/no conversion terms

### Quality Score Target: 7+ out of 10
- Below 5: definitely paying too much
- Fix in this order: Ad Relevance first, then Expected CTR, then Landing Page Experience
- **Priority formula:** (10 - Quality Score) x Impressions = Priority Score

---

## PMax Optimization Quick Reference

### 10 Optimization Levers (Despite Black Box)
1. Negative keyword optimization (now available in PMax)
2. Offer optimization
3. Bid/budget adjustments
4. Final URL Expansion (on/off + page feeds)
5. Asset optimization (performance quadrants)
6. Product feed optimization
7. Audience signal / search theme optimization
8. Value Rules optimization
9. New Customer Acquisition Goals
10. Hidden insights via scripts (channel reporting)

### Brand Exclusion is CRITICAL
- Exclude brand traffic from PMax campaigns
- Create separate branded fallback campaigns
- Brand traffic inflates PMax ROAS, hiding real non-brand performance

---

## POAS vs. ROAS

### Why ROAS Alone Fails
- Revenue does NOT equal profit
- Different products have different margins but you bid on one average target
- A 10x ROAS campaign can be near break-even if margins are low
- Cross-selling effects completely ignored by ROAS

### POAS Solution
- Set minimum profit per ad dollar (not revenue per ad dollar)
- Algorithm promotes products based on expected profitability
- Upload gross profit at order level to Google Ads
- Requires: conversion tracking with cart data + COGS import
- Tools: ProfitMetrics, custom implementations

---

## Cross-References

| Condition | Skill to Load |
|---|---|
| Quality Score or structural issues found | `strategy-google-ads` |
| Need to set up or fix conversion tracking | `setup-google-ads` |
| Shopping feed needs technical optimization | `setup-google-ads` |
| Scaling decisions needed | `scale-campaigns` |
| Meta campaigns also running, need cross-channel view | `optimize-meta` |
| Creative testing methodology needed | `test-creative` |
| Need to create new RSA copy or PMax assets | `create-google-assets` |
