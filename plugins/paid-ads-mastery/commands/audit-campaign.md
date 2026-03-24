---
name: Audit Campaign
description: Campaign audit tool that accepts pasted metrics (spend, ROAS, CPA, CTR, etc.) and runs diagnostic decision trees from the optimize-campaigns skill. Outputs ranked issues with specific fixes.
---

# Campaign Audit Tool

## Step 1: Paste Campaign Data

**Provide the following metrics (copy/paste from Ads Manager):**

```
REQUIRED FIELDS:
- Platform: Meta / Google / Other?
- Campaign Name:
- Days Running:
- Total Spend: $___
- Total Conversions: ___
- Total Revenue: $___
- Average ROAS: ___x
- Average CPA: $___

RECOMMENDED FIELDS (For deeper diagnosis):
- CTR: _%
- CPM: $___
- Conversion Rate: _%
- Frequency (Meta): __x
- Hold Rate / Video (Meta): _%
- Quality Score (Google): __/10
- Impression Share (Google): _%
- Hook Rate (Meta): _%

TREND DATA (Last 3-7 days):
- 7-day ROAS: ___x
- 7-day CPA: $___
- Yesterday ROAS: ___x
- 30-day average ROAS: ___x
- Is CPA trending up or down?: Up / Down / Flat
- Is ROAS trending up or down?: Up / Down / Flat
```

---

## Step 2: Platform-Specific Diagnostic

### FOR META ADS CAMPAIGNS

**Decision Tree 1: Pixel & Tracking**

```
Is pixel actively firing?
├─ Unknown → TEST: Add to cart + purchase, check Events Manager
├─ YES ✅ → Continue to Decision Tree 2
└─ NO ❌ → ISSUE #1 [CRITICAL]
    Problem: Tracking not working
    Impact: Cannot optimize campaigns accurately
    Fix: 1) Verify pixel code installed
         2) Check for ad blockers in test browser
         3) Implement Conversions API (more reliable)
    Timeline: 24-48 hours
    Priority: 🔴 CRITICAL - Fix before optimizing
```

**Decision Tree 2: Days Running vs. Learning Phase**

```
Days Running: [INSERT NUMBER]
├─ <7 days → ANALYSIS: Learning Phase
│            Decision: Too early to optimize
│            Action: Wait 7 days, collect baseline data
│
├─ 7-14 days → ANALYSIS: Exiting Learning Phase
│             Decision: Early performance signals
│             Actions:
│             - If ROAS >1.5x breakeven: SCALE 10%
│             - If ROAS <1.0x: TEST new creative
│             - If ROAS 1.0-1.5x: HOLD, monitor 3 more days
│
└─ >14 days → ANALYSIS: Established Campaign
              Decision: Full optimization possible
              Continue to Decision Tree 3
```

**Decision Tree 3: ROAS Performance**

```
ROAS: [INSERT NUMBER]x
├─ >2.0x Breakeven ✅
│  ├─ Trend: Up? → SCALE 15% (momentum!)
│  ├─ Trend: Flat? → SCALE 10% (steady growth)
│  └─ Trend: Down? → HOLD, test new hook (fatigue warning)
│
├─ 1.5-2.0x Breakeven ⚠️ (Marginal)
│  ├─ Days <21? → HOLD, let data mature
│  ├─ Days 21-30? → HOLD, test new creative
│  └─ Days >30? → Plan refresh (creative fatigue)
│
└─ <1.5x Breakeven ❌ (Problem)
   ├─ Days <7? → HOLD (learning phase, normal)
   ├─ Days 7-14? → TEST new hook immediately
   └─ Days >14? → PAUSE 48h, investigate + refresh, OR KILL if no recovery
```

**Decision Tree 4: CPA Inflation**

```
Current 7-day CPA vs. 30-day Average CPA: [INSERT %]
├─ +0 to +10% (Stable) ✅
│  Decision: Normal variance
│  Action: Continue monitoring
│
├─ +10 to +20% ⚠️ (Inflation)
│  Decision: Creative fatigue emerging
│  Actions: 1) Reduce frequency cap (2x/week instead of 3x)
│           2) Pause for 48 hours
│           3) Relaunch with new hook variant
│           4) Continue monitoring CPA closely
│
└─ >+20% ❌ (Critical Inflation)
   Decision: Audience saturation or creative fatigue
   Actions: 1) PAUSE immediately (48-72 hours)
            2) Refresh entire creative set
            3) Relaunch at 50% original budget
            4) Expand targeting (remove interest exclusions)
```

**Decision Tree 5: Frequency & Fatigue**

```
Average Frequency: [INSERT #]x
├─ <2.0x ✅
│  Decision: Healthy frequency
│  Action: No changes needed
│
├─ 2.0-3.5x ⚠️
│  Decision: Monitor closely for fatigue
│  Actions: 1) Set frequency cap to 2x/week
│           2) If ROAS drops >10% in next 3 days, prepare refresh
│           3) Continue scaling if ROAS remains stable
│
└─ >3.5x ❌ (High Fatigue Risk)
   Decision: Audience seeing ad too many times
   Actions: 1) SET frequency cap to 1.5-2x/week
            2) PAUSE if conversions declining >15%
            3) Expand targeting (new interests/lookalikes)
            4) OR reduce budget to manage frequency
```

**Decision Tree 6: Account Quality**

```
Account Quality Score: [INSERT: Good / Fair / Poor]
├─ Good ✅
│  Decision: No issues
│  Action: Safe to scale
│
├─ Fair ⚠️
│  Decision: Potential issue
│  Investigate: 1) Payment method valid?
│              2) Account age >3 months?
│              3) Any recent account restrictions?
│  Action: Resolve issues, then continue
│
└─ Poor ❌
   Decision: Serious issue blocking scale
   Actions: 1) STOP scaling immediately
            2) Audit payment & account history
            3) Contact Meta support if needed
            4) Resume scaling only after "Good" rating
```

**Decision Tree 7: Creative Fatigue Pattern**

```
30-day ROAS Trend: [Plot mentally: Stable / Declining / Volatile]
├─ Stable ±0.2x ✅
│  Decision: No creative fatigue
│  Action: Continue standard optimization
│
├─ Declining 0.05-0.1x per week ⚠️
│  Decision: Gradual creative fatigue
│  Timeline: 3-4 weeks until burnout
│  Actions: 1) Increase testing budget to 30%
│           2) Plan creative refresh in 2 weeks
│           3) Test 3-5 hook variations
│           4) Prepare duplicate campaign
│
├─ Declining >0.1x per week ❌
│  Decision: Rapid creative fatigue
│  Actions: 1) PAUSE for 7 days
│           2) Redesign all creatives
│           3) Relaunch at 50% budget
│           4) Increase daily testing allocation to 40%
│
└─ Volatile ±0.3-0.5x (Erratic)
   Decision: Data quality issue OR external factor
   Investigate: 1) Algorithm update?
               2) Seasonal event impact?
               3) External news affecting category?
   Actions: 1) Check if volatility is category-wide
            2) If just you: Test new audience
            3) If industry-wide: Hold spend, wait 7 days
```

---

### FOR GOOGLE ADS CAMPAIGNS

**Decision Tree 1: Conversion Tracking**

```
Conversions in last 7 days: [INSERT NUMBER]
├─ 50+ ✅
│  Decision: Solid data flow
│  Action: Continue to Decision Tree 2
│
├─ 10-50 ⚠️
│  Decision: Moderate data
│  Actions: 1) Campaign needs more volume to optimize
│           2) Increase budget or expand keywords
│           3) Wait for 50+ before major bid changes
│
└─ <10 ❌
   Decision: Insufficient data
   Actions: 1) Check conversion tag implementation
            2) Verify correct conversion selected
            3) Wait 48+ hours for data to flow
            4) Increase daily budget temporarily to accelerate learning
```

**Decision Tree 2: Quality Score Health**

```
% of keywords with Quality Score 6+: [INSERT %]
├─ >70% ✅
│  Decision: Quality score is healthy
│  Action: Continue to Decision Tree 3
│
├─ 50-70% ⚠️
│  Decision: Some quality score issues
│  Actions: 1) Identify keywords with QS <5
│           2) Improve ad copy relevance
│           3) Increase max CPC bids by 10% on QS 5-6 keywords
│           4) Audit landing page experience
│
└─ <50% ❌
   Decision: Systemic quality score problem
   Actions: 1) PAUSE all QS <4 keywords
            2) Rewrite ad copy for higher relevance
            3) Check landing page loading speed
            4) Audit: Do ads match keyword intent?
            5) Expect 3-7 days for QS to improve
```

**Decision Tree 3: Budget Limitations**

```
Is budget limiting impressions? [Check Diagnostics tab]
├─ No ✅
│  Decision: Budget is adequate
│  Action: Continue to Decision Tree 4
│
├─ Yes, "Lost to Budget" >20% ⚠️
   Decision: Bid too low for current budget
   Actions: 1) Increase daily budget 15-20%
            2) Monitor: Do more impressions = more conversions?
            3) If conversions increase proportionally: Budget was issue
            4) Continue scaling budget incrementally
│
└─ Yes, "Lost to Rank" >20%
   Decision: Bids too low for keyword competition
   Actions: 1) Increase max CPC by 15%
            2) Monitor if impressions increase
            3) If ROAS remains stable: Continue increasing bids
            4) If ROAS declines: Reduce bids or pause keywords
```

**Decision Tree 4: ROAS & Bid Strategy**

```
ROAS: [INSERT NUMBER]x | Bid Strategy: [INSERT: Maximize Clicks / Target ROAS / Manual CPC]
├─ ROAS >3.0x
│  ├─ Strategy: Maximize Clicks? → PERFECT for new accounts
│  ├─ Strategy: Target ROAS? → Conservative ROAS target (3.5+?)
│  └─ Strategy: Manual CPC? → INCREASE bids 10-15%
│
├─ ROAS 2.5-3.0x (Healthy)
│  ├─ Strategy: Maximize Clicks? → HOLD, collecting more data
│  ├─ Strategy: Target ROAS? → Good, continue
│  └─ Strategy: Manual CPC? → INCREASE bids 5-10%
│
├─ ROAS 1.5-2.5x (Marginal)
│  ├─ Conversions >30/week? → HOLD, monitor for improvement
│  ├─ Conversions <30/week? → Test new keywords or ad copy
│  └─ Days running <21? → Normal for new campaigns, let mature
│
└─ ROAS <1.5x (Losing)
   ├─ Days <14? → HOLD (learning phase), OK for new
   ├─ Days 14-30? → TEST new keywords or improve landing page
   └─ Days >30? → KILL keywords, reallocate budget OR refresh
```

**Decision Tree 5: Product Feed Quality (Shopping)**

```
Merchant Center Diagnostic Errors: [INSERT % or "Unknown"]
├─ 0-2% ✅
│  Decision: Feed is healthy
│  Action: Monitor for compliance
│
├─ 2-5% ⚠️
│  Decision: Feed issues emerging
│  Actions: 1) Identify products with errors
│           2) Fix: Missing images? Pricing issues? Descriptions?
│           3) Resubmit products
│           4) Expect 24-48 hours propagation
│
└─ >5% ❌
   Decision: Significant feed issues
   Actions: 1) Audit all products for:
              - Missing images (needs 3+ images)
              - Missing descriptions
              - Pricing discrepancies
              - Category misclassification
            2) Fix critical issues first
            3) Resubmit in batches
            4) Expect 5-10% ROAS improvement post-fix
```

**Decision Tree 6: Impression Share & Competition**

```
Impression Share: [INSERT %]
├─ >70% ✅
│  Decision: Capturing majority of available impressions
│  Action: Continue optimization
│
├─ 50-70% ⚠️
│  Decision: Missing 30%+ of impressions
│  Diagnose: Lost to Budget? OR Lost to Rank?
│  ├─ Lost to Budget >15%? → INCREASE daily budget 20%
│  └─ Lost to Rank >15%? → INCREASE max CPC by 15%
│
└─ <50% ❌
   Decision: Significant impression loss
   Actions: 1) INCREASE budget 25%
            2) INCREASE bids 20%
            3) EXPAND keyword list (add similar keywords)
            4) Monitor next 7 days for improvement
            5) If no improvement: Keywords too competitive for margin
```

**Decision Tree 7: Profitability Status**

```
Calculate: ROAS × Profit Margin × (1 - Platform Fee)
Example: 3.0 ROAS × 0.40 margin × 0.97 = 1.164 (net 16.4% profit)

├─ Result >1.20 (>20% net profit) ✅
│  Decision: Highly profitable
│  Action: SCALE aggressively (increase budget 15-20% daily)
│
├─ Result 1.10-1.20 (10-20% profit) ✅
│  Decision: Profitable
│  Action: Scale 5-10% every 5 days
│
├─ Result 1.05-1.10 (5-10% profit) ⚠️
│  Decision: Marginal profitability
│  Actions: 1) Test new keywords
│           2) Optimize landing page
│           3) Monitor closely for margin compression
│           4) Limited scaling potential
│
└─ Result <1.05 (<5% profit) ❌
   Decision: Unsustainable
   Actions: 1) If new campaign: HOLD 14 more days
            2) If mature: KILL and reallocate to winners
            3) OR use as loss leader (limited budget)
```

---

## Step 3: Summarized Audit Report

Based on your metrics, here's the prioritized issues:

### ISSUE PRIORITY RANKING

**🔴 CRITICAL Issues (Fix in next 48 hours)**
- [List any tracking, account, or red flag issues]
- Recommended action: [Specific fix]
- Expected impact: [Timeline and ROAS improvement estimate]

**🟠 HIGH Issues (Fix in next 3-7 days)**
- [List performance, creative fatigue, bid issues]
- Recommended action: [Specific fix]
- Expected impact: [Estimate]

**🟡 MEDIUM Issues (Fix next week)**
- [List optimization opportunities]
- Recommended action: [Specific fix]
- Expected impact: [Estimate]

**🟢 GREEN LIGHTS (Safe to continue)**
- [List what's working well]
- Recommended action: [Scale or maintain]

---

## Step 4: Next Steps

**Immediate Actions (Today):**
1. [Action based on issues]
2. [Action based on issues]

**This Week:**
1. [Action]
2. [Action]

**Deep Dive:**
- Need creative audit? → `/write-ad` or `/create-meta-traditional`
- Need testing plan? → `/test-plan`
- Need scaling roadmap? → `/scale-plan`
- Need daily monitoring SOP? → `/brief-media-buyer`
- Need creative research? → `/research-brief`
