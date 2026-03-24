---
name: Meta Campaign Methods
description: Crazy Method, Blender Method, Stacked LLA Method, CBO/ABO/ASC selection criteria, and campaign type decision tree by pixel maturity and country size.
---

# Meta Campaign Methods

## THE CRAZY METHOD (Konstantinos)

### What It Is
A CBO campaign where ALL ad sets are IDENTICAL -- same targeting, same ads, duplicated multiple times. Purpose: find different hot pockets from the same targeting/creative combination.

### Why It Works
The randomness of initial results means each duplicated ad set may discover a DIFFERENT hot pocket. Each ad set's first buyers shape the audience profile differently.

### CRITICAL: Crazy Method Is an AMPLIFIER
Only use with something already proven to work. If it fails:
- Either the source creative/audience was not actually working, OR
- You do not know how to optimize CBO campaigns.

### Setup Rules
1. **Calculate ad sets:** Budget / Average CPP = number of ad sets.
   - $100 budget / $30 CPP = 3-4 ad sets.
   - $200 budget / $30 CPP = 6-7 ad sets.
   - For 15+, divide by 2 for slower/safer approach.
   - Post-iOS maximum: ~10 ad sets recommended.
2. **Max 3-5 ads per ad set** (not 1, not 10).
3. Must be CBO -- cannot be ABO.
4. **Do NOT abuse it:** Running 6 identical Crazy Method campaigns with same creative collapses the system (targeting same hot pocket repeatedly).
5. The Crazy Method is for SCALING, not initial testing.

### Crazy Method for Lead Gen
- Works especially well for local businesses (auto detailing, plastic surgery).
- In local areas, use broad targeting + demographic filters + Crazy Method.
- Tip: Call leads at the same time they submitted the form (creatures of routine).
- Use screening questions in lead forms to filter quality.

### ASC Crazy Method Variant
Duplicate the same ad multiple times within a single ASC campaign to find different hot pockets (since hot pockets form at the ad level, not ad set level).

---

## THE STACKED LOOKALIKE (STACKED LLA) METHOD (Konstantinos)

### What It Is
Stack multiple 10% lookalikes into one ad set, then run as Crazy Method.

### Lookalike Sources to Stack (All at 10%, Max Retention)
- Purchase (180 days)
- Add to cart (180 days)
- Initiate checkout (180 days)
- View content (180 days)
- Instagram engagers (365 days)
- Facebook engagers (365 days)
- Video viewers top 25%
- Customer list upload

### Critical Rules
- **Only stack SAME percentages together.** Mixing 1% + 5% + 10% = money goes to the 10% only.
- Provides multiple entry points for the algorithm to find hot pockets.
- **Use for:** New/struggling pixels on the journey to broad targeting.
- **Do NOT use on seasoned pixels** -- go straight to broad/ASC instead.
- Can combine with Crazy Method: stack LLAs in one ad set, then duplicate that ad set multiple times.

---

## THE BLENDER METHOD (Konstantinos)

### What It Is
Combination of lookalikes + interests in the same ad set.

### When to Use
- Interests alone are not working AND lookalikes alone are not working, but both show promise.
- "Last resort" method for problematic/new pixels.

### Modern Version
Stack 10% lookalikes + working interests in the same ad set.

### Rules
- Can be run as Crazy Method (stack -> duplicate multiple times).
- **Group similar-sized audiences together:**
  - Small: 500K-4M together.
  - Medium: 5-20M together.
  - Large: 50M+ together.
- Don't mix 500K interest with 50M interest (big one takes all budget).

---

## CBO (CAMPAIGN BUDGET OPTIMIZATION / ADVANTAGE+ BUDGET)

### How It Works
Budget set at campaign level, distributed to ad sets by the algorithm. Works in 99% of cases better than ABO.

### Konstantinos's Primary Campaign Type
- Budget distribution tends to be more even across ad sets than ASC (which can give 90% to one ad).
- **Structure guidelines:**
  - 3-10 ad sets per CBO (based on budget/CPP calculation).
  - 3-5 ads per ad set.
  - Don't mix vastly different audience sizes.
- Can use with: interests, lookalikes, broad, Crazy Method, stacked LLAs, Blender.

### Deividas's View on CBO
- Good for scaling/consolidation. Algorithm allocates budget.
- 80% typically goes to one ad set.
- Don't rely on it for testing (unreliable budget distribution).
- Some underperforming ads in a CBO stack may serve a top-of-funnel awareness role.

---

## ABO (AD BUDGET OPTIMIZATION)

### How It Works
Budget set at ad set level, distributed to ads within that ad set.

### When to Use (Deividas)
- **Best for testing.** Gives full control over budget allocation per ad set.
- Forces ad spend to creatives.
- Use original audiences (not Advantage+) for controlled testing.

### When to Use (Konstantinos)
- Mostly for cost caps and bid caps campaigns.
- Structure: One cost cap ABO + one bid cap ABO running simultaneously.

### Testing Structure (Deividas)
Split testing into 4 separate campaigns:
1. New video testing
2. Video variation testing
3. New image testing
4. Image variation testing

---

## ASC (ADVANTAGE SHOPPING / ADVANTAGE+ SALES CAMPAIGNS)

### How It Works
One ad set, multiple ads. Meta handles ALL targeting.

### When It Works Best
- **Trained/seasoned accounts** (Konstantinos).
- Smaller countries where it may work even with new pixels.
- For larger countries (US), usually requires more pixel data.

### Key Characteristics (Deividas)
- Works like retargeting without setup.
- Can upload new creatives without resetting learning phase.
- Tends to over-attribute by ~30% (especially with view-through attribution).
- Best for big markets; frequency issues in small markets.

### Meta Auction Context (ACA/Seth)
- Total Value = Bid + Estimated Action Rate + User Value.
- Highest total value wins (not highest bid).
- Target as broadly as possible -- creative becomes the targeting.

### Budget Cap Setting
- Started with 20% retargeting / 80% cold.
- Meta has been removing the existing customer budget cap.
- CBO may outperform ASC in some accounts, especially when CPMs are lower in CBO.

---

## CAMPAIGN TYPE SELECTION QUICK REFERENCE

| Scenario | Recommended Type | Method |
|---|---|---|
| New pixel, small country | ASC or CBO + broad | Standard |
| New pixel, large country | CBO + interests | Standard -> progress to LLAs |
| Seasoned pixel, scaling | ASC broad + CBO Crazy Method broad | Multi-campaign |
| Struggling pixel | CBO + Blender Method | Crazy Method variant |
| Lead gen, local | CBO + broad + demographics | Crazy Method |
| Cost control needed | ABO + cost cap/bid cap | Dual ABO |
| Testing new creatives | ABO (Deividas) or CBO + interests (Konstantinos) | Controlled test |

---

## PIXEL TRAINING PATH (Most Cost-Efficient Route to Broad)

1. Small interests (2-3M audience)
2. Normal interests (20M+)
3. Broader interests (30-60M)
4. Lookalikes 1% then 10%
5. Stacked lookalikes (10% multiple sources)
6. Broad targeting (ultimate goal)

**First benchmark:** ~100 purchase events to start testing lookalikes.
**CPM is the compass** -- always compare CPMs between targeting types; follow the lowest CPM path.

### Audience Testing Order (Deividas)
1. Find best-performing interest (15-25M size).
2. Find best-performing landing page.
3. Test creatives on proven interest + landing page combo.
4. Winners get pushed to broad/Advantage Shopping.
