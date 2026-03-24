# Breakeven ROAS & Profitability Analysis

## Core Breakeven Formula

```
Breakeven ROAS = (1 + Platform Fee %) / Gross Margin %

Where:
  Gross Margin = (Selling Price - Cost of Goods) / Selling Price
  Platform Fee = Stripe + Payment Gateway + Shipping (typically 3-8%)
```

### Complete Example Calculation

**Product Details:**
- Selling Price: $50
- COGS: $20 (sourcing cost)
- Stripe Fee: 2.9% + $0.30 per transaction
- Shipping: $5 (included in COGS)
- Platform Fee (Total): $50 × 0.029 + $0.30 + $5 = $7.75

**Calculation:**
```
Gross Margin = ($50 - $20 - $5) / $50 = $25 / $50 = 50%

Breakeven ROAS = (1 + 0.155) / 0.50
               = 1.155 / 0.50
               = 2.31x
```

**Meaning:** You need ROAS of 2.31x just to break even. Any ROAS below this = losing money.

---

## Breakeven by Business Model

### E-commerce Dropshipping

**Typical Costs:**
- COGS: 40-60% of price
- Stripe: 2.9% + $0.30
- Shipping: Included in product cost

**Example:** $30 product with $12 COGS

```
Gross Margin = ($30 - $12) / $30 = 60%
Platform Fee = 3.5% = $1.05
Total Cost = $12 + $1.05 = $13.05

Breakeven ROAS = 1 / (($30 - $13.05) / $30)
               = 1 / 0.565
               = 1.77x
```

**Healthy ROAS Target:** 2.2-3.0x (healthy buffer above 1.77x)

---

### E-commerce (Own Inventory)

**Typical Costs:**
- COGS: 25-45% of price
- Stripe: 2.9% + $0.30
- Shipping: 10-15% of price
- Customer Service: 5% of order value

**Example:** $50 product, $15 COGS, $8 shipping

```
Total Cost = $15 COGS + $8 shipping + ($50 × 0.029) + $0.30 + ($50 × 0.05)
           = $15 + $8 + $1.45 + $0.30 + $2.50
           = $27.25

Gross Margin = ($50 - $27.25) / $50 = 45.5%

Breakeven ROAS = 1 / 0.455 = 2.20x
```

**Healthy ROAS Target:** 2.8-3.5x (healthy buffer)

---

### Digital Products / Courses

**Typical Costs:**
- COGS: 0-5% (hosting, payment processing)
- Stripe: 2.9% + $0.30
- Customer Support: 5-10% of revenue
- Platform Fee: $0-200/month (platform cost)

**Example:** $99 course, $30/month platform cost, 10% support cost

```
Per Sale:
  Stripe: $99 × 0.029 + $0.30 = $3.17
  Support: $99 × 0.10 = $9.90
  COGS: $0
  Allocated Platform: $30 / (300 sales/month) = $0.10
  Total Cost = $13.17 per sale

Gross Margin = ($99 - $13.17) / $99 = 86.7%

Breakeven ROAS = 1 / 0.867 = 1.15x
```

**Healthy ROAS Target:** 1.8-2.5x (healthy buffer)

---

### SAAS / Subscription (Monthly)

**Typical Costs:**
- COGS: 5-15% (hosting, support)
- Stripe: 2.9%
- Assume: Customer LTV = 12 months

**Example:** $99/month SAAS, expected 8-month churn, 10% COGS

```
Customer LTV = $99 × 8 months = $792

One-Time Acquisition Cost:
  Stripe (first month): $99 × 0.029 = $2.87
  COGS (first month): $99 × 0.10 = $9.90
  Total = $12.77

Breakeven ROAS = 1 / (($792 - $12.77) / $792)
               = 1 / 0.984
               = 1.02x
```

**Healthy ROAS Target:** 2.0-3.0x (MASSIVE buffer because of LTV)

---

### Information Products / Affiliate

**Typical Costs:**
- COGS: 0-5% (delivery, support)
- Stripe: 2.9% + $0.30
- Affiliate Commission: 20-40% of price (if paying affiliates)

**Example:** $47 product, 30% affiliate commission

```
Total Cost = ($47 × 0.30) + ($47 × 0.029) + $0.30
           = $14.10 + $1.36 + $0.30
           = $15.76

Gross Margin = ($47 - $15.76) / $47 = 66.5%

Breakeven ROAS = 1 / 0.665 = 1.50x
```

**Healthy ROAS Target:** 2.0-3.0x (healthy buffer)

---

## Profitability Tiers

### Tier 1: Highly Profitable (Should Scale Aggressively)

**ROAS: >2x Breakeven**

| Model | Breakeven | Target ROAS | Net Profit/$ |
|-------|-----------|-------------|----------------|
| E-com Dropship (50% margin) | 2.0x | 3.5x+ | $0.35 |
| E-com Owned (45% margin) | 2.2x | 3.5x+ | $0.30 |
| Digital Product (87% margin) | 1.15x | 2.5x+ | $0.85 |
| SAAS (98% margin) | 1.02x | 2.5x+ | $1.48 |

**Action:** Scale 20%+ daily, duplicate campaigns, test new audiences

---

### Tier 2: Profitable But Limited (Scale Cautiously)

**ROAS: 1.3x - 2.0x Breakeven**

| Model | Breakeven | Target ROAS | Net Profit/$ |
|-------|-----------|-------------|----------------|
| E-com Dropship (50% margin) | 2.0x | 2.6-4.0x | $0.10-0.20 |
| E-com Owned (45% margin) | 2.2x | 2.9-4.4x | $0.08-0.18 |
| Digital Product (87% margin) | 1.15x | 1.5-2.3x | $0.35-0.75 |

**Action:** Scale 5-10% every 5 days, test new audiences before scaling, monitor CPA weekly

---

### Tier 3: Marginal (Test Only, Minimal Scale)

**ROAS: 1.0 - 1.3x Breakeven**

**Action:** Keep spend minimal (<$200/day), only test new creatives/audiences, don't scale, prepare to kill

---

### Tier 4: Losing Money (Kill Immediately)

**ROAS: <1.0x Breakeven**

**Action:** Pause campaign, audit creative/pixel/targeting, or kill and reallocate budget

---

## Profitability Calculator Template

### Quick Calculator Format

```
PRODUCT DETAILS
Selling Price:                    $_______
COGS (sourcing cost):             $_______
Shipping (if included):           $_______
Payment Processing Fee (%):       _______%
Monthly Platform Cost:            $_______
Customer Support (% of order):    _______%

CALCULATIONS
Gross Revenue per Sale:           $_______
Total Cost per Sale:              $_______
Gross Margin %:                   _______%

Breakeven ROAS:                   _______x
Target ROAS (2.5x breakeven):     _______x
Profit per Sale at Target ROAS:   $_______

CAMPAIGN PERFORMANCE
Actual ROAS:                      _______x
Actual CPA:                       $_______
Profit per Conversion:            $_______
Safe Scale Budget:                $_______/day
```

---

## Scenario Analysis: When to Kill vs. Scale

### Scenario 1: E-commerce with Thin Margin

**Product:** $20 item, $8 COGS, 2.7x breakeven ROAS requirement

```
Campaign 1: ROAS 3.2x (well above breakeven)
  → Profit per sale = $20 - $8 - (cost_per_conversion) = $4-6
  → SCALE aggressively ✅

Campaign 2: ROAS 2.8x (slightly above breakeven)
  → Profit per sale = $1-2
  → SCALE cautiously (5% increments) ⚠️

Campaign 3: ROAS 2.6x (barely above breakeven)
  → Profit per sale = $0.50-1.00
  → DO NOT SCALE, test only ❌
```

---

### Scenario 2: Info Product (High Margin)

**Product:** $97 course, 1.15x breakeven ROAS requirement

```
Campaign 1: ROAS 1.8x
  → Profit per sale = $97 × (1.8 - 1.15) / 1.8 = $35
  → SCALE aggressively ✅

Campaign 2: ROAS 1.3x
  → Profit per sale = $97 × (1.3 - 1.15) / 1.3 = $11.25
  → SCALE cautiously ⚠️

Campaign 3: ROAS 1.1x
  → Profit per sale = $97 × (1.1 - 1.15) / 1.1 = LOSS
  → KILL immediately ❌
```

---

### Scenario 3: SAAS (Very High Margin)

**Product:** $99/month, 8-month LTV, 1.02x breakeven

```
Campaign 1: ROAS 2.5x
  → CAC = $99 / 2.5 = $39.60
  → LTV = $792, Profit margin = 95%+
  → SCALE to maximum capacity ✅

Campaign 2: ROAS 1.5x
  → CAC = $99 / 1.5 = $66
  → Still highly profitable
  → SCALE moderately ✅

Campaign 3: ROAS 1.05x
  → CAC = $99 / 1.05 = $94.29
  → Still profitable (95% margin after payback)
  → Test, but can maintain ⚠️
```

---

## Advanced: Lifetime Value Calculation

### For Repeat-Purchase Businesses

**Formula:**
```
LTV = (Average Order Value × Repeat Purchase Rate × Months Active) - Customer Service Costs

Example: Repeat e-commerce store
  AOV: $60
  Repeat Rate: 25% make second purchase, 10% make 3+ purchases
  Average Repeat Purchases: 1.35
  Average Customer Lifetime: 12 months
  Service Cost per Customer: $15

LTV = ($60 × 1.35) × 12 - $15
    = $81 × 12 - $15
    = $972 - $15
    = $957
```

**Breakeven CAC:** $957 × margin = $957 × 0.45 = $430 (safe CAC ceiling)

**ROAS Target:** Use LTV instead of single order value
- If spending $99 to acquire $957 customer = 9.6x "effective ROAS"
- Therefore, breaking even on first order (ROAS 2.0x) is acceptable

---

## Margin Compression Warning

### When to Stop Scaling

**Red Flag:** ROAS stable but CPA trending up while margin stays same
- Implies: You're reaching less-qualified audience as you scale
- Action: Stop vertical scaling, switch to horizontal (new audiences)

**Critical Issue:** ROAS stable but gross margin declining
- Example: Supplier raises COGS 10%, breakeven ROAS goes from 2.0 to 2.2x
- Action: Either increase prices or reduce ad spend until margin recovers

