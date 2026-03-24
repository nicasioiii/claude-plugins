# Naming Conventions & Reporting SOP

## Campaign Naming Convention (Meta Ads)

### Formula

```
[BRAND]_[FUNNEL]_[TYPE]_[VARIABLE]_[OPTIMIZATION]_[DATE]
```

### Fields Breakdown

| Field | Values | Example |
|-------|--------|---------|
| **BRAND** | 3-4 letter brand code | GNR, BLS, SKN |
| **FUNNEL** | COLD, WARM, HOT, RET (retargeting) | COLD |
| **TYPE** | IMG, VID, CAR (carousel) | VID |
| **VARIABLE** | What you're testing (hook/copy/audience) | HOOK_NEW |
| **OPTIMIZATION** | ABO, CBO, MOB | ABO |
| **DATE** | MM_YYYY or date launched | 03_2026 |

### Complete Examples

```
GNR_COLD_VID_HOOK_ABO_03_2026
  → Brand: GNR
  → Funnel: Cold traffic
  → Type: Video
  → Variable: Testing new hook
  → Optimization: ABO (manual budget split)
  → Date: March 2026

BLS_RET_IMG_COPY_CBO_03_2026
  → Brand: BLS
  → Funnel: Retargeting
  → Type: Static image
  → Variable: Testing new copy
  → Optimization: CBO (algorithm budget split)
  → Date: March 2026
```

---

## Ad Set Naming Convention (Meta Ads)

### Formula

```
[CAMPAIGN_CODE]_[AUDIENCE]_[DEMOGRAPHIC]_[BID_TYPE]_[VARIATION]
```

### Examples

```
GNR_COLD_VID_HOOK_ABO_03_2026_Lookalike1%_25-34_Manual_V1
  → Campaign: GNR_COLD_VID_HOOK_ABO_03_2026
  → Audience: Lookalike 1%
  → Demographic: 25-34 age
  → Bid Type: Manual CPC
  → Variation: Version 1

GNR_COLD_VID_HOOK_ABO_03_2026_Interest_AllGenders_CPA_V2
  → Campaign: GNR_COLD_VID_HOOK_ABO_03_2026
  → Audience: Interest-based
  → Demographic: All genders
  → Bid Type: CPA optimization
  → Variation: Version 2
```

---

## Ad Naming Convention (Meta Ads)

### Formula

```
[ADSET_CODE]_[CREATIVE_ID]_[HOOK/HOOK_VARIANT]_[FORMAT]
```

### Examples

```
Lookalike1%_25-34_Manual_V1_Creative005_Hook_ShakingTransition_9x16
  → Ad Set: Lookalike1%_25-34_Manual_V1
  → Creative: 005
  → Hook: Shaking transition effect
  → Format: 9x16 vertical

Interest_AllGenders_CPA_V2_Creative012_Hook_Voiceover_1x1
  → Ad Set: Interest_AllGenders_CPA_V2
  → Creative: 012
  → Hook: Voice-over pattern interrupt
  → Format: 1x1 square
```

---

## Google Ads Campaign/Ad Group Naming

### Shopping Campaign Formula

```
[PRODUCT]_[BID_STRATEGY]_[GEO]_[PHASE]_[DATE]
```

### Examples

```
ColorBlindGlasses_MaximizeClicks_US_Testing_03_2026
  → Product: Color Blind Glasses
  → Bid Strategy: Maximize Clicks
  → Geography: United States
  → Phase: Testing
  → Date: March 2026

ColorBlindGlasses_TargetROAS3.0_US_Scaling_03_2026
  → Product: Color Blind Glasses
  → Bid Strategy: Target ROAS 3.0
  → Geography: United States
  → Phase: Scaling
  → Date: March 2026
```

### Search Campaign Formula

```
[PRODUCT]_[KEYWORD_TYPE]_[MATCH_TYPE]_[DATE]
```

### Examples

```
GolfNet_Branded_Exact_03_2026
  → Product: Golf Net
  → Keyword Type: Branded (product name)
  → Match Type: Exact match
  → Date: March 2026

GolfNet_Competitor_Phrase_03_2026
  → Product: Golf Net
  → Keyword Type: Competitor keywords
  → Match Type: Phrase match
  → Date: March 2026
```

### Ad Group Formula

```
[KEYWORD_CLUSTER]_[AUDIENCE]_[INTENT]
```

### Examples

```
BestGolfNets_US_Purchase
  → Keyword cluster: Best golf nets
  → Audience: US traffic
  → Intent: Purchase (high intent)

GolfNetAlternatives_Competitive_Comparison
  → Keyword cluster: Golf net alternatives
  → Audience: Competitive buyers
  → Intent: Comparison shopping
```

---

## Performance Max Campaign Naming

### Formula

```
[BRAND]_[TARGETING]_[PHASE]_[ASSET_GROUP_ID]_[DATE]
```

### Examples

```
GNR_Prospecting_Testing_AssetGroup1_03_2026
  → Brand: GNR
  → Targeting: Prospecting (cold)
  → Phase: Testing
  → Asset Group: 1
  → Date: March 2026

GNR_Retargeting_Scaling_AssetGroup3_03_2026
  → Brand: GNR
  → Targeting: Retargeting
  → Phase: Scaling
  → Asset Group: 3
  → Date: March 2026
```

---

## Creative File Naming (For Designers/Editors)

### Formula

```
[BRAND]_[FORMAT]_[HOOK_TYPE]_[VARIATION]_[STATUS].[extension]
```

### Examples

```
GNR_9x16_TransitionShake_V1_READY.mp4
  → Brand: GNR
  → Format: 9x16 vertical video
  → Hook: Transition with shake effect
  → Variation: Version 1
  → Status: Ready for upload

GNR_1x1_BeforeAfter_V3_DRAFT.psd
  → Brand: GNR
  → Format: 1x1 square static
  → Hook: Before/after comparison
  → Variation: Version 3
  → Status: Draft (not ready)
```

---

## Reporting Dashboard Setup (Google Sheets Template)

### Columns for Daily Monitoring

| Date | Campaign | Spend | ROAS | CPA | CTR | Freq | Hold/Conv | Status | Notes |
|------|----------|-------|------|-----|-----|------|-----------|--------|-------|
| 3/6 | GNR_COLD_VID | $240 | 2.1 | $18 | 1.8% | 2.4 | 12% | SCALE | Strong day |
| 3/6 | GNR_RET_IMG | $150 | 3.2 | $12 | 3.1% | 1.8 | - | HOLD | Perform well |
| 3/6 | BLS_TEST | $45 | 0.8 | $65 | 0.9% | 3.2 | 5% | KILL | Hook failing |

### Columns for Weekly Analysis

| Campaign | Wk Spend | Wk ROAS | Avg CPA | Impressions | Conversions | Revenue | Profit | % of Total |
|----------|----------|---------|---------|-------------|-------------|---------|--------|-----------|
| GNR_COLD | $1,680 | 2.15 | $18.50 | 45,000 | 91 | $3,612 | $1,932 | 35% |
| GNR_RET | $1,050 | 3.05 | $11.25 | 12,000 | 94 | $3,203 | $2,153 | 65% |

### Columns for Monthly Review

| Campaign | Month Spend | Month ROAS | Month Revenue | Target Hit? | Scaling Status | Notes |
|----------|-------------|-----------|----------------|-------------|-----------------|-------|
| Main | $5,000 | 2.3 | $11,500 | Yes | Scale 10% | Strong performer |
| Testing | $1,200 | 0.95 | $1,140 | No | Kill | Not viable |

---

## Testing Campaign Naming Convention

### A/B Test Format

```
[BASE_CAMPAIGN]_TEST_[VARIABLE]_[CONTROL_VS_TEST]_[DATE]
```

### Examples

```
GNR_COLD_VID_TEST_HOOK_ControlTransition_vs_TestVoiceover_03_2026
  → Base: GNR Cold Video
  → Test: Hook comparison
  → Control: Transition effect
  → Test variant: Voice-over
  → Date: March 2026

GNR_RET_IMG_TEST_COPY_ControlUrgency_vs_TestEducation_03_2026
  → Base: GNR Retargeting Image
  → Test: Copy comparison
  → Control: Urgency message
  → Test variant: Educational content
  → Date: March 2026
```

---

## Escalation Criteria Tracking

### Red Flag Campaigns (Requires Daily Monitoring)

Create a separate tab called "Red Flags" with:
- Campaign name
- Red flag: Low ROAS, High CPA, High Frequency, etc.
- Date flagged
- Action taken
- Resolution date

### Example Format

| Campaign | Flag | Date Flagged | Action Taken | Resolved? |
|----------|------|--------------|--------------|-----------|
| GNR_OLD_VID | Low ROAS <1.2x | 3/4 | Paused, tested new creative | 3/7 |
| BLS_HIGH_FREQ | Frequency >4x | 3/5 | Reduced to 2x/week | 3/6 |
| SKN_HIGH_CPA | CPA 2x target | 3/3 | Investigating pixel | Pending |

---

## Weekly Reporting Template

### Executive Summary (1 sentence)
"Overall spend up 15%, ROAS down 0.1 due to creative fatigue on main campaign. Plan: 2 new hook tests launching Monday."

### Key Metrics This Week

```
Metric          This Week    Last Week    Change
─────────────────────────────────────────────────
Total Spend     $8,500       $7,200       +18%
Total Revenue   $18,500      $15,600      +18%
Blended ROAS    2.18x        2.17x        +0.01x
Blended CPA     $22.50       $22.40       +$0.10
Conversions     378          360          +5%
```

### Campaign Status Dashboard

```
Campaign               Status    ROAS   CPA    Action Next Week
─────────────────────────────────────────────────────────────────
GNR Main (Cold)        🟢 OK    2.1x   $19   Scale 10%
GNR Retarget (Warm)    🟢 OK    3.2x   $11   Keep stable
BLS Testing            🟠 Alert 1.1x   $65   Kill if no improvement
SKN Launch             🟢 OK    1.8x   $25   Monitor 2 more weeks
```

### Weekly Actions Completed

```
✅ Launched 3 new hook variations (Creative 045-047)
✅ Paused Creative 032 (hold rate dropped 25%)
✅ Scaled GNR Main from $200 to $220/day
✅ Expanded BLS audience to 15M+ interests
⏳ Waiting on: Product image refresh (ETA: Friday)
```

### Next Week Priorities

```
1. Monitor new hook tests (expect winner by Wednesday)
2. Scale GNR Retargeting by 10% if ROAS >3.0
3. Kill BLS campaign if ROAS <1.5 by Thursday
4. Prepare Q2 seasonal strategy (Mother's Day campaign brief)
```

---

## Audit Trail Template

### For Every Kill Decision

Document in spreadsheet:

| Campaign Killed | Kill Date | Reason | Final ROAS | Final CPA | Total Spend | Notes |
|-----------------|-----------|--------|-----------|-----------|-------------|-------|
| BLS_OLD_VID | 3/6 | ROAS <1.0 for 5 days | 0.85x | $78 | $600 | Retest hook in May |
| SKN_AUDIENCE | 3/3 | Frequency >5x, ROAS <1.2 | 1.1x | $52 | $450 | Audience exhausted |

### For Every Major Scale Decision

Document:

| Campaign Scaled | Scale Date | From Budget | To Budget | ROAS | Days Running | Next Scale? |
|-----------------|-----------|-------------|-----------|------|--------------|------------|
| GNR_MAIN | 3/6 | $200/day | $220/day | 2.1x | 14 | 3/9 (+10%) |
| BLS_DUP1 | 3/5 | $150/day | $180/day | 1.8x | 7 | 3/8 (+10%) |

