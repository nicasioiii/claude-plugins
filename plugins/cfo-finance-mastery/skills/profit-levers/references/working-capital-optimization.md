---
name: Working Capital Optimization & Cash Flow Management
---

# Working Capital Optimization & Cash Flow Management

## Working Capital Formula & Cash Impact

**Working Capital = Accounts Receivable + Inventory - Accounts Payable**

This is cash **stuck** in operations. The goal is to minimize it.

**Cash Conversion Cycle = DSO + DIO - DPO**
- DSO: Days Sales Outstanding (how long until customers pay)
- DIO: Days Inventory Outstanding (how long inventory sits)
- DPO: Days Payable Outstanding (how long until you pay suppliers)

**Impact:** Each day reduced = working capital freed. With $1M revenue / 365 days = $2,740 daily spend. Cutting 10 days = ~$27K freed.

---

## AR Optimization: Collect Faster

### Accounts Receivable Best Practices

**1. Set Terms in Writing**
- Invoice immediately upon delivery/service completion (not end-of-month)
- Specify due date clearly ("Payment due 15 days from invoice date, not delivery date")
- Include payment methods (bank transfer, credit card) to reduce friction

**2. Automated Follow-Up Sequence**
- Day 10: Automated email reminder ("Invoice #123 due [date]")
- Day 20: Second reminder + phone call
- Day 30: Call from manager + discuss payment plan if needed
- Day 45: Consider legal action (small claims, collection agency) if large amount

**3. Track DSO Monthly**
```
DSO = (Average AR / Annual Revenue) × 365
Example: AR $150K, revenue $1.2M → DSO = ($150K / $1.2M) × 365 = 45.6 days
Benchmark by industry:
- SaaS: 30–45 days (predictable, recurring)
- B2B Services: 45–60 days (project-based billing)
- Manufacturing: 60–90 days (standard net 60 terms)
- Retail: 1–7 days (immediate payment or credit card)
```

**4. Customer Segmentation**
- A-tier: Net 30 (reliable payment)
- B-tier: Net 15 or COD (slower payers, require monitoring)
- C-tier: Prepay or progress billing (unreliable payment history)

**5. Early Payment Discounts (Only If Cost of Capital >36%)**
- Offer: 2% discount if paid in 10 days (vs. net 30)
- Cost: 2% over 20 days = 36% APY
- Decision: Only take if your cost of capital >36% (unlikely unless in crisis)

### Case Study: $50K Cash Freed

```
Before:
- DSO: 55 days
- Average AR: $183K (from $1.2M annual revenue)

Changes:
- Invoice same day of delivery (vs. end of week) → 3 days faster
- Implement automated 10-day reminder → 5 days faster (faster payment response)
- Require payment within 15 days for new customers (old customers net 30) → Average 7 days faster

New DSO: 40 days
Freed AR: $183K - ($1.2M / 365 × 40) = $183K - $131K = $52K freed

Cost to execute: 10 hours billing staff time + software tool ($200/month) = $2.4K annually
ROI: $52K freed cash / $2.4K annual cost = 21.7x first-year ROI
```

---

## Inventory Optimization: Reduce Tied-Up Capital

### Inventory Management Framework

**Safety Stock Formula:**
```
Safety Stock = Z-score × Demand Volatility × sqrt(Lead Time in days)

Example:
- Z-score: 2.0 (95% confidence of not stockout)
- Demand volatility: 20 units/day standard deviation
- Lead time: 30 days

Safety Stock = 2.0 × 20 × sqrt(30) = 2.0 × 20 × 5.48 = 219 units

This assumes you need 219 units buffer to avoid 95% of stockouts.
Don't carry 500 units "just in case."
```

**Reorder Point:**
```
Reorder Point = (Average Daily Demand × Lead Time) + Safety Stock

Example:
- Average daily demand: 100 units
- Lead time: 30 days
- Safety stock: 219 units

Reorder Point = (100 × 30) + 219 = 3,219 units
Order when inventory hits 3,219; resupply arrives 30 days later.
```

**Inventory Turnover:**
```
Inventory Turnover = Annual COGS / Average Inventory
Days Inventory Outstanding (DIO) = 365 / Inventory Turnover

Example:
- Annual COGS: $500K
- Average inventory: $100K
- Inventory Turnover: 5x
- DIO: 73 days (inventory sits 73 days before sale)
```

### Dead Stock Disposal (Without Destroying Margin)

**Avoid:** Deep discounts (e.g., 50% off). This destroys brand and trains customers to wait for sales.

**Instead:**
1. **Bundle with popular products** — Sell old + new together at blended price
2. **Liquidators** — Sell entire lot to inventory buyer (recover 20–40% of value)
3. **Donations** — Donate for tax credit (itemize at fair market value, tax deduction = ~35% × donation value)
4. **Secondary markets** — eBay, Amazon, Facebook Marketplace
5. **Employee discount** — Let staff buy at cost (morale boost, capital recovery)

### Case Study: $100K Cash Freed

```
Before:
- Average inventory: $300K (manufacturing, high lead times)
- DIO: 85 days

Changes:
- Negotiate shorter lead times with suppliers (45 days vs. 60 days) → DIO down 15 days
- Improve demand forecasting (reduce buffer from 25% to 15% safety stock) → DIO down 8 days
- Implement JIT ordering for fast-moving SKUs → DIO down 12 days

New DIO: 50 days
Freed inventory capital: $300K × (85 - 50) / 365 = $300K × 35/365 = $28.8K

But with higher turnover, confidence in stockouts increases. Second-order savings:
- Fewer stockouts → less expedited shipping costs: $5K saved
- Less obsolescence risk → lower write-offs: $8K saved

Total benefit: ~$42K annual benefit, one-time $29K cash freed
```

---

## AP Extension: Strategic Payment Timing

### Accounts Payable Management

**1. Negotiate Terms with All Vendors**
- Standard: Net 30 (pay 30 days after invoice)
- Negotiated: Net 45–60 (if you have volume leverage)
- Ask in writing: "Can we move to net 60 given our annual volume of $500K?"

**2. Strategic Payment Timing**
- Align payments with cash inflow (collect customer payment, then pay vendor)
- Don't pay early unless contractually required
- Use payment float strategically (vendor invoices you on day 1, you pay day 45 = 44 days of free float)

**3. Evaluate Early Payment Discounts**
```
Vendor offers: 2% discount if paid in 10 days (vs. net 30)

Cost of discount:
- 2% over 20 days = (2% / 20) × 365 = 36.5% annualized cost
- Your cost of capital: ~30% (small business baseline)
- Decision: Not worth it (discount costs more than capital)

Exception: If cost of capital is 50%+ (crisis), early discount might make sense.
```

**4. Vendor Relationships**
- Don't abuse payment terms (late payments damage relationships)
- Communicate if payment delayed ("We'll pay on the 15th, not due date")
- Use predictable payment patterns (vendors prefer consistency)

### Negotiation Tactics

**Annual Volume Leverage:**
```
Old approach: Pay per order as invoiced
New approach: "We spent $600K with you last year. Can we negotiate net 60?"

Vendor calculation:
- You're valuable customer (top 10–20% by volume)
- Cost to lose you: Revenue loss + reallocation costs
- Cost to extend terms: Minor (they refinance through bank)

Likely outcome: Vendor grants net 60 (or net 45 compromise)
Value to you: Extra 30 days cash float = ~$50K (at $600K annual spend)
```

**Consolidation Leverage:**
```
Current: 5 suppliers, each $120K annual volume (fragmented)
New: 1 main supplier $600K, 1 secondary $120K

Pitch to main supplier:
"If you can match competitor pricing and offer net 60, we'll consolidate 80% of business to you."

Likely outcome: Supplier agrees (concentrated customer > fragmented customer)
```

### Case Study: $100K Cash Float Improvement

```
Before:
- 15 different suppliers
- Average payment terms: Net 30
- Average invoice value: $5K
- Average payment lag: 30 days after invoice

After:
- Consolidated to 6 main suppliers (standardized spend)
- Negotiated average terms: Net 50 (20-day improvement)
- Improved cash process: Invoice received same day, payment sent day 45 (systematic)

Cash flow impact:
- Old: 15 suppliers × $5K average × 30 days = $2.25M in AP at any time
- New: 15 suppliers × $5K average × 50 days = $3.75M in AP at any time
- Freed cash: $1.5M additional float

But consolidated approach reduces invoice volume (fewer suppliers = fewer, larger invoices):
- New average invoice: $7.5K
- Revised calculation: 10 invoices in progress × $7.5K × 50 days = $3.75M (validates above)

Net benefit: $1.5M additional working capital freed through negotiation (no cash outlay, pure negotiation)
```

---

## Putting It Together: Cash Conversion Cycle Optimization

**Example: E-Commerce Startup**

Before optimization:
```
DSO (customer collection): 7 days (credit cards, immediate)
DIO (inventory sitting): 60 days (standard for retail)
DPO (paying suppliers): 25 days (small company, limited leverage)

Cash Conversion Cycle = 7 + 60 - 25 = 42 days
Daily revenue: $3K → Need $126K working capital (42 days × $3K)
```

After optimization:
```
Reduce DSO to 5 days (improve payment processing): -2 days
Reduce DIO to 45 days (better forecasting, faster turnover): -15 days
Extend DPO to 40 days (negotiate with suppliers): +15 days

New CCC = 5 + 45 - 40 = 10 days
Daily revenue: $3K → Need $30K working capital (10 days × $3K)

Freed capital: $126K - $30K = $96K
```

**Cost to execute:** 30 hours process improvement + 5 hours supplier negotiation = ~$2.5K
**Cash freed:** $96K (one-time)
**ROI:** 38x

---

## Monitoring: Monthly KPIs

Track these metrics monthly:

| Metric | Formula | Target | Action if Off |
|--------|---------|--------|----------------|
| DSO | (AR / Annual Rev) × 365 | -5 days YoY | Review collections process |
| DIO | (Avg Inventory / COGS) × 365 | -10% YoY | Review demand forecast, excess SKUs |
| DPO | (AP / COGS) × 365 | +5 days YoY | Renegotiate vendor terms |
| CCC | DSO + DIO - DPO | -20 days YoY | Holistic view; combines all three |

---

## Common Mistakes to Avoid

1. **Aggressive AR collection damages customer relationships** — Be professional but firm.
2. **Cutting inventory so thin you stockout** — Cost of stockout (lost sale, customer churn) often exceeds inventory carrying cost.
3. **Paying late damages vendor relationships** — Suppliers may drop you or raise prices. Communicate, don't ghost.
4. **Not monitoring CCC regularly** — Working capital changes are subtle; monthly review catches trends early.
5. **Assuming terms are fixed** — They're not. Ask for better terms; worst case, vendor says no. Many say yes.

Done well, working capital optimization is the fastest way to improve cash flow without raising debt or cutting growth.
