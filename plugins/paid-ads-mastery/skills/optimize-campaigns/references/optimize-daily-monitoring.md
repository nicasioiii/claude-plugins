# Daily Monitoring Checklist Template

## Morning Routine (7 minutes)

### Meta Ads Check
- [ ] Open Ads Manager
- [ ] View all active campaigns (last 24 hours)
- [ ] Spend check: Is spend tracking to 1/7 of weekly budget?
- [ ] Any campaigns in Learning Phase (unexpected)?
- [ ] Any pixel errors in Events Manager?
- [ ] Top 3 creatives: Above or below account average?

### Google Ads Check
- [ ] Go to Dashboard → Performance Summary
- [ ] Check Budget Remaining (on track?)
- [ ] Any Disapproved Ads (policy violations)?
- [ ] Shopping campaigns: Any quality score drops (7→5)?
- [ ] Search campaigns: Impression share <70%?
- [ ] Performance Max: Asset quality warnings?

### Action Items
- [ ] Any red flags identified? → Document in spreadsheet
- [ ] Any campaigns need pause? → Note for afternoon review

---

## Afternoon Routine (8 minutes)

### Meta Ads Deep Dive
- [ ] View 7-day ROAS: Compare today to 7-day average
- [ ] CPA check: Is it trending up (bad) or stable (good)?
- [ ] High-frequency analysis: Any campaigns >3x frequency with dropping ROAS?
- [ ] Creative performance: Which ad has most spend? Is it above average?
- [ ] Account Quality Score: Has it dropped? (triggers manual investigation)

### Google Ads Deep Dive
- [ ] Shopping: Product-level performance → Identify top 3 products (by revenue)
- [ ] Search: Keyword-level quality scores → Any <5?
- [ ] Performance Max: Asset group performance → Which performs best?
- [ ] Conversion lag: Check yesterday's conversions vs. 3 days ago (validate counting)

### Scaling/Killing Decision
- [ ] Any campaigns ready to scale? (ROAS >target for 3+ days) → Mark for tomorrow
- [ ] Any campaigns ready to pause? (ROAS <breakeven for 3+ days) → Mark for tomorrow
- [ ] Testing campaigns: Any ready to scale winners into main budget?

### End-of-Day Log
- [ ] Update tracking spreadsheet with daily metrics
- [ ] Note any alerts for next morning (pixel issues, approval delays, etc.)

---

## Weekly Audit (30 minutes, Friday)

### Meta Account Health
- [ ] Account Quality Score: Good or Excellent?
- [ ] Account Spending Pacing: On track for month?
- [ ] Pixel Events: Check firing accuracy (test purchase)
- [ ] Account Restrictions: Any new limits or warnings?
- [ ] Conversions API: Is it active and deduplicating correctly?

### Google Account Health
- [ ] Conversion Tracking: Data flowing from all campaigns?
- [ ] Merchant Center: Feed status (all products active?)
- [ ] Quality Scores: % of keywords at 7+? Target: >75%
- [ ] Budget Pacing: On track for month?
- [ ] Landing Page Experience: Any poor scores affecting CTR?

### Performance Analysis
- [ ] Plot 4-week ROAS trend (should be relatively flat)
- [ ] Plot CPA trend (identify inflation early)
- [ ] Identify top 3 winning creatives by ROAS
- [ ] Identify 2-3 underperformers (kill candidates)
- [ ] Calculate creative refresh rate needed (if fatigue detected)

### Next Week Planning
- [ ] Budget allocation: Adjust based on performance
- [ ] New creatives needed: Estimate design time
- [ ] Testing plan: What to test next week (hooks? Audiences? Copy?)
- [ ] Scaling opportunities: Which campaigns have runway?

---

## Monthly Review (1 hour, last Friday of month)

### Financial Summary
- [ ] Total spend: On budget?
- [ ] Total revenue: On target?
- [ ] Blended ROAS: Compare to target (variance <10% is healthy)
- [ ] Blended CPA: Compare to target (variance <15% is healthy)
- [ ] Profitability analysis: Revenue - (Spend + COGS) = ?

### Performance Trends
- [ ] Which platform (Meta vs. Google) drove most profit?
- [ ] Which campaign type won? (DPA vs. Search vs. Shopping)
- [ ] Creative performance: Which variable (hook/copy/format) drove ROAS?
- [ ] Audience tier performance: Retargeting vs. prospecting (which won?)
- [ ] Seasonal impact: Any holidays/events that spiked traffic?

### Team Performance & Process
- [ ] Creative production rate: # of ads produced vs. target
- [ ] Iteration rate: # of iterations vs. new creatives
- [ ] Decision speed: Avg. days from creative launch to kill/scale decision
- [ ] Audit any campaigns that underperformed expectations

### Next Month Strategy
- [ ] Allocate budget by platform (based on profitability)
- [ ] Plan seasonal campaigns (awareness for upcoming holidays)
- [ ] Target ROAS: Adjust based on seasonal trends
- [ ] Creative themes: What worked last month to double down on?
- [ ] Team goals: Increase creative volume? Improve ROAS? Launch new platform?

---

## Spreadsheet Template

Create a Google Sheet with these columns for daily logging:

| Date | Campaign | Spend | ROAS | CPA | CTR | Frequency | Notes | Action |
|------|----------|-------|------|-----|-----|-----------|-------|--------|
| 3/6 | Meta - Main | $245 | 2.1 | $18 | 1.8% | 2.4 | Strong day | Scale 10% |
| 3/6 | Google - Shop | $156 | 3.2 | $15 | 4.1% | - | New product winner | Monitor |
| 3/6 | Meta - Test | $48 | 0.8 | $62 | 0.9% | 3.8 | Hook failing | Kill tomorrow |

---

## Alert Escalation

**Yellow Alert (Discuss with team, monitor next 24h):**
- ROAS ±0.2 from target
- CPA ±10% from target
- Budget 10% off pace
- Any disapproved ads on Google

**Red Alert (Take immediate action):**
- ROAS <breakeven x 2 consecutive days
- CPA >50% above target
- Campaign in unplanned Learning Phase
- Pixel quality score "Poor"
- Disapproved ads blocking >20% of spend
