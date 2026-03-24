---
name: Customer Segmentation & RFM Analysis
---

# Customer Segmentation & RFM Analysis

## RFM Framework

RFM = Recency, Frequency, Monetary Value

Segment customers into groups based on purchase behavior:

**Recency (R):** How recently did they buy? (More recent = more engaged)
**Frequency (F):** How often do they buy? (More often = more loyal)
**Monetary (M):** How much do they spend? (Higher = higher value)

---

## RFM Scoring System

Score each customer on 1–5 scale for each dimension:

```
Recency: How many days since last purchase?
  5 = 0–30 days ago
  4 = 31–60 days ago
  3 = 61–180 days ago
  2 = 181–365 days ago
  1 = >365 days ago

Frequency: How many purchases in last 12 months?
  5 = 10+ purchases
  4 = 6–9 purchases
  3 = 3–5 purchases
  2 = 2 purchases
  1 = 1 purchase

Monetary: Total spend in last 12 months?
  5 = >$5,000
  4 = $2,000–$5,000
  3 = $500–$2,000
  2 = $100–$500
  1 = <$100

RFM Score: Combine as RFM (e.g., 543 = high recency, high frequency, high monetary)
```

---

## Customer Segments & Actions

### VIP (RFM Score 444–555)
**Profile:** Recent, frequent, high-spend customers (typically top 10% by revenue)

**Characteristics:**
- High lifetime value
- Loyal to brand
- Lower price-sensitive
- Influential (likely referrers)

**Actions:**
- **Don't discount** (they buy regardless; discounts reduce margin)
- Prioritize support (VIP support line, faster response)
- Exclusive access (new products, beta features, early sales)
- Personalization (remember preferences, custom offerings)
- Upsell premium tiers (higher-value product variants)

**Example:** Top 10% of customers spend $50K+ annually. Invest in relationship; a 10% price increase yields massive profit with minimal churn risk.

### Champions (RFM Score 333–555, but not top 10%)
**Profile:** Good recent, frequent, moderate-to-high spend

**Actions:**
- Standard pricing with potential for negotiation
- Regular engagement (newsletters, webinars, community)
- Retention focus (make switching costly through habits, integrations)
- Upsell complementary products

### At-Risk (RFM Score 211–333)
**Profile:** Used to be good customers; now inactive or declining spend

**Characteristics:**
- Recency: Old (haven't bought recently)
- Frequency: Declining
- Monetary: Still decent historical spend

**Actions:**
- Win-back campaign ("We miss you..." offer)
- Survey (understand why they left)
- Special re-engagement offer (limited-time discount or new product preview)
- If unsuccessful after 2 attempts: Move to lost segment

### Lost (RFM Score 111–222)
**Profile:** No recent activity; very low spend

**Actions:**
- Deprioritize (high cost to win back, low expected LTV)
- Passive retention only (email newsletter, not proactive outreach)
- If significant historical customer: One final win-back attempt with generous offer
- Consider: Let them go (cost to serve >CLV)

### New Customers (RFM Score 555 but low overall history)
**Profile:** Bought recently but lack frequency/spend to be VIP yet

**Actions:**
- Nurture into VIP (onboarding, education, quick wins)
- Monitor closely (some will drop off; optimize conversion)
- Personalize based on initial purchase (e.g., if they bought basic tier, offer upgrade roadmap)

---

## Customer Concentration Risk

**Rule:** If top 10 customers represent >30% of revenue, you have concentration risk.

### Metrics to Track

```
Concentration = Top 10 Customer Revenue / Total Revenue

Example:
- Customer 1: $50K/year
- Customers 2–10: $35K average = $315K
- All others: $400K
- Total: $765K

Concentration: ($50K + $315K) / $765K = 47.6%

Risk: If top customer leaves, revenue drops ~7% immediately, plus ripple effects
```

### Mitigation Strategies

1. **Diversify customer base** — Acquire more small/medium customers (reduces top-10 reliance)
2. **Increase switching costs** — Custom integration, training, data lock-in
3. **Lock in contracts** — Multi-year agreements reduce churn risk
4. **Cross-sell** — Multiple products = stickier (harder to leave if using 3 of your products)

---

## Profitability by Customer Segment

Not all customers equally profitable. Cost to serve varies.

### Customer Service Cost Variation

```
VIP Customer ($50K annual spend):
- Dedicated account manager: $30K/year ÷ 5 customers = $6K per customer
- Priority support: $2K
- Custom features/integrations: $3K
- Total cost: $11K
- Gross margin on revenue: 50% × $50K = $25K
- Net profit: $25K - $11K = $14K (28% margin on revenue)

Standard Customer ($5K annual spend):
- Self-serve support (email): $100 per customer (shared)
- No customization: $0
- Total cost: $100
- Gross margin on revenue: 50% × $5K = $2.5K
- Net profit: $2.5K - $100 = $2.4K (48% margin on revenue)

Insight: VIP generates more absolute profit ($14K vs. $2.4K) but lower margin % (28% vs. 48%)
This is OK because VIP customer spends 10x more. Absolute profit is what matters.
```

### Profitability Analysis by Segment

Calculate profit by segment:

```
Segment          Revenue    COGS    Gross Margin    Service Cost    Net Profit
VIP (top 10%)    $250K      $125K   $125K (50%)     $40K           $85K (34%)
Core (mid 40%)   $300K      $150K   $150K (50%)     $50K           $100K (33%)
Standard (40%)   $150K      $75K    $75K (50%)      $30K           $45K (30%)
Marginal (10%)   $65K       $33K    $32K (50%)      $35K           -$3K (LOSS!)

Insight: Marginal segment losing money. Either raise prices 10%+, reduce service cost, or let them churn.
```

---

## RFM-Based Pricing & Service Levels

Implement tiered service with RFM as proxy:

### Pricing by Segment

```
VIP Tier:      $500/month (all features, priority support)
Core Tier:     $150/month (core features, standard support)
Standard Tier: $50/month (basic features, email support only)
```

### Support Response Time by Tier

```
VIP:      1-hour response time, dedicated account manager
Core:     4-hour response time, shared support
Standard: 24-hour response time, self-serve + email only
Marginal: Email only, 48-hour SLA (encourage self-serve docs)
```

---

## RFM-Based Retention Campaigns

### Win-Back Campaign (At-Risk Segment)

Target: Customers with old recent score but previously high frequency/spend

```
Campaign: "We miss you"
Offer: 25% off next purchase (limited time)
Message: Highlight new features since they last purchased
Success metric: 20% conversion = win-back success
Cost: Email campaign ($500) + discount cannibalization
ROI: If win back 50 customers at $2K annual spend = $100K revenue regained
```

### Churn Prevention (Champions→VIP Transition)

Target: High-potential customers at risk of downgrade

```
Campaign: "Let's grow together"
Offer: Exclusive beta feature access
Message: Highlight upsell opportunity (next tier features)
Goal: Move from $150 → $500 tier (3.3x increase)
Success metric: 10% upgrade rate = $500 MRR additional from Champions segment
```

---

## Monitoring RFM Quarterly

Recalculate RFM scores quarterly to catch segment shifts:

```
Customer ABC:
Q1 Score: 443 (Champion)
Q2 Score: 433 (Champion, slight Recency drop)
Q3 Score: 322 (At-Risk, frequency falling, recency old)
Q4 Score: 222 (Lost, no purchases in 6 months)

Action triggered at Q3: Win-back campaign for At-Risk customers
If Q4 score doesn't improve: Accept loss, move to email-only list
```

---

## Common RFM Mistakes

1. **Ignoring frequency/recency, focusing only on monetary** → Highest-spend customers may be one-time buyers (low LTV)
2. **Treating all customers equally** → Massive opportunity cost (VIP deserve more investment)
3. **Not re-segmenting** → RFM changes over time; segment monthly or quarterly
4. **Applying same messaging to all segments** → VIP messaging (premium) different than Lost (win-back)
5. **Overlooking LTV differences** → Segment with different profit margins; adjust service cost accordingly

---

## Implementation Checklist

- [ ] Calculate RFM scores for all customers
- [ ] Segment into 5 categories (VIP, Champions, At-Risk, Lost, New)
- [ ] Identify concentration risk (top 10 customers % of revenue)
- [ ] Determine profitability by segment (margin after service cost)
- [ ] Create service/pricing tier structure aligned to segments
- [ ] Plan retention campaigns for At-Risk (win-back offer)
- [ ] Set up quarterly RFM recalculation
- [ ] Monitor segment migration (VIP→Champions→At-Risk trend)

Done well, RFM segmentation ensures you're investing where it matters: high-value, loyal customers.
