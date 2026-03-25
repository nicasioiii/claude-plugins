---
name: Design Upsells
description: Design the complete post-purchase upsell flow including order bumps, upsells, downsells, and continuity offers. Asks about the main product, customer problems, and business model, then produces a full upsell/downsell map with copy outlines and take rate targets.
---

# /design-upsells -- Post-Purchase Upsell Flow Designer

## INTAKE QUESTIONS (Ask All Before Designing)

### Question 1: Main Product
**What is your main (front-end) product?**
- Product name and what it does
- Price point
- Delivery format (digital course, physical product, service, software)

### Question 2: Customer's Next Problems
**After someone buys your main product, what problems do they hit next?**
- What frustration comes immediately? (bump/upsell 1 territory)
- What bigger challenge emerges after that? (upsell 2 territory)
- What ongoing need do they have? (continuity territory)

If the user is unsure, help them brainstorm using Georgi's categories: Better Results, Faster Results, Easier Results, Expanded Results, Savings, Holism, Improved Version.

### Question 3: Existing Products
**Do you already have other products you could use as upsells?**
- List any existing courses, templates, tools, services, coaching offers
- Include pricing for each
- Note which ones are already in a funnel

### Question 4: Business Model
**What type of business are you running?**

| Choice | Implications |
|--------|-------------|
| A) Digital info products / courses | Katie's pricing architecture applies. Short upsell pages. Backend email sequences. |
| B) E-commerce / physical products | Georgi's new problem framing applies. Subscription/refill continuity. |
| C) Service business / agency | Hormozi's Menu + Anchor upsell types apply. Waived Fee continuity. |
| D) SaaS / software | Annual plan upsell. Feature-tier upsells. Expansion revenue. |
| E) Coaching / consulting | High-ticket backend. Rollover upsells. Transformation positioning. |

### Question 5: Current Metrics (If Applicable)
**If you already have a funnel running, what are your current numbers?**
- Current AOV
- Current bump take rate (if any)
- Current upsell take rates (if any)
- Number of customers through the funnel so far

---

## DESIGN PROCESS

### Step 1: Load Upsell Strategy
Load `upsell-downsell-strategy` for:
- Order bump framework and 4-Part copy structure
- Upsell pricing architecture (Katie's sequence)
- Hormozi's 4 upsell types for mechanism selection
- Georgi's 7 upsell categories for brainstorming
- Downsell rules and types

### Step 2: Load Checkout Optimization
Load `checkout-optimization` for:
- Order form placement recommendation
- Bump integration on checkout page
- Payment plan options
- Trust elements

### Step 3: Design the Flow
Build the complete post-purchase path:

**For each offer in the flow, specify:**
- Product name and description
- Price point with rationale
- Upsell type being used (Classic, Menu, Anchor, Rollover, or direct)
- Georgi category (Better/Faster/Easier/Expanded/Savings/Holism/Improved)
- Copy outline using Katie's 6-Part structure (headline, objection-prevention, value shift, credibility, snapshot, what's included)
- Take rate target based on benchmarks
- Downsell path if they say no

### Step 4: Validate Economics
Cross-reference with `funnel-economics` principles:
- Calculate projected AOV based on prices and expected take rates
- Verify AOV meets $70 minimum target (if running ads)
- Estimate 30-day gross profit per customer

---

## OUTPUT FORMAT

Deliver the complete upsell flow as:

1. **Visual Flow Map** -- Sequence diagram showing: Main Product -> Bump -> Upsell 1 -> (Yes/No branches) -> Upsell 2 -> etc.

2. **Offer Detail Cards** -- For each offer:
   - Name, price, format
   - Problem it solves (specific customer language)
   - Upsell type + Georgi category
   - Copy headline draft
   - Take rate target
   - Downsell if declined

3. **Economics Summary** -- Projected AOV, revenue per 100 customers, comparison to current (if applicable)

4. **Build Priority** -- Which offer to build first (start with bump + 1 upsell, expand from there)

5. **Continuity Recommendation** -- Which continuity type fits their business (Bonus, Discount, or Waived Fee) and when to introduce it in the customer journey
