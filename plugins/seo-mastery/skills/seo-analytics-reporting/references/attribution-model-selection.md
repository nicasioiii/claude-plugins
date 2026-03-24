# Attribution Model Selection: Proving SEO ROI

**Length:** ~180 lines

## Why Attribution Matters

**Problem:** User journey is multi-touch:
1. Finds you via organic search
2. Reads blog article
3. Leaves (no conversion)
4. Returns via direct (clicks bookmark)
5. Buys on third visit

**With last-click attribution:** Direct gets 100% credit. Organic gets 0%.
**With linear attribution:** Organic gets 33%, Direct gets 33%.
**Reality:** Organic initiated the journey. Organic deserves credit.

## GA4 Attribution Models

### 1. Last Click (Default)
**How:** 100% credit to final touchpoint
**Best for:** Quick estimates
**Problem:** Undervalues organic dramatically (users research before buying)

**When to use:** Never. But useful for understanding baseline.

### 2. First Click
**How:** 100% credit to first touchpoint
**Best for:** Understanding top-of-funnel awareness
**Problem:** Ignores consideration stage (middle content)

**When to use:** Understanding how people discover you initially

### 3. Linear
**How:** Equal credit to all touchpoints
**Best for:** Multi-touch journeys without clear hierarchy
**Problem:** Doesn't weight decision-making touchpoints higher

**When to use:** When all touches are equally important

**Example:**
```
User journey:
1. Organic search → Blog article
2. Direct → Product page
3. Email → Checkout → Purchase

Linear credit:
Organic: 33%
Direct: 33%
Email: 33%
```

### 4. Time Decay
**How:** More credit to recent touchpoints, less to old ones
**Best for:** Sales cycles where final touchpoint is most influential
**Problem:** May undervalue early brand building

**When to use:** Enterprise SaaS with long sales cycles

**Example:**
```
User journey:
1. Organic search (Week 1) → 10% credit
2. Direct (Week 2) → 20% credit
3. Email (Day of purchase) → 70% credit
```

### 5. Position-Based (Google's proprietary)
**How:** GA4's machine learning algorithm weights contribution
**Best for:** Largest accounts (need 10K+ conversions)
**Problem:** Requires sufficient data to train model

**When to use:** Enterprise accounts with scale

**How it works:**
- GA4 analyzes millions of conversion paths
- Learns which positions (first click, middle, last) matter most
- Auto-weights attribution accordingly

---

## Best Attribution Model for SEO

**Recommendation:** **Position-based (if you have 10K+ conversions) OR Linear**

**Why?** Because:
1. Organic initiates journey (deserves first-click credit)
2. Organic content educates (deserves middle-touch credit)
3. Sometimes organic closes (deserves last-click credit)
4. Linear splits evenly = fairest representation

### Setup in GA4

1. GA4 → Admin → Attribution settings
2. Select model: "Linear" (if <10K conversions) or "Data-driven" (if >10K)
3. Lookback window: "30 days" (standard)
4. Apply to all conversions ✓

---

## Manual Attribution Calculation (Spreadsheet)

**For non-GA4 users or verification:**

```
Create spreadsheet:

| Customer ID | Touchpoint 1 | Touchpoint 2 | Touchpoint 3 | Conversion | Value |
|-------------|--------------|--------------|--------------|-----------|-------|
| 1 | Organic | Direct | Organic | Yes | $500 |
| 2 | Paid | Organic | Organic | Yes | $750 |
| 3 | Organic | - | - | Yes | $200 |

Linear attribution:
Customer 1: Organic gets 66% ($330), Direct gets 33% ($170)
Customer 2: Paid gets 33%, Organic gets 66% ($495)
Customer 3: Organic gets 100% ($200)

Total organic credit: $330 + $495 + $200 = $1,025
Total conversions: 3
Organic attribution %: 67% ($1,025 / $1,525 total value)
```

---

## Attribution Models by Business Type

| Business Type | Recommended Model | Reason |
|---------------|-------------------|--------|
| E-commerce | Linear or Position-based | Buyers research before purchasing |
| SaaS B2B | Position-based (time decay second) | Longer sales cycles, multiple stakeholders |
| Content/Publisher | First-click | Understanding how people discover content |
| Local Service | Position-based | Multiple location searches, then call |

---

## Organic Revenue Calculation (3 Methods)

### Method 1: GA4 Conversion Value (Easiest)

1. GA4 → Reports → Conversions
2. Filter to organic traffic
3. Sum conversion value

**Pro:** Built-in, automatic
**Con:** Limited to GA4 conversion events

### Method 2: Linear Attribution (Most Accurate)

1. Export GA4 conversion paths
2. Apply linear weighting to touchpoints
3. Sum organic-attributed revenue

**Pro:** Accounts for multi-touch journeys
**Con:** Requires data export and calculation

### Method 3: Blended Rate (Quick Estimate)

1. Calculate: Organic sessions × Conversion rate × AOV
2. Example: 10,000 sessions × 3% CR × $150 AOV = $45,000

**Pro:** Simple, quick
**Con:** Doesn't account for channel-specific conversion rates

---

## Creating Attribution Report for Boss

**Template:**

```
ORGANIC REVENUE ATTRIBUTION REPORT

Attribution Model: Linear (reflects multi-touch journeys)

Organic-Attributed Revenue: $45,000
Total Company Revenue: $150,000
Organic Attribution %: 30%

Methodology:
- GA4 conversion path data analyzed
- Linear model applied (equal credit to all touches)
- 30-day lookback window
- Only transactions included (excludes leads/trials)

Breakdown by Journey Length:
- Single-touch organic: $15,000 (direct purchase from organic)
- 2-touch journeys (organic + 1 other): $20,000
- 3+ touch journeys: $10,000

Implications:
- Without organic content, 30% of purchases wouldn't happen
- Organic drives awareness (first-click) + consideration (middle) + conversion (last)
- Estimated payback of organic investment: 2-4 months
```

---

## Tracking Attribution Over Time

Monthly spreadsheet:

```
| Month | Model | Organic Revenue | Total Revenue | Attribution % | YoY Change |
|-------|-------|-----------------|---------------|---------------|-----------|
| Jan | Linear | $40K | $130K | 31% | +15% |
| Feb | Linear | $45K | $145K | 31% | +18% |
| Mar | Linear | $50K | $160K | 31% | +22% |
```

**Insight:** Consistent 31% attribution means organic maintains predictable value. Growth is due to overall business growth.

---

## Warning: Attribution Model Gaming

**Don't:** Choose attribution models to inflate SEO numbers.

**Example of cheating:**
- "Last click shows organic 40%"
- "First click shows organic 60%"
- Present whichever number is higher

**Reality:** Stakeholders eventually notice inflated claims vs. actual revenue.

**Best practice:** Use same attribution model every month. Consistency > fluctuation.
