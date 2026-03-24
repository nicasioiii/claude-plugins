# Kill vs. Scale Decision Matrix

## Meta Ads - Spend Threshold Method

### Using Spend Milestones to Kill/Scale

**Principle:** Use spend thresholds to make kill/scale decisions, NOT just ROAS (prevents overthinking)

### Campaign Spend <$100 (Early Testing Phase)

**Spend Range:** $0-100
**Decision Framework:**

| Status | Signals | Action |
|--------|---------|--------|
| **Go** | >1 conversion at target CPA | Scale to $200 |
| **Maybe** | 0-1 conversions, low CTR (<1%) | Keep at current spend, wait 2 more days |
| **Kill** | 0 conversions after $100 spend | Kill immediately, replace with new creative |

**Rationale:** $100 spend at $20 CPA = 5 conversions expected. If getting <1, creative isn't resonating.

---

### Campaign Spend $100-300 (Validation Phase)

**Spend Range:** $100-300
**Decision Framework:**

| Status | ROAS | CPA | Hold Rate | Action |
|--------|------|-----|-----------|--------|
| **Scale** | >1.5x breakeven | <$25 target | >10% (video) | Increase to $500/day |
| **Hold** | 1.0-1.5x breakeven | At target | 8-10% | Keep spend, test new copy |
| **Kill** | <1.0x breakeven | >1.5x target | <5% | Kill immediately |

**Rationale:** By $300 spend at $20 CPA, you have ~15 conversions of data. This is enough to make a kill/scale call.

---

### Campaign Spend $300-1,000 (Growth Phase)

**Spend Range:** $300-1,000
**Decision Framework:**

| ROAS Trend | 7-Day ROAS | Action |
|------------|-----------|--------|
| Stable up | >1.8x breakeven | Scale 20% every 3 days |
| Stable | 1.2-1.8x breakeven | Scale 10% every 5 days |
| Declining | Dropping >0.1/day | Pause, refresh creative, relaunch at 50% |
| Crashed | <1.0x breakeven, staying there | Kill campaign entirely |

**Rationale:** At $300-1,000 spend, you have 50-150 conversions. Trends matter more than day-to-day ROAS noise.

---

### Campaign Spend $1,000+ (Mature Phase)

**Spend Range:** $1,000+ daily
**Decision Framework:**

| Metric | Healthy | Yellow | Red |
|--------|---------|--------|-----|
| **7-day ROAS** | >1.5x breakeven | 1.2-1.5x | <1.2x |
| **7-day trend** | Flat ±5% | Declining 5-10% | Declining 10%+ |
| **CPA** | Stable ±8% | Inflating 8-15% | Inflating 15%+ |
| **Frequency** | <2.5x | 2.5-3.5x | >3.5x |

**Actions:**
- **2+ Healthy metrics:** Increase budget 10% OR duplicate campaign
- **1-2 Yellow metrics:** Hold spend, test new hook, reduce frequency
- **2+ Red metrics:** Pause for 48 hours, investigate creative fatigue

---

## Google Ads - Product/Keyword Level Matrix

### Shopping Campaigns - Product Level

**Kill Criteria (Pause Product Immediately):**

1. **Spend 2-3x profit margin with zero conversions**
   - Example: $40 profit margin, spent $100 → Pause
   - Rationale: This product has no demand signal

2. **3+ sales but CPA 3x+ profit margin**
   - Example: $40 profit, 3 sales at $120 CPA → Pause
   - Rationale: Not sustainable even with volume

3. **Spent $500+ with ROAS <1.5**
   - Example: $500 spend, $650 revenue → Pause
   - Rationale: Low quality product or poor images

**Scale Criteria (Increase Bid):**

1. **3+ sales, CPA within 1.5-2.5x profit margin**
   - Example: $40 profit, 3 sales at $50-80 CPA → Increase bid $0.05
   - Rationale: Product works, just needs more visibility

2. **5+ sales, ROAS >3.0**
   - Example: $300 spend, $1,000 revenue → Increase bid $0.10
   - Rationale: Strong product, scale aggressively

3. **10+ sales, stable CPA for 7+ days**
   - Example: Consistent $22 CPA (vs $30 target) → Increase bid $0.10-0.15
   - Rationale: Winner product, maximize volume

---

### Search Campaigns - Keyword Level

**Kill Criteria (Pause Keyword):**

1. **Spent 1x target CPA, zero conversions**
   - Example: $20 target CPA, spent $20 with 0 conversions → Pause
   - Rationale: No conversion intent on this keyword

2. **Quality Score <4 + High CPC**
   - Example: QS 2-3, CPC $2.00+ → Pause
   - Rationale: Algorithm penalizing ad relevance, not worth the cost

3. **5+ clicks, zero conversions**
   - Example: 5 clicks, no sales → Pause
   - Rationale: Traffic but no conversion match

**Scale Criteria (Increase Max CPC):**

1. **1-2 conversions, CPA <target, QS >7**
   - Example: 1 sale, $18 CPA (vs $20 target), QS 8 → Increase bid to $0.80
   - Rationale: Efficient traffic, increase visibility

2. **3+ conversions, ROAS >2.5**
   - Example: 3 sales, ROAS 3.0 → Increase bid $0.10
   - Rationale: Proven winner, scale volume

3. **Stable conversions for 14+ days at target CPA**
   - Example: Consistent conversions at $20 CPA for 2 weeks → Increase bid 15%
   - Rationale: Reliable performer, increase reach

---

## Performance Max Scaling Decision Tree

```
START: Is campaign profitable?
  ├─ NO (ROAS <breakeven) → PAUSE for 7 days
  │    └─ Relaunch: Yes or No?
  │        ├─ Yes → Test new asset group + creative
  │        └─ No → KILL campaign
  │
  └─ YES (ROAS >breakeven)
       ├─ ROAS >2.0x target?
       │    └─ YES → SCALE: Increase budget 20% daily for 5 days
       │         └─ After 5 days, recheck. If still >2.0 → Scale 10% ongoing
       │
       ├─ ROAS 1.5-2.0x target?
       │    └─ YES → HOLD: Keep budget stable, test new assets in parallel campaign
       │         └─ After 7 days, recheck. If same → Keep holding
       │
       └─ ROAS <1.5x target (but >breakeven)?
            └─ ASSESS: Days running?
                 ├─ <14 days → HOLD (still learning)
                 ├─ 14-30 days → TEST new asset group, hold main
                 └─ >30 days → PAUSE, refresh assets, relaunch at 50% budget
```

---

## Creative Rotation Strategy

### When to Replace Winning Creative

**Criteria for Creative Rotation:**

| Days Running | Performance | Action |
|--------------|-------------|--------|
| 0-7 days | ROAS >1.5x breakeven | Keep, don't touch |
| 7-14 days | ROAS >1.5x breakeven | Keep main, start testing variations |
| 14-30 days | ROAS >1.5x breakeven | Keep main, test 2-3 new creatives |
| 30-45 days | ROAS >1.5x breakeven | Start phasing out, have 2-3 backups ready |
| 45-60 days | ROAS still >1.5x breakeven | Rotate out, can still use as control |
| 60+ days | Any performance | Replace entirely (creative fatigue inevitable) |

**Fallback Creative Budget:**
- Keep 20-30% of budget on "proven" creatives that are >30 days old
- Use as performance baseline
- If new creative underperforms, can revert quickly

---

## Account-Level Kill/Scale Gates

### Meta Account Spending >$10,000/month

**Gate 1: Account Quality Score**
- Must be "Good" or "Excellent" to scale
- If "Fair" or "Poor": Stop all scaling, audit account
- Typical issues: Repeated pauses, account age, payment issues

**Gate 2: Learning Phase Frequency**
- If campaigns re-entering Learning Phase >2x/month: Audience saturation signal
- Action: Expand to broader targeting OR refresh all creatives

**Gate 3: Blended ROAS Trend**
- Track 30-day blended ROAS
- If declining >0.05 per week: Creative fatigue across account
- Action: Reduce testing%, increase production budget for new creatives

### Google Account Spending >$10,000/month

**Gate 1: Conversion Quality**
- Ensure 50+ daily conversions (validates data collection)
- If <50: Campaign volume too low for reliable optimization

**Gate 2: Account Budget Pacing**
- Should hit 90-110% of daily budget every day
- If <85%: Bids too low OR quality issues
- Action: Increase bids 15% OR audit quality scores

**Gate 3: Impression Share Health**
- Target 70%+ impression share on performing keywords
- If <60%: Bidding too low
- Action: Increase bids 10-20% OR expand keyword list

---

## Quick Reference: Scale/Kill by the Numbers

### Meta Ads Quick Trigger Table

| Spend | ROAS | CPA vs Target | Hold Rate | Recommendation |
|-------|------|---------------|-----------|-----------------|
| <$100 | >1.5x breakeven | -40% | >10% | **SCALE to $300** |
| <$100 | 1.0x breakeven | -20% | 8% | **HOLD, retest in 24h** |
| <$100 | <1.0x breakeven | >+30% | <5% | **KILL** |
| $300-1k | >1.5x breakeven | -30% | >10% | **SCALE 20%** |
| $300-1k | 1.0-1.5x breakeven | At target | 8-10% | **HOLD, test copy** |
| $300-1k | <1.0x breakeven | >target | <5% | **PAUSE 48h, refresh creative** |
| >$1k | Trend ↑ | Trend ↓ | >10% | **SCALE 10%, hold 3 days** |
| >$1k | Trend → | Trend → | 8-10% | **HOLD, test audience** |
| >$1k | Trend ↓ | Trend ↑ | <8% | **PAUSE 7 days, rotate creative** |

### Google Shopping Quick Trigger Table

| Product Spend | Conv Count | CPA vs Margin | Q Score | Recommendation |
|---------------|------------|---------------|---------|-----------------|
| $50 | 0 | - | - | **PAUSE if no sales by day 3** |
| $100 | 1 | Within 2x | - | **Keep, monitor for scale** |
| $200 | 1 | >3x | - | **PAUSE, likely no fit** |
| $300+ | 3+ | 1.5-2.5x | 6+ | **INCREASE BID** |
| $500+ | 5+ | <1.5x margin | 8+ | **SCALE: Increase bid 20%** |
| $500+ | 0 | - | Any | **KILL, remove product** |

