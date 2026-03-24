# Diagnostic Flowcharts

## Meta Diagnostics: 7-Step Protocol

### Step 1: Verify Pixel Functionality

**Question:** Is the pixel firing correctly?

**Test:**
1. Go to Events Manager → Data Quality tab
2. Add test product to cart
3. Complete purchase
4. Check Events Manager: Does Purchase event show within 60 seconds?

**Results:**
- ✅ Event fires: Continue to Step 2
- ❌ Event doesn't fire:
  - Check pixel code installation (Events Manager → Pixel Setup)
  - Verify no ad blockers
  - Test in incognito window
  - Implement Conversions API if persistent
  - **Action:** Fix pixel before optimizing campaigns

---

### Step 2: Diagnose Audience vs. Creative Issue

**Question:** Is the problem audience saturation or creative fatigue?

**Test:**
1. Find 3 different cold audiences (interests/lookalikes):
   - Audience A: Lookalike 1-2% (control)
   - Audience B: Interest-based 10M+ size
   - Audience C: Lookalike 2-3% (expanded)

2. Run same creative across all 3 simultaneously for 3-5 days

3. Compare average ROAS:
   - If Audience A: ROAS 2.1, B: ROAS 1.8, C: ROAS 1.6 → **Audience Issue**
   - If Audience A: ROAS 0.9, B: ROAS 0.8, C: ROAS 0.9 → **Creative Issue**

**Results:**
- **Audience Issue:** Audience getting saturated. Solution: Expand targeting, duplicate audience, or launch new campaign.
- **Creative Issue:** Creative not resonating. Solution: Test new hook, new copy, new format.

---

### Step 3: Analyze CPA Inflation

**Question:** Is CPA creeping up (sign of fatigue)?

**Test:**
1. Pull last 30 days of daily CPA data
2. Calculate: 7-day rolling average CPA
3. Compare: Is current 7-day CPA >15% above 30-day average?

**Results:**
- ✅ CPA stable (±10%): Continue to Step 4
- ⚠️ CPA inflating 10-15%: Reduce frequency for 3 days, continue to Step 4
- ❌ CPA inflating 15%+: Pause campaign for 7 days, refresh creative, relaunch at 50% budget

---

### Step 4: Identify Creative Fatigue Pattern

**Question:** Is ROAS declining due to creative fatigue?

**Test:**
1. Plot ROAS trend line for last 30 days
2. Identify pattern:
   - **Flat line:** No fatigue (±0.1 variance normal)
   - **Gradual decline:** Creative fatigue (0.05-0.1 per week)
   - **Sharp drop:** Audience saturation or algorithm change

3. Cross-check: Hold rate (video) or CTR (static) declining?

**Results:**
- **Flat ROAS + Stable Metrics:** No fatigue detected. Proceed to Step 5.
- **Declining ROAS + Declining Hold Rate:** Creative fatigue. **Action:** Pause winning creative 48 hours, relaunch OR test 3-5 hook variations.
- **Declining ROAS + Flat Metrics:** Audience saturation. **Action:** Expand audience, duplicate campaign, or pause 7 days.

---

### Step 5: Check Account Health Score

**Question:** Is account quality blocking optimization?

**Test:**
1. Go to Ads Manager Settings → Account Quality
2. Check status: Good, Fair, or Poor?

**Results:**
- ✅ Good or Excellent: No account issues. Proceed to Step 6.
- ⚠️ Fair: Likely issue with payment method or account age.
  - **Action:** Verify payment method updated, confirm no billing issues
- ❌ Poor: Significant issue blocking scale.
  - **Action:** Stop scaling immediately. Audit: Recent account restrictions? Repeated pauses? Payment issues? Resolve before scaling.

---

### Step 6: Detect Learning Phase Re-entry

**Question:** Is campaign stuck in learning phase unexpectedly?

**Test:**
1. Check campaign status: Is "Learning" indicator showing?
2. Days since campaign launch: >30 days?
3. Recent changes: Did you pause and restart? Change audience? Change budget dramatically?

**Results:**
- ✅ Not in learning phase OR just launched: Proceed to Step 7.
- ⚠️ In learning phase, <14 days old: Normal. Let it complete. **Action:** No optimizations for 24 hours.
- ❌ Re-entered learning phase at 30+ days:
  - **Cause:** Audience exhaustion from rapid scaling or budget changes
  - **Action:** Pause for 7 days, modify audience (expand or change), relaunch at 50% budget

---

### Step 7: Assess Long-Term Trajectory

**Question:** What's the 60-day trend telling us?

**Test:**
1. Plot ROAS + CPA over last 60 days
2. Identify trend:
   - **Healthy:** ROAS flat ±0.2, CPA stable ±10%
   - **Warning:** ROAS declining 0.05/week, CPA inflating 5%/week
   - **Critical:** ROAS declining 0.1+/week, CPA inflating 10%+/week

**Results:**
- ✅ Healthy: Campaign is stable. Continue standard monitoring and incremental 10% scaling.
- ⚠️ Warning:
  - Increase creative production (allocate 30% of budget to testing)
  - Reduce vertical scaling to 5% increments
  - Plan creative refresh in 2-3 weeks
- ❌ Critical:
  - Campaign approaching end of lifecycle
  - Implement immediate refresh: New hook testing (50% of budget)
  - Prepare duplicate campaign launch
  - Plan pivot to different audience in 7-10 days

---

## Google Diagnostics: 9-Step Protocol

### Step 1: Verify Conversion Tracking

**Question:** Is conversion data flowing correctly?

**Test:**
1. Go to Conversions → Check conversion status
2. Look for: "Collecting data" or showing 5+ conversions in last 7 days?

**Results:**
- ✅ 5+ conversions: Data is flowing. Continue to Step 2.
- ⚠️ <5 conversions in 7 days: Insufficient data.
  - **Action:** Wait 48 hours, check again. If still <5, check tag implementation.
- ❌ No conversions showing: Tag not firing.
  - **Action:** Re-implement conversion tag in GTM or Google Tag Manager.

---

### Step 2: Assess Quality Score Health

**Question:** Are keyword quality scores blocking performance?

**Test:**
1. Go to Keywords tab → Quality Score column
2. Calculate: % of keywords with QS 6-10
3. Target: 70%+ should be QS 6+

**Results:**
- ✅ 70%+ at QS 6+: Quality score is healthy. Continue to Step 3.
- ⚠️ 50-70% at QS 6+: Quality score issue emerging.
  - **Action:** Improve ad copy relevance to keywords, increase max CPC bids
- ❌ <50% at QS 6+:
  - **Cause:** Low relevance, high CPC, or poor landing page experience
  - **Action:** Pause QS <4 keywords, rewrite ad copy for QS 5-6 keywords, audit landing page

---

### Step 3: Check Budget Limitations

**Question:** Is budget capping your impression share?

**Test:**
1. Go to Diagnostics & Recommendations
2. Look for: "Budget limiting impressions" message?
3. If yes: Note which campaigns

**Results:**
- ✅ No budget limiting: Budget is adequate. Continue to Step 4.
- ⚠️ Budget limiting: Impressions being capped by budget.
  - **Action:** Increase daily budget 15-20%
  - **Impact:** Expect 20-30% more impressions immediately
- Monitor: Does increase lead to more conversions or just clicks? (Bidding issue if just clicks)

---

### Step 4: Identify Bid Strategy Appropriateness

**Question:** Is your bid strategy right for your account maturity?

**Test:**
1. Check current bid strategy: Maximize Clicks / Target ROAS / Manual CPC?
2. Check total historical conversions: <500 or 500+?

**Results:**
- ✅ New account <$500 spend + Maximize Clicks: Best strategy.
- ⚠️ New account using Target ROAS:
  - **Risk:** Algorithm lacks data, will make poor bid decisions
  - **Action:** Switch to Maximize Clicks, collect 500+ conversions, then switch to Target ROAS
- ✅ Mature account ($1,000+ spend) with Target ROAS + stable ROAS: Good fit.
- ❌ Target ROAS set too high (5.0+ on ecom):
  - **Impact:** Algorithm can't achieve target, undershoots
  - **Action:** Reduce ROAS target to 3.0-4.0 (realistic)

---

### Step 5: Analyze Impression Share Loss

**Question:** Where are your impressions going?

**Test:**
1. Go to Dimensions tab → Search impression share columns
2. Check: Impression Share % + Impression Share Lost to Budget + Lost to Rank

**Interpretation:**
- Impression Share >70%: Good. You're capturing majority of available impressions.
- Lost to Budget >20%: Budget too low. Increase by 20%.
- Lost to Rank >20%: Bids too low or quality score issue. Increase max CPC by 15%.

**Results:**
- ✅ IS >70%, LTB <10%, LTR <10%: Optimal. Continue to Step 6.
- ⚠️ IS 50-70%: Opportunity loss.
  - If LTB >15%: Increase budget 20%
  - If LTR >15%: Increase bids 15%
- ❌ IS <50%: Significant opportunity loss. Combine fixes: Increase budget + bids.

---

### Step 6: Check for Audience Fatigue

**Question:** Is declining performance due to audience saturation?

**Test:**
1. Compare CPC week-over-week: Is it trending up 15%+?
2. Compare conversion rate: Is it down 20%+?
3. Check keyword click count: Is it flat while budget increased?

**Results:**
- ✅ CPC stable, Conv rate stable: No audience fatigue. Continue to Step 7.
- ⚠️ CPC up 10-15%, Conv rate down 10-15%: Early fatigue signals.
  - **Action:** Expand keywords (add broad match variants, competitor keywords)
- ❌ CPC up 20%+, Conv rate down 20%+: Audience exhaustion.
  - **Action:** Add 10-15 new keywords, expand negative keyword list refresh, consider demand generation (YouTube, Display)

---

### Step 7: Audit Product Feed Quality

**Question:** Is feed quality limiting performance?

**Test:**
1. Go to Merchant Center → Diagnostics
2. Check: % of products with processing errors
3. Check: Missing images, missing descriptions, low-quality images?

**Results:**
- ✅ <2% error rate, all products have images/descriptions: Feed is healthy. Continue to Step 8.
- ⚠️ 2-5% error rate: Feed issues emerging.
  - **Action:** Identify and fix products with errors
  - **Impact:** Expect 5-10% performance improvement
- ❌ >5% error rate: Significant feed issues.
  - **Action:** Audit all products, fix critical errors (missing images, pricing issues)
  - **Process:** This typically takes 3-7 days to propagate

---

### Step 8: Check for Algorithm/Seasonal Changes

**Question:** Is performance drop due to external factors?

**Test:**
1. Check Google Trends for product category: Is search volume down?
2. Check Google Blog for Shopping/Search algorithm updates (past 7 days)?
3. Compare to prior month same week: Seasonal pattern?

**Results:**
- ✅ Trends stable, no recent algorithm changes: Internal issue. Continue to Step 9.
- ⚠️ Google announced update in past 7 days:
  - **Action:** Wait 7-10 days for algorithm to stabilize
  - **Note:** Don't make major bid changes during algorithm transition
- ❌ Seasonal decline (Jan→Mar, May→July): Expected.
  - **Action:** Adjust ROAS target expectations, reduce scaling plans

---

### Step 9: Calculate Profitability Status

**Question:** Is this campaign sustainable long-term?

**Test:**
1. Calculate: ROAS × Profit Margin × (1 - Platform Fee %)
2. Example: ROAS 3.0 × 0.40 margin × 0.97 (3% fee) = 1.164 (net 16.4% profit per ad dollar)
3. Minimum viable: Net profit >10% (ROAS >2.5 with 40% margin)

**Results:**
- ✅ Net profit >15%: Campaign is healthy and scalable.
- ⚠️ Net profit 10-15%: Campaign is profitable but limited scaling potential.
- ❌ Net profit <10%: Campaign unsustainable.
  - **Action:** Reduce to small budget (loss leader) OR kill and reallocate to better performers

---

## Quick Decision Tree: "Should I Kill or Scale?"

```
START: Campaign ROAS?
  ├─ >2.0x breakeven (Meta) / >3.0 (Google)
  │  └─ Days running?
  │     ├─ <7 days: HOLD (let data stabilize)
  │     ├─ 7-14 days: SCALE 10% (vertical)
  │     ├─ 14-30 days: SCALE 10-15% (vertical + start duplicate)
  │     └─ >30 days: HOLD main, scale duplicate OR reduce scope
  │
  ├─ 1.5-2.0x breakeven (Meta) / 2.5-3.0 (Google)
  │  └─ Trend?
  │     ├─ Trending up: SCALE 5% (cautious)
  │     ├─ Flat: HOLD (test new creative)
  │     └─ Trending down: INVESTIGATE (Step 1-7)
  │
  ├─ 1.0-1.5x breakeven (Meta) / 1.5-2.5 (Google)
  │  └─ Days running?
  │     ├─ <7 days: HOLD (learning phase)
  │     ├─ 7-14 days: TEST new creative
  │     └─ >14 days: KILL (reallocate budget)
  │
  └─ <1.0x breakeven / <1.5 (Google)
     └─ KILL immediately (stop losing money)
```

