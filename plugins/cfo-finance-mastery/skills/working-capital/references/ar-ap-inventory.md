---
name: AR, AP, and Inventory Tactics Reference
description: "Detailed AR management (28-day billing, factoring, retainer models), AP management (6-month vendor negotiation, early-pay discount math at 30% hurdle), inventory tactics (ABC analysis, JIT), working capital formula, CCC deep dive, payroll frequency analysis."
---

# AR, AP, and Inventory Tactics Reference

## AR Tactics -- Detailed Playbook

### 28-Day Billing Implementation (Leikauf)

**Setup steps:**
1. Calculate your current billing frequency and revenue per cycle
2. Set your next invoice date 28 days from the last one (not tied to calendar months)
3. Update your billing software to 28-day intervals
4. Communicate to clients: "We invoice every 4 weeks for consistent service delivery"
5. For annual contracts: 13 invoices instead of 12 (same annual total, faster collection)

**Revenue impact calculation:**
```
Monthly billing: 12 cycles x $10,000 = $120,000/year
28-day billing:  13 cycles x $10,000 = $130,000/year
Incremental:     +$10,000 (8.3% more billing frequency)
```

**For retainer/subscription businesses:** The extra cycle is pure incremental. For project-based businesses, it accelerates cash collection timing even if total annual revenue stays the same.

### Factoring Decision Framework

| Factor | Evaluate |
|--------|---------|
| **Factoring cost** | Typically 2-5% of invoice face value |
| **Your cost of capital** | If factoring is cheaper than your alternative, use it |
| **Cash urgency** | Bridge financing during growth spurts or seasonal dips |
| **Customer quality** | Factors prefer invoices from creditworthy customers |
| **Volume** | Most factors have minimum monthly volume requirements |

**When factoring makes sense:**
- Seasonal business with predictable AR but uneven cash flow
- Rapid growth outpacing cash availability
- Alternative is more expensive debt (credit cards, MCA)
- Short-term bridge while improving organic cash flow

**When factoring does NOT make sense:**
- Chronic cash flow problems (fix the root cause instead)
- Customer credit quality is poor (factor will reject or charge premium)
- Factoring cost exceeds your gross margin on the work

### Retainer Model Design (Services Businesses)

| Model | Structure | Best For |
|-------|----------|----------|
| **Fixed retainer** | Same amount every month regardless of work | Predictable services, CFO advisory |
| **Hours-based retainer** | Prepaid hours with rollover/expiry | Variable scope services |
| **Value-based retainer** | Priced on outcomes, not hours | High-value strategic work |
| **Hybrid** | Base retainer + project fees | Businesses with recurring + project work |

**Cash flow benefit:** Retainers eliminate DSO. Cash arrives before or at the start of the service period. Combined with 28-day billing, this creates reliable cash inflow.

### Progress Billing for Large Projects

| Milestone | Typical % | Invoice Trigger |
|-----------|----------|----------------|
| Contract signed | 25-30% | Deposit before work begins |
| Phase 1 complete | 25% | Deliverable accepted |
| Phase 2 complete | 25% | Deliverable accepted |
| Project completion | 15-25% | Final deliverable + sign-off |

**Rules:**
- Never do more than 25% of work ahead of payment
- Deposit is non-refundable (covers setup and opportunity cost)
- Tie payments to specific, measurable deliverables
- Do not release final deliverables until final payment clears

### E-Invoicing Best Practices

1. **Invoice same day** as delivery or service completion
2. **Include all details** on the invoice (PO number, contact, description, terms)
3. **Offer multiple payment methods** (ACH, credit card, wire) -- reduce friction
4. **Automate recurring invoices** for retainer clients
5. **Track invoice opens** if your system supports it (follow up on unopened invoices faster)

---

## AP Tactics -- Detailed Playbook

### 6-Month Vendor Negotiation Process (Leikauf)

**Month 1-2: Data gathering**
- Pull 12-month spend by vendor from your accounting system
- Identify top 10 vendors by annual spend (these are your leverage targets)
- Research 2-3 alternatives for each vendor
- Calculate your projected forward 12-month spend

**Month 3: Outreach**
- Schedule calls (not emails) with each vendor's sales rep
- Script: "We are reviewing our vendor relationships for the coming year. We project $X in spend with you. We want to explore how we can get better value from this partnership."

**Month 4: Negotiation**
- Present your projected spend and alternatives
- Use tactical empathy: "It seems like locking in our volume for the year would be valuable for your team"
- Negotiate price, terms, delivery, service levels
- Ask for Net 60 if currently on Net 30

**Month 5: Finalization**
- Document new terms in writing
- Update your accounting system with new payment terms
- Set calendar reminder for next review in 6 months

**Month 6: Implementation and monitoring**
- Verify new terms are applied correctly
- Track savings vs. prior terms
- Begin data gathering for next cycle

### Early-Pay Discount Math (Leikauf's 30% Hurdle)

**Common offer: 2/10 Net 30**
- 2% discount if paid within 10 days instead of 30 days
- You give up 20 days of float for 2% savings

**Annualized cost calculation:**
```
Annualized Rate = (Discount % / (1 - Discount %)) x (365 / (Full Terms - Discount Period))

2/10 Net 30:
= (0.02 / 0.98) x (365 / 20)
= 0.0204 x 18.25
= 37.2% annualized

1/10 Net 30:
= (0.01 / 0.99) x (365 / 20)
= 18.4% annualized
```

**Decision matrix:**

| Offer | Annualized Rate | Leikauf Decision |
|-------|----------------|-----------------|
| 2/10 Net 30 | 37.2% | Take only if your capital earns < 30% elsewhere |
| 1/10 Net 30 | 18.4% | Skip -- your capital likely earns more elsewhere |
| 3/10 Net 60 | 22.3% | Marginal -- depends on your cost of capital |
| 2/10 Net 60 | 14.9% | Skip |

**Leikauf's rule of thumb:** Unless the annualized rate exceeds ~30%, keep the cash and deploy it in the business. Most small businesses can earn 20-40%+ ROI on retained working capital.

### Trade Credit Optimization

1. **Request extended terms** from all vendors (Net 60 or Net 90)
2. **Use trade credit as free financing** -- vendor is essentially lending you inventory/supplies
3. **Build a payment calendar** -- pay every vendor on their due date, not before
4. **Automate payments** to eliminate human error (no early payments, no late fees)

---

## Inventory Tactics -- Detailed Playbook

### ABC Analysis Implementation

**Step 1: Classify inventory**
```
A items: Top 20% of SKUs by revenue contribution (usually 80% of value)
B items: Next 30% of SKUs (usually 15% of value)
C items: Bottom 50% of SKUs (usually 5% of value)
```

**Step 2: Set management rules**

| Class | Reorder Frequency | Safety Stock | Review Cycle | Forecasting |
|-------|-------------------|-------------|-------------|------------|
| **A** | Weekly or on-demand | 2-4 weeks | Weekly | Detailed demand forecasting |
| **B** | Bi-weekly or monthly | 2-3 weeks | Monthly | Trend-based |
| **C** | Monthly or quarterly | 1-2 weeks | Quarterly | Simple reorder point |

**Step 3: Monitor and reclassify quarterly**
- Items can shift classes as demand changes
- New products start as B until data is available
- Discontinued items move to C and get liquidated

### JIT (Just-in-Time) Implementation

**Prerequisites:**
- Reliable suppliers with consistent lead times
- Predictable demand patterns (or strong forecasting)
- Good supplier communication systems

**Benefits:**
- Minimizes carrying cost (20-30% of inventory value per year)
- Reduces warehouse space needs
- Forces supply chain discipline

**Risks:**
- Supply disruption shuts down operations
- Requires buffer strategy (safety stock for A items)
- Not suitable for highly volatile demand

### Safety Stock Calculation

```
Safety Stock = (Max Daily Sales x Max Lead Time) - (Avg Daily Sales x Avg Lead Time)
```

**Example:**
- Max daily sales: 15 units
- Max lead time: 10 days
- Avg daily sales: 10 units
- Avg lead time: 7 days
- Safety stock: (15 x 10) - (10 x 7) = 150 - 70 = 80 units

### Phased Payment Strategy for Bulk Orders

Instead of paying 100% upfront for a large inventory order:

| Phase | Payment | Trigger |
|-------|---------|---------|
| Order placed | 30% deposit | Purchase order signed |
| Production complete | 30% | Quality inspection passed |
| Delivery received | 40% | Goods received and verified |

**Benefit:** Spreads cash outflow over weeks instead of a single large payment. Reduces risk if supplier fails to deliver.

### Inventory Carrying Cost Calculator

```
Annual Carrying Cost Components:
  Storage (rent, utilities per sq ft)    : ___
  Insurance                               : ___
  Depreciation / obsolescence risk        : ___
  Opportunity cost (cost of capital x value): ___
  Handling / labor                        : ___
  = Total Carrying Cost

Carrying Cost % = Total Carrying Cost / Average Inventory Value
```

**Benchmark:** 20-30% per year. If your carrying cost exceeds 30%, you are over-inventoried.

---

## CCC Optimization Scenarios

### Scenario 1: Service Business (No Inventory)

```
CCC = DSO + 0 - DPO = DSO - DPO
Focus: Reduce DSO (faster collection) and increase DPO (slower payment)
```

**Quick wins:**
- Switch to retainer billing (DSO = 0)
- Request Net 60 from all vendors
- Automate invoicing on delivery day

### Scenario 2: Product Business

```
CCC = DSO + DIO - DPO
All three components matter
```

**Prioritize by impact:**
1. DIO reduction usually has the largest dollar impact
2. DSO reduction is the fastest to implement
3. DPO extension requires vendor cooperation

### Scenario 3: E-Commerce

```
Many e-commerce businesses have negative CCC:
- Customers pay immediately (DSO near 0)
- Inventory turns fast (low DIO)
- Vendors paid on Net 30-60 (positive DPO)
```

**Risk:** Payment processor holds (Stripe, PayPal) can temporarily spike DSO. Factor this into cash planning.

---

## 13-Week Cash Flow Forecast Template

For anti-Profit-First cash management (Leikauf):

```
Week | Opening Cash | Inflows (AR collected) | Outflows (AP, payroll, rent, debt) | Net | Closing Cash
1    | $50,000      | $15,000               | $22,000                            | -$7K| $43,000
2    | $43,000      | $18,000               | $12,000                            | +$6K| $49,000
...
13   | ...          | ...                   | ...                                | ... | ...
```

**Rules:**
- Update weekly with actuals
- Flag any week where closing cash drops below minimum reserve
- Minimum reserve = 2 weeks of operating expenses
- If a gap appears: accelerate AR collection, delay discretionary AP, or arrange bridge financing

---

## Working Capital Benchmarks

| Metric | Healthy | Warning | Critical |
|--------|---------|---------|----------|
| Current Ratio | > 1.5 | 1.0-1.5 | < 1.0 |
| Quick Ratio | > 1.0 | 0.5-1.0 | < 0.5 |
| DSO | < 30 days | 30-60 days | > 60 days |
| DIO | < 45 days | 45-90 days | > 90 days |
| DPO | > 30 days | 15-30 days | < 15 days (paying too fast) |
| CCC | < 30 days | 30-60 days | > 60 days |

> For ratio formulas and complete benchmarks, see the financial-ratios skill.
